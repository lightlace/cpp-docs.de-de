---
title: "Dynamisches Binden von Spalten im Anbieter | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Spalten [C++], Dynamische Spaltenbindung"
  - "Dynamische Spaltenbindung"
  - "Anbieter [C++], Dynamische Spaltenbindung"
ms.assetid: 45e811e3-f5a7-4627-98cc-bf817c4e556e
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Dynamisches Binden von Spalten im Anbieter
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Prüfen Sie, ob die dynamische Spaltenbindung wirklich erforderlich ist.  Möglicherweise ist sie aus folgenden Gründen erforderlich:  
  
-   Rowsetspalten werden nicht zur Kompilierungszeit definiert.  
  
-   Es werden Elemente wie Lesezeichen unterstützt, durch die Spalten hinzugefügt werden.  
  
### So implementieren Sie die dynamische Spaltenbindung  
  
1.  Entfernen Sie alle **PROVIDER\_COLUMN\_MAP**\-Zuordnungen aus dem Code.  
  
2.  Fügen Sie dem Benutzerdatensatz \(Ihrer Struktur\) die folgende Deklaration hinzu:  
  
    ```  
    static ATLCOLUMNINFO* GetColumnInfo(void* pThis, ULONG* pcCols);  
    ```  
  
3.  Implementieren Sie die `GetColumnInfo`\-Funktion.  Diese Funktion legt fest, wie die Informationen gespeichert und angeordnet werden.  Für diese Funktion müssen Sie u. U. Eigenschaften oder andere Informationen abrufen.  Um die Informationen hinzuzufügen, können Sie ein Makro wie [COLUMN\_ENTRY](../../data/oledb/column-entry.md) erstellen.  
  
     Im folgenden Beispiel ist eine `GetColumnInfo`\-Funktion dargestellt.  
  
    ```  
    // Check the property flag for bookmarks, if it is set, set the zero  
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
          ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Bookmark"), 0, sizeof(DWORD), DBTYPE_BYTES,   
             0, 0, GUID_NULL, CAgentMan, dwBookmark, DBCOLUMNFLAGS_ISBOOKMARK)  
          ulCols++;  
       }  
    }  
  
    // Next, set up the other columns.  
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
  
## Siehe auch  
 [Arbeiten mit OLE DB\-Anbietervorlagen](../../data/oledb/working-with-ole-db-provider-templates.md)