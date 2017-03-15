---
title: "COLUMN_ENTRY_TYPE | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "COLUMN_ENTRY_TYPE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COLUMN_ENTRY_TYPE-Makro"
ms.assetid: ac424261-ff6c-443b-a197-2cec8d78d738
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# COLUMN_ENTRY_TYPE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt eine Bindung zur spezifischen Spalte in der Datenbank dar.  Unterstützt `type`\-Parameter.  
  
## Syntax  
  
```  
  
COLUMN_ENTRY_TYPE (  
nOrdinal  
,   
wType  
,   
data  
 )  
  
```  
  
#### Parameter  
 `nOrdinal`  
 \[in\] Spaltennummer.  
  
 `wType`  
 \[in\] Datentyp des Spalteneintrags.  
  
 `data`  
 \[in\] der entsprechenden Datenmember im Benutzerdatensatz.  
  
## Hinweise  
 Dieses Makro ist eine besondere Variante des Makros [COLUMN\_ENTRY](../../data/oledb/column-entry.md), d Angabe des Datentyps bereitstellt.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [Makros und globale Funktionen für OLE\-Consumervorlagen](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN\_COLUMN\_MAP](../../data/oledb/begin-column-map.md)   
 [END\_COLUMN\_MAP](../../data/oledb/end-column-map.md)