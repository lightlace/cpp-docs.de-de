---
title: "ITopologyNode-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrtrm/concurrency::ITopologyNode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ITopologyNode-Struktur"
ms.assetid: 92e7e032-04f6-4c7c-be36-8f9a35fc4734
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# ITopologyNode-Struktur
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Eine Schnittstelle für einen vom Ressourcen\-Manager definierten Topologieknoten.  Ein Knoten enthält mindestens eine Ausführungsressource.  
  
## Syntax  
  
```  
struct ITopologyNode;  
```  
  
## Member  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[ITopologyNode::GetExecutionResourceCount\-Methode](../Topic/ITopologyNode::GetExecutionResourceCount%20Method.md)|Gibt die Anzahl der Ausführungsressourcen zurück, die zusammen gruppiert werden unter diesem Knoten.|  
|[ITopologyNode::GetFirstExecutionResource\-Methode](../Topic/ITopologyNode::GetFirstExecutionResource%20Method.md)|Gibt die ersten Ausführungsressource zurück, die unter diesem Knoten in der Enumerationsreihenfolge gruppiert wird.|  
|[ITopologyNode::GetId\-Methode](../Topic/ITopologyNode::GetId%20Method.md)|Gibt dem eindeutigen Bezeichner des Ressourcen\-Managers für diesen Knoten zurück.|  
|[ITopologyNode::GetNext\-Methode](../Topic/ITopologyNode::GetNext%20Method.md)|Gibt eine Schnittstelle dem folgenden Topologieknoten in der Enumerationsreihenfolge zurück.|  
|[ITopologyNode::GetNumaNode\-Methode](../Topic/ITopologyNode::GetNumaNode%20Method.md)|Gibt die von Windows zugewiesene NUMA\-Knotenzahl zurück, zu der dieser Ressource\-Manager\-Knoten gehört.|  
  
## Hinweise  
 Diese Schnittstelle wird in der Regel verwendet, um die Topologie des Systems zu durchlaufen, wie vom Ressourcen\-Manager beachtet.  
  
## Vererbungshierarchie  
 `ITopologyNode`  
  
## Anforderungen  
 **Header:** concrtrm.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)