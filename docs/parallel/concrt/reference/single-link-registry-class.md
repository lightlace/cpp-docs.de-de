---
title: "single_link_registry-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "agents/concurrency::single_link_registry"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "single_link_registry-Klasse"
ms.assetid: 09540a4e-c34e-4ff9-af49-21b8612b6ab3
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# single_link_registry-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Das `single_link_registry`\-Objekt ist eine `network_link_registry`, die nur eine einzige Quelle oder einen einzigen Zielblock verwaltet.  
  
## Syntax  
  
```  
template<  
   class _Block  
>  
class single_link_registry : public network_link_registry<_Block>;  
```  
  
#### Parameter  
 `_Block`  
 Der Blockdatentyp, der im `single_link_registry`\-Objekt gespeichert wird.  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[single\_link\_registry::single\_link\_registry\-Konstruktor](../Topic/single_link_registry::single_link_registry%20Constructor.md)|Erstellt ein `single_link_registry`\-Objekt.|  
|[single\_link\_registry::~single\_link\_registry\-Destruktor](../Topic/single_link_registry::~single_link_registry%20Destructor.md)|Zerstört das `single_link_registry`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[single\_link\_registry::add\-Methode](../Topic/single_link_registry::add%20Method.md)|Fügt dem `single_link_registry`\-Objekt einen Link hinzu. \(Überschreibt [network\_link\_registry::add](../Topic/network_link_registry::add%20Method.md).\)|  
|[single\_link\_registry::begin\-Methode](../Topic/single_link_registry::begin%20Method.md)|Gibt einen Iterator auf das erste Element im `single_link_registry`\-Objekt zurück. \(Überschreibt [network\_link\_registry::begin](../Topic/network_link_registry::begin%20Method.md).\)|  
|[single\_link\_registry::contains\-Methode](../Topic/single_link_registry::contains%20Method.md)|Sucht im `single_link_registry`\-Objekt nach dem angegebenen Block. \(Überschreibt [network\_link\_registry::contains](../Topic/network_link_registry::contains%20Method.md).\)|  
|[single\_link\_registry::count\-Methode](../Topic/single_link_registry::count%20Method.md)|Zählt die Anzahl der Elemente im `single_link_registry`\-Objekt. \(Überschreibt [network\_link\_registry::count](../Topic/network_link_registry::count%20Method.md).\)|  
|[single\_link\_registry::remove\-Methode](../Topic/single_link_registry::remove%20Method.md)|Entfernt ein Link aus dem `single_link_registry`\-Objekt. \(Überschreibt [network\_link\_registry::remove](../Topic/network_link_registry::remove%20Method.md).\)|  
  
## Vererbungshierarchie  
 [network\_link\_registry](../../../parallel/concrt/reference/network-link-registry-class.md)  
  
 `single_link_registry`  
  
## Anforderungen  
 **Header:** agents.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [multi\_link\_registry\-Klasse](../../../parallel/concrt/reference/multi-link-registry-class.md)