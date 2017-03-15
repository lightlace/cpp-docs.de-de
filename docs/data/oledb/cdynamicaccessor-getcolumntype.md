---
title: "CDynamicAccessor::GetColumnType | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.CDynamicAccessor.GetColumnType"
  - "CDynamicAccessor::GetColumnType"
  - "GetColumnType"
  - "CDynamicAccessor.GetColumnType"
  - "ATL::CDynamicAccessor::GetColumnType"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetColumnType-Methode"
ms.assetid: ac96a2e9-6049-4eb5-9718-9f5f5446b74e
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDynamicAccessor::GetColumnType
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft den Datentyp einer bestimmten Spalte ab.  
  
## Syntax  
  
```  
  
      bool GetColumnType(   
   DBORDINAL nColumn,   
   DBTYPE* pType    
) const throw( );  
```  
  
#### Parameter  
 `nColumn`  
 \[in\] Spaltennummer.  Spaltennummern beginnen mit 1.  Ein Wert von 0 werden die Lesezeichenspalte an, falls welche vorhanden.  
  
 `pType`  
 \[out\] Ein Zeiger auf den Datentyp der angegebenen Spalte.  
  
## Rückgabewert  
 **true** Gibt bei Erfolg oder **false** auf Fehler.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CDynamicAccessor\-Klasse](../../data/oledb/cdynamicaccessor-class.md)   
 [DBTYPE](https://msdn.microsoft.com/en-us/library/ms711251.aspx)