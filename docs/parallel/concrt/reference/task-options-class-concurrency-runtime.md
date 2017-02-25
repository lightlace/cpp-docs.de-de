---
title: "task-options-Klasse (Concurrency Runtime) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ppltasks/concurrency::task_options"
dev_langs: 
  - "C++"
ms.assetid: f93d146b-70f7-46ec-8c2f-c33b8bb0af69
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# task-options-Klasse (Concurrency Runtime)
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Stellt die zulässigen Optionen zum Erstellen einer Aufgabe dar  
  
## Syntax  
  
```  
class task_options;  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[task\_options::task\_options\-Konstruktor \(Concurrency Runtime\)](../Topic/task_options::task_options%20Constructor%20\(Concurrency%20Runtime\).md)|Überladen.  Standardliste von Aufgabenerstellungsoptionen|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[task\_options::get\_cancellation\_token\-Methode \(Concurrency Runtime\)](../Topic/task_options::get_cancellation_token%20Method%20\(Concurrency%20Runtime\).md)|Gibt das Abbruchtoken zurück.|  
|[task\_options::get\_continuation\_context\-Methode \(Concurrency Runtime\)](../Topic/task_options::get_continuation_context%20Method%20\(Concurrency%20Runtime\).md)|Gibt den Fortsetzungskontext zurück.|  
|[task\_options::get\_scheduler\-Methode \(Concurrency Runtime\)](../Topic/task_options::get_scheduler%20Method%20\(Concurrency%20Runtime\).md)|Gibt den Planer zurück.|  
|[task\_options::has\_cancellation\_token\-Methode \(Concurrency Runtime\)](../Topic/task_options::has_cancellation_token%20Method%20\(Concurrency%20Runtime\).md)|Gibt an, ob ein Abbruchtoken vom Benutzer angegeben wurde.|  
|[task\_options::has\_scheduler\-Methode \(Concurrency Runtime\)](../Topic/task_options::has_scheduler%20Method%20\(Concurrency%20Runtime\).md)|Gibt an, ob ein Planer vom Benutzer angegeben wurde.|  
|[task\_options::set\_cancellation\_token\-Methode \(Concurrency Runtime\)](../Topic/task_options::set_cancellation_token%20Method%20\(Concurrency%20Runtime\).md)|Legt das angegebene Token in den Optionen fest.|  
|[task\_options::set\_continuation\_context\-Methode \(Concurrency Runtime\)](../Topic/task_options::set_continuation_context%20Method%20\(Concurrency%20Runtime\).md)|Legt den angegebenen Fortsetzungskontext in den Optionen fest.|  
  
## Vererbungshierarchie  
 `task_options`  
  
## Anforderungen  
 **Header:** ppltasks.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)