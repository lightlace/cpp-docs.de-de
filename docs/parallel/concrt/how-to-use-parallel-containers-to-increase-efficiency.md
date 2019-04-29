---
title: 'Vorgehensweise: Erhöhen der Effizienz mithilfe von parallelen Containern'
ms.date: 11/04/2016
helpviewer_keywords:
- increasing efficiency with parallel containers [Concurrency Runtime]
- concurrent_queue class, examples
- concurrent_vector class, examples
ms.assetid: bd00046d-e9b6-4ae1-b661-3995f671b867
ms.openlocfilehash: 2479915b167ee3dbc2ce43d9c2733efc74818bbe
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394441"
---
# <a name="how-to-use-parallel-containers-to-increase-efficiency"></a>Vorgehensweise: Erhöhen der Effizienz mithilfe von parallelen Containern

In diesem Thema wird aufgezeigt, wie parallele Container verwendet werden, um Daten effizient zu speichern und parallel auf sie zuzugreifen.

Im Beispielcode werden der Satz von Primzahlen und Carmichael-Zahlen parallel berechnet. Anschließend berechnet der Code für jede Carmichael-Zahl die Primfaktoren dieser Zahl.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird die `is_prime`-Funktion gezeigt, durch die bestimmt wird, ob ein Eingabewert eine Primzahl ist, und die `is_carmichael`-Funktion, durch die bestimmt wird, ob der Eingabewert eine Carmichael-Zahl ist.

[!code-cpp[concrt-carmichael-primes#1](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-containers-to-increase-efficiency_1.cpp)]

## <a name="example"></a>Beispiel

Im folgenden Beispiel werden die Funktionen `is_prime` und `is_carmichael` zum Berechnen der Sätze von Primzahlen und Carmichael-Zahlen verwendet. Im Beispiel wird die [Concurrency:: parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) und [Concurrency:: parallel_for](reference/concurrency-namespace-functions.md#parallel_for) Algorithmen zum Berechnen der einzelnen parallel festgelegt. Weitere Informationen zu parallelen Algorithmen finden Sie unter [parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md).

Dieses Beispiel verwendet eine [Concurrency:: concurrent_queue](../../parallel/concrt/reference/concurrent-queue-class.md) Objekt, das den Satz von Carmichael Zahlen verwendet, da dieses Objekt später als Arbeitswarteschlange eingesetzt wird. Er verwendet eine [Concurrency:: concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) Objekt, das den Satz von Primzahlen speichern, weil es später noch Mal festgelegt wird, um Primfaktoren zu suchen durchlaufen wird.

[!code-cpp[concrt-carmichael-primes#2](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-containers-to-increase-efficiency_2.cpp)]

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird die `prime_factors_of`-Funktion veranschaulicht, von der die Versuchsdivision verwendet wird, um alle Primfaktoren des angegebenen Werts zu suchen.

Diese Funktion verwendet die [Concurrency:: parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) Algorithmus zum Durchlaufen der Auflistung von Primzahlen. Das `concurrent_vector`-Objekt macht es möglich, dass die parallele Schleife dem Ergebnis gleichzeitig Primfaktoren hinzufügen kann.

[!code-cpp[concrt-carmichael-primes#3](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-containers-to-increase-efficiency_3.cpp)]

## <a name="example"></a>Beispiel

In diesem Beispiel wird jedes Element in der Warteschlange von Carmichael-Zahlen verarbeitet, indem zum Berechnen der Primfaktoren die `prime_factors_of`-Funktion aufgerufen wird. Es führt diese Arbeit mithilfe einer Aufgabengruppe parallel aus. Weitere Informationen zu Aufgabengruppen finden Sie unter [Aufgabenparallelität](../../parallel/concrt/task-parallelism-concurrency-runtime.md).

In diesem Beispiel werden die Primfaktoren für jede Carmichael-Zahl gedruckt, wenn diese Zahl mehr als vier Primfaktoren hat.

[!code-cpp[concrt-carmichael-primes#4](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-containers-to-increase-efficiency_4.cpp)]

## <a name="example"></a>Beispiel

Im folgenden Code wird das vollständige Beispiel veranschaulicht, in dem parallele Container zum Berechnen der Primfaktoren der Carmichael-Zahlen verwendet werden.

[!code-cpp[concrt-carmichael-primes#5](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-containers-to-increase-efficiency_5.cpp)]

Dieses Beispiel erzeugt die folgende Beispielausgabe.

```Output
Prime factors of 9890881 are: 7 11 13 41 241.
Prime factors of 825265 are: 5 7 17 19 73.
Prime factors of 1050985 are: 5 13 19 23 37.
```

## <a name="compiling-the-code"></a>Kompilieren des Codes

Kopieren Sie den Beispielcode und fügen Sie ihn in ein Visual Studio-Projekt, oder fügen Sie ihn in eine Datei mit dem Namen `carmichael-primes.cpp` und führen Sie dann den folgenden Befehl in einem Fenster von Visual Studio-Eingabeaufforderung.

**CL.exe/EHsc Carmichael-primes.cpp**

## <a name="see-also"></a>Siehe auch

[Parallele Container und Objekte](../../parallel/concrt/parallel-containers-and-objects.md)<br/>
[Aufgabenparallelität](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[concurrent_vector-Klasse](../../parallel/concrt/reference/concurrent-vector-class.md)<br/>
[concurrent_queue-Klasse](../../parallel/concrt/reference/concurrent-queue-class.md)<br/>
[Parallel_invoke-Funktion](reference/concurrency-namespace-functions.md#parallel_invoke)<br/>
[Parallel_for-Funktion](reference/concurrency-namespace-functions.md#parallel_for)<br/>
[task_group-Klasse](reference/task-group-class.md)
