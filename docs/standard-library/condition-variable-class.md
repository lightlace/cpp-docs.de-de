---
title: "condition_variable-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "condition_variable/std::condition_variable"
dev_langs: 
  - "C++"
ms.assetid: 80b1295c-b73d-4d46-b664-6e183f2eec1b
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# condition_variable-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Verwenden Sie die `condition_variable`\-Klasse, um ein Ereignis zu erwarten, wenn Sie über ein `mutex` des Typs `unique_lock<mutex>` verfügen.  Objekte dieses Typs bieten möglicherweise bessere Leistung, als Objekte des Typs [condition\_variable\_any\<unique\_lock\<Mutex\>\>](../standard-library/condition-variable-any-class.md).  
  
## Syntax  
  
```  
class condition_variable;  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[condition\_variable::condition\_variable\-Konstruktor](../Topic/condition_variable::condition_variable%20Constructor.md)|Erstellt ein `condition_variable`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[condition\_variable::native\_handle\-Methode](../Topic/condition_variable::native_handle%20Method.md)|Gibt den implementierungsspezifischen Typ zurück, der das Handle "condition\_variable" darstellt.|  
|[condition\_variable::notify\_all\-Methode](../Topic/condition_variable::notify_all%20Method.md)|Hebt die Blockierung aller Threads auf, die das `condition_variable`\-Objekt erwarten.|  
|[condition\_variable::notify\_one\-Methode](../Topic/condition_variable::notify_one%20Method.md)|Hebt die Blockierung von einem der Threads, die auf das `condition_variable`\-Objekt warten, auf.|  
|[condition\_variable::wait\-Methode](../Topic/condition_variable::wait%20Method.md)|Blockiert einen Thread.|  
|[condition\_variable::wait\_for\-Methode](../Topic/condition_variable::wait_for%20Method.md)|Blockiert einen Thread und legt ein Zeitintervall fest, nachdem die Blockierung des Threads aufgehoben wird.|  
|[condition\_variable::wait\_until\-Methode](../Topic/condition_variable::wait_until%20Method.md)|Blockiert einen Thread und legt einen maximalen Zeitpunkt fest, an dem die Blockierung des Threads aufgehoben wird.|  
  
## Anforderungen  
 **Header:** condition\_variable  
  
 **Namespace:** std  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [\<condition\_variable\>](../standard-library/condition-variable.md)