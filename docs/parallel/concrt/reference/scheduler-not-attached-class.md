---
title: "scheduler_not_attached-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::scheduler_not_attached"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "scheduler_not_attached-Klasse"
ms.assetid: 26001970-b400-463b-be3d-8623359c399a
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
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