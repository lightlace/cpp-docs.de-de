---
title: "insert_iterator-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::insert_iterator"
  - "iterator/std::insert_iterator"
  - "std.insert_iterator"
  - "insert_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "insert_iterator-Klasse"
  - "insert_iterator-Klasse, Syntax"
ms.assetid: d5d86405-872e-4e3b-9e68-c69a2b7e8221
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# insert_iterator-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beschreibt einen Iteratoradapter, der den Anforderungen eines Ausgabeiterators entspricht.  Er fügt Elemente in eine Sequenz ein, anstatt sie zu überschreiben, und bietet somit Semantik, die sich von der Semantik zum Überschreiben unterscheidet, die von den Iteratoren der C\+\+\-Sequenz und assoziativen Containern bereitgestellt wird.  Die `insert_iterator`\-Klasse ist für den Typ des Containers, der angepasst wird, vorlagenbasiert.  
  
## Syntax  
  
```  
template <class Container> class insert_iterator;  
```  
  
#### Parameter  
 `Container`  
 Der Typ des Containers, in den Elementen von einem `insert_iterator` eingefügt werden sollen.  
  
## Hinweise  
 Der Container vom Typ **Container** muss den Anforderungen für einen Container variabler Größe erfüllen und über eine Memberfunktion zum Einfügen von zwei Argumenten verfügen, wobei die Parameter vom Typ **Container::iterator** und **Container::value\_type** sind und dieser einen Typ **Container::iterator** zurückgibt.  Die Standardvorlagenbibliothekssequenz und sortierte assoziative Container erfüllen diese Anforderungen und können mit `insert_iterator`\-Objekten angepasst werden.  Für assoziative Container wird das Positionsargument als Hinweis behandelt, der die Leistung je nach Qualität potenziell verbessern oder verschlechtern kann.  Ein `insert_iterator` muss immer mit seinem Container initialisiert werden.  
  
### Konstruktoren  
  
|||  
|-|-|  
|[insert\_iterator](../Topic/insert_iterator::insert_iterator.md)|Erstellt einen `insert_iterator`, der ein Element an einer bestimmten Position in einen Container einfügt.|  
  
### Typedefs  
  
|||  
|-|-|  
|[container\_type](../Topic/insert_iterator::container_type.md)|Ein Typ, der den Container darstellt, in dem eine allgemeine Einfügung vorgenommen werden soll.|  
|[Verweis](../Topic/insert_iterator::reference.md)|Ein Typ, der einen Verweis auf ein Element in einer Sequenz enthält, die durch den zugehörigen Container gesteuert wird.|  
  
### Operators  
  
|||  
|-|-|  
|[operator\*](../Topic/insert_iterator::operator*.md)|Der Dereferenzierungsoperator, der verwendet wird, um den Ausgabeiteratorausdruck \*`i` \= `x` für eine allgemeine Einfügung zu implementieren.|  
|[operator\+\+](../Topic/insert_iterator::operator++.md)|Inkrementiert `insert_iterator` zum folgenden Speicherort, an dem ein Wert gespeichert werden kann.|  
|[operator\=](../Topic/insert_iterator::operator=.md)|Der Zuweisungsoperator, der verwendet wird, um den Ausgabeiteratorausdruck \*`i` \= `x` für eine allgemeine Einfügung zu implementieren.|  
  
## Anforderungen  
 **Header**: \<Iterator\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<iterator\>](../standard-library/iterator.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)