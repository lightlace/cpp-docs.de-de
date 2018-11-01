---
title: 'Gewusst wie: Verwenden von parallel_invoke zum Schreiben einer Runtime für paralleles Sortieren'
ms.date: 11/04/2016
helpviewer_keywords:
- task_handle class, example
- task_group class, example
- make_task function, example
- structured_task_group class, example
- improving parallel performance with task groups [Concurrency Runtime]
ms.assetid: 53979a2a-525d-4437-8952-f1ff85b37673
ms.openlocfilehash: e72d99cb1b9168e3de1e109d93c163e21cb7fad7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50440156"
---
# <a name="how-to-use-parallelinvoke-to-write-a-parallel-sort-routine"></a>Gewusst wie: Verwenden von parallel_invoke zum Schreiben einer Runtime für paralleles Sortieren

Dieses Dokument beschreibt, wie die [Parallel_invoke](../../parallel/concrt/parallel-algorithms.md#parallel_invoke) -Algorithmus die Leistung des bitonischen Sortieralgorithmus verbessert werden kann. Der bitonische Sortieralgorithmus unterteilt die Eingabesequenz rekursiv in kleinere sortierte Partitionen. Der bitonische Sortieralgorithmus kann parallel ausgeführt werden, da alle Partitionsvorgänge von allen anderen Vorgängen unabhängig sind.

Obwohl das bitonische sortieren ein Beispiel ist eine *sortiernetzwerk* , die alle Kombinationen von Eingabesequenzen sortiert, die in diesem Beispiel sortiert, deren Länge eine Potenz von zwei sind, Sequenzen.

> [!NOTE]
>  Dieses Beispiel verwendet eine parallele Sortierungsroutine zur Veranschaulichung. Sie können auch die integrierten Sortieralgorithmen, der die PPL bereitstellt: [Concurrency:: parallel_sort](reference/concurrency-namespace-functions.md#parallel_sort), [Concurrency:: parallel_buffered_sort](reference/concurrency-namespace-functions.md#parallel_buffered_sort), und [concurrency::parallel_ Radixsort](reference/concurrency-namespace-functions.md#parallel_radixsort). Weitere Informationen finden Sie unter [parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md).

##  <a name="top"></a> Abschnitte

In diesem Dokument werden die folgenden Aufgaben erläutert:

- [Ausführen der Bitonischen Sortierung](#serial)

- [Verwenden von Parallel_invoke für Bitonische parallel](#parallel)

##  <a name="serial"></a> Ausführen der Bitonischen Sortierung

Im folgenden Beispiel wird die serielle Version des bitonischen Sortieralgorithmus dargestellt. Die `bitonic_sort`-Funktion unterteilt die Sequenz in zwei Partitionen, sortiert diese Partitionen in entgegengesetzten Richtungen, und führt dann die Ergebnisse zusammen. Diese Funktion ruft sich selbst zweimal auf, um alle Partitionen rekursiv zu sortieren.

[!code-cpp[concrt-parallel-bitonic-sort#1](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_1.cpp)]

[[Nach oben](#top)]

##  <a name="parallel"></a> Verwenden von Parallel_invoke für Bitonische parallel

In diesem Abschnitt wird beschrieben, wie der bitonischen Sortieralgorithmus mit dem `parallel_invoke`-Algorithmus parallel ausgeführt werden kann.

### <a name="procedures"></a>Verfahren

##### <a name="to-perform-the-bitonic-sort-algorithm-in-parallel"></a>So führen Sie den bitonischen Sortieralgorithmus parallel aus

1. Fügen Sie für die Headerdatei ppl.h eine `#include`-Anweisung hinzu.

[!code-cpp[concrt-parallel-bitonic-sort#10](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_2.cpp)]

1. Fügen Sie eine `using`-Anweisung für den `concurrency`-Namespace hinzu.

[!code-cpp[concrt-parallel-bitonic-sort#11](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_3.cpp)]

1. Erstellen Sie die neue Funktion `parallel_bitonic_mege` für den `parallel_invoke`-Algorithmus, um die Sequenzen parallel zusammenzuführen, wenn genügend Arbeit vorhanden ist. Rufen Sie andernfalls `bitonic_merge` auf, um die Sequenzen seriell zusammenzuführen.

[!code-cpp[concrt-parallel-bitonic-sort#2](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_4.cpp)]

1. Führen Sie einen Prozess aus, der demjenigen im Schritt weiter oben gleicht, jedoch für die `bitonic_sort`-Funktion ausgeführt wird.

[!code-cpp[concrt-parallel-bitonic-sort#3](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_5.cpp)]

1. Erstellen Sie eine überladene Version der `parallel_bitonic_sort`-Funktion, durch die das Array in aufsteigender Reihenfolge sortiert wird.

[!code-cpp[concrt-parallel-bitonic-sort#4](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_6.cpp)]

Mit dem `parallel_invoke`-Algorithmus wird der Aufwand reduziert, indem die letzte einer Reihe von Aufgaben im aufrufenden Kontext ausgeführt wird. Beispielsweise wird in der `parallel_bitonic_sort`-Funktion die erste Aufgabe in einem separaten Kontext und die zweite Aufgabe im aufrufenden Kontext ausgeführt.

[!code-cpp[concrt-parallel-bitonic-sort#5](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_7.cpp)]

Im folgenden vollständigen Beispiel wird sowohl die serielle als auch die parallele Version des bitonischen Sortieralgorithmus durchgeführt. Das Beispiel gibt außerdem die Zeit, die zum Ausführen beider Berechnungen benötigt wird, an der Konsole aus.

[!code-cpp[concrt-parallel-bitonic-sort#8](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_8.cpp)]

Die folgende Beispielausgabe entspricht einem Ergebnis auf einem Computer mit vier Prozessoren.

```Output
serial time: 4353
parallel time: 1248
```

[[Nach oben](#top)]

## <a name="compiling-the-code"></a>Kompilieren des Codes

Um den Code zu kompilieren, kopieren Sie ihn und fügen Sie ihn in ein Visual Studio-Projekt ein, oder fügen Sie ihn in eine Datei mit dem Namen `parallel-bitonic-sort.cpp` und führen Sie dann den folgenden Befehl in einem Fenster von Visual Studio-Eingabeaufforderung.

**/ EHsc CL.exe Parallel-Bitonic-sort.cpp**

## <a name="robust-programming"></a>Stabile Programmierung

Dieses Beispiel verwendet die `parallel_invoke` Algorithmus anstelle von der [Concurrency:: task_group](reference/task-group-class.md) Klasse, da die Lebensdauer der einzelnen Aufgabengruppen nicht über eine Funktion hinausreicht. Es wird empfohlen, wenn möglich `parallel_invoke`-Objekte zu verwenden, da diese im Vergleich zu `task group`-Objekten einen geringeren Ausführungsaufwand erfordern, sodass Sie einen leistungsfähigeren Code schreiben können.

Die parallelen Versionen einiger Algorithmen erzielen nur eine bessere Leistung, wenn es genügend Arbeit gibt. So ruft beispielsweise die `parallel_bitonic_merge`-Funktion die serielle Version `bitonic_merge` auf, wenn in der Sequenz 500 oder weniger Elemente vorhanden sind. Sie können die allgemeine Vorgehensweise bei der Sortierung auch an dem voraussichtlichen Arbeitsaufwand ausrichten. Beispielsweise ist es möglicherweise effizienter, die serielle Version des QuickSort-Algorithmus zu verwenden, wenn das Array weniger als 500 Elemente enthält, wie im folgenden Beispiel gezeigt:

[!code-cpp[concrt-parallel-bitonic-sort#9](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine_9.cpp)]

Analog zu allen anderen parallelen Algorithmen wird empfohlen, nach Bedarf Profile und Anpassungen für den Code bereitzustellen.

## <a name="see-also"></a>Siehe auch

[Aufgabenparallelität](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[Parallel_invoke-Funktion](reference/concurrency-namespace-functions.md#parallel_invoke)

