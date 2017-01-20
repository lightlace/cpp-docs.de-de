---
title: "ScheduleGroup-Klasse"
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
  - "concrt/concurrency::ScheduleGroup"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ScheduleGroup-Klasse"
ms.assetid: 86d380ff-f2e8-411c-b1a8-22bd3079824a
caps.latest.revision: 20
caps.handback.revision: "14"
ms.author: "mblome"
manager: "ghogen"
---
# ScheduleGroup-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Stellt die Abstraktion für eine Planungsgruppe dar.  In Planungsgruppen werden Sätze verwandter Arbeitsaufgaben organisiert, die von einer gemeinsamen Planung profitieren. Die kann entweder zeitlich durch das Ausführen einer anderen Aufgabe in der gleichen Gruppe vor dem Wechsel in eine andere Gruppe, oder räumlich durch das Ausführen mehrerer Elemente innerhalb der gleichen Gruppe auf dem gleichen NUMA\-Knoten oder physischem Socket geschehen.  
  
## Syntax  
  
```  
class ScheduleGroup;  
```  
  
## Member  
  
### Geschützte Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[ScheduleGroup::~ScheduleGroup\-Destruktor](../Topic/ScheduleGroup::~ScheduleGroup%20Destructor.md)||  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[ScheduleGroup::Id\-Methode](../Topic/ScheduleGroup::Id%20Method.md)|Gibt einen Bezeichner für die Planungsgruppe zurück, der innerhalb des Planers eindeutig ist, zu dem die Gruppe gehört.|  
|[ScheduleGroup::Reference\-Methode](../Topic/ScheduleGroup::Reference%20Method.md)|Inkrementiert den Verweiszähler dieser Planergruppe.|  
|[ScheduleGroup::Release\-Methode](../Topic/ScheduleGroup::Release%20Method.md)|Dekrementiert den Verweiszähler dieser Planergruppe.|  
|[ScheduleGroup::ScheduleTask\-Methode](../Topic/ScheduleGroup::ScheduleTask%20Method.md)|Plant eine einfache Aufgabe innerhalb der Planungsgruppe.|  
  
## Vererbungshierarchie  
 `ScheduleGroup`  
  
## Anforderungen  
 **Header:** concrt.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [CurrentScheduler\-Klasse](../../../parallel/concrt/reference/currentscheduler-class.md)   
 [Scheduler\-Klasse](../../../parallel/concrt/reference/scheduler-class.md)   
 [Taskplaner](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)