---
title: "CTable-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CTable"
  - "ATL.CTable"
  - "CTable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTable-Klasse"
ms.assetid: f13fdaa3-e198-4557-977d-54b0bbc3454d
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# CTable-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt eine Möglichkeit bereit, um auf eines einfachen, Rowsets \(eines ohne Parameter\) direkt zugreifen.  
  
## Syntax  
  
```  
template <   
   class TAccessor = CNoAccessor,    
   template <typename T> class TRowset = CRowset    
>  
class CTable :    
   public CAccessorRowset <   
      TAccessor,    
      TRowset    
   >  
```  
  
#### Parameter  
 `TAccessor`  
 Eine Accessorklasse.  
  
 `TRowset`  
 Eine Rowsetklasse.  
  
## Member  
  
### Methoden  
  
|||  
|-|-|  
|[Öffnen](../../data/oledb/ctable-open.md)|Öffnet die Tabelle.|  
  
## Hinweise  
 Siehe [CCommand](../../data/oledb/ccommand-class.md) zu Informationen darüber, wie ein Befehl ausgeführt wird, in ein Rowset zugreifen.  
  
## Anforderungen  
 **Header:**  atldbcli.h  
  
## Siehe auch  
 [OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [IOpenRowset::OpenRowset](https://msdn.microsoft.com/en-us/library/ms716724.aspx)