---
title: Dynamisches Festlegen der an den Consumer zurückgegebenen Spalten
ms.date: 10/26/2018
helpviewer_keywords:
- bookmarks [C++], dynamically determining columns
- dynamically determining columns [C++]
ms.assetid: 58522b7a-894e-4b7d-a605-f80e900a7f5f
ms.openlocfilehash: 7db319aa153cb281c8fd8b4eec16972f5ac0c2c9
ms.sourcegitcommit: 943c792fdabf01c98c31465f23949a829eab9aad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2018
ms.locfileid: "51265177"
---
# <a name="dynamically-determining-columns-returned-to-the-consumer"></a>Dynamisches Festlegen der an den Consumer zurückgegebenen Spalten

Die-Makros normalerweise behandelt die `IColumnsInfo::GetColumnsInfo` aufrufen. Allerdings da ein Consumer kann Lesezeichen verwenden, muss der Anbieter Lage Ändern der Spalten, die zurückgegeben werden, je nachdem, ob der Consumer ein Lesezeichen anfordert.

Behandelt die `IColumnsInfo::GetColumnsInfo` aufrufen, löschen Sie Makro, das eine Funktion definiert `GetColumnInfo`, aus der `CCustomWindowsFile` Benutzerdatensatz im *benutzerdefinierte*RS.h und Ersetzen Sie sie mit der Definition für Ihre eigenen `GetColumnInfo` Funktion:

```cpp
////////////////////////////////////////////////////////////////////////
// CustomRS.H
class CCustomWindowsFile
{
public:
   DWORD dwBookmark;
   static const int iSize = 256;
   TCHAR szCommand[iSize];
   TCHAR szText[iSize];
   TCHAR szCommand2[iSize];
   TCHAR szText2[iSize];
  
   static ATLCOLUMNINFO* GetColumnInfo(void* pThis, ULONG* pcCols);
   bool operator==(const CCustomWindowsFile& am)
   {
      return (lstrcmpi(szCommand, am.szCommand) == 0);
   }
};
```

Implementieren Sie als Nächstes die `GetColumnInfo` -Funktion in *benutzerdefinierte*RS.cpp, wie im folgenden Code gezeigt.

`GetColumnInfo` überprüft zunächst, ob der OLE DB-Eigenschaft `DBPROP_BOOKMARKS` festgelegt ist. Zum Abrufen der Eigenschaft, `GetColumnInfo` verwendet einen Zeiger (`pRowset`) auf das Rowsetobjekt. Die `pThis` Zeiger darstellt, die Klasse, die das Rowset erstellt wurde, dies ist die Klasse, in die eigenschaftenzuordnung gespeichert ist. `GetColumnInfo` typenumwandlungen der `pThis` Zeiger auf ein `RCustomRowset` Zeiger.

Zu prüfen, die `DBPROP_BOOKMARKS` Eigenschaft `GetColumnInfo` verwendet die `IRowsetInfo` -Schnittstelle, die Sie durch den Aufruf abrufen können `QueryInterface` auf die `pRowset` Schnittstelle. Als Alternative können Sie eine ATL [CComQIPtr](../../atl/reference/ccomqiptr-class.md) Methode stattdessen.

```cpp
////////////////////////////////////////////////////////////////////
// CustomRS.cpp
ATLCOLUMNINFO* CCustomWindowsFile::GetColumnInfo(void* pThis, ULONG* pcCols)
{
   static ATLCOLUMNINFO _rgColumns[5];
   ULONG ulCols = 0;
  
   // Check the property flag for bookmarks; if it is set, set the zero 
   // ordinal entry in the column map with the bookmark information.
   CCustomRowset* pRowset = (CCustomRowset*) pThis;
   CComQIPtr<IRowsetInfo, &IID_IRowsetInfo> spRowsetProps = pRowset;
  
   CDBPropIDSet set(DBPROPSET_ROWSET);
   set.AddPropertyID(DBPROP_BOOKMARKS);
   DBPROPSET* pPropSet = NULL;
   ULONG ulPropSet = 0;
   HRESULT hr;
  
   if (spRowsetProps)
      hr = spRowsetProps->GetProperties(1, &set, &ulPropSet, &pPropSet);
  
   if (pPropSet)
   {
      CComVariant var = pPropSet->rgProperties[0].vValue;
      CoTaskMemFree(pPropSet->rgProperties);
      CoTaskMemFree(pPropSet);
  
      if (SUCCEEDED(hr) && (var.boolVal == VARIANT_TRUE))
      {
         ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Bookmark"), 0, sizeof(DWORD), 
         DBTYPE_BYTES, 0, 0, GUID_NULL, CCustomWindowsFile, dwBookmark, 
         DBCOLUMNFLAGS_ISBOOKMARK)
         ulCols++;
      }
   }
  
   // Next, set the other columns up.
   ADD_COLUMN_ENTRY(ulCols, OLESTR("Command"), 1, 256, DBTYPE_STR, 0xFF, 0xFF, 
      GUID_NULL, CCustomWindowsFile, szCommand)
   ulCols++;
   ADD_COLUMN_ENTRY(ulCols, OLESTR("Text"), 2, 256, DBTYPE_STR, 0xFF, 0xFF, 
      GUID_NULL, CCustomWindowsFile, szText)
   ulCols++;
  
   ADD_COLUMN_ENTRY(ulCols, OLESTR("Command2"), 3, 256, DBTYPE_STR, 0xFF, 0xFF, 
      GUID_NULL, CCustomWindowsFile, szCommand2)
   ulCols++;
   ADD_COLUMN_ENTRY(ulCols, OLESTR("Text2"), 4, 256, DBTYPE_STR, 0xFF, 0xFF, 
      GUID_NULL, CCustomWindowsFile, szText2)
   ulCols++;
  
   if (pcCols != NULL)
      *pcCols = ulCols;
  
   return _rgColumns;
}
```

In diesem Beispiel verwendet ein statisches Array für die Spalteninformationen. Wenn der Consumer die Lesezeichenspalte nicht möchte, wird ein Eintrag im Array nicht verwendet. Behandeln Sie die Informationen, die Sie erstellen zwei Array-Makros: ADD_COLUMN_ENTRY und ADD_COLUMN_ENTRY_EX. ADD_COLUMN_ENTRY_EX verwendet einen zusätzlichen Parameter, *Flags*, d. h. erforderlich, wenn Sie eine Lesezeichenspalte zu bestimmen.

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

In der `GetColumnInfo` -Funktion, die Lesezeichenmakro wird wie folgt verwendet:

```cpp
ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Bookmark"), 0, sizeof(DWORD),
   DBTYPE_BYTES, 0, 0, GUID_NULL, CAgentMan, dwBookmark,
   DBCOLUMNFLAGS_ISBOOKMARK)
```

Sie können jetzt kompilieren und führen Sie den erweiterten Anbieter. Um den Anbieter zu testen, ändern Sie den Testconsumer, wie unter beschrieben [Implementieren eines einfachen Consumers](../../data/oledb/implementing-a-simple-consumer.md). Führen Sie den Testconsumer mit dem Anbieter aus, und stellen Sie sicher, dass der Testconsumer die richtigen Zeichenfolgen vom Anbieter empfängt.

## <a name="see-also"></a>Siehe auch

[Erweitern des einfachen schreibgeschützten Anbieters](../../data/oledb/enhancing-the-simple-read-only-provider.md)<br/>
