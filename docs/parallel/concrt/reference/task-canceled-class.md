---
title: "task_canceled-Klasse"
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
  - "concrt/concurrency::task_canceled"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "task_canceled-Klasse"
ms.assetid: c3f0b234-2cc1-435f-a48e-995f45b190be
caps.latest.revision: 11
caps.handback.revision: "4"
ms.author: "mblome"
manager: "ghogen"
---
# task_canceled-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse beschreibt eine Ausnahme, die von den PPL\-Aufgaben ausgelöst wird, um das Abbrechen der aktuellen Aufgabe zu erzwingen.  Sie wird auch von der `get()`\-Methode auf [task](../Topic/Task%20Class%20-%20Internal%20Members.md) für eine abgebrochene Aufgabe ausgelöst.  
  
## Syntax  
  
```  
class task_canceled : public std::exception;  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[task\_canceled::task\_canceled\-Konstruktor](../Topic/task_canceled::task_canceled%20Constructor.md)|Überladen.  Erstellt ein `task_canceled`\-Objekt.|  
  
## Vererbungshierarchie  
 `exception`  
  
 `task_canceled`  
  
## Anforderungen  
 **Header:** concrt.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [task::get\-Methode](../Topic/task::get%20Method.md)   
 [cancel\_current\_task\-Funktion](../Topic/cancel_current_task%20Function.md)