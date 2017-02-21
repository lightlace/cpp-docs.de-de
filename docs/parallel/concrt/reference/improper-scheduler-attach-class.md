---
title: "improper_scheduler_attach-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::improper_scheduler_attach"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "improper_scheduler_attach-Klasse"
ms.assetid: 5a76da0a-091b-4748-8f62-b3a28f674f9e
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# improper_scheduler_attach-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn die `Attach`\-Methode für ein `Scheduler`\-Objekt aufgerufen wird, das bereits an den aktuellen Kontext angefügt wurde.  
  
## Syntax  
  
```  
class improper_scheduler_attach : public std::exception;  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[improper\_scheduler\_attach::improper\_scheduler\_attach\-Konstruktor](../Topic/improper_scheduler_attach::improper_scheduler_attach%20Constructor.md)|Überladen.  Erstellt ein `improper_scheduler_attach`\-Objekt.|  
  
## Vererbungshierarchie  
 `exception`  
  
 `improper_scheduler_attach`  
  
## Anforderungen  
 **Header:** concrt.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Scheduler\-Klasse](../../../parallel/concrt/reference/scheduler-class.md)   
 [Scheduler::Attach\-Methode](../Topic/Scheduler::Attach%20Method.md)