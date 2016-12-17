---
title: "invalid_multiple_scheduling-Klasse"
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
  - "concrt/concurrency::invalid_multiple_scheduling"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "invalid_multiple_scheduling-Klasse"
ms.assetid: e9a47cb7-a778-4df7-92b0-3752119fd4c7
caps.latest.revision: 19
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# invalid_multiple_scheduling-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn ein `task_handle`\-Objekt mehrmals mittels der `run`\-Methode eines `task_group`\-Objekts oder `structured_task_group`\-Objekts ohne einen zwischenzeitlichen Aufruf der `wait`\-Methode oder `run_and_wait`\-Methode geplant wird.  
  
## Syntax  
  
```  
class invalid_multiple_scheduling : public std::exception;  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[invalid\_multiple\_scheduling::invalid\_multiple\_scheduling\-Konstruktor](../Topic/invalid_multiple_scheduling::invalid_multiple_scheduling%20Constructor.md)|Überladen.  Erstellt ein `invalid_multiple_scheduling`\-Objekt.|  
  
## Vererbungshierarchie  
 `exception`  
  
 `invalid_multiple_scheduling`  
  
## Anforderungen  
 **Header:** concrt.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [task\_handle\-Klasse](../../../parallel/concrt/reference/task-handle-class.md)   
 [task\_group\-Klasse](../Topic/task_group%20Class.md)   
 [task\_group::run\-Methode](../Topic/task_group::run%20Method.md)   
 [task\_group::wait\-Methode](../Topic/task_group::wait%20Method.md)   
 [task\_group::run\_and\_wait\-Methode](../Topic/task_group::run_and_wait%20Method.md)   
 [structured\_task\_group\-Klasse](../../../parallel/concrt/reference/structured-task-group-class.md)   
 [structured\_task\_group::run\-Methode](../Topic/structured_task_group::run%20Method.md)   
 [structured\_task\_group::wait\-Methode](../Topic/structured_task_group::wait%20Method.md)   
 [structured\_task\_group::run\_and\_wait\-Methode](../Topic/structured_task_group::run_and_wait%20Method.md)