---
title: "scheduler_not_attached-Klasse"
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
  - "concrt/concurrency::scheduler_not_attached"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "scheduler_not_attached-Klasse"
ms.assetid: 26001970-b400-463b-be3d-8623359c399a
caps.latest.revision: 19
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# scheduler_not_attached-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse beschreibt eine Ausnahme, die bei Ausführen eines Vorgangs ausgelöst wird, der erfordert, dass ein Planer an den aktuellen Kontext angefügt wird, und einer nicht.  
  
## Syntax  
  
```  
class scheduler_not_attached : public std::exception;  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[scheduler\_not\_attached::scheduler\_not\_attached\-Konstruktor](../Topic/scheduler_not_attached::scheduler_not_attached%20Constructor.md)|Überladen.  Erstellt ein `scheduler_not_attached`\-Objekt.|  
  
## Vererbungshierarchie  
 `exception`  
  
 `scheduler_not_attached`  
  
## Anforderungen  
 **Header:** concrt.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Scheduler\-Klasse](../../../parallel/concrt/reference/scheduler-class.md)   
 [Scheduler::Attach\-Methode](../Topic/Scheduler::Attach%20Method.md)