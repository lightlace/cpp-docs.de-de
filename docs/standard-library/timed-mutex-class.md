---
title: "timed_mutex-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "mutex/std::timed_mutex"
dev_langs: 
  - "C++"
ms.assetid: cd198081-6f38-447a-9dba-e06dfbfafe59
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# timed_mutex-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Stellt einen *Mutextyp zeitgesteuerten* dar.  Objekte dieses Typs werden verwendet, um den gegenseitigen Ausschluss durch das Zeit\-eingeschränkte Blockieren innerhalb eines Programms zu erzwingen.  
  
## Syntax  
  
```  
class timed_mutex;  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[timed\_mutex::timed\_mutex\-Konstruktor](../Topic/timed_mutex::timed_mutex%20Constructor.md)|Erstellt ein `timed_mutex`\-Objekt, das nicht gesperrt ist.|  
|[timed\_mutex::~timed\_mutex\-Destruktor](../Topic/timed_mutex::~timed_mutex%20Destructor.md)|Gibt alle Ressourcen frei, die vom `timed_mutex`\-Objekt verwendet werden.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[timed\_mutex::lock\-Methode](../Topic/timed_mutex::lock%20Method.md)|Blockiert den aufrufenden Thread, bis der Thread in den Besitz von `mutex` gelangt.|  
|[timed\_mutex::try\_lock\-Methode](../Topic/timed_mutex::try_lock%20Method.md)|Versucht, ohne Blockierung in den Besitz von `mutex` zu gelangen.|  
|[timed\_mutex::try\_lock\_for\-Methode](../Topic/timed_mutex::try_lock_for%20Method.md)|Versucht, den Besitz `mutex` für ein angegebenes Zeitintervall zu erhalten.|  
|[timed\_mutex::try\_lock\_until\-Methode](../Topic/timed_mutex::try_lock_until%20Method.md)|Versucht, um `mutex` abzurufen bis eine festgelegte Zeit.|  
|[timed\_mutex::unlock\-Methode](../Topic/timed_mutex::unlock%20Method.md)|Gibt den Besitz von `mutex` frei.|  
  
## Anforderungen  
 **Header:** mutex  
  
 **Namespace:** std  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex\>](../standard-library/mutex.md)