---
title: "Gewusst wie: Verwenden von parallel_invoke zum Schreiben einer Runtime f&#252;r paralleles Sortieren"
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
  - "task_handle-Klasse, Beispiel"
  - "task_group-Klasse, Beispiel"
  - "make_task-Funktion, Beispiel"
  - "structured_task_group-Klasse, Beispiel"
  - "Verbessern der parallelen Leistung mit Aufgabengruppen [Concurrency Runtime]"
ms.assetid: 53979a2a-525d-4437-8952-f1ff85b37673
caps.latest.revision: 23
caps.handback.revision: "20"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Verwenden von parallel_invoke zum Schreiben einer Runtime f&#252;r paralleles Sortieren
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In diesem Dokument wird beschrieben, wie mit dem [parallel\_invoke](../Topic/parallel_invoke%20Function.md)\-Algorithmus die Leistung des bitonischen Sortieralgorithmus verbessert werden kann.  Der bitonische Sortieralgorithmus unterteilt die Eingabesequenz rekursiv in kleinere sortierte Partitionen.  Der bitonische Sortieralgorithmus kann parallel ausgeführt werden, da alle Partitionsvorgänge von allen anderen Vorgängen unabhängig sind.  
  
 Obwohl das bitonische Sortieren ein Beispiel für ein *Sortiernetzwerk* ist, das alle Kombinationen von Eingabesequenzen sortiert, werden in diesem Beispiel Sequenzen sortiert, deren Länge eine Potenz von zwei ist.  
  
> [!NOTE]
>  Dieses Beispiel verwendet eine parallele Sortierungsroutine zur Veranschaulichung.  Sie können auch die integrierten Sortieralgorithmen verwenden, die die PPL bereitstellt: [concurrency::parallel\_sort](../Topic/parallel_sort%20Function.md), [concurrency::parallel\_buffered\_sort](../Topic/parallel_buffered_sort%20Function.md) und [concurrency::parallel\_radixsort](../Topic/parallel_radixsort%20Function.md).  Weitere Informationen finden Sie unter [Parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md).  
  
##  <a name="top"></a> Abschnitte  
 In diesem Dokument werden die folgenden Aufgaben erläutert:  
  
-   [Serielles Ausführen der bitonischen Sortierung](#serial)  
  
-   [Verwenden von parallel\_invoke für die parallele bitonische Suche](#parallel)  
  
##  <a name="serial"></a> Serielles Ausführen der bitonischen Sortierung  
 Im folgenden Beispiel wird die serielle Version des bitonischen Sortieralgorithmus dargestellt.  Die `bitonic_sort`\-Funktion unterteilt die Sequenz in zwei Partitionen, sortiert diese Partitionen in entgegengesetzten Richtungen, und führt dann die Ergebnisse zusammen.  Diese Funktion ruft sich selbst zweimal auf, um alle Partitionen rekursiv zu sortieren.  
  
 [!CODE [concrt-parallel-bitonic-sort#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-parallel-bitonic-sort#1)]  
  
 \[[Nach oben](#top)\]  
  
##  <a name="parallel"></a> Verwenden von parallel\_invoke für die parallele bitonische Suche  
 In diesem Abschnitt wird beschrieben, wie der bitonischen Sortieralgorithmus mit dem `parallel_invoke`\-Algorithmus parallel ausgeführt werden kann.  
  
### Prozeduren  
  
##### So führen Sie den bitonischen Sortieralgorithmus parallel aus  
  
1.  Fügen Sie für die Headerdatei ppl.h eine `#include`\-Direktive hinzu.  
  
     [!CODE [concrt-parallel-bitonic-sort#10](../CodeSnippet/VS_Snippets_ConcRT/concrt-parallel-bitonic-sort#10)]  
  
2.  Fügen Sie für den `concurrency`\-Namespace eine `using`\-Direktive hinzu.  
  
     [!CODE [concrt-parallel-bitonic-sort#11](../CodeSnippet/VS_Snippets_ConcRT/concrt-parallel-bitonic-sort#11)]  
  
3.  Erstellen Sie die neue Funktion `parallel_bitonic_mege` für den `parallel_invoke`\-Algorithmus, um die Sequenzen parallel zusammenzuführen, wenn genügend Arbeit vorhanden ist.  Rufen Sie andernfalls `bitonic_merge` auf, um die Sequenzen seriell zusammenzuführen.  
  
     [!CODE [concrt-parallel-bitonic-sort#2](../CodeSnippet/VS_Snippets_ConcRT/concrt-parallel-bitonic-sort#2)]  
  
4.  Führen Sie einen Prozess aus, der demjenigen im Schritt weiter oben gleicht, jedoch für die `bitonic_sort`\-Funktion ausgeführt wird.  
  
     [!CODE [concrt-parallel-bitonic-sort#3](../CodeSnippet/VS_Snippets_ConcRT/concrt-parallel-bitonic-sort#3)]  
  
5.  Erstellen Sie eine überladene Version der `parallel_bitonic_sort`\-Funktion, durch die das Array in aufsteigender Reihenfolge sortiert wird.  
  
     [!CODE [concrt-parallel-bitonic-sort#4](../CodeSnippet/VS_Snippets_ConcRT/concrt-parallel-bitonic-sort#4)]  
  
 Mit dem `parallel_invoke`\-Algorithmus wird der Aufwand reduziert, indem die letzte einer Reihe von Aufgaben im aufrufenden Kontext ausgeführt wird.  Beispielsweise wird in der `parallel_bitonic_sort`\-Funktion die erste Aufgabe in einem separaten Kontext und die zweite Aufgabe im aufrufenden Kontext ausgeführt.  
  
 [!CODE [concrt-parallel-bitonic-sort#5](../CodeSnippet/VS_Snippets_ConcRT/concrt-parallel-bitonic-sort#5)]  
  
 Im folgenden vollständigen Beispiel wird sowohl die serielle als auch die parallele Version des bitonischen Sortieralgorithmus durchgeführt.  Das Beispiel gibt außerdem die Zeit, die zum Ausführen beider Berechnungen benötigt wird, an der Konsole aus.  
  
 [!CODE [concrt-parallel-bitonic-sort#8](../CodeSnippet/VS_Snippets_ConcRT/concrt-parallel-bitonic-sort#8)]  
  
 Die folgende Beispielausgabe entspricht einem Ergebnis auf einem Computer mit vier Prozessoren.  
  
  **serial time: 4353**  
**parallel time: 1248** \[[Nach oben](#top)\]  
  
## Kompilieren des Codes  
 Zum Kompilieren kopieren Sie den Code, und fügen Sie ihn in ein Visual Studio\-Projekt ein, oder fügen Sie ihn in eine Datei mit dem Namen `parallel-bitonic-sort.cpp` ein, und führen Sie dann den folgenden Befehl in einem Visual Studio\-Eingabeaufforderungsfenster aus.  
  
 **cl.exe \/EHsc parallel\-bitonic\-sort.cpp**  
  
## Stabile Programmierung  
 In diesem Beispiel wird anstelle der [concurrency::task\_group](../Topic/task_group%20Class.md)\-Klasse der `parallel_invoke`\-Algorithmus verwendet, da die Lebensdauer der einzelnen Aufgabengruppen nicht über eine Funktion hinausreicht.  Es wird empfohlen, wenn möglich `parallel_invoke`\-Objekte zu verwenden, da diese im Vergleich zu `task group`\-Objekten einen geringeren Ausführungsaufwand erfordern, sodass Sie einen leistungsfähigeren Code schreiben können.  
  
 Die parallelen Versionen einiger Algorithmen erzielen nur eine bessere Leistung, wenn es genügend Arbeit gibt.  So ruft beispielsweise die `parallel_bitonic_merge`\-Funktion die serielle Version `bitonic_merge` auf, wenn in der Sequenz 500 oder weniger Elemente vorhanden sind.  Sie können die allgemeine Vorgehensweise bei der Sortierung auch an dem voraussichtlichen Arbeitsaufwand ausrichten.  Beispielsweise ist es möglicherweise effizienter, die serielle Version des QuickSort\-Algorithmus zu verwenden, wenn das Array weniger als 500 Elemente enthält, wie im folgenden Beispiel gezeigt:  
  
 [!CODE [concrt-parallel-bitonic-sort#9](../CodeSnippet/VS_Snippets_ConcRT/concrt-parallel-bitonic-sort#9)]  
  
 Analog zu allen anderen parallelen Algorithmen wird empfohlen, nach Bedarf Profile und Anpassungen für den Code bereitzustellen.  
  
## Siehe auch  
 [Aufgabenparallelität](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [parallel\_invoke\-Funktion](../Topic/parallel_invoke%20Function.md)