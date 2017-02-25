---
title: "CRowset::MoveFirst | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CRowset<TAccessor>::MoveFirst"
  - "ATL::CRowset::MoveFirst"
  - "CRowset<TAccessor>.MoveFirst"
  - "CRowset::MoveFirst"
  - "CRowset.MoveFirst"
  - "ATL.CRowset.MoveFirst"
  - "ATL.CRowset<TAccessor>.MoveFirst"
  - "ATL::CRowset<TAccessor>::MoveFirst"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MoveFirst-Methode"
ms.assetid: a17c0799-ead9-4d85-9a1d-8b17188d01e3
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# CRowset::MoveFirst
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Verschiebt den Cursor auf die Startposition und ruft die Originalzeile ab.  
  
## Syntax  
  
```  
  
HRESULT MoveFirst( ) throw( );  
  
```  
  
## Rückgabewert  
 Standard\- `HRESULT`.  
  
## Hinweise  
 Ruft [IRowset::RestartPosition](https://msdn.microsoft.com/en-us/library/ms712877.aspx) auf, um den NEXTAbrufspeicherort zur Anfangsposition \(die Position, die der NEXTAbrufspeicherort, als wäre das Rowset erstellt wurde\), neu anordnen und ruft die Originalzeile ab.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CRowset\-Klasse](../../data/oledb/crowset-class.md)   
 [CRowset::MoveNext](../../data/oledb/crowset-movenext.md)   
 [CRowset::MoveToBookmark](../../data/oledb/crowset-movetobookmark.md)   
 [CRowset::MovePrev](../../data/oledb/crowset-moveprev.md)   
 [CRowset::MoveLast](../../data/oledb/crowset-movelast.md)   
 [IRowset::RestartPosition](https://msdn.microsoft.com/en-us/library/ms712877.aspx)