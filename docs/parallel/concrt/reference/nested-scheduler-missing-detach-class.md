---
title: "nested_scheduler_missing_detach-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::nested_scheduler_missing_detach"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "nested_scheduler_missing_detach-Klasse"
ms.assetid: 65d3f277-6d43-4160-97ef-caf8b26c1641
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# nested_scheduler_missing_detach-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn die Concurrency Runtime erkennt, dass versäumt wurde, die `CurrentScheduler::Detach`\-Methode für einen Kontext aufzurufen, der mittels der `Attach`\-Methode des `Scheduler`\-Objekts an einen zweiten Planer angefügt wurde.  
  
## Syntax  
  
```  
class nested_scheduler_missing_detach : public std::exception;  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[nested\_scheduler\_missing\_detach::nested\_scheduler\_missing\_detach\-Konstruktor](../Topic/nested_scheduler_missing_detach::nested_scheduler_missing_detach%20Constructor.md)|Überladen.  Erstellt ein `nested_scheduler_missing_detach`\-Objekt.|  
  
## Hinweise  
 Diese Ausnahme wird ausgelöst, wenn Sie ein Planerinnere nicht schachteln, indem Sie die `Attach`\-Methode eines `Scheduler`\-Objekts auf einen Kontext aufrufen, den bereits gehört oder einen anderen Planer angefügt.  Die Concurrency Runtime löst diese Ausnahme opportunistisch aus, wenn es das Szenario ermitteln kann, um die Problemsuche zu unterstützen.  Es ist nicht sichergestellt, dass diese Ausnahme bei jedem fehlenden Aufruf der `CurrentScheduler::Detach`\-Methode wirklich ausgelöst wird.  
  
## Vererbungshierarchie  
 `exception`  
  
 `nested_scheduler_missing_detach`  
  
## Anforderungen  
 **Header:** concrt.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Scheduler\-Klasse](../../../parallel/concrt/reference/scheduler-class.md)   
 [CurrentScheduler::Detach\-Methode](../Topic/CurrentScheduler::Detach%20Method.md)   
 [Scheduler::Attach\-Methode](../Topic/Scheduler::Attach%20Method.md)