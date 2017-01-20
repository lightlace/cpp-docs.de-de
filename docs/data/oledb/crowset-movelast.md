---
title: "CRowset::MoveLast"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "ATL::CRowset<TAccessor>::MoveLast"
  - "CRowset<TAccessor>::MoveLast"
  - "ATL.CRowset.MoveLast"
  - "ATL::CRowset::MoveLast"
  - "CRowset<TAccessor>.MoveLast"
  - "MoveLast"
  - "CRowset::MoveLast"
  - "ATL.CRowset<TAccessor>.MoveLast"
  - "CRowset.MoveLast"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MoveLast-Methode"
ms.assetid: 81063578-ae9d-467b-8c88-81d8fc66e020
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# CRowset::MoveLast
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Verschiebt den Cursor zur letzten Zeile.  
  
## Syntax  
  
```  
  
HRESULT MoveLast( ) throw( );  
  
```  
  
## Rückgabewert  
 Standard\- `HRESULT`.  
  
## Hinweise  
 Ruft [IRowset::RestartPosition](https://msdn.microsoft.com/en-us/library/ms712877.aspx) auf, um den NEXTAbrufspeicherort zur letzten Speicherort neu anzuordnen und die letzte Zeile ab.  
  
 Diese Methode erfordert dass Sie sowohl **DBPROP\_CANSCROLLBACKWARDS** werden `VARIANT_TRUE`, bevor sie auf dem Tisch **Öffnen** oder den Befehl, die das Rowset enthält aufruft. \(Zur Leistungsverbesserung, könnten Sie auch **DBPROP\_QUICKRESTART** auf `VARIANT_TRUE` fest.\)  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CRowset\-Klasse](../../data/oledb/crowset-class.md)   
 [CRowset::MoveNext](../../data/oledb/crowset-movenext.md)   
 [IRowset::RestartPosition](https://msdn.microsoft.com/en-us/library/ms712877.aspx)   
 [CRowset::MovePrev](../../data/oledb/crowset-moveprev.md)