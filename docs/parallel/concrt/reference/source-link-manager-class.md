---
title: "source_link_manager-Klasse"
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
  - "agents/concurrency::source_link_manager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "source_link_manager-Klasse"
ms.assetid: 287487cf-e0fe-4c35-aa3c-24f081d1ddae
caps.latest.revision: 17
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# source_link_manager-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Das `source_link_manager`\-Objekt verwaltet Meldungsblock\-Netzwerklinks zu `ISource`\-Blöcken.  
  
## Syntax  
  
```  
template<  
   class _LinkRegistry  
>  
class source_link_manager;  
```  
  
#### Parameter  
 `_LinkRegistry`  
 Die Netzwerklinkregistrierung.  
  
## Member  
  
### Öffentliche Typedefs  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|`const_pointer`|Ein Typ, der einen Zeiger auf ein `const`\-Element in einem `source_link_manager`\-Objekt bereitstellt.|  
|`const_reference`|Ein Typ, der einen Verweis auf ein `const`\-Element bereitstellt, das in einem `source_link_manager`\-Objekt zum Lesen gespeichert ist und const\-Operationen durchführt.|  
|`iterator`|Ein Typ, der einen Iterator bereitstellt, der ein beliebiges Element im `source_link_manager`\-Objekt lesen und bearbeiten kann.|  
|`type`|Der Typ der Linkregistrierung, der vom `source_link_manager`\-Objekt verwaltet wird.|  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[source\_link\_manager::source\_link\_manager\-Konstruktor](../Topic/source_link_manager::source_link_manager%20Constructor.md)|Erstellt ein `source_link_manager`\-Objekt.|  
|[source\_link\_manager::~source\_link\_manager\-Destruktor](../Topic/source_link_manager::~source_link_manager%20Destructor.md)|Zerstört das `source_link_manager`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[source\_link\_manager::add\-Methode](../Topic/source_link_manager::add%20Method.md)|Fügt dem `source_link_manager`\-Objekt einen Quelllink hinzu.|  
|[source\_link\_manager::begin\-Methode](../Topic/source_link_manager::begin%20Method.md)|Gibt einen Iterator auf das erste Element im `source_link_manager`\-Objekt zurück.|  
|[source\_link\_manager::contains\-Methode](../Topic/source_link_manager::contains%20Method.md)|Durchsucht `network_link_registry` in diesem `source_link_manager`\-Objekt nach einem angegebenen Block.|  
|[source\_link\_manager::count\-Methode](../Topic/source_link_manager::count%20Method.md)|Zählt die Anzahl der verknüpften Blocks im `source_link_manager`\-Objekt.|  
|[source\_link\_manager::reference\-Methode](../Topic/source_link_manager::reference%20Method.md)|Ruft einen Verweis auf das `source_link_manager`\-Objekt ab.|  
|[source\_link\_manager::register\_target\_block\-Methode](../Topic/source_link_manager::register_target_block%20Method.md)|Registriert den Zielblock, der dieses `source_link_manager`\-Objekt aufnimmt.|  
|[source\_link\_manager::release\-Methode](../Topic/source_link_manager::release%20Method.md)|Gibt den Verweis auf das `source_link_manager`\-Objekt frei.|  
|[source\_link\_manager::remove\-Methode](../Topic/source_link_manager::remove%20Method.md)|Entfernt ein Link aus dem `source_link_manager`\-Objekt.|  
|[source\_link\_manager::set\_bound\-Methode](../Topic/source_link_manager::set_bound%20Method.md)|Legt die maximale Anzahl von Quelllinks fest, die diesem `source_link_manager`\-Objekt hinzugefügt werden können.|  
  
## Hinweise  
 Derzeit werden die Quellblöcke als Verweis gezählt.  Dies ist ein Wrapper für ein `network_link_registry`\-Objekt, das gleichzeitigen Zugriff auf die Links zulässt und die Fähigkeit bereitstellt, durch Rückrufe auf die Links zu verweisen.  Meldungsblöcke \(`target_block`s oder `propagator_block`s\) sollten diese Klasse für ihre Quellenlinks verwenden.  
  
## Vererbungshierarchie  
 `source_link_manager`  
  
## Anforderungen  
 **Header:** agents.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [single\_link\_registry\-Klasse](../../../parallel/concrt/reference/single-link-registry-class.md)   
 [multi\_link\_registry\-Klasse](../../../parallel/concrt/reference/multi-link-registry-class.md)