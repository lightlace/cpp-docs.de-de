---
title: "improper_scheduler_reference-Klasse"
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
  - "concrt/concurrency::improper_scheduler_reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "improper_scheduler_reference-Klasse"
ms.assetid: 434a7512-7796-4255-92a7-f3bf71c6a7a7
caps.latest.revision: 19
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# improper_scheduler_reference-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn die `Reference`\-Methode für ein `Scheduler`\-Objekt aufgerufen wird, das aus einem Kontext heruntergefahren wird, der nicht Teil dieses Planers ist.  
  
## Syntax  
  
```  
class improper_scheduler_reference : public std::exception;  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[improper\_scheduler\_reference::improper\_scheduler\_reference\-Konstruktor](../Topic/improper_scheduler_reference::improper_scheduler_reference%20Constructor.md)|Überladen.  Erstellt ein `improper_scheduler_reference`\-Objekt.|  
  
## Vererbungshierarchie  
 `exception`  
  
 `improper_scheduler_reference`  
  
## Anforderungen  
 **Header:** concrt.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Scheduler\-Klasse](../../../parallel/concrt/reference/scheduler-class.md)   
 [Scheduler::Reference\-Methode](../Topic/Scheduler::Reference%20Method.md)