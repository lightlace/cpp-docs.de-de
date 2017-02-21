---
title: "Gewusst wie: Schreiben einer parallel_for_each-Schleife | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Schreiben einer parallel_for_each-Schleife [Concurrency Runtime]"
  - "parallel_for_each-Funktion, Beispiel"
ms.assetid: fa9c0ba6-ace0-4f88-8681-c7c1f52aff20
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# Gewusst wie: Schreiben einer parallel_for_each-Schleife
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In diesem Beispiel wird gezeigt, wie der [concurrency::parallel\_for\_each](../Topic/parallel_for_each%20Function.md)\-Algorithmus verwendet wird, um die Anzahl von Primzahlen in einem [std::array](../../standard-library/array-class-stl.md)\-Objekt parallel zu berechnen.  
  
## Beispiel  
 Im folgenden Beispiel wird die Anzahl von Primzahlen in einem Array zweimal berechnet.  Im Beispiel wird zunächst die Anzahl mit dem [std::for\_each](../Topic/for_each.md)\-Algorithmus seriell berechnet.  Anschließend wird die gleiche Aufgabe mit dem `parallel_for_each`\-Algorithmus parallel ausgeführt.  Das Beispiel gibt außerdem die Zeit, die zum Ausführen beider Berechnungen benötigt wird, in der Konsole aus.  
  
 [!CODE [concrt-parallel-count-primes#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-parallel-count-primes#1)]  
  
 Die folgende Beispielausgabe entspricht einem Ergebnis auf einem Computer mit vier Prozessoren.  
  
  **serial version:**  
**found 17984 prime numbers**  
**took 6115 ms**  
**parallel version:**  
**found 17984 prime numbers**  
**took 1653 ms**   
## Kompilieren des Codes  
 Zum Kompilieren kopieren Sie den Code, und fügen Sie ihn in ein Visual Studio\-Projekt ein, oder fügen Sie ihn in eine Datei mit dem Namen `parallel-count-primes.cpp` ein, und führen Sie dann den folgenden Befehl in einem Visual Studio\-Eingabeaufforderungsfenster aus.  
  
 **cl.exe \/EHsc parallel\-count\-primes.cpp**  
  
## Robuste Programmierung  
 Der Lambda\-Ausdruck, der im Beispiel an den `parallel_for_each`\-Algorithmus übergeben wird, aktiviert mithilfe der `InterlockedIncrement`\-Funktion parallele Iterationen der Schleife, um den Zähler gleichzeitig zu inkrementieren.  Wenn Sie Funktionen wie z. B. `InterlockedIncrement` verwenden, um Zugriff auf freigegebene Ressourcen zu synchronisieren, kann es zu Leistungsengpässen im Code kommen.  Sie können einen Synchronisierungsmechanismus ohne Sperren verwenden, z. B. die [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md)\-Klasse, um den gleichzeitigen Zugriff auf freigegebene Ressourcen zu vermeiden.  Ein Beispiel, in dem die `combinable`\-Klasse auf diese Weise verwendet wird, finden Sie unter [Gewusst wie: Verbessern der Leistung mithilfe von combinable](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md).  
  
## Siehe auch  
 [Parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md)   
 [parallel\_for\_each\-Funktion](../Topic/parallel_for_each%20Function.md)