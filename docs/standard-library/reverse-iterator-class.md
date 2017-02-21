---
title: "reverse_iterator-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "reverse_iterator"
  - "std::reverse_iterator"
  - "std.reverse_iterator"
  - "xutility/std::reverse_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "reverse_iterator-Klasse"
ms.assetid: c0b34d04-ae9a-4999-9aff-28b313897ffa
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# reverse_iterator-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Vorlagenklasse ist ein Iteratoradapter, der ein Reverse\-Iterator\-Objekt beschreibt, das sich wie ein Random\-Access\- oder ein bidirektionaler Iterator verhält, nur umgekehrt.  Er ermöglicht es, einen Bereich rückwärts zu durchlaufen.  
  
## Syntax  
  
```  
template <class RandomIterator>  
class reverse_iterator  
```  
  
#### Parameter  
 RandomIterator  
 Der Typ, der den Iterator darstellt, der angepasst werden muss, um rückwärts zu funktionieren.  
  
## Hinweise  
 Vorhandene Standardvorlagenbibliothekscontainer definieren auch die Typen `reverse_iterator` und `const_reverse_iterator` und verfügen über die Memberfunktionen `rbegin` und `rend`, die Reverse\-Iteratoren zurückgeben.  Diese Iteratoren verfügen über Semantik zum Überschreiben.  Der `reverse_iterator`\-Adapter ergänzt diese Funktionalität durch Einfügesemantik und kann außerdem mit Streams verwendet werden.  
  
 Die `reverse_iterator`\-Objekte, die einen bidirektionalen Iterator erfordern, dürfen keine der Memberfunktionen `operator+=`, `operator+`, `operator-=`, `operator-` oder `operator[]` aufrufen, die nur mit Random\-Access\-Iteratoren verwendet werden dürfen.  
  
 Wenn der Bereich eines Iterators \[`_First`, \_Last\) ist, gibt die eckige Klammer links den Einschluss von \_*First* und die Klammer rechts den Einschluss von Elementen bis zu \_*\_Left* an, ohne jedoch \_*Left* selbst einzubeziehen.  Die gleichen Elemente sind in der umgekehrten Sequenz \[**rev** – `_First`, **rev** – \_*Left*\) enthalten. Wenn \_*Left* ein Element hinter dem Ende einer Sequenz ist, dann zeigt das erste Element **rev** – \_*First* in der umgekehrten Sequenz auf \*\(\_*Left* – 1 \).  Die Identität, die alle umgekehrten Iteratoren auf die zugrunde liegenden Iteratoren bezieht:  
  
 &\*\(**reverse\_iterator** \( *i* \) \) \=\= &\*\( *i* – 1 \).  
  
 In der Praxis bedeutet dies, dass in der umgekehrten Sequenz das reverse\_iterator\-Objekt auf das Element verweist, das eine Position hinter dem Element \(rechts davon\) liegt, auf das der Iterator in der ursprünglichen Sequenz verwiesen hat.  Wenn ein Iterator das Element 6 in der Sequenz adressierte \(2, 4, 6, 8\), dann adressiert `reverse_iterator` das Element 4 in der umgekehrten Sequenz \(8, 6, 4, 2\).  
  
### Konstruktoren  
  
|||  
|-|-|  
|[reverse\_iterator](../Topic/reverse_iterator::reverse_iterator.md)|Erstellt aus einem zugrunde liegenden Iterator einen standardmäßigen `reverse_iterator` oder `reverse_iterator`.|  
  
### Typedefs  
  
|||  
|-|-|  
|[difference\_type](../Topic/reverse_iterator::difference_type.md)|Ein Typ, mit dem der Unterschied zwischen zwei `reverse_iterator`en bereitgestellt wird, die auf Elemente innerhalb desselben Containers verweisen.|  
|[iterator\_type](../Topic/reverse_iterator::iterator_type.md)|Ein Typ, der einen zugrunde liegenden Iterator für einen `reverse_iterator` bereitstellt.|  
|[pointer](../Topic/reverse_iterator::pointer.md)|Ein Typ, mit dem ein Zeiger auf ein Element bereitgestellt wird, die von `reverse_iterator` adressiert werden.|  
|[Verweis](../Topic/reverse_iterator::reference.md)|Ein Typ, mit dem ein Verweis auf ein Element bereitgestellt wird, die von `reverse_iterator` adressiert werden.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[base](../Topic/reverse_iterator::base.md)|Stellt den zugrunde liegenden Iterator aus `reverse_iterator` wieder her.|  
  
### Operators  
  
|||  
|-|-|  
|[operator\*](../Topic/reverse_iterator::operator*.md)|Gibt das Element zurück, das ein `reverse_iterator` adressiert.|  
|[operator\+](../Topic/reverse_iterator::operator+.md)|Fügt einen Offset zu einem Iterator hinzu und gibt den neuen `reverse_iterator` zurück, der auf das eingefügte Element an der neuen Offsetposition zeigt.|  
|[operator\+\+](../Topic/reverse_iterator::operator++.md)|Erhöht `reverse_iterator` zum nächsten Element.|  
|[Operator\+\=](../Topic/reverse_iterator::operator+=.md)|Fügt einen angegebenen Offset aus einem `reverse_iterator` hinzu.|  
|[operator\-](../Topic/reverse_iterator::operator-.md)|Subtrahiert einen Offset von einem `reverse_iterator` und gibt einen `reverse_iterator` zurück, der das Element an die Offsetposition adressiert.|  
|[Operator\-\-](../Topic/reverse_iterator::operator--.md)|Verringert `reverse_iterator` zum vorherigen Element.|  
|[Operator\-\=](../Topic/reverse_iterator::operator-=.md)|Subtrahiert einen angegebenen Offset von einem `reverse_iterator`.|  
|[Operator\-\>](../Topic/reverse_iterator::operator-%3E.md)|Gibt einen Zeiger auf das Element zurück, das von `reverse_iterator` adressiert wird.|  
|[operator&#91;&#93;](../Topic/reverse_iterator::operator.md)|Gibt einen Verweis auf ein Elementoffset aus dem Element zurück, das von `reverse_iterator` mithilfe der angegebenen Anzahl von Positionen adressiert wird.|  
  
## Anforderungen  
 **Header:** \<Iterator\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<iterator\>](../standard-library/iterator.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)