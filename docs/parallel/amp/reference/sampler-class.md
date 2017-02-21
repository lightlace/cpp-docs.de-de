---
title: "Samplerklasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 9a6a9807-497d-402d-b092-8c4d86275b80
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Samplerklasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Die Samplerklasse aggregiert Informationen für die Samplingkonfiguration, die für das Textursampling verwendet werden sollen.  
  
## Syntax  
  
```  
class sampler;  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[sampler::sampler\-Konstruktor](../Topic/sampler::sampler%20Constructor.md)|Überladen.  Erstellt eine Samplerinstanz.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[sampler::get\_address\_mode\-Methode](../Topic/sampler::get_address_mode%20Method.md)|Gibt das `address_mode`\-Objekt zurück, das mit dem Samplerobjekt verknüpft ist.|  
|[sampler::get\_border\_color\-Methode](../Topic/sampler::get_border_color%20Method.md)|Gibt die Rahmenfarbe zurück, die dem Samplerobjekt verknüpft ist.|  
|[sampler::get\_filter\_mode\-Methode](../Topic/sampler::get_filter_mode%20Method.md)|Gibt das `filter_mode`\-Objekt zurück, das mit dem Samplerobjekt verknüpft ist.|  
  
### Öffentliche Operatoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[sampler::operator\= Operator](../Topic/sampler::operator=%20Operator.md)|Überladen.  Zuweisungsoperator.|  
  
### Öffentliche Datenmember  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[sampler::address\_mode\-Datenmember](../Topic/sampler::address_mode%20Data%20Member.md)|Ruft den Adressmodus des `sampler`\-Objekts ab.|  
|[sampler::border\_color\-Datenmember](../Topic/sampler::border_color%20Data%20Member.md)|Legt die Rahmenfarbe des `sampler`\-Objekts fest.|  
|[sampler::filter\_mode\-Datenmember](../Topic/sampler::filter_mode%20Data%20Member.md)|Ruft den Filtermodus des `sampler`\-Objekts ab.|  
  
## Vererbungshierarchie  
 `sampler`  
  
## Anforderungen  
 **Header:** amp\_graphics.h  
  
 **Namespace:** concurrency::graphics  
  
## Siehe auch  
 [Concurrency::graphics\-Namespace](../../../parallel/amp/reference/concurrency-graphics-namespace.md)