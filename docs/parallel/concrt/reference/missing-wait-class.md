---
title: "missing_wait-Klasse"
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
  - "concrt/concurrency::missing_wait"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "missing_wait-Klasse"
ms.assetid: ff981875-bd43-47e3-806f-b03c9f418b18
caps.latest.revision: 19
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# missing_wait-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn es Aufgaben gibt, die noch für ein `task_group`\-Objekt oder `structured_task_group`\-Objekt geplant sind, während der Destruktor des Objekts ausgeführt wird.  Diese Ausnahme wird nie ausgelöst, wenn der Destruktor aufgrund einer Stapelentladung als Ergebnis einer Ausnahme erreicht wird.  
  
## Syntax  
  
```  
class missing_wait : public std::exception;  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[missing\_wait::missing\_wait\-Konstruktor](../Topic/missing_wait::missing_wait%20Constructor.md)|Überladen.  Erstellt ein `missing_wait`\-Objekt.|  
  
## Hinweise  
 Abwesender Ausnahmefluss. Sie sind für das Aufrufen der `wait`\-Methode oder der `run_and_wait`\-Methode eines `task_group`\-Objekts oder eines `structured_task_group`\-Objekts zuständig, bevor eine Zerstörung des Objekts zugelassen wird.  Die Laufzeit löst diese Ausnahme aus, um anzugeben, dass Sie vergessen haben, die `wait`\-Methode oder die `run_and_wait`\-Methode aufzurufen.  
  
## Vererbungshierarchie  
 `exception`  
  
 `missing_wait`  
  
## Anforderungen  
 **Header:** concrt.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [task\_group\-Klasse](../Topic/task_group%20Class.md)   
 [task\_group::wait\-Methode](../Topic/task_group::wait%20Method.md)   
 [task\_group::run\_and\_wait\-Methode](../Topic/task_group::run_and_wait%20Method.md)   
 [structured\_task\_group\-Klasse](../../../parallel/concrt/reference/structured-task-group-class.md)   
 [structured\_task\_group::wait\-Methode](../Topic/structured_task_group::wait%20Method.md)   
 [structured\_task\_group::run\_and\_wait\-Methode](../Topic/structured_task_group::run_and_wait%20Method.md)