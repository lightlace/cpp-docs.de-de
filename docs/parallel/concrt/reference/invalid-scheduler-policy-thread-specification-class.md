---
title: "invalid_scheduler_policy_thread_specification-Klasse"
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
  - "concrt/concurrency::invalid_scheduler_policy_thread_specification"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "invalid_scheduler_policy_thread_specification-Klasse"
ms.assetid: 2d0fafb2-18f8-4284-8040-3db640d33303
caps.latest.revision: 19
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# invalid_scheduler_policy_thread_specification-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse beschreibt eine Ausnahme, die bei dem Versuch ausgelöst wird, die Parallelitätsgrenzen eines `SchedulerPolicy`\-Objekts so festzulegen, dass der Wert des `MinConcurrency`\-Schlüssels kleiner ist, als der Wert des `MaxConcurrency`\-Schlüssels.  
  
## Syntax  
  
```  
class invalid_scheduler_policy_thread_specification : public std::exception;  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[invalid\_scheduler\_policy\_thread\_specification::invalid\_scheduler\_policy\_thread\_specification\-Konstruktor](../Topic/invalid_scheduler_policy_thread_specification::invalid_scheduler_policy_thread_specification%20Constructor.md)|Überladen.  Erstellt ein `invalid_scheduler_policy_value`\-Objekt.|  
  
## Vererbungshierarchie  
 `exception`  
  
 `invalid_scheduler_policy_thread_specification`  
  
## Anforderungen  
 **Header:** concrt.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [SchedulerPolicy\-Klasse](../../../parallel/concrt/reference/schedulerpolicy-class.md)   
 [PolicyElementKey\-Enumeration](../Topic/PolicyElementKey%20Enumeration.md)   
 [SchedulerPolicy::SetConcurrencyLimits\-Methode](../Topic/SchedulerPolicy::SetConcurrencyLimits%20Method.md)