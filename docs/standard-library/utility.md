---
title: "&lt;utility&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<utility>"
  - "utility/std::<utility>"
  - "std.<utility>"
  - "std::<utility>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "utility-Header"
ms.assetid: c4491103-5da9-47a1-9c2b-ed8bc64b0599
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# &lt;utility&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Definiert Typen, Funktionen und Operatoren einer Standardvorlagenbibliothek \(Standard Template Library, STL\), mit denen Paare von Objekten erstellt und verwaltet werden können. Solche Paare von Objekten sind immer dann nützlich, wenn zwei Objekte so behandelt werden müssen, als wären sie ein Objekt.  
  
## Syntax  
  
```  
  
#include <utility>  
  
```  
  
## Hinweise  
 Paare werden häufig in der C\+\+\-Standardbibliothek verwendet.  Sie sind sowohl als Argumente als auch als Rückgabewerte für verschiedene Funktionen sowie als Elementtypen für Container wie [map\-Klasse](../standard-library/map-class.md) und [multimap\-Klasse](../standard-library/multimap-class.md) erforderlich.  Der \<utility\>\-Header wird automatisch von \<map\> eingefügt, damit deren Typelemente für Schlüssel\/Wert\-Paare einfacher zu verwalten sind.  
  
### Klassen  
  
|||  
|-|-|  
|[tuple\_element](../standard-library/tuple-element-class-utility.md)|Eine Klasse, die den Typ eines `pair`\-Elements umschließt.|  
|[tuple\_size](../standard-library/tuple-size-class-utility.md)|Eine Klasse, die eine `pair`\-Elementanzahl umschließt.|  
  
### Funktionen  
  
|||  
|-|-|  
|[forward](../Topic/forward.md)|Verhindert durch perfektes Weiterleiten, dass der Referenztyp \(entweder `lvalue` oder `rvalue`\) des Arguments verdeckt wird.|  
|[Abrufen](../Topic/get%20Function%20%3Cutility%3E.md)|Eine Funktion, die ein Element aus einem `pair`\-Objekt abruft.|  
|[make\_pair](../Topic/make_pair.md)|Eine Vorlagenhilfsfunktion, die zum Erstellen von Objekten des Typs `pair` verwendet wird, wobei die Komponententypen auf den Datentypen basieren, die als Parameter übergeben werden.|  
|[verschieben](../Topic/move.md)|Gibt das als Eingabe übergebene Argument als einen `rvalue`\-Verweis zurück.|  
|[swap](../Topic/swap%20\(%3Cutility%3E\).md)|Tauscht die Elemente zweier `pair`\-Objekte.|  
  
### Operatoren  
  
|||  
|-|-|  
|[Operator\!\=](../Topic/operator!=%20\(%3Cutility%3E\).md)|Testet, ob das pair\-Objekt links vom Operator ungleich dem pair\-Objekt rechts vom Operator ist.|  
|[operator\=\=](../Topic/operator==%20\(%3Cutility%3E\).md)|Testet, ob das pair\-Objekt links vom Operator gleich dem pair\-Objekt rechts vom Operator ist.|  
|[Operator \<](../Topic/operator%3C%20\(%3Cutility%3E\).md)|Testet, ob das pair\-Objekt links vom Operator kleiner als das pair\-Objekt rechts vom Operator ist.|  
|[Operator \<\=](../Topic/operator%3C=%20\(%3Cutility%3E\).md)|Testet, ob das pair\-Objekt links vom Operator kleiner gleich dem pair\-Objekt rechts vom Operator ist.|  
|[Operator \>](../Topic/operator%3E%20\(%3Cutility%3E\).md)|Testet, ob das pair\-Objekt links vom Operator größer als das pair\-Objekt rechts vom Operator ist.|  
|[Operator \>\=](../Topic/operator%3E=%20\(%3Cutility%3E\).md)|Testet, ob das pair\-Objekt links vom Operator größer gleich dem pair\-Objekt rechts vom Operator ist.|  
  
### Strukturen  
  
|||  
|-|-|  
|[Identität](../standard-library/identity-structure.md)||  
|[pair](../standard-library/pair-structure.md)|Ein Typ, der die Möglichkeit bietet, zwei Objekte als ein einzelnes Objekt zu behandeln.|  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)