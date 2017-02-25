---
title: "promise-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "future/std::promise"
dev_langs: 
  - "C++"
ms.assetid: 2931558c-d94a-4ba1-ac4f-20bf7b6e23f9
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# promise-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beschreibt einen *asynchronen Anbieter*.  
  
## Syntax  
  
```  
template<class Ty>  
class promise;  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[promise::promise\-Konstruktor](../Topic/promise::promise%20Constructor.md)|Erstellt ein `promise`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[promise::get\_future\-Methode](../Topic/promise::get_future%20Method.md)|Gibt eine dieser Zusage zugeordnete [Zukunft](../standard-library/future-class.md) zurück.|  
|[promise::set\_exception\-Methode](../Topic/promise::set_exception%20Method.md)|Legt das Ergebnis dieser Zusage atomisch zum Angeben einer Ausnahme fest.|  
|[promise::set\_exception\_at\_thread\_exit\-Methode](../Topic/promise::set_exception_at_thread_exit%20Method.md)|Legt das Ergebnis dieser Zusage zum Angeben einer Ausnahme atomisch fest, und stellt die Benachrichtigung nur zu, nachdem alle Objekte eines lokalen Threads im aktuellen Thread zerstört wurden \(normalerweise zur Threadbeendigung\).|  
|[promise::set\_value\-Methode](../Topic/promise::set_value%20Method.md)|Legt das Ergebnis dieser Zusage zum Angeben eines Werts atomisch fest.|  
|[promise::set\_value\_at\_thread\_exit\-Methode](../Topic/promise::set_value_at_thread_exit%20Method.md)|Legt das Ergebnis dieser Zusage zum Angeben eines Werts atomisch fest, und stellt die Benachrichtigung nur zu, nachdem alle Objekte eines lokalen Threads im aktuellen Thread zerstört wurden \(normalerweise zur Threadbeendigung\).|  
|[promise::swap\-Methode](../Topic/promise::swap%20Method.md)|Tauscht den *zugeordneten asynchronen Zustand* dieser Zusage mit dem eines angegebenen Zusageobjekts aus.|  
  
### Öffentliche Operatoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[promise::operator\= Operator](../Topic/promise::operator=%20Operator.md)|Zuweisung des Freigabestatus dieses Zusageobjekts.|  
  
## Vererbungshierarchie  
 `promise`  
  
## Anforderungen  
 **Header:** future  
  
 **Namespace:** std  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)