---
title: "&lt; Zuordnung &gt;"
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
  - "std::<map>"
  - "std.<map>"
  - "<map>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "map-Header"
ms.assetid: bbf76680-7362-456e-88fa-ecda93561b6a
caps.latest.revision: 20
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# &lt; Zuordnung &gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Definiert die Containervorlagenklassen "map" und "multimap" und deren unterstützende Vorlagen.  
  
## Syntax  
  
```  
  
#include <map>  
  
```  
  
## Mitglieder  
  
### Operatoren  
  
|map\-Version|multimap\-Version|Beschreibung|  
|------------------|-----------------------|------------------|  
|[operator\!\= \(map\)](../Topic/operator!=%20\(map\).md)|[operator\!\= \(multimap\)](../Topic/operator!=%20\(multimap\).md)|Überprüft, ob das map\- oder multimap\-Objekt links vom Operator ungleich dem map\- oder multimap\-Objekt rechts vom Operator ist.|  
|[operator\< \(map\)](../Topic/operator==%20\(map\).md)|[operator\< \(multimap\)](../Topic/operator==%20\(multimap\).md)|Überprüft, ob das map\- oder multimap\-Objekt links vom Operator kleiner als das map\- oder multimap\-Objekt rechts vom Operator ist.|  
|[operator\<\= \(map\)](../Topic/operator%3C%20\(map\).md)|[operator\<\= \(multimap\)](../Topic/operator%3C%20\(multimap\).md)|Überprüft, ob das map\- oder multimap\-Objekt links vom Operator kleiner gleich dem map\- oder multimap\-Objekt rechts vom Operator ist.|  
|[operator\=\= \(map\)](../Topic/operator%3C=%20\(map\).md)|[operator\=\= \(multimap\)](../Topic/operator%3C=%20\(multimap\).md)|Überprüft, ob das map\- oder multimap\-Objekt links vom Operator gleich dem map\- oder multimap\-Objekt rechts vom Operator ist.|  
|[operator\> \(map\)](../Topic/operator%3E%20\(map\).md)|[operator\> \(multimap\)](../Topic/operator%3E%20\(multimap\).md)|Überprüft, ob das map\- oder multimap\-Objekt links vom Operator größer als das map\- oder multimap\-Objekt rechts vom Operator ist.|  
|[operator\>\= \(map\)](../Topic/operator%3E=%20\(map\).md)|[operator\>\= \(multimap\)](../Topic/operator%3E=%20\(multimap\).md)|Überprüft, ob das map\- oder multimap\-Objekt links vom Operator größer gleich dem map\- oder multimap\-Objekt rechts vom Operator ist.|  
  
### Spezialisierte Vorlagenfunktionen  
  
|map\-Version|multimap\-Version|Beschreibung|  
|------------------|-----------------------|------------------|  
|[swap \(map\)](../Topic/swap%20\(map\).md)|[swap \(multimap\)](../Topic/swap%20\(multimap\).md)|Tauscht die Elemente zweier map\- oder multimap\-Objekte aus.|  
  
### Klassen  
  
|||  
|-|-|  
|[value\_compare\-Klasse](../standard-library/value-compare-class-map.md)|Stellt ein Funktionsobjekt bereit, das die Elemente einer Zuordnung vergleichen kann, indem die Werte ihrer Schlüssel verglichen werden, um deren relative Reihenfolge in der Zuordnung zu bestimmen.|  
|[map\-Klasse](../standard-library/map-class.md)|Wird zum Speichern und Abrufen von Daten aus einer Sammlung verwendet, in der jedes der Elemente einen eindeutigen Schlüssel hat, mit dem die Daten automatisch geordnet werden.|  
|[multimap\-Klasse](../standard-library/multimap-class.md)|Wird zum Speichern und Abrufen von Daten aus einer Sammlung verwendet, in der jedes der Elemente einen Schlüssel hat, mit dem die Daten automatisch geordnet werden. Die Schlüssel müssen keine eindeutigen Werte haben.|  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)