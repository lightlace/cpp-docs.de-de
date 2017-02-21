---
title: "network_link_registry-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "agents/concurrency::network_link_registry"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "network_link_registry-Klasse"
ms.assetid: 3e7b4097-09f1-4252-964e-b15b8f7f7fc6
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# network_link_registry-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Die abstrakte `network_link_registry`\-Basisklasse verwaltet die Verknüpfung zwischen Quell\- und Zielblöcken.  
  
## Syntax  
  
```  
template<  
   class _Block  
>  
class network_link_registry;  
```  
  
#### Parameter  
 `_Block`  
 Der Blockdatentyp, der in `network_link_registry` gespeichert wird.  
  
## Member  
  
### Öffentliche Typedefs  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|`const_pointer`|Ein Typ, der einen Zeiger auf ein `const`\-Element in einem `network_link_registry`\-Objekt bereitstellt.|  
|`const_reference`|Ein Typ, der einen Verweis auf ein `const`\-Element bereitstellt, das in einem `network_link_registry`\-Objekt zum Lesen gespeichert ist und const\-Operationen durchführt.|  
|`iterator`|Ein Typ, der einen Iterator bereitstellt, der ein beliebiges Element in einem `network_link_registry`\-Objekt lesen und bearbeiten kann.|  
|`type`|Ein Typ, der den im `network_link_registry`\-Objekt gespeicherten Blocktyp darstellt.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[network\_link\_registry::add\-Methode](../Topic/network_link_registry::add%20Method.md)|Fügt beim Überschreiben in einer abgeleiteten Klasse einen Link auf das `network_link_registry`\-Objekt hinzu.|  
|[network\_link\_registry::begin\-Methode](../Topic/network_link_registry::begin%20Method.md)|Gibt beim Überschreiben in einer abgeleiteten Klasse einen Iterator an das erste Element im `network_link_registry`\-Objekt zurück.|  
|[network\_link\_registry::contains\-Methode](../Topic/network_link_registry::contains%20Method.md)|Durchsucht beim Überschreiben in einer abgeleiteten Klasse das `network_link_registry`\-Objekt nach einen angegebenen Block.|  
|[network\_link\_registry::count\-Methode](../Topic/network_link_registry::count%20Method.md)|Gibt beim Überschreiben in einer abgeleiteten Klasse die Anzahl der Elemente im `network_link_registry`\-Objekt ab.|  
|[network\_link\_registry::remove\-Methode](../Topic/network_link_registry::remove%20Method.md)|Entfernt beim Überschreiben in einer abgeleiteten Klasse einen angegebenen Block aus dem `network_link_registry`\-Objekt.|  
  
## Hinweise  
 Der `network link registry` ist für gleichzeitigen Zugriff nicht sicher.  
  
## Vererbungshierarchie  
 `network_link_registry`  
  
## Anforderungen  
 **Header:** agents.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [single\_link\_registry\-Klasse](../../../parallel/concrt/reference/single-link-registry-class.md)   
 [multi\_link\_registry\-Klasse](../../../parallel/concrt/reference/multi-link-registry-class.md)