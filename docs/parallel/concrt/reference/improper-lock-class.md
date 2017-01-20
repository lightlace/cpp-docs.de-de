---
title: "improper_lock-Klasse"
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
  - "concrt/concurrency::improper_lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "improper_lock-Klasse"
ms.assetid: 8f494942-7748-4a2a-8de2-23414bfe6346
caps.latest.revision: 19
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# improper_lock-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn eine Sperre nicht ordnungsgemäß abgerufen wird.  
  
## Syntax  
  
```  
class improper_lock : public std::exception;  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[improper\_lock::improper\_lock\-Konstruktor](../Topic/improper_lock::improper_lock%20Constructor.md)|Überladen.  Erstellt eine `improper_lock exception`.|  
  
## Hinweise  
 In der Regel wird diese Ausnahme ausgelöst, wenn versucht wird, rekursiv im gleichen Kontext eine nicht wiedereintretende Sperre abzurufen.  
  
## Vererbungshierarchie  
 `exception`  
  
 `improper_lock`  
  
## Anforderungen  
 **Header:** concrt.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [critical\_section\-Klasse](../../../parallel/concrt/reference/critical-section-class.md)   
 [reader\_writer\_lock\-Klasse](../../../parallel/concrt/reference/reader-writer-lock-class.md)