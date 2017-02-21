---
title: "default_scheduler_exists-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::default_scheduler_exists"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "default_scheduler_exists-Klasse"
ms.assetid: f6e575e2-4e0f-455a-9e06-54f462ce0c1c
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# default_scheduler_exists-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, sobald die `Scheduler::SetDefaultSchedulerPolicy`\-Methode aufgerufen wird, sofern ein Standardplaner bereits innerhalb des Prozesses vorhanden ist.  
  
## Syntax  
  
```  
class default_scheduler_exists : public std::exception;  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[default\_scheduler\_exists::default\_scheduler\_exists\-Konstruktor](../Topic/default_scheduler_exists::default_scheduler_exists%20Constructor.md)|Überladen.  Erstellt ein `default_scheduler_exists`\-Objekt.|  
  
## Vererbungshierarchie  
 `exception`  
  
 `default_scheduler_exists`  
  
## Anforderungen  
 **Header:** concrt.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Scheduler::SetDefaultSchedulerPolicy\-Methode](../Topic/Scheduler::SetDefaultSchedulerPolicy%20Method.md)