---
title: Iteratoren | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- iterator conventions
- C++ Standard Library, iterator conventions
ms.assetid: 2f746be7-b37d-4bfc-bf05-be4336ca982f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b75a4f682b83fb8a738a5b19a7c5aa9a1b38166a
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="iterators"></a>Iterators
Ein Iterator ist ein Objekt, das Elemente in einem C++-Standardbibliothekscontainer durchlaufen kann und den Zugriff auf einzelne Elemente bereitstellt. Alle C++-Standardbibliothekscontainer stellen Iteratoren bereit, damit Algorithmen standardisiert auf ihre Elemente zugreifen können, ohne dass die Art des Containers von Bedeutung ist, in dem die Elemente gespeichert werden.  
  
 Sie können Iteratoren explizit mit Member- und globalen Funktionen wie z. B. begin() und end() verwenden und sich mit Operatoren wie z. B. ++ und --vorwärts oder rückwärts bewegen. Sie können Iteratoren auch implizit mit einer range-for-Schleife (für bestimmte Iteratortypen) oder dem Unterskriptoperator [] verwenden.  
  
 In der C++-Standardbibliothek ist der Anfang einer Sequenz oder eines Bereichs das erste Element. Das Ende einer Sequenz oder eines Bereichs wird immer als eins hinter dem letzten Element definiert. Die globalen Funktionen „begin“ und „end“ geben Iteratoren zu einem angegebenen Container zurück. Die typische explizite Iteratorschleife durch alle Elemente in einem Container sieht folgendermaßen aus:  
  
```  
 
vector<int> vec{ 0,1,2,3,4 };  
for (auto it = begin(vec);

it != end(vec);

it++)  
{  // Access element using dereference operator
    cout <<*it <<" ";  
}  
```  
  
 Das Gleiche kann einfacher mit einer range-for-Schleife erreicht werden:  
  
```  
for (auto num : vec)  
 {  // no deference operator
    cout <<num <<" ";  
 }  
```  
  
 Es gibt fünf Kategorien von Iteratoren. Die Kategorien zum Erhöhen der Leistung sind:  
  
- **Output**. Ein Ausgabeiterator`X` kann eine Sequenz mit dem Operator ++ vorwärts durchlaufen, und ein Element nur einmal mit dem Operator * schreiben.  
  
- **Input**. Ein Eingabeiterator`X` kann eine Sequenz mit dem Operator ++ vorwärts durchlaufen, und ein Element mit dem Operator * beliebig oft lesen. Sie können Eingabeiteratoren mithilfe der Iteratoren ++ und != vergleichen. Nach der Inkrementierung einer Kopie eines Eingabeiterators kann keine der anderen Kopien sicher verglichen, dereferenziert oder inkrementiert werden.  
  
- **Forward**. Ein Forward-Iterator`X` kann eine Sequenz mit dem Operator ++ vorwärts durchlaufen, und ein beliebiges Element lesen oder nicht konstante Elemente beliebig oft mit dem Operator * schreiben. Sie können mithilfe des Operators -> auf Elementmitglieder zugreifen und Forward-Iteratoren mithilfe der Operatoren == und != vergleichen. Sie können mehrere Kopien eines Forward-Iterators anfertigen, wobei jede einzelne unabhängig dereferenziert und inkrementiert werden kann. Ein Forward-Iterator, der ohne Bezug zu einem beliebigen Container initialisiert ist, wird Null-Forward-Iterator genannt. Null-Forward-Iteratoren vergleichen immer gleich.  
  
-   Bidirektional. Ein bidirektionaler Iterator `X` kann an die Stelle eines Forward-Iterators treten. Sie können einen bidirektionalen Iterator jedoch wie in --`X`, `X`-- oder (`V` = *`X`--) auch verringern. Sie können auf Elementmitglieder zugreifen und bidirektionale Iteratoren genauso wie Forward-Iteratoren vergleichen.  
  
- **Random Access**. Ein Random-Access-Iterator `X` kann an die Stelle eines bidirektionalen Iterators treten. Mit einem Random-Access-Iterator können Sie den Unterskriptoperator [] zum Zugriff auf Elemente verwenden. Sie können sich mit dem Operatoren +, -, += und -= eine bestimmte Anzahl an Elementen vorwärts oder rückwärts bewegen und den Abstand zwischen Iteratoren berechnen. Sie können bidirektionale Iteratoren mithilfe von ==, !=, \<, >, \<=, und >= vergleichen.  
  
 Alle Iteratoren können zugewiesen oder kopiert werden. Es wird angenommen, dass es sich bei ihnen um Lightweight-Objekte handelt, und sie werden oftmals nach Wert und nicht nach Verweis weiter- und zurückgegeben. Beachten Sie zudem, dass einer der zuvor beschriebenen Vorgänge eine Ausnahme auslösen kann, wenn er für einen gültigen Iterator ausgeführt wird.  
  
 Die Hierarchie der Iteratorkategorien kann durch das Zeigen von drei Sequenzen zusammengefasst werden. Für den schreibgeschützten Zugriff auf eine Sequenz können Sie Folgendes verwenden:  
  
```  
output iterator  
 -> forward iterator  
 -> bidirectional iterator  
 -> random-access iterator  
```  
  
 Der Pfeil nach rechts meint: „kann ersetzt werden durch“. Jeder einen Ausgabeiterator aufrufende Algorithmus sollte beispielsweise problemlos mit einem Forward-Iterator funktionieren; dies gilt jedoch *nicht* umgekehrt.  
  
 Für den schreibgeschützten Zugriff auf eine Sequenz können Sie Folgendes verwenden:  
  
```  
input iterator  
 -> forward iterator  
 -> bidirectional iterator  
 -> random-access iterator  
```  
  
 In diesem Fall ist ein Eingabeiterator die schwächste aller Kategorien.  
  
 Schließlich können Sie für den Lese-/Schreibzugriff auf eine Sequenz Folgendes verwenden:  
  
```  
forward iterator  
 -> bidirectional iterator  
 -> random-access iterator  
```  
  
 Ein Objektzeiger kann immer als ein Random-Access-Iterator fungieren. Er kann demnach als eine beliebige Kategorie des Iterators fungieren, wenn er den entsprechenden Lese-/Schreibzugriff auf die Sequenz unterstützt, die er festlegt.  
  
 Ein Iterator `Iterator`, der dem Objektzeiger nicht entspricht, muss zudem die Membertypen definieren, die durch die Spezialisierung `iterator_traits<Iterator>` erforderlich ist. Bitte beachten Sie, dass diese Anforderungen erfüllt werden können, indem `Iterator` aus der öffentlichen Basisklasse [iterator](../standard-library/iterator-struct.md) abgeleitet wird.  
  
 Es ist wichtig, die Zusagen und Einschränkungen jeder Iteratorkategorie zu verstehen, um nachzuvollziehen, wie Iteratoren durch Container und Algorithmen in der C++-Standardbibliothek verwendet werden.  
  
> [!NOTE]
>  Sie können die explizite Verwendung von Iteratoren mithilfe von range-for-Schleifen umgehen. Weitere Informationen finden Sie unter [Schleifen (Modern C++)](http://msdn.microsoft.com/en-us/b1b2779c-750e-4576-a514-a84178eae9da).  
  
 Visual C++ bietet jetzt checked-Iteratoren und Debug-Iteratoren, um sicherzustellen, dass Sie die Grenzen des Containers nicht überschreiben. Weitere Informationen finden Sie unter [Überprüfte Iteratoren](../standard-library/checked-iterators.md) und [Unterstützung für Iteratordebugging](../standard-library/debug-iterator-support.md).  
  
## <a name="see-also"></a>Siehe auch  
 [C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)   
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)

