---
title: "Gewusst wie: Verbessern der Leistung mithilfe von combinable | Microsoft Docs"
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
  - "combinable-Klasse, Beispiel"
  - "Verbessern der parallelen Leistung mit Combinable [Concurrency Runtime]"
ms.assetid: fa730580-1c94-4b2d-8aec-57c91dc0497e
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# Gewusst wie: Verbessern der Leistung mithilfe von combinable
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In diesem Beispiel wird gezeigt, wie die [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md)\-Klasse verwendet wird, um die Summe der Zahlen in einem [std::array](../../standard-library/array-class-stl.md)\-Objekt zu berechnen, bei denen es sich um Primzahlen handelt.  Die `combinable`\-Klasse steigert die Leistung, indem sie Freigabezustand ausschließt.  
  
> [!TIP]
>  In einigen Fällen kann die parallele Zuordnung \([concurrency::parallel\_transform](../Topic/parallel_transform%20Function.md)\) und eine Reduzierung \([concurrency::parallel\_reduce](../Topic/parallel_reduce%20Function.md)\) zu Leistungsverbesserungen im Vergleich zu `combinable` führen.  Ein Beispiel, in dem Zuordnungs\- und Reduzierungsoperationen verwendet werden, und das die gleichen Ergebnisse wie dieses Beispiel ergibt, finden Sie unter [Parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md).  
  
## Beispiel  
 Im folgenden Beispiel wird die [std::accumulate](../Topic/accumulate.md)\-Funktion verwendet, um die Summe der Elemente in einem Array zu berechnen, bei denen es sich um Primzahlen handelt.  In diesem Beispiel ist `a` ein `array`\-Objekt, und die `is_prime`\-Funktion bestimmt, ob sein Eingabewert eine Primzahl ist.  
  
 [!CODE [concrt-parallel-sum-of-primes#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-parallel-sum-of-primes#1)]  
  
## Beispiel  
 Das folgende Beispiel zeigt einen naiven Weg, das vorherige Beispiel zu parallelisieren.  In diesem Beispiel wird der [concurrency::parallel\_for\_each](../Topic/parallel_for_each%20Function.md)\-Algorithmus zum parallelen Verarbeiten des Arrays und ein [concurrency::critical\_section](../../parallel/concrt/reference/critical-section-class.md)\-Objekt zum Synchronisieren des Zugriffs auf die `prime_sum`\-Variable verwendet.  Dieses Beispiel skaliert nicht, da jeder Thread warten muss, bis die freigegebene Ressource verfügbar wird.  
  
 [!CODE [concrt-parallel-sum-of-primes#2](../CodeSnippet/VS_Snippets_ConcRT/concrt-parallel-sum-of-primes#2)]  
  
## Beispiel  
 Im folgenden Beispiel wird ein `combinable`\-Objekt zum Steigern der Leistung des vorherigen Beispiels verwendet.  In diesem Beispiel sind keine Synchronisierungsobjekte erforderlich. Es skaliert, da das `combinable`\-Objekt dafür sorgt, dass jeder Thread seine Aufgabe unabhängig ausführt.  
  
 Ein `combinable`\-Objekt wird in der Regel in zwei Schritten verwendet.  Erzeugen Sie zuerst eine Reihe von differenzierten Berechnungen, indem Sie Arbeiten parallel ausführen.  Fassen Sie danach die Berechnungen in einem Endergebnis zusammen \(oder reduzieren Sie sie\).  In diesem Beispiel wird die [concurrency::combinable::local](../Topic/combinable::local%20Method.md)\-Methode verwendet, um einen Verweis auf die lokale Summe zu erhalten.  Anschließend werden mit der [concurrency::combinable::combine](../Topic/combinable::combine%20Method.md)\-Methode und einem [std::plus](../../standard-library/plus-struct.md)\-Objekt die lokalen Berechnungen zum Endergebnis zusammengefasst.  
  
 [!CODE [concrt-parallel-sum-of-primes#3](../CodeSnippet/VS_Snippets_ConcRT/concrt-parallel-sum-of-primes#3)]  
  
## Beispiel  
 Im folgenden vollständigen Beispiel wird die Summe von Primzahlen sowohl seriell als auch parallel berechnet.  Das Beispiel gibt die Zeit, die zum Ausführen beider Berechnungen benötigt wird, in der Konsole aus.  
  
 [!CODE [concrt-parallel-sum-of-primes#4](../CodeSnippet/VS_Snippets_ConcRT/concrt-parallel-sum-of-primes#4)]  
  
 Die folgende Beispielausgabe entspricht einem Ergebnis auf einem Computer mit vier Prozessoren.  
  
  **1709600813**  
**serielle Uhrzeit: 6178 ms**  
**1709600813**  
**parallele Uhrzeit: 1638 ms**   
## Kompilieren des Codes  
 Zum Kompilieren kopieren Sie den Code, und fügen Sie ihn in ein Visual Studio\-Projekt ein, oder fügen Sie ihn in eine Datei mit dem Namen `parallel-sum-of-primes.cpp` ein, und führen Sie dann den folgenden Befehl in einem Visual Studio\-Eingabeaufforderungsfenster aus.  
  
 **cl.exe \/EHsc parallel\-sum\-of\-primes.cpp**  
  
## Robuste Programmierung  
 Ein Beispiel, in dem Zuordnungs\- und Reduzierungsoperationen verwendet werden, und das die gleichen Ergebnisse erzeugt, finden Sie unter [Parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md).  
  
## Siehe auch  
 [Parallele Container und Objekte](../../parallel/concrt/parallel-containers-and-objects.md)   
 [combinable\-Klasse](../../parallel/concrt/reference/combinable-class.md)   
 [critical\_section\-Klasse](../../parallel/concrt/reference/critical-section-class.md)