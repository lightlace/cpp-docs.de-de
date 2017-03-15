---
title: "CDynamicAccessor::GetColumnName | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CDynamicAccessor::GetColumnName"
  - "GetColumnName"
  - "ATL.CDynamicAccessor.GetColumnName"
  - "CDynamicAccessor::GetColumnName"
  - "CDynamicAccessor.GetColumnName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetColumnName-Methode"
ms.assetid: 96a7452a-1f5b-41e9-ab37-88dac026f961
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDynamicAccessor::GetColumnName
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft den Namen der angegebenen Spalte ab.  
  
## Syntax  
  
```  
  
      LPOLESTR GetColumnName(   
   DBORDINAL nColumn    
) const throw( );  
```  
  
#### Parameter  
 `nColumn`  
 \[in\] Spaltennummer.  Spaltennummern beginnen mit 1.  Ein Wert von 0 werden die Lesezeichenspalte an, falls welche vorhanden.  
  
## Rückgabewert  
 Der Name der angegebenen Spalte.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CDynamicAccessor\-Klasse](../../data/oledb/cdynamicaccessor-class.md)