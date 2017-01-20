---
title: "mutex-Klasse (STL)"
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
  - "mutex/std::mutex"
dev_langs: 
  - "C++"
ms.assetid: 7999d055-f74f-4303-810f-8d3c9cde2f69
caps.latest.revision: 11
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# mutex-Klasse (STL)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Stellt einen *Mutex\-Typ* dar.  Objekte dieses Typs können dazu verwendet werden, den gegenseitigen Ausschluss innerhalb eines Programms zu erzwingen.  
  
## Syntax  
  
```  
class mutex;  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[mutex::mutex\-Konstruktor \(STL\)](../Topic/mutex::mutex%20Constructor%20\(STL\).md)|Erstellt ein `mutex`\-Objekt.|  
|[mutex::~mutex\-Destruktor \(STL\)](../Topic/mutex::~mutex%20Destructor%20\(STL\).md)|Gibt alle Ressourcen frei, die vom `mutex`\-Objekt verwendet wurden.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[mutex::lock\-Methode \(STL\)](../Topic/mutex::lock%20Method%20\(STL\).md)|Blockiert den aufrufenden Thread, bis der Thread in den Besitz von `mutex` gelangt.|  
|[mutex::native\_handle\-Methode \(STL\)](../Topic/mutex::native_handle%20Method%20\(STL\).md)|Gibt den implementierungsspezifischen Typ zurück, der das Mutexhandle darstellt.|  
|[mutex::try\_lock\-Methode \(STL\)](../Topic/mutex::try_lock%20Method%20\(STL\).md)|Versucht, ohne Blockierung in den Besitz von `mutex` zu gelangen.|  
|[mutex::unlock\-Methode \(STL\)](../Topic/mutex::unlock%20Method%20\(STL\).md)|Gibt den Besitz von `mutex` frei.|  
  
## Anforderungen  
 **Header:** mutex  
  
 **Namespace:** std  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex\>](../standard-library/mutex.md)