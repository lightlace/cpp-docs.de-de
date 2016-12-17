---
title: "BEGIN_SCHEMA_MAP"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "BEGIN_SCHEMA_MAP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BEGIN_SCHEMA_MAP-Makro"
ms.assetid: 4e751023-35bc-4efd-9018-5448dd1ad751
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# BEGIN_SCHEMA_MAP
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Deutet auf den Beginn einer Schemazuordnung.  
  
## Syntax  
  
```  
  
      BEGIN_SCHEMA_MAP(  
   SchemaClass   
);  
```  
  
#### Parameter  
 *SchemaClass*  
 Die Klasse, die die ZUORDNUNG enthält.  In der Regel ist dies die Sitzungsklasse.  
  
## Hinweise  
 Siehe [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) in [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] zu Informationen über Schemarowsets.  
  
## Anforderungen  
 **Header:** atldb.h  
  
## Siehe auch  
 [Makros für OLE DB\-Anbietervorlagen](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [SCHEMA\_ENTRY](../../data/oledb/schema-entry.md)   
 [END\_SCHEMA\_MAP](../../data/oledb/end-schema-map.md)   
 [IDBSchemaRowsetImpl\-Klasse](../../data/oledb/idbschemarowsetimpl-class.md)