---
title: "lock_guard-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "mutex/std::lock_guard"
dev_langs: 
  - "C++"
ms.assetid: 57121f0d-9c50-481c-b971-54e64df864e0
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# lock_guard-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Stellt eine Vorlage dar, die instanziiert werden kann, um ein Objekt zu erstellen, dessen Destruktor `mutex` entsperrt.  
  
## Syntax  
  
```  
template<class Mutex>  
class lock_guard;  
```  
  
## Hinweise  
 Das Vorlagenargument `Mutex` muss einen *Mutextyp* benennen.  
  
## Member  
  
### Öffentliche Typedefs  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|`lock_guard::mutex_type`|Synonym für das Vorlagenargument `Mutex`.|  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[lock\_guard::lock\_guard\-Konstruktor](../Topic/lock_guard::lock_guard%20Constructor.md)|Erstellt ein `lock_guard`\-Objekt.|  
|[lock\_guard::~lock\_guard\-Destruktor](../Topic/lock_guard::~lock_guard%20Destructor.md)|Entsperrt `mutex`, das an den Konstruktor übergeben wurde.|  
  
## Anforderungen  
 **Header:** mutex  
  
 **Namespace:** std  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex\>](../standard-library/mutex.md)