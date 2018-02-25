---
title: Dynamisches Binden von Spalten im Anbieter | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- columns [C++], dynamic column binding
- dynamic column binding
- providers [C++], dynamic column binding
ms.assetid: 45e811e3-f5a7-4627-98cc-bf817c4e556e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6dbb189e1eb08616c12e927f9247bb1199f269a4
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="dynamically-binding-columns-in-your-provider"></a>Dynamisches Binden von Spalten im Anbieter
Stellen Sie sicher, dass Sie dynamische spaltenbindung eigentlich benötigen. Sie können ihn benötigen, da:  
  
-   Die Rowsetspalten sind nicht zum Zeitpunkt der Kompilierung definiert.  
  
-   Sie unterstützen ein Element wie das Lesezeichen, die Spalten hinzugefügt.  
  
### <a name="to-implement-dynamic-column-binding"></a>Dynamische spaltenbindung implementieren.  
  
1.  Entfernen Sie alle **Makro**s aus dem Code.  
  
2.  Fügen Sie im Benutzerdatensatz (Ihrer Struktur) die folgende Deklaration hinzu:  
  
    ```  
    static ATLCOLUMNINFO* GetColumnInfo(void* pThis, ULONG* pcCols);  
    ```  
  
3.  Implementieren der `GetColumnInfo` Funktion. Diese Funktion Layout wie die Informationen gespeichert werden. Möglicherweise müssen Sie die Eigenschaften oder andere Informationen für diese Funktion zu erhalten. Möglicherweise möchten Sie erstellen Sie ein Makro, ähnlich wie die [COLUMN_ENTRY](../../data/oledb/column-entry.md) -Makro, um Ihre eigenen Informationen hinzuzufügen.  
  
     Das folgende Beispiel zeigt eine `GetColumnInfo` Funktion.  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [Arbeiten mit OLE DB-Anbietervorlagen](../../data/oledb/working-with-ole-db-provider-templates.md)