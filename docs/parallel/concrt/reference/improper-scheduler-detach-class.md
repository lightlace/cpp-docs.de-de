---
title: "improper_scheduler_detach-Klasse"
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
  - "concrt/concurrency::improper_scheduler_detach"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "improper_scheduler_detach-Klasse"
ms.assetid: 30132102-c900-4951-a470-b63b4e3aa2d2
caps.latest.revision: 19
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# improper_scheduler_detach-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn die `CurrentScheduler::Detach`\-Methode für einen Kontext aufgerufen wird, der nicht mittels der `Attach`\-Methode eines `Scheduler`\-Objekts an einen Planer angefügt wurde.  
  
## Syntax  
  
```  
class improper_scheduler_detach : public std::exception;  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[improper\_scheduler\_detach::improper\_scheduler\_detach\-Konstruktor](../Topic/improper_scheduler_detach::improper_scheduler_detach%20Constructor.md)|Überladen.  Erstellt ein `improper_scheduler_detach`\-Objekt.|  
  
## Vererbungshierarchie  
 `exception`  
  
 `improper_scheduler_detach`  
  
## Anforderungen  
 **Header:** concrt.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Scheduler\-Klasse](../../../parallel/concrt/reference/scheduler-class.md)   
 [CurrentScheduler::Detach\-Methode](../Topic/CurrentScheduler::Detach%20Method.md)   
 [Scheduler::Attach\-Methode](../Topic/Scheduler::Attach%20Method.md)