---
title: "CArrayRowset-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.CArrayRowset<TAccessor>"
  - "ATL.CArrayRowset"
  - "CArrayRowset"
  - "ATL::CArrayRowset"
  - "ATL::CArrayRowset<TAccessor>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CArrayRowset-Klasse"
ms.assetid: 511427e1-73ca-4fd8-9ba1-ae9463557cb6
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# CArrayRowset-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Greift auf Elemente eines Rowsets mithilfe von Arraysyntax zu.  
  
## Syntax  
  
```  
template < class TAccessor >  
class CArrayRowset :   
   public CVirtualBuffer <TAccessor>,   
   protected CBulkRowset <TAccessor>  
```  
  
#### Parameter  
 `TAccessor`  
 Der Typ der Accessorklasse, dass Sie das Rowset verwenden soll.  
  
## Member  
  
### Methoden  
  
|||  
|-|-|  
|[CArrayRowset](../../data/oledb/carrayrowset-carrayrowset.md)|Konstruktor.|  
|[Momentaufnahme](../../data/oledb/carrayrowset-snapshot.md)|Liest das gesamte Rowset in den Arbeitsspeicher.|  
  
### Operatoren  
  
|||  
|-|-|  
|[Operator &#91;&#93;](../../data/oledb/carrayrowset-operator.md)|Greift auf ein Element des Rowsets zu.|  
  
### Datenmember  
  
|||  
|-|-|  
|[CArrayRowset::m\_nRowsRead](../../data/oledb/carrayrowset-m-nrowsread.md)|Die Anzahl von Zeilen bereits gelesen.|  
  
## Anforderungen  
 **Header:**  atldbcli.h  
  
## Siehe auch  
 [OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB\-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CRowset\-Klasse](../../data/oledb/crowset-class.md)