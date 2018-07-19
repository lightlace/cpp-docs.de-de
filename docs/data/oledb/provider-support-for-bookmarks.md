---
title: Anbieterunterstützung für Lesezeichen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IRowsetLocate class, provider support for bookmarks
- OLE DB provider templates, bookmarks
- bookmarks, OLE DB
- IRowsetLocate class
- OLE DB providers, bookmark support
ms.assetid: 1b14ccff-4f76-462e-96ab-1aada815c377
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 139956fcd7d9244c486ad37797696817c7080fbd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33112507"
---
# <a name="provider-support-for-bookmarks"></a>Anbieterunterstützung für Lesezeichen
Im Beispiel in diesem Thema wird die `IRowsetLocate` Schnittstelle für die `CMyProviderRowset` Klasse. In fast allen Fällen starten Sie durch Hinzufügen einer Schnittstelle zu einem vorhandenen COM-Objekt. Anschließend können Sie sie testen, indem mehr Aufrufe über die Consumervorlagen hinzufügen. Im Beispiel wird veranschaulicht, wie Sie:  
  
-   Hinzufügen einer Schnittstelle zu einem Anbieter.  
  
-   Dynamisch bestimmen Sie die Spalten an den Consumer zurückgegeben.  
  
-   Lesezeichenunterstützung für hinzufügen.  
  
 Die `IRowsetLocate`-Schnittstelle erbt von der `IRowset`-Schnittstelle. Hinzufügen der `IRowsetLocate` Schnittstelle, erben `CMyProviderRowset` aus [IRowsetLocateImpl](../../data/oledb/irowsetlocateimpl-class.md).  
  
 Hinzufügen der `IRowsetLocate` Schnittstelle unterscheidet sich etwas von den meisten Schnittstellen. Stellen Sie die v-Tabellen-Zeile nach oben, den OLE DB-haben Anbietervorlagen einen Vorlagenparameter, die abgeleitete Schnittstelle zu behandeln. Der folgende Code zeigt die neue Vererbungsliste:  
  
```cpp
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.h  
  
// CMyProviderRowset  
class CMyProviderRowset : public CRowsetImpl< CMyProviderRowset,   
      CTextData, CMyProviderCommand, CAtlArray<CTextData>,   
      CSimpleRow,   
          IRowsetLocateImpl<CMyProviderRowset, IRowsetLocate>>  
```  
  
 Die vierten, fünften und sechsten Parameter, die alle hinzugefügt werden. In diesem Beispiel verwendet die Standardeinstellungen für die vierte und fünfte Parameter jedoch angeben `IRowsetLocateImpl` als sechsten Parameters. `IRowsetLocateImpl` ist eine OLE DB-Vorlagenklasse, die zwei Vorlagenparameter akzeptiert: Diese verknüpfen die `IRowsetLocate` Schnittstelle für die `CMyProviderRowset` Klasse. Um die meisten Schnittstellen hinzuzufügen, können Sie diesen Schritt überspringen und mit dem nächsten zu verschieben. Nur die `IRowsetLocate` und `IRowsetScroll` Schnittstellen, die auf diese Weise behandelt werden müssen.  
  
 Dann müssen Sie die `CMyProviderRowset` Aufrufen `QueryInterface` für die `IRowsetLocate` Schnittstelle. Fügen Sie die Zeile `COM_INTERFACE_ENTRY(IRowsetLocate)` zur Zuordnung. Die schnittstellenzuordnung für `CMyProviderRowset` sollte angezeigt werden, wie im folgenden Code gezeigt:  
  
```cpp
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.h  
  
typedef CRowsetImpl< CMyProviderRowset, CTextData, CMyProviderCommand, CAtlArray<CTextData>, CSimpleRow, IRowsetLocateImpl<CMyProviderRowset, IRowsetLocate>> _RowsetBaseClass;  
  
BEGIN_COM_MAP(CMyProviderRowset)  
   COM_INTERFACE_ENTRY(IRowsetLocate)  
   COM_INTERFACE_ENTRY_CHAIN(_RowsetBaseClass)  
END_COM_MAP()  
```  
  
 Außerdem müssen Sie die Zuordnung in verknüpft die `CRowsetImpl` Klasse. Hinzufügen-Makro zum Verknüpfen der `CRowsetImpl` Zuordnung. Erstellen Sie auch eine Typdefinition namens `RowsetBaseClass` , die Vererbungsinformationen besteht. Diese Typedef ist ein beliebiger und kann ignoriert werden.  
  
 Behandeln Sie schließlich die **IColumnsInfo:: GetColumnsInfo** aufrufen. Normalerweise würden Sie dazu die-Makros verwenden. Allerdings kann ein Consumer Lesezeichen verwenden möchten. Sie müssen die Spalten ändern können, die die Anbieter zurück, je nachdem, ob der Consumer ein Lesezeichen anfordert sein.  
  
 Behandeln der **IColumnsInfo:: GetColumnsInfo** aufrufen, löschen Sie die **PROVIDER_COLUMN** ordnen die `CTextData` Klasse. Das Makro-Makro definiert eine Funktion `GetColumnInfo`. Sie definieren müssen eigene `GetColumnInfo` Funktion. Die Funktionsdeklaration sollte wie folgt aussehen:  
  
```cpp
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.H  
  
class CTextData  
{  
   ...  
     // NOTE: Be sure you removed the PROVIDER_COLUMN_MAP!  
   static ATLCOLUMNINFO* GetColumnInfo(CMyProviderRowset* pThis,   
        ULONG* pcCols);  
   static ATLCOLUMNINFO* GetColumnInfo(CMyProviderCommand* pThis,   
        ULONG* pcCols);  
...  
};  
```  
  
 Implementieren Sie anschließend die `GetColumnInfo` -Funktion in der Datei MyProviderRS.cpp wie folgt:  
  
```cpp
////////////////////////////////////////////////////////////////////  
// MyProviderRS.cpp  
  
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
  
ATLCOLUMNINFO* CTextData::GetColumnInfo(CMyProviderCommand* pThis,   
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
  
 `GetColumnInfo` prüft zunächst, um festzustellen, ob eine Eigenschaft mit dem Namen **DBPROP_IRowsetLocate** festgelegt ist. OLE DB verfügt über Eigenschaften für jede der optionalen Schnittstellen außerhalb der Rowset-Objekte. Wenn der Consumer eine dieser optionalen Schnittstellen verwenden möchte, legt eine Eigenschaft auf "true" fest. Der Anbieter kann dann überprüfen Sie diese Eigenschaft und besondere Maßnahmen darauf basieren.  
  
 In der Implementierung rufen Sie diese Eigenschaft mithilfe des Zeigers auf das Befehlsobjekt aus. Die `pThis` -Zeiger stellt die Rowset- oder -Klasse. Da hier Vorlagen verwendet werden, müssen Sie diesen als übergeben einer `void` Zeiger oder den Code nicht kompiliert.  
  
 Geben Sie einen statischen Array, um die Informationen in der Spalte enthalten. Wenn der Consumer die Lesezeichenspalte nicht möchten, wird ein Eintrag im Array verschwendet. Sie können dieses Array dynamisch reservieren, jedoch müssen Sie sicherstellen, dass sie ordnungsgemäß zerstört werden. In diesem Beispiel definiert und die Makros ADD_COLUMN_ENTRY und ADD_COLUMN_ENTRY_EX verwendet, um die Informationen in das Array eingefügt werden. Sie können die Makros in der Datei MyProviderRS.H wie im folgenden Code gezeigt hinzufügen:  
  
```cpp
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.h  
  
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
  
 Um den Code in der Consumer zu testen, müssen Sie einige Änderungen an der `OnRun` Handler. Die erste Änderung an die Funktion ist, fügen Sie Code zum Hinzufügen einer Eigenschaft zum Eigenschaftensatz hinzu. Der Code legt die **DBPROP_IRowsetLocate** Eigenschaft auf "true", wodurch der Anbieter darüber informiert wird, die Lesezeichenspalte wirklich. Die `OnRun` Handlercode sollte wie folgt aussehen:  
  
```cpp
//////////////////////////////////////////////////////////////////////  
// TestProv Consumer Application in TestProvDlg.cpp  
  
void CTestProvDlg::OnRun()   
{  
   CCommand<CAccessor<CProvider>> table;  
   CDataSource source;  
   CSession   session;  
  
   if (source.Open("MyProvider.MyProvider.1", NULL, NULL, NULL,   
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
  
 Die While-Schleife enthält Code zum Aufrufen der `Compare` Methode in der `IRowsetLocate` Schnittstelle. Der Code, den Sie sollten immer übergeben werden, da Sie die genaue dieselben Lesezeichen verglichen werden. Darüber hinaus ein Lesezeichen in einer temporären Variablen gespeichert werden, damit Sie ihn nach Beendigung der While verwenden können Schleife abgeschlossen ist, rufen Sie die `MoveToBookmark` -Funktion in die Consumervorlagen. Die `MoveToBookmark` Funktionsaufrufe, die `GetRowsAt` Methode in `IRowsetLocate`.  
  
 Sie müssen auch die Benutzerdatensatz im Consumer zu aktualisieren. Fügen Sie einen Eintrag in der Klasse zum Behandeln von Lesezeichen und einen Eintrag in der **COLUMN_MAP**:  
  
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
  
 Wenn Sie den Code aktualisiert haben, Sie sollten Lage zu erstellen, und führen den Anbieter mit der `IRowsetLocate` Schnittstelle.  
  
## <a name="see-also"></a>Siehe auch  
 [Erweiterte Anbietertechniken](../../data/oledb/advanced-provider-techniques.md)