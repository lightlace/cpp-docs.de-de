---
title: "CBulkRowset::SetRows | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.CBulkRowset.SetRows"
  - "CBulkRowset::SetRows"
  - "CBulkRowset<TAccessor>.SetRows"
  - "ATL.CBulkRowset<TAccessor>.SetRows"
  - "CBulkRowset<TAccessor>::SetRows"
  - "ATL::CBulkRowset<TAccessor>::SetRows"
  - "ATL::CBulkRowset::SetRows"
  - "CBulkRowset.SetRows"
  - "SetRows"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetRows-Methode"
ms.assetid: 7e92312a-bfd0-4c24-a799-62bef663f28e
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CBulkRowset::SetRows
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Legt die Anzahl der den Zeilenhandles fest, die von jedem Aufruf abgefragt werden.  
  
## Syntax  
  
```  
  
      void SetRows(  
   DBROWCOUNT nRows   
) throw( );  
```  
  
#### Parameter  
 `nRows`  
 \[in\] Die neue Größe des Rowsets \(Zahl Zeilen\).  
  
## Hinweise  
 Wenn Sie diese Funktion aufrufen, muss sie ihr, bevor das Rowset geöffnet ist.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CBulkRowset\-Klasse](../../data/oledb/cbulkrowset-class.md)