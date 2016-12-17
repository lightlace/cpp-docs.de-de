---
title: "recursive_timed_mutex-Klasse"
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
  - "mutex/std::recursive_timed_mutex"
dev_langs: 
  - "C++"
ms.assetid: 59cc2d5c-ed80-45f3-a0a8-05652a8ead7e
caps.latest.revision: 9
caps.handback.revision: "3"
ms.author: "corob"
manager: "ghogen"
---
# recursive_timed_mutex-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Stellt einen *Mutextyp zeitgesteuerten* dar.  Objekte dieses Typs werden verwendet, um den gegenseitigen Ausschluss zu erzwingen, indem das Zeit\-eingeschränkte Blockieren innerhalb eines Programms verwendet.  Anders als Objekte vom Typ [timed\_mutex](../standard-library/timed-mutex-class.md), besteht die Auswirkung des mehrmaligen Aufrufens von Sperrenmethoden für `recursive_timed_mutex`\-Objekte genau definiert.  
  
## Syntax  
  
```  
class recursive_timed_mutex;  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[recursive\_timed\_mutex::recursive\_timed\_mutex\-Konstruktor](../Topic/recursive_timed_mutex::recursive_timed_mutex%20Constructor.md)|Erstellt ein `recursive_timed_mutex`\-Objekt, das nicht gesperrt ist.|  
|[recursive\_timed\_mutex::~recursive\_timed\_mutex\-Destruktor](../Topic/recursive_timed_mutex::~recursive_timed_mutex%20Destructor.md)|Gibt alle Ressourcen frei, die vom `recursive_timed_mutex`\-Objekt verwendet werden.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[recursive\_timed\_mutex::lock\-Methode](../Topic/recursive_timed_mutex::lock%20Method.md)|Blockiert den aufrufenden Thread, bis der Thread in den Besitz von `mutex` gelangt.|  
|[recursive\_timed\_mutex::try\_lock\-Methode](../Topic/recursive_timed_mutex::try_lock%20Method.md)|Versucht, ohne Blockierung in den Besitz von `mutex` zu gelangen.|  
|[recursive\_timed\_mutex::try\_lock\_for\-Methode](../Topic/recursive_timed_mutex::try_lock_for%20Method.md)|Versucht, den Besitz `mutex` für ein angegebenes Zeitintervall zu erhalten.|  
|[recursive\_timed\_mutex::try\_lock\_until\-Methode](../Topic/recursive_timed_mutex::try_lock_until%20Method.md)|Versucht, um `mutex` abzurufen bis eine festgelegte Zeit.|  
|[recursive\_timed\_mutex::unlock\-Methode](../Topic/recursive_timed_mutex::unlock%20Method.md)|Gibt den Besitz von `mutex` frei.|  
  
## Anforderungen  
 **Header:** mutex  
  
 **Namespace:** std  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex\>](../standard-library/mutex.md)