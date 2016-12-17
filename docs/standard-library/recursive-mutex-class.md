---
title: "recursive_mutex-Klasse"
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
  - "mutex/std::recursive_mutex"
dev_langs: 
  - "C++"
ms.assetid: eb5ffd1b-7e78-4559-8391-bb220ead42fc
caps.latest.revision: 9
caps.handback.revision: "3"
ms.author: "corob"
manager: "ghogen"
---
# recursive_mutex-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Stellt einen *Mutex\-Typ* dar.  Im Gegensatz zu [Mutex](../standard-library/mutex-class-stl.md) ist das Verhalten der Aufrufe zum Sperren von Methoden für Objekte, die bereits gesperrt werden, genau definiert.  
  
## Syntax  
  
```  
class recursive_mutex;  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[recursive\_mutex::recursive\_mutex\-Konstruktor](../Topic/recursive_mutex::recursive_mutex%20Constructor.md)|Erstellt ein `recursive_mutex`\-Objekt.|  
|[recursive\_mutex::~recursive\_mutex\-Destruktor](../Topic/recursive_mutex::~recursive_mutex%20Destructor.md)|Gibt alle Ressourcen frei, die vom `recursive_mutex`\-Objekt verwendet werden.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[recursive\_mutex::lock\-Methode](../Topic/recursive_mutex::lock%20Method.md)|Blockiert den aufrufenden Thread, bis der Thread den Besitz der Mutex erhält.|  
|[recursive\_mutex::try\_lock\-Methode](../Topic/recursive_mutex::try_lock%20Method.md)|Versucht, den Besitz der Mutex abzurufen, ohne zu blockieren.|  
|[recursive\_mutex::unlock\-Methode](../Topic/recursive_mutex::unlock%20Method.md)|Gibt Besitz der Mutex frei.|  
  
## Anforderungen  
 **Header:** mutex  
  
 **Namespace:** std  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex\>](../standard-library/mutex.md)