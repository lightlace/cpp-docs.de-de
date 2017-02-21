---
title: "invalid_scheduler_policy_value-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::invalid_scheduler_policy_value"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "invalid_scheduler_policy_value-Klasse"
ms.assetid: 8c533e3f-2774-4192-8616-b2313b859bf7
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# invalid_scheduler_policy_value-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn der Richtlinienschlüssel eines `SchedulerPolicy`\-Objekts auf einen ungültigen Wert für diesen Schlüssel festgelegt wird.  
  
## Syntax  
  
```  
class invalid_scheduler_policy_value : public std::exception;  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[invalid\_scheduler\_policy\_value::invalid\_scheduler\_policy\_value\-Konstruktor](../Topic/invalid_scheduler_policy_value::invalid_scheduler_policy_value%20Constructor.md)|Überladen.  Erstellt ein `invalid_scheduler_policy_value`\-Objekt.|  
  
## Vererbungshierarchie  
 `exception`  
  
 `invalid_scheduler_policy_value`  
  
## Anforderungen  
 **Header:** concrt.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [SchedulerPolicy\-Klasse](../../../parallel/concrt/reference/schedulerpolicy-class.md)   
 [PolicyElementKey\-Enumeration](../Topic/PolicyElementKey%20Enumeration.md)   
 [SchedulerPolicy::SetPolicyValue\-Methode](../Topic/SchedulerPolicy::SetPolicyValue%20Method.md)   
 [SchedulerPolicy::SetConcurrencyLimits\-Methode](../Topic/SchedulerPolicy::SetConcurrencyLimits%20Method.md)