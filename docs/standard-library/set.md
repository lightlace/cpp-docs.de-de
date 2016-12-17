---
title: "&lt;set&gt;"
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
  - "std.<set>"
  - "std::<set>"
  - "<set>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "set-Header"
ms.assetid: 43cb1ab2-6383-48cf-8bdc-2b96d7203596
caps.latest.revision: 20
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# &lt;set&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Definiert die Containervorlagenklassen "set" und "multiset" und deren unterstützende Vorlagen.  
  
## Syntax  
  
```  
  
#include <set>  
  
```  
  
## Mitglieder  
  
### Operatoren  
  
|set\-Version|multiset\-Version|Beschreibung|  
|------------------|-----------------------|------------------|  
|[operator\!\= \(set\)](../Topic/operator!=%20\(set\).md)|[operator\!\= \(multiset\)](../Topic/operator!=%20\(multiset\).md)|Überprüft, ob das set\- oder multiset\-Objekt links vom Operator ungleich dem set\- oder multiset\-Objekt rechts vom Operator ist.|  
|[operator\< \(set\)](../Topic/operator%3C%20\(set\).md)|[operator\< \(multiset\)](../Topic/operator%3C%20\(multiset\).md)|Überprüft, ob das set\- oder multiset\-Objekt links vom Operator kleiner als das set\- oder multiset\-Objekt rechts vom Operator ist.|  
|[operator\<\= \(set\)](../Topic/operator%3C=%20\(set\).md)|[operator\<\= \(multiset\)](../Topic/operator%3C=%20\(multiset\).md)|Überprüft, ob das set\- oder multiset\-Objekt links vom Operator kleiner gleich dem set\- oder multiset\-Objekt rechts vom Operator ist.|  
|[operator\=\= \(set\)](../Topic/operator==%20\(set\).md)|[operator\=\= \(multiset\)](../Topic/operator==%20\(multiset\).md)|Überprüft, ob das set\- oder multiset\-Objekt links vom Operator gleich dem set\- oder multiset\-Objekt rechts vom Operator ist.|  
|[operator\> \(set\)](../Topic/operator%3E%20\(set\).md)|[operator\> \(multiset\)](../Topic/operator%3E%20\(multiset\).md)|Überprüft, ob das set\- oder multiset\-Objekt links vom Operator größer als das set\- oder multiset\-Objekt rechts vom Operator ist.|  
|[operator\>\= \(set\)](../Topic/operator%3E=%20\(set\).md)|[operator\>\= \(multiset\)](../Topic/operator%3E=%20\(multiset\).md)|Überprüft, ob das set\- oder multiset\-Objekt links vom Operator größer gleich dem set\- oder multiset\-Objekt rechts vom Operator ist.|  
  
### Spezialisierte Vorlagenfunktionen  
  
|set\-Version|multiset\-Version|Beschreibung|  
|------------------|-----------------------|------------------|  
|[swap \(set\)](../Topic/swap%20\(set\).md)|[swap \(multiset\)](../Topic/swap%20\(multiset\).md)|Tauscht die Elemente von zwei set\- oder multiset\-Objekten aus.|  
  
### Klassen  
  
|||  
|-|-|  
|[set\-Klasse](../standard-library/set-class.md)|Wird zum Speichern und Abrufen von Daten aus einer Sammlung verwendet, in der die Werte der enthaltenen Elemente eindeutig sind und als Schlüsselwerte dienen, entsprechend denen die Daten automatisch geordnet werden.|  
|[multiset\-Klasse](../standard-library/multiset-class.md)|Wird zum Speichern von Daten in und zum Abrufen von Daten aus einer Sammlung verwendet, in der die Werte der enthaltenen Elemente nicht eindeutig sein müssen und als Schlüsselwerte dienen, entsprechend denen die Daten automatisch geordnet werden.|  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)