---
title: "&lt;iterator&gt;"
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
  - "std::<iterator>"
  - "std.<iterator>"
  - "<iterator>"
  - "iterator/std::<iterator>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "iterator-Header"
ms.assetid: c61a3962-f3ed-411a-b5a3-e8b3c2b500bd
caps.latest.revision: 27
caps.handback.revision: "17"
ms.author: "corob"
manager: "ghogen"
---
# &lt;iterator&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Definiert die primitiven Elemente von Iteratoren, vordefinierte Iteratoren sowie Stream\-Iteratoren sowie einige unterstützende Vorlagen.  Die vordefinierten Iteratoren beinhalten Insert\- und Reverse\-Adapter.  Es gibt drei Klassen von Insert\-Adaptern für Iteratoren: Front, Back und General.  Sie bieten Einfügesemantik anstelle der Semantik zum Überschreiben, die von Iteratoren der Memberfunktion des Containers bereitgestellt wird.  
  
## Syntax  
  
```  
  
#include <iterator>  
  
```  
  
## Hinweise  
 Iteratoren sind eine Verallgemeinerung von Zeigern. Die Anforderungen werden so abstrahiert, dass ein C\+\+\-Programm mit unterschiedlichen Datenstrukturen einheitlich arbeiten kann.  Iteratoren dienen als Vermittler zwischen Containern und allgemeinen Algorithmen.  Algorithmen sind nicht für bestimmte Datentypen definiert, sondern für Bereiche, die durch den Iterator\-Typ festgelegt sind.  Der Algorithmus funktioniert dann für jede Datenstruktur, die den Anforderungen des Iterators entspricht.  Es wird zwischen fünf Typen oder Kategorien von Iteratoren mit jeweils eigenen Anforderungen und Funktionen unterschieden:  
  
-   Output: Kann vorwärts bewegt werden, Werte speichern, aber nicht abrufen, und wird von ostream und inserter bereitgestellt.  
  
-   Input: Kann vorwärts bewegt werden, Werte abrufen, aber nicht speichern, und wird von istream bereitgestellt.  
  
-   Forward: Kann vorwärts bewegt werden und Werte speichern sowie abrufen.  
  
-   Bidirektional: Kann vorwärts und rückwärts bewegt werden, Werte speichern und abrufen, und wird durch List, Set, Multiset, Map und Multimap bereitgestellt.  
  
-   Random\-Access: Auf Elemente wird in beliebiger Reihenfolge zugegriffen, Werte können gespeichert und abgerufen werden, wird durch Vector, Deque, String und Array bereitgestellt.  
  
 Iteratoren mit höheren Anforderungen und besserem Zugriff auf Elemente können anstelle von Iteratoren mit geringeren Anforderungen verwendet werden.  Wird beispielsweise ein Forward\-Iterator aufgerufen, kann stattdessen auch ein Random\-Access\-Iterator verwendet werden.  
  
 Visual Studio besitzt zusätzliche Erweiterungen für C\+\+\-Standardbibliotheksiteratoren, um eine Vielzahl von Debugmodussituationen für aktivierte und nicht aktivierte Iteratoren zu unterstützen.  Weitere Informationen finden Sie unter [Sichere Bibliotheken: C\+\+\-Standardbibliothek](../standard-library/safe-libraries-cpp-standard-library.md).  
  
### Funktionen  
  
|||  
|-|-|  
|[advance](../Topic/advance.md)|Damit kann ein Iterator um eine bestimmte Anzahl von Positionen vorwärts verschoben werden.|  
|[back\_inserter](../Topic/back_inserter.md)|Damit wird ein Iterator erstellt, mit dem Elemente an das Ende eines bestimmten Containers eingefügt werden können.|  
|[begin](../Topic/begin.md)|Ruft einen Iterator für das erste Element in einem angegebenen Container ab.|  
|[cbegin](../Topic/cbegin.md)|Ruft einen konstanten Iterator für das erste Element in einem angegebenen Container ab.|  
|[cend](../Topic/cend.md)|Ruft einen konstanten Iterator für das Element ab, das auf das letzte Element im angegebenen Container folgt.|  
|[distance](../Topic/distance.md)|Bestimmt die Anzahl von Inkrementen zwischen den durch zwei Iteratoren festgelegten Positionen.|  
|[end](../Topic/end.md)|Ruft einen Iterator für das Element ab, das auf das letzte Element im angegebenen Container folgt.|  
|[front\_inserter](../Topic/front_inserter.md)|Damit wird ein Iterator erstellt, mit dem Elemente an den Anfang eines bestimmten Containers eingefügt werden können.|  
|[Inserter](../Topic/inserter.md)|Ein Iterator\-Adapter, mit dem einem Container an einem bestimmten Punkt ein neues Element hinzugefügt wird.|  
|[make\_checked\_array\_iterator](../Topic/make_checked_array_iterator.md)|Erstellt ein [checked\_array\_iterator](../standard-library/checked-array-iterator-class.md)\-Objekt, das von anderen Algorithmen verwendet werden kann. **Note:**  Bei dieser Funktion handelt es sich um eine Microsoft\-Erweiterung der C\+\+\-Standardbibliothek.  Der Code, der mit dieser Funktion implementiert wird, ist nicht auf C\+\+\-Standardbuildumgebungen übertragbar, die die Microsoft\-Erweiterung nicht unterstützen.|  
|[make\_move\_iterator](../Topic/make_move_iterator.md)|Gibt einen Move\-Iterator zurück, der den bereitgestellten Iterator als gespeicherten Basis\-Iterator enthält.|  
|[make\_unchecked\_array\_iterator](../Topic/make_unchecked_array_iterator.md)|Erstellt ein [unchecked\_array\_iterator](../standard-library/unchecked-array-iterator-class.md)\-Objekt, das von anderen Algorithmen verwendet werden kann. **Note:**  Bei dieser Funktion handelt es sich um eine Microsoft\-Erweiterung der C\+\+\-Standardbibliothek.  Der Code, der mit dieser Funktion implementiert wird, ist nicht auf C\+\+\-Standardbuildumgebungen übertragbar, die die Microsoft\-Erweiterung nicht unterstützen.|  
|[next](../Topic/next.md)|Führt eine bestimmte Anzahl von Iterationen aus und gibt die neue Position des Iterators zurück.|  
|[prev](../Topic/prev.md)|Führt eine bestimmte Anzahl von Iterationen rückwärts aus und gibt die neue Position des Iterators zurück.|  
  
### Operatoren  
  
|||  
|-|-|  
|[operator\!\=](../Topic/operator!=%20\(%3Citerator%3E\).md)|Testet, ob das Iterator\-Objekt links vom Operator ungleich dem Iterator\-Objekt rechts vom Operator ist.|  
|[operator\=\=](../Topic/operator==%20\(%3Citerator%3E\).md)|Testet, ob das Iterator\-Objekt links vom Operator gleich dem Iterator\-Objekt rechts vom Operator ist.|  
|[Operator implementiert.\<](../Topic/operator%3C%20\(%3Citerator%3E\).md)|Testet, ob das Iterator\-Objekt links vom Operator kleiner ist als das Iterator\-Objekt rechts vom Operator.|  
|[operator\<\=](../Topic/operator%3C=%20\(%3Citerator%3E\).md)|Testet, ob das Iterator\-Objekt links vom Operator kleiner als oder gleich dem Iterator\-Objekt rechts vom Operator ist.|  
|[Operator implementiert.\>](../Topic/operator%3E%20\(%3Citerator%3E\).md)|Testet, ob das Iterator\-Objekt links vom Operator größer als das Iterator\-Objekt rechts vom Operator ist.|  
|[operator\>\=](../Topic/operator%3E=%20\(%3Citerator%3E\).md)|Testet, ob das Iterator\-Objekt links vom Operator größer als oder gleich dem Iterator\-Objekt rechts vom Operator ist.|  
|[operator\+](../Topic/operator+%20\(%3Citerator%3E\).md)|Fügt einen Offset zu einem Iterator hinzu und gibt den neuen `reverse_iterator` zurück, der auf das eingefügte Element an der neuen Offsetposition zeigt.|  
|[operator\-](../Topic/operator-%20\(%3Citerator%3E\).md)|Subtrahiert einen Iterator von einem anderen und gibt die Differenz zurück.|  
  
### Klassen  
  
|||  
|-|-|  
|[back\_insert\_iterator](../standard-library/back-insert-iterator-class.md)|Die Vorlagenklasse beschreibt einen Output\-Iterator.  Es werden Elemente in einen Container des Typs **Container** eingefügt, auf den über das geschützte **Zeiger**\-Objekt zugegriffen wird \(Container\).|  
|[bidirectional\_iterator\_tag](../standard-library/bidirectional-iterator-tag-struct.md)|Eine Klasse, die einen Rückgabetyp für eine **iterator\_category**\-Funktion bereitstellt, die einen bidirektionalen Iterator darstellt.|  
|[checked\_array\_iterator](../standard-library/checked-array-iterator-class.md)|Eine Klasse, die auf ein Array mit einem Iterator vom Typ "Random\-Access, Checked" zugreift. **Note:**  Bei dieser Klasse handelt es sich um eine Microsoft\-Erweiterung der C\+\+\-Standardbibliothek.  Der Code, der mit dieser Funktion implementiert wird, ist nicht auf C\+\+\-Standardbuildumgebungen übertragbar, die die Microsoft\-Erweiterung nicht unterstützen.|  
|[forward\_iterator\_tag](../standard-library/forward-iterator-tag-struct.md)|Eine Klasse, die einen Rückgabetyp für eine **iterator\_category**\-Funktion bereitstellt, die einen Forward\-Iterator darstellt.|  
|[front\_insert\_iterator](../standard-library/front-insert-iterator-class.md)|Die Vorlagenklasse beschreibt einen Output\-Iterator.  Es werden Elemente in einen Container des Typs **Container** eingefügt, auf den über das geschützte **Zeiger**\-Objekt zugegriffen wird \(Container\).|  
|[input\_iterator\_tag](../standard-library/input-iterator-tag-struct.md)|Eine Klasse, die einen Rückgabetyp für eine **iterator\_category**\-Funktion bereitstellt, die einen Input\-Iterator darstellt.|  
|[insert\_iterator](../standard-library/insert-iterator-class.md)|Die Vorlagenklasse beschreibt einen Output\-Iterator.  Es werden Elemente in einen Container des Typs **Container** eingefügt, auf den über das geschützte **Zeiger**\-Objekt zugegriffen wird \(Container\).  Gespeichert wird außerdem das geschützte **Iterator**\-Objekt der Klasse **Container::iterator** namens **iter**.|  
|[istream\_iterator](../standard-library/istream-iterator-class.md)|Die Vorlagenklasse beschreibt einen Input\-Iterator.  Es werden Objekte der Klasse **Ty** von einem Input\-Stream extrahiert. Der Zugriff darauf erfolgt durch ein gespeichertes Objekt des Typs Zeiger zu `basic_istream`\<**Elem**, **Tr**\>.|  
|[istreambuf\_iterator](../standard-library/istreambuf-iterator-class.md)|Die Vorlagenklasse beschreibt einen Input\-Iterator.  Elemente der Klasse **Elem** werden in einen Ausgabestreampuffer eingefügt. Der Zugriff darauf erfolgt durch ein gespeichertes Objekt des Typs **Zeiger** zu `basic_streambuf`\<**Elem**, **Tr**\>.|  
|[Iterator](../standard-library/iterator-struct.md)|Die Vorlagenklasse wird als Basistyp für alle Iteratoren verwendet.|  
|[iterator\_traits](../standard-library/iterator-traits-struct.md)|Eine Hilfsklasse für Vorlagen, die wichtige Typen bereitstellt, die mit verschiedenen Iterator\-Typen verknüpft sind, damit die Verweise auf dieselbe Weise funktionieren.|  
|[move\_iterator](../standard-library/move-iterator-class.md)|Ein `move_iterator`\-Objekt speichert einen Random\-Access\-Iterator des Typs `RandomIterator`.  Es verhält sich wie ein Rand\-Access\-Iterator, außer bei einer Dereferenzierung.  Das Ergebnis von `operator*` wird implizit umgewandelt in `value_type&&:`, um `rvalue reference` zu erhalten.|  
|[ostream\_iterator](../standard-library/ostream-iterator-class.md)|Die Vorlagenklasse beschreibt einen Output\-Iterator.  Objekte der Klasse **Type** werden in einen Ausgabestream eingefügt. Der Zugriff darauf erfolgt durch ein gespeichertes Objekt des Typs **Zeiger** zu `basic_ostream`\<**Elem**, **Tr**\>.|  
|[ostreambuf\_iterator Class](../standard-library/ostreambuf-iterator-class.md)|Die Vorlagenklasse beschreibt einen Output\-Iterator.  Elemente der Klasse **Elem** werden in einen Ausgabestreampuffer eingefügt. Der Zugriff darauf erfolgt durch ein gespeichertes Objekt des Typs Zeiger zu `basic_streambuf`\<**Elem**, **Tr**\>.|  
|[output\_iterator\_tag](../standard-library/output-iterator-tag-struct.md)|Eine Klasse, die einen Rückgabetyp für eine **iterator\_category**\-Funktion bereitstellt, die einen Output\-Iterator darstellt.|  
|[random\_access\_iterator\_tag](../standard-library/random-access-iterator-tag-struct.md)|Eine Klasse, die einen Rückgabetyp für eine **iterator\_category**\-Funktion bereitstellt, die einen Random\-Access\-Iterator darstellt.|  
|[reverse\_iterator](../standard-library/reverse-iterator-class.md)|Die Vorlagenklasse beschreibt ein Objekt, das sich wie ein Random\-Access\-Iterator verhält, nur in umgekehrter Reihenfolge.|  
|[unchecked\_array\_iterator](../standard-library/unchecked-array-iterator-class.md)|Eine Klasse, die auf ein Array mit einem Iterator vom Typ "Random\-Access, Unchecked" zugreift. **Note:**  Bei dieser Klasse handelt es sich um eine Microsoft\-Erweiterung der C\+\+\-Standardbibliothek.  Der Code, der mit dieser Funktion implementiert wird, ist nicht auf C\+\+\-Standardbuildumgebungen übertragbar, die die Microsoft\-Erweiterung nicht unterstützen.|  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)