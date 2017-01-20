---
title: "multi_link_registry-Klasse"
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
  - "agents/concurrency::multi_link_registry"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "multi_link_registry-Klasse"
ms.assetid: b2aa73a8-e8a6-4255-b117-d07530c328b2
caps.latest.revision: 19
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# multi_link_registry-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Das `multi_link_registry`\-Objekt ist eine `network_link_registry`, die mehrere Quellblöcke oder mehrere Zielblöcke verwaltet.  
  
## Syntax  
  
```  
template<  
   class _Block  
>  
class multi_link_registry : public network_link_registry<_Block>;  
```  
  
#### Parameter  
 `_Block`  
 Der Blockdatentyp, der im `multi_link_registry`\-Objekt gespeichert wird.  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[multi\_link\_registry::multi\_link\_registry\-Konstruktor](../Topic/multi_link_registry::multi_link_registry%20Constructor.md)|Erstellt ein `multi_link_registry`\-Objekt.|  
|[multi\_link\_registry::~multi\_link\_registry\-Destruktor](../Topic/multi_link_registry::~multi_link_registry%20Destructor.md)|Zerstört das `multi_link_registry`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[multi\_link\_registry::add\-Methode](../Topic/multi_link_registry::add%20Method.md)|Fügt dem `multi_link_registry`\-Objekt einen Link hinzu. \(Überschreibt [network\_link\_registry::add](../Topic/network_link_registry::add%20Method.md).\)|  
|[multi\_link\_registry::begin\-Methode](../Topic/multi_link_registry::begin%20Method.md)|Gibt einen Iterator auf das erste Element im `multi_link_registry`\-Objekt zurück. \(Überschreibt [network\_link\_registry::begin](../Topic/network_link_registry::begin%20Method.md).\)|  
|[multi\_link\_registry::contains\-Methode](../Topic/multi_link_registry::contains%20Method.md)|Sucht im `multi_link_registry`\-Objekt nach dem angegebenen Block. \(Überschreibt [network\_link\_registry::contains](../Topic/network_link_registry::contains%20Method.md).\)|  
|[multi\_link\_registry::count\-Methode](../Topic/multi_link_registry::count%20Method.md)|Zählt die Anzahl der Elemente im `multi_link_registry`\-Objekt. \(Überschreibt [network\_link\_registry::count](../Topic/network_link_registry::count%20Method.md).\)|  
|[multi\_link\_registry::remove\-Methode](../Topic/multi_link_registry::remove%20Method.md)|Entfernt ein Link aus dem `multi_link_registry`\-Objekt. \(Überschreibt [network\_link\_registry::remove](../Topic/network_link_registry::remove%20Method.md).\)|  
|[multi\_link\_registry::set\_bound\-Methode](../Topic/multi_link_registry::set_bound%20Method.md)|Legt eine Obergrenze für die Anzahl der Links fest, die das `multi_link_registry`\-Objekt enthalten kann.|  
  
## Vererbungshierarchie  
 [network\_link\_registry](../../../parallel/concrt/reference/network-link-registry-class.md)  
  
 `multi_link_registry`  
  
## Anforderungen  
 **Header:** agents.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [single\_link\_registry\-Klasse](../../../parallel/concrt/reference/single-link-registry-class.md)