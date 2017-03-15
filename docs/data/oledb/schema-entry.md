---
title: "SCHEMA_ENTRY | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SCHEMA_ENTRY"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SCHEMA_ENTRY-Makro"
ms.assetid: e8bee479-80f3-417e-8f41-cdaddd49690c
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# SCHEMA_ENTRY
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ordnet eine GUID mit einer Klasse zu.  
  
## Syntax  
  
```  
  
      SCHEMA_ENTRY(  
   guid,  
   rowsetClass   
);   
```  
  
#### Parameter  
 `guid`  
 Eine Schemarowset GUID.  Siehe [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) in *der OLE DB\-Programmierreferenz* für eine Liste der Schemarowsets und zugehörigen GUIDs.  
  
 *rowsetClass*  
 Die Klasse, die erstellt wird, um das zu unterstützende Schemarowset darzustellen.  
  
## Hinweise  
 [IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md) kann die Zuordnung für eine Liste von GUIDs dann abfragen, oder sie kann ein Rowset, die eine GUID hat.  Das Schemarowset `IDBSchemaRowsetImpl` erstellt ist ähnlich Standard\- `CRowsetImpl` abgeleitete Klasse, außer eine **Ausführen**\-Methode bereitstellen muss, die folgende Signatur aufweist:  
  
 `HRESULT Execute (LONG* pcRowsAffected, ULONG cRestrictions,`  
  
 `const VARIANT* rgRestrictions)`  
  
 **Ausführen** Diese Funktion füllt die Daten eines Rowsets auf.  Der ATL\-Projekt\-Assistent erstellt, wie unter [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) in der *OLE* DB\-Programmierreferenz beschrieben, drei Schemarowsets ursprüngliche im Projekt für jedes der drei erforderlichen OLE DB\-Schemas:  
  
-   `DBSCHEMA_TABLES`  
  
-   **DBSCHEMA\_COLUMNS**  
  
-   **DBSCHEMA\_PROVIDER\_TYPES**  
  
 Der Assistent fügt auch drei entsprechende Einträge in der Schemazuordnung hinzu.  Siehe [Erstellen eines OLE DB\-Vorlagen\-Anbieters](../../data/oledb/creating-an-ole-db-provider.md) weitere Informationen zur Verwendung des Assistenten, um einen Anbieter zu erstellen.  
  
## Anforderungen  
 **Header:** atldb.h  
  
## Siehe auch  
 [Makros für OLE DB\-Anbietervorlagen](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [BEGIN\_SCHEMA\_MAP](../../data/oledb/begin-schema-map.md)   
 [END\_SCHEMA\_MAP](../../data/oledb/end-schema-map.md)