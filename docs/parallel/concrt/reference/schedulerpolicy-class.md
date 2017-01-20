---
title: "SchedulerPolicy-Klasse"
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
  - "concrt/concurrency::SchedulerPolicy"
  - "concrtrm/concurrency::SchedulerPolicy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SchedulerPolicy-Klasse"
ms.assetid: bcebf51a-65f8-45a3-809b-d1ff93527dc4
caps.latest.revision: 22
caps.handback.revision: "16"
ms.author: "mblome"
manager: "ghogen"
---
# SchedulerPolicy-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Die `SchedulerPolicy`\-Klasse enthält einen Satz von Schlüssel\-Wert\-Paaren. Einen für jedes Richtlinienelement, von dem das Verhalten einer Planerinstanz gesteuert wird.  
  
## Syntax  
  
```  
class SchedulerPolicy;  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[SchedulerPolicy::SchedulerPolicy\-Konstruktor](../Topic/SchedulerPolicy::SchedulerPolicy%20Constructor.md)|Überladen.  Erstellt eine neue Planerrichtlinie und füllt sie mit Werten für [Richtlinienschlüssel](../Topic/PolicyElementKey%20Enumeration.md) auf, die von Concurrency Runtime\-Planern und dem Ressourcen\-Manager unterstützt wurden.|  
|[SchedulerPolicy::~SchedulerPolicy\-Destruktor](../Topic/SchedulerPolicy::~SchedulerPolicy%20Destructor.md)|Zerstört eine Planerrichtlinie.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[SchedulerPolicy::GetPolicyValue\-Methode](../Topic/SchedulerPolicy::GetPolicyValue%20Method.md)|Ruft den Wert des als `_Key`\-Parameter angegebenen Richtlinienschlüssels ab.|  
|[SchedulerPolicy::SetConcurrencyLimits\-Methode](../Topic/SchedulerPolicy::SetConcurrencyLimits%20Method.md)|Legt gleichzeitig die `MinConcurrency`\-Richtlinie und die `MaxConcurrency`\-Richtlinie des `SchedulerPolicy`\-Objekts fest.|  
|[SchedulerPolicy::SetPolicyValue\-Methode](../Topic/SchedulerPolicy::SetPolicyValue%20Method.md)|Legt den Wert des Richtlinienschlüssels fest, der als `_Key`\-Parameter angegeben wurde, und gibt den alten Wert zurück.|  
  
### Öffentliche Operatoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[SchedulerPolicy::operator\=\-Operator](../Topic/SchedulerPolicy::operator=%20Operator.md)|Weist die Planerrichtlinie von einer anderen Planerrichtlinie zu.|  
  
## Hinweise  
 Weitere Informationen zu den Richtlinien, die mithilfe der `SchedulerPolicy`\-Klasse gesteuert werden können, finden Sie unter [PolicyElementKey\-Enumeration](../Topic/PolicyElementKey%20Enumeration.md).  
  
## Vererbungshierarchie  
 `SchedulerPolicy`  
  
## Anforderungen  
 **Header:** concrt.h, concrtrm.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [PolicyElementKey\-Enumeration](../Topic/PolicyElementKey%20Enumeration.md)   
 [CurrentScheduler\-Klasse](../../../parallel/concrt/reference/currentscheduler-class.md)   
 [Scheduler\-Klasse](../../../parallel/concrt/reference/scheduler-class.md)   
 [Taskplaner](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)