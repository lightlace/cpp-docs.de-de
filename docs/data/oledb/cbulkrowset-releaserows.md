---
title: "CBulkRowset::ReleaseRows | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ReleaseRows"
  - "ATL.CBulkRowset<TAccessor>.ReleaseRows"
  - "ATL::CBulkRowset<TAccessor>::ReleaseRows"
  - "ATL.CBulkRowset.ReleaseRows"
  - "CBulkRowset<TAccessor>::ReleaseRows"
  - "ATL::CBulkRowset::ReleaseRows"
  - "CBulkRowset::ReleaseRows"
  - "CBulkRowset.ReleaseRows"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ReleaseRows-Methode"
ms.assetid: ba48aff3-0887-47ba-aed7-7ff28fa1c4a8
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CBulkRowset::ReleaseRows
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft [IRowset::ReleaseRows](https://msdn.microsoft.com/en-us/library/ms719771.aspx) auf, um den Verweiszähler für alle Zeilen zu dekrementieren, die gerade vom Massenrowset abgerufen werden.  
  
## Syntax  
  
```  
  
HRESULT ReleaseRows( ) throw( );  
  
```  
  
## Rückgabewert  
 Standard\- `HRESULT`.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CBulkRowset\-Klasse](../../data/oledb/cbulkrowset-class.md)   
 [CBulkRowset::AddRefRows](../../data/oledb/cbulkrowset-addrefrows.md)