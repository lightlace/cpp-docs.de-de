---
title: "event-Klasse"
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
  - "concrt/concurrency::event"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "event-Klasse"
ms.assetid: fba35a53-6568-4bfa-9aaf-07c0928cf73d
caps.latest.revision: 22
caps.handback.revision: "15"
ms.author: "mblome"
manager: "ghogen"
---
# event-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Ein Ereignis für manuelles Zurücksetzen, das explizit die Concurrency Runtime beachtet.  
  
## Syntax  
  
```  
class event;  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[event::~event\-Destruktor](../Topic/event::~event%20Destructor.md)|Zerstört ein Ereignis.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[event::reset\-Methode](../Topic/event::reset%20Method.md)|Setzt das Ereignis auf einen nicht signalisierten Zustand zurück.|  
|[event::set\-Methode](../Topic/event::set%20Method.md)|Signalisiert das Ereignis.|  
|[event::wait\-Methode](../Topic/event::wait%20Method.md)|Wartet, bis das Ereignis signalisiert wird.|  
|[event::wait\_for\_multiple\-Methode](../Topic/event::wait_for_multiple%20Method.md)|Wartet, bis mehrere Ereignisse signalisiert werden.|  
  
### Öffentliche Konstanten  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[event::timeout\_infinite\-Konstante](../Topic/event::timeout_infinite%20Constant.md)|Ein Wert, der angibt, dass ein Wartevorgang nie durch einen Timeout beendet werden sollte.|  
  
## Hinweise  
 Weitere Informationen finden Sie unter [Synchronisierungsdatenstrukturen](../../../parallel/concrt/synchronization-data-structures.md).  
  
## Vererbungshierarchie  
 `event`  
  
## Anforderungen  
 **Header:** concrt.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)