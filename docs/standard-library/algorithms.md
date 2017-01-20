---
title: "Algorithmen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "algorithm-Vorlagenfunktion C++-Bibliothekskonventionen"
  - "Algorithmen [C++], C++"
  - "Konventionen [C++], C++-Algorithmus"
  - "Bibliotheken [C++], C++-Algorithmus-Konventionen"
  - "C++-Standardbibliothek, Algorithmen"
ms.assetid: dec9b373-7d5c-46cc-b7d2-21a938ecd0a6
caps.latest.revision: 10
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Algorithmen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Algorithmen sind grundlegender Bestandteil der Standardvorlagenbibliothek.  Algorithmen arbeiten nicht mit Containern selbst, sondern mit Iteratoren.  Daher kann der gleiche Algorithmus von den meisten, wenn nicht gar allen, STL\-Containern verwendet werden.  Dieser Abschnitt beschreibt die Konventionen und die Terminologie von STL\-Algorithmen.  
  
## Hinweise  
 Die Beschreibungen der Algorithmusvorlagenfunktionen verwenden einige Kurznotationsausdrücke:  
  
-   Der Ausdruck „im Bereich \[*A*, *B*\)“ bezeichnet eine Sequenz von 0 oder mehreren diskreten Werten beginnend mit *A* bis, jedoch nicht einschließlich, *B*.  Ein Bereich ist nur gültig, wenn *B* von *A* aus erreichbar ist. Sie können *A* in einem Objekt *N* \(*N* \= *A*\) speichern, das Objekt null oder mehrmals erhöhen \(\+\+*N*\) und das Objekt nach einer endlichen Anzahl von Erhöhungsschritten \(N \=\= B*\)* gleich *B* entsprechen lassen.  
  
-   Der Ausdruck „jedes *N* im Bereich \[*A*, *B*\)“ bedeutet, dass *N* mit dem Wert *A* beginnt und null oder mehrmals erhöht wird, bis es gleich dem Wert *B* ist.  Der Fall *N* \=\= *B* ist nicht im Bereich.  
  
-   Der Ausdruck „der niedrigste Wert von *N* im Bereich \[*A*, *B*\), sodass *X*“ bedeutet, dass die Bedingung *X* für jedes *N* im Bereich \[*A*, *B*\) bestimmt wird, bis die Bedingung *X* erfüllt ist.  
  
-   Der Ausdruck „der höchste Wert von *N* im Bereich \[*A*, *B*\), sodass *X*“ bedeutet, dass *X* für jedes *N* im Bereich \[*A*, *B*\) bestimmt wird.  Die Funktion speichert jedes Mal, wenn die Bedingung *X* erfüllt ist, eine Kopie von *N* in `K`.  Wenn eine solche Speicherung auftritt, ersetzt die Funktion den endgültigen Wert von *N*, der gleich *B* ist, mit dem Wert von `K`.  Bei einem bidirektionalen Iterator oder einem Iterator mit wahlfreiem Zugriff kann dies jedoch auch bedeuten, dass *N* mit dem höchsten Wert des Bereichs beginnt und so lange über den Bereich erniedrigt wird, bis die Bedingung *X* erfüllt ist.  
  
-   Ausdrücke wie *X* \- *Y*, wobei *X* und *Y* andere Iteratoren als solche mit wahlfreiem Zugriff sein können, sind im mathematischen Sinn vorgesehen.  Die Funktion wertet den Operator **\-** nicht notwendigerweise aus, wenn sie einen solchen Wert bestimmen muss.  Dasselbe gilt auch für Ausdrücke wie *X* \+ *N* und *X* \- *N*, wobei *N* ein ganzzahliger Typ ist.  
  
 Mehrere Algorithmen verwenden ein Prädikat, das einen paarweisen Vergleich vornimmt, wie z. B. mit `operator==`, um ein `bool`\-Ergebnis auszugeben.  Die Prädikatfunktion `operator==`, oder jeder Ersatz hierfür, darf keinen der beiden Operanden ändern.  Sie muss bei jeder Auswertung dasselbe `bool`\-Ergebnis ausgeben. Außerdem muss sie dasselbe Ergebnis ausgeben, wenn eine Kopie einer der Operanden für den Operanden ersetzt wird.  
  
 Mehrere Algorithmen verwenden ein Prädikat, das eine strikte schwache Sortierung für Elementpaare aus einer Sequenz anwendet.  Für das Prädikat `pr`\(*X*, *Y*\):  
  
-   bedeutet „Strict“, dass `pr`\(*X*, *X*\) als „falsch“ ausgewertet wird.  
  
-   „Schwach“ bedeutet, dass *X* und *Y* die gleiche Sortierung aufweisen, wenn \!`pr`\(*X*, *Y*\) && \!`pr`\(*Y*, *X*\) \(*X* \=\= *Y* muss nicht definiert sein\).  
  
-   „Sortierung“ bedeutet, dass `pr`\(*X*, *Y*\) & & `pr`\(*Y*, Z\) `pr`\(*X*, Z\) impliziert.  
  
 Einige dieser Algorithmen verwenden implizit das Prädikat *X* \< *Y*.  Andere Prädikate, die in der Regel die Anforderung der strikten schwachen Sortierung erfüllen, sind *X* \> *Y*, **kleiner als**\(*X*, *Y*\) und `greater`\(*X*, *Y*\).  Beachten Sie jedoch, dass Prädikate wie *X* \<\= *Y* und *X* \>\= *Y* diese Anforderung nicht erfüllen.  
  
 Eine Sequenz von Elementen, durch Iteratoren festgelegt, im Bereich \[`First`, `Last`\) ist eine durch den Operator **\<** sortierte Sequenz, wenn für jedes *N* im Bereich \[0, `Last` \- `First`\) und für jedes *M* im Bereich \(N, `Last` \- `First`\) das Prädikat \! \(\*\(`First` \+ *M*\) \< \*\(*First* \+ *N*\)\) „wahr“ ist.  \(Beachten Sie, dass die Elemente in aufsteigender Reihenfolge sortiert werden.\) Die Prädikatfunktion **operator\<**, oder jeder Ersatz hierfür, darf keinen der beiden Operanden ändern.  Sie muss bei jeder Auswertung dasselbe `bool`\-Ergebnis ausgeben. Außerdem muss sie dasselbe Ergebnis ausgeben, wenn eine Kopie einer der Operanden für den Operanden ersetzt wird.  Darüber hinaus muss sie eine strikte schwache Sortierung für die verglichenen Operanden anwenden.  
  
 Eine Sequenz von Elementen, die durch Iteratoren im Bereich \[`First`, `Last`\) festgelegt werden, ist eine durch den **operator\<** sortierte Sequenz, wenn für jedes *N* im Bereich \[1, `Last` \- `First`\) das Prädikat \! \(\*`First` \< \*\(`First` \+ *N*\)\) „wahr“ ist.  \(Das erste Element ist das größte.\) Ihre interne Struktur ist andernfalls nur den Vorlagenfunktionen [make\_heap](../Topic/make_heap.md), [pop\_heap](../Topic/pop_heap.md) und [push\_heap](../Topic/push_heap.md) bekannt.  Wie bei eine geordnete Sequenz darf die Prädikatfunktion **operator \<**, oder jeder Ersatz hierfür, keinen der beiden Operanden ändern, und sie muss eine strikte schwache Sortierung auf die verglichenen Operanden anwenden.  Sie muss bei jeder Auswertung dasselbe `bool`\-Ergebnis ausgeben. Außerdem muss sie dasselbe Ergebnis ausgeben, wenn eine Kopie einer der Operanden für den Operanden ersetzt wird.  
  
 Die STL\-Algorithmen befinden sich in den Headerdateien [\<algorithm\>](../standard-library/algorithm.md) und [\<numeric\>](../standard-library/numeric.md).  
  
## Siehe auch  
 [Standard Template Library](../misc/standard-template-library.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)