---
title: Anbieterunterstützung für Lesezeichen
ms.date: 11/04/2016
helpviewer_keywords:
- IRowsetLocate class, provider support for bookmarks
- OLE DB provider templates, bookmarks
- bookmarks, OLE DB
- IRowsetLocate class
- OLE DB providers, bookmark support
ms.assetid: 1b14ccff-4f76-462e-96ab-1aada815c377
ms.openlocfilehash: 4a0a0ea51cf6ac347cd79cb777f9cb6a51670063
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50584625"
---
# <a name="provider-support-for-bookmarks"></a>Anbieterunterstützung für Lesezeichen

Im Beispiel in diesem Thema wird die `IRowsetLocate` Schnittstelle zu den `CCustomRowset` Klasse. In fast allen Fällen zunächst fügen Sie eine Schnittstelle zu einem vorhandenen COM-Objekt. Anschließend können Sie es testen, durch das Hinzufügen weitere Aufrufe der Consumervorlagen aus. Im Beispiel wird veranschaulicht, wie Sie:

- Fügen Sie eine Schnittstelle zu einem Anbieter hinzu.

- Dynamisches Festlegen der Spalten, die an den Consumer zurückgegeben.

- Hinzufügen von lesezeichenunterstützung.

Die `IRowsetLocate` -Schnittstelle erbt von der `IRowset` -Schnittstelle. Hinzufügen der `IRowsetLocate` Schnittstelle, erben `CCustomRowset` aus [IRowsetLocateImpl](../../data/oledb/irowsetlocateimpl-class.md).

Hinzufügen der `IRowsetLocate` Schnittstelle unterscheidet sich geringfügig von den meisten Schnittstellen. Um die VTABLEs auszurichten, OLE DB-machen haben Anbietervorlagen einen Vorlagenparameter, die abgeleitete Schnittstelle zu behandeln. Der folgende Code zeigt die neue Vererbungsliste:

```cpp
////////////////////////////////////////////////////////////////////////
// CustomRS.h

// CCustomRowset
class CCustomRowset : public CRowsetImpl< CCustomRowset,
      CTextData, CCustomCommand, CAtlArray<CTextData>,
      CSimpleRow,
          IRowsetLocateImpl<CCustomRowset, IRowsetLocate>>
```

Die vierten, fünften und sechsten Parameter, die alle hinzugefügt werden. In diesem Beispiel verwendet die Standardeinstellungen für die vierte und fünfte Parameter jedoch angeben `IRowsetLocateImpl` als der sechste Parameter. `IRowsetLocateImpl` ist eine OLE DB-Vorlagenklasse, die zwei Vorlagenparameter akzeptiert: Diese Verknüpfen der `IRowsetLocate` Schnittstelle zu den `CCustomRowset` Klasse. Um die meisten Schnittstellen hinzuzufügen, können Sie diesen Schritt überspringen und zur nächsten zu verschieben. Nur die `IRowsetLocate` und `IRowsetScroll` Schnittstellen auf diese Weise behandelt werden müssen.

Sie müssen dann teilen Sie die `CCustomRowset` Aufrufen `QueryInterface` für die `IRowsetLocate` Schnittstelle. Fügen Sie die Zeile `COM_INTERFACE_ENTRY(IRowsetLocate)` zur Karte. Die schnittstellenzuordnung für `CCustomRowset` sollte angezeigt werden, wie im folgenden Code gezeigt:

```cpp
////////////////////////////////////////////////////////////////////////
// CustomRS.h

typedef CRowsetImpl< CCustomRowset, CTextData, CCustomCommand, CAtlArray<CTextData>, CSimpleRow, IRowsetLocateImpl<CCustomRowset, IRowsetLocate>> _RowsetBaseClass;

BEGIN_COM_MAP(CCustomRowset)
   COM_INTERFACE_ENTRY(IRowsetLocate)
   COM_INTERFACE_ENTRY_CHAIN(_RowsetBaseClass)
END_COM_MAP()
```

Sie müssen auch die Zuordnung in verknüpft die `CRowsetImpl` Klasse. -Makro Verknüpfung hinzufügen der `CRowsetImpl` zuordnen. Erstellen Sie auch eine Typdefinition namens `RowsetBaseClass` , die aus die Vererbungsinformationen besteht. Diese Typdefinition ist beliebig und kann ignoriert werden.

Behandeln Sie abschließend die `IColumnsInfo::GetColumnsInfo` aufrufen. Normalerweise würden Sie dazu die-Makros verwenden. Allerdings kann ein Consumer Lesezeichen verwenden möchten. Sie müssen möglicherweise von zum Ändern der Spalten, die der Anbieter gibt zurück, je nachdem, ob der Consumer ein Lesezeichen anfordert.

Behandelt die `IColumnsInfo::GetColumnsInfo` aufrufen, löschen Sie die `PROVIDER_COLUMN` ordnen Sie in der `CTextData` Klasse. Das Makro-Makro definiert eine Funktion `GetColumnInfo`. Sie definieren müssen Ihre eigenen `GetColumnInfo` Funktion. Die Funktionsdeklaration sollte wie folgt aussehen:

```cpp
////////////////////////////////////////////////////////////////////////
// CustomRS.H

class CTextData
{
   ...
     // NOTE: Be sure you removed the PROVIDER_COLUMN_MAP!
   static ATLCOLUMNINFO* GetColumnInfo(CCustomRowset* pThis,
        ULONG* pcCols);
   static ATLCOLUMNINFO* GetColumnInfo(CCustomCommand* pThis,
        ULONG* pcCols);
...
};
```

Implementieren Sie anschließend die `GetColumnInfo` -Funktion in der Datei CustomRS.cpp wie folgt:

```cpp
////////////////////////////////////////////////////////////////////
// CustomRS.cpp

template <class TInterface>
ATLCOLUMNINFO* CommonGetColInfo(IUnknown* pPropsUnk, ULONG* pcCols)
{
   static ATLCOLUMNINFO _rgColumns[5];
   ULONG ulCols = 0;

   CComQIPtr<TInterface> spProps = pPropsUnk;

   CDBPropIDSet set(DBPROPSET_ROWSET);
   set.AddPropertyID(DBPROP_BOOKMARKS);
   DBPROPSET* pPropSet = NULL;
   ULONG ulPropSet = 0;
   HRESULT hr;

   if (spProps)
      hr = spProps->GetProperties(1, &set, &ulPropSet, &pPropSet);

   // Check the property flag for bookmarks, if it is set, set the
// zero ordinal entry in the column map with the bookmark
// information.

   if (pPropSet)
   {
      CComVariant var = pPropSet->rgProperties[0].vValue;
      CoTaskMemFree(pPropSet->rgProperties);
      CoTaskMemFree(pPropSet);

      if ((SUCCEEDED(hr) && (var.boolVal == VARIANT_TRUE)))
      {
         ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Bookmark"), 0,
                     sizeof(DWORD), DBTYPE_BYTES,
            0, 0, GUID_NULL, CAgentMan, dwBookmark,
                        DBCOLUMNFLAGS_ISBOOKMARK)
         ulCols++;
      }

   }

   // Next set the other columns up.
   ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Field1"), 1, 16, DBTYPE_STR,
          0xFF, 0xFF, GUID_NULL, CTextData, szField1)
   ulCols++;
   ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Field2"), 2, 16, DBTYPE_STR,
       0xFF, 0xFF, GUID_NULL, CTextData, szField2)
   ulCols++;

   if (pcCols != NULL)
      *pcCols = ulCols;

   return _rgColumns;
}

ATLCOLUMNINFO* CTextData::GetColumnInfo(CCustomCommand* pThis,
     ULONG* pcCols)
{
   return CommonGetColInfo<ICommandProperties>(pThis->GetUnknown(),
        pcCols);
}

ATLCOLUMNINFO* CAgentMan::GetColumnInfo(RUpdateRowset* pThis, ULONG* pcCols)
{
   return CommonGetColInfo<IRowsetInfo>(pThis->GetUnknown(), pcCols);
}
```

`GetColumnInfo` zuerst überprüft, ob eine Eigenschaft namens `DBPROP_IRowsetLocate` festgelegt ist. OLE DB verfügt über Eigenschaften für jede der optionalen Schnittstellen außerhalb der Rowset-Objekt. Wenn der Consumer eine optionale Schnittstellen verwenden möchte, legt eine Eigenschaft auf "true" fest. Der Anbieter kann Klicken Sie dann diese Eigenschaft überprüfen und spezielle darauf basierenden Maßnahmen ergreifen.

In Ihrer Implementierung erhalten Sie die Eigenschaft mithilfe des Zeigers auf das Befehlsobjekt aus. Die `pThis` Zeiger darstellt, die Rowset- oder -Klasse. Da Vorlagen hier verwendet werden, müssen Sie als übergeben eine `void` Zeiger oder der Code nicht kompiliert.

Geben Sie ein statisches Array die Spalteninformationen enthalten. Wenn der Consumer die Lesezeichenspalte nicht möchte, wird ein Eintrag im Array verschwendet. Sie können dieses Array dynamisch zuordnen, aber Sie müssen sicherstellen, dass es ordnungsgemäß zerstört. In diesem Beispiel definiert und verwendet die Makros ADD_COLUMN_ENTRY und ADD_COLUMN_ENTRY_EX, die Informationen in das Array eingefügt werden. Sie können die Makros, die in die Datei CustomRS.H, wie im folgenden Code gezeigt hinzufügen:

```cpp
////////////////////////////////////////////////////////////////////////
// CustomRS.h

#define ADD_COLUMN_ENTRY(ulCols, name, ordinal, colSize, type, precision, scale, guid, dataClass, member) \
   _rgColumns[ulCols].pwszName = (LPOLESTR)name; \
   _rgColumns[ulCols].pTypeInfo = (ITypeInfo*)NULL; \
   _rgColumns[ulCols].iOrdinal = (ULONG)ordinal; \
   _rgColumns[ulCols].dwFlags = 0; \
   _rgColumns[ulCols].ulColumnSize = (ULONG)colSize; \
   _rgColumns[ulCols].wType = (DBTYPE)type; \
   _rgColumns[ulCols].bPrecision = (BYTE)precision; \
   _rgColumns[ulCols].bScale = (BYTE)scale; \
   _rgColumns[ulCols].cbOffset = offsetof(dataClass, member);

#define ADD_COLUMN_ENTRY_EX(ulCols, name, ordinal, colSize, type, precision, scale, guid, dataClass, member, flags) \
   _rgColumns[ulCols].pwszName = (LPOLESTR)name; \
   _rgColumns[ulCols].pTypeInfo = (ITypeInfo*)NULL; \
   _rgColumns[ulCols].iOrdinal = (ULONG)ordinal; \
   _rgColumns[ulCols].dwFlags = flags; \
   _rgColumns[ulCols].ulColumnSize = (ULONG)colSize; \
   _rgColumns[ulCols].wType = (DBTYPE)type; \
   _rgColumns[ulCols].bPrecision = (BYTE)precision; \
   _rgColumns[ulCols].bScale = (BYTE)scale; \
   _rgColumns[ulCols].cbOffset = offsetof(dataClass, member); \
   memset(&(_rgColumns[ulCols].columnid), 0, sizeof(DBID)); \
   _rgColumns[ulCols].columnid.uName.pwszName = (LPOLESTR)name;
```

Um den Code im Consumer zu testen, müssen Sie einige Änderungen an der `OnRun` Handler. Die erste Änderung an die Funktion ist, fügen Sie Code zum Hinzufügen einer Eigenschaft zum Eigenschaftensatz hinzu. Der Code legt die `DBPROP_IRowsetLocate` Eigenschaft auf True, um dem Anbieter, dass die Lesezeichenspalte werden sollen. Die `OnRun` Handlercode sollte wie folgt aussehen:

```cpp
//////////////////////////////////////////////////////////////////////
// TestProv Consumer Application in TestProvDlg.cpp

void CTestProvDlg::OnRun()
{
   CCommand<CAccessor<CProvider>> table;
   CDataSource source;
   CSession   session;

   if (source.Open("Custom.Custom.1", NULL, NULL, NULL,
          NULL) != S_OK)
      return;

   if (session.Open(source) != S_OK)
      return;

   CDBPropSet propset(DBPROPSET_ROWSET);
   propset.AddProperty(DBPROP_IRowsetLocate, true);
   if (table.Open(session, _T("c:\\public\\testprf2\\myData.txt"),
          &propset) != S_OK)
      return;

   CBookmark<4> tempBookmark;
   ULONG ulCount=0;
   while (table.MoveNext() == S_OK)
   {

      DBCOMPARE compare;
      if (ulCount == 2)
         tempBookmark = table.bookmark;

HRESULT hr = table.Compare(table.dwBookmark, table.dwBookmark,
                 &compare);
      if (FAILED(hr))
         ATLTRACE(_T("Compare failed: 0x%X\n"), hr);
      else
         _ASSERTE(compare == DBCOMPARE_EQ);

      m_ctlString1.AddString(table.szField1);
      m_ctlString2.AddString(table.szField2);
      ulCount++;
   }

   table.MoveToBookmark(tempBookmark);
   m_ctlString1.AddString(table.szField1);
   m_ctlString2.AddString(table.szField2);
}
```

Die **während** Schleife enthält Code zum Aufrufen der `Compare` -Methode in der die `IRowsetLocate` Schnittstelle. Der Code, was man sollte immer übergeben werden, da Sie exakten dieselben Lesezeichen vergleichen. Darüber hinaus ein Lesezeichen in einer temporären Variablen gespeichert werden, damit Sie ihn nach dem verwenden können die **während** Schleife abgeschlossen ist, rufen Sie die `MoveToBookmark` -Funktion in die Consumervorlagen. Die `MoveToBookmark` Funktionsaufrufe der `GetRowsAt` -Methode in der `IRowsetLocate`.

Sie müssen auch den Benutzerdatensatz im Consumer zu aktualisieren. Fügen Sie einen Eintrag in der Klasse, behandeln ein Lesezeichen und ein Eintrag in der `COLUMN_MAP`:

```cpp
///////////////////////////////////////////////////////////////////////
// TestProvDlg.cpp

class CProvider
{
// Attributes
public:
   CBookmark<4>    bookmark;  // Add this line
   char   szCommand[16];
   char   szText[256];

   // Binding Maps
BEGIN_ACCESSOR_MAP(CProvider, 1)
   BEGIN_ACCESSOR(0, true)   // auto accessor
      BOOKMARK_ENTRY(bookmark)  // Add this line
      COLUMN_ENTRY(1, szField1)
      COLUMN_ENTRY(2, szField2)
   END_ACCESSOR()
END_ACCESSOR_MAP()
};
```

Wenn Sie den Code aktualisiert haben, Sie sollten in der Lage zu erstellen, und führen den Anbieter mit der `IRowsetLocate` Schnittstelle.

## <a name="see-also"></a>Siehe auch

[Erweiterte Anbietertechniken](../../data/oledb/advanced-provider-techniques.md)