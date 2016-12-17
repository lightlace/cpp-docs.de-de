---
title: "Dynamisches Festlegen der an den Consumer zur&#252;ckgegebenen Spalten"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Lesezeichen [C++], Dynamisches Bestimmen von Spalten"
  - "Dynamisches Bestimmen von Spalten [C++]"
ms.assetid: 58522b7a-894e-4b7d-a605-f80e900a7f5f
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Dynamisches Festlegen der an den Consumer zur&#252;ckgegebenen Spalten
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der **IColumnsInfo::GetColumnsInfo**\-Aufruf wird normalerweise durch die `PROVIDER_COLUMN_ENTRY`\-Makros behandelt.  Da ein Consumer jedoch möglicherweise Lesezeichen verwenden möchte, muss der Anbieter die zurückgegebenen Spalten ändern können, wenn der Consumer ein Lesezeichen anfordert.  
  
 Löschen Sie das **PROVIDER\_COLUMN\_MAP**\-Makro, durch das die `GetColumnInfo`\-Funktion definiert wird, aus dem `CAgentMan`\-Benutzerdatensatz der Datei **MyProviderRS.h**, um den **IColumnsInfo::GetColumnsInfo**\-Aufruf zu verarbeiten. Ersetzen Sie diese Definition durch Ihre eigene `GetColumnInfo`\-Funktionsdefinition:  
  
```  
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.H  
class CAgentMan  
{  
public:  
   DWORD dwBookmark;  
   TCHAR szCommand[256];  
   TCHAR szText[256];  
   TCHAR szCommand2[256];  
   TCHAR szText2[256];  
  
   static ATLCOLUMNINFO* GetColumnInfo(void* pThis, ULONG* pcCols);  
   bool operator==(const CAgentMan& am)  
   {  
      return (lstrcmpi(szCommand, am.szCommand) == 0);  
   }  
  
};  
```  
  
 Implementieren Sie als nächstes die `GetColumnInfo`\-Funktion in **MyProviderRS.cpp**, wie im folgenden Code dargestellt.  
  
 Zunächst prüft `GetColumnInfo`, ob die OLE DB\-Eigenschaft **DBPROP\_BOOKMARKS** festgelegt wurde.  `GetColumnInfo` verwendet zum Abrufen der Eigenschaft einen Zeiger \(`pRowset`\), der auf das Rowsetobjekt verweist.  Der `pThis`\-Zeiger stellt die Klasse dar, durch die das Rowset erstellt wurde. Hierbei handelt es sich um die Klasse, in der die Eigenschaftenzuordnung gespeichert ist.  Der `pThis`\-Zeiger wird mithilfe von `GetColumnInfo`\-Typumwandlungen in einen `RMyProviderRowset`\-Zeiger konvertiert.  
  
 Um die **DBPROP\_BOOKMARKS**\-Eigenschaft zu überprüfen, verwendet `GetColumnInfo` die `IRowsetInfo`\-Schnittstelle. Sie erhalten diese Schnittstelle, indem Sie `QueryInterface` für die `pRowset`\-Schnittstelle aufrufen.  Alternativ können Sie auch eine [CComQIPtr](../../atl/reference/ccomqiptr-class.md)\-ATL\-Methode verwenden.  
  
```  
////////////////////////////////////////////////////////////////////  
// MyProviderRS.cpp  
ATLCOLUMNINFO* CAgentMan::GetColumnInfo(void* pThis, ULONG* pcCols)  
{  
   static ATLCOLUMNINFO _rgColumns[5];  
   ULONG ulCols = 0;  
  
   // Check the property flag for bookmarks; if it is set, set the zero   
   // ordinal entry in the column map with the bookmark information.  
   CAgentRowset* pRowset = (CAgentRowset*) pThis;  
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
         DBTYPE_BYTES, 0, 0, GUID_NULL, CAgentMan, dwBookmark,   
         DBCOLUMNFLAGS_ISBOOKMARK)  
         ulCols++;  
      }  
   }  
  
   // Next, set the other columns up.  
   ADD_COLUMN_ENTRY(ulCols, OLESTR("Command"), 1, 256, DBTYPE_STR, 0xFF, 0xFF,   
      GUID_NULL, CAgentMan, szCommand)  
   ulCols++;  
   ADD_COLUMN_ENTRY(ulCols, OLESTR("Text"), 2, 256, DBTYPE_STR, 0xFF, 0xFF,   
      GUID_NULL, CAgentMan, szText)  
   ulCols++;  
  
   ADD_COLUMN_ENTRY(ulCols, OLESTR("Command2"), 3, 256, DBTYPE_STR, 0xFF, 0xFF,   
      GUID_NULL, CAgentMan, szCommand2)  
   ulCols++;  
   ADD_COLUMN_ENTRY(ulCols, OLESTR("Text2"), 4, 256, DBTYPE_STR, 0xFF, 0xFF,   
      GUID_NULL, CAgentMan, szText2)  
   ulCols++;  
  
   if (pcCols != NULL)  
      *pcCols = ulCols;  
  
   return _rgColumns;  
}  
```  
  
 In diesem Beispiel wird ein statisches Array verwendet, in dem die Spalteninformationen enthalten sind.  Falls die Lesezeichenspalte nicht vom Consumer benötigt wird, bleibt ein Eintrag im Array unbenutzt.  Zur Verarbeitung der Informationen erstellen Sie die beiden Arraymakros ADD\_COLUMN\_ENTRY und ADD\_COLUMN\_ENTRY\_EX.  **ADD\_COLUMN\_ENTRY\_EX** nimmt den zusätzlichen Parameter `flags` an, der beim Festlegen einer Lesezeichenspalte erforderlich ist.  
  
```  
////////////////////////////////////////////////////////////////////////  
// MyProviderRS.h  
  
#define ADD_COLUMN_ENTRY(ulCols, name, ordinal, colSize, type, precision,   
scale, guid, dataClass, member) \  
   _rgColumns[ulCols].pwszName = (LPOLESTR)name; \  
   _rgColumns[ulCols].pTypeInfo = (ITypeInfo*)NULL; \  
   _rgColumns[ulCols].iOrdinal = (ULONG)ordinal; \  
   _rgColumns[ulCols].dwFlags = 0; \  
   _rgColumns[ulCols].ulColumnSize = (ULONG)colSize; \  
   _rgColumns[ulCols].wType = (DBTYPE)type; \  
   _rgColumns[ulCols].bPrecision = (BYTE)precision; \  
   _rgColumns[ulCols].bScale = (BYTE)scale; \  
   _rgColumns[ulCols].cbOffset = offsetof(dataClass, member);  
  
#define ADD_COLUMN_ENTRY_EX(ulCols, name, ordinal, colSize, type,   
precision, scale, guid, dataClass, member, flags) \  
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
  
 In der `GetColumnInfo`\-Funktion wird das Lesezeichenmakro wie folgt verwendet:  
  
```  
ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Bookmark"), 0, sizeof(DWORD),  
   DBTYPE_BYTES, 0, 0, GUID_NULL, CAgentMan, dwBookmark,   
   DBCOLUMNFLAGS_ISBOOKMARK)  
```  
  
 Jetzt können Sie den erweiterten Anbieter kompilieren und ausführen.  Um den Anbieter zu testen, ändern Sie den Testconsumer wie unter [Implementieren eines einfachen Consumers](../../data/oledb/implementing-a-simple-consumer.md) beschrieben.  Führen Sie den Testconsumer mit dem Anbieter aus.  Stellen Sie sicher, dass der Testconsumer die richtigen Zeichenfolgen vom Anbieter abruft, wenn Sie im Dialogfeld **Testconsumer** auf **Ausführen** klicken.  
  
## Siehe auch  
 [Erweitern des einfachen schreibgeschützten Anbieters](../../data/oledb/enhancing-the-simple-read-only-provider.md)