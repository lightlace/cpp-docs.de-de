---
title: "condition_variable_any-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "condition_variable/std::condition_variable_any"
dev_langs: 
  - "C++"
ms.assetid: d8afe5db-1561-4ec2-8e85-21ea03ee4321
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# condition_variable_any-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Verwenden Sie die `condition_variable_any`\-Klasse, um ein Ereignis mit jeglichem `mutex`\-Typ zu erwarten.  
  
## Syntax  
  
```  
class condition_variable_any;  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[condition\_variable\_any::condition\_variable\_any\-Konstruktor](../Topic/condition_variable_any::condition_variable_any%20Constructor.md)|Erstellt ein `condition_variable_any`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[condition\_variable\_any::notify\_all\-Methode](../Topic/condition_variable_any::notify_all%20Method.md)|Hebt die Blockierung aller Threads auf, die das `condition_variable_any`\-Objekt erwarten.|  
|[condition\_variable\_any::notify\_one\-Methode](../Topic/condition_variable_any::notify_one%20Method.md)|Hebt die Blockierung von einem der Threads, die auf das `condition_variable_any`\-Objekt warten, auf.|  
|[condition\_variable\_any::wait\-Methode](../Topic/condition_variable_any::wait%20Method.md)|Blockiert einen Thread.|  
|[condition\_variable\_any::wait\_for\-Methode](../Topic/condition_variable_any::wait_for%20Method.md)|Blockiert einen Thread und legt ein Zeitintervall fest, nachdem die Blockierung des Threads aufgehoben wird.|  
|[condition\_variable\_any::wait\_until\-Methode](../Topic/condition_variable_any::wait_until%20Method.md)|Blockiert einen Thread und legt einen maximalen Zeitpunkt fest, an dem die Blockierung des Threads aufgehoben wird.|  
  
## Anforderungen  
 **Header:** condition\_variable  
  
 **Namespace:** std  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [\<condition\_variable\>](../standard-library/condition-variable.md)