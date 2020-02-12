---
title: 'Gewusst wie: Schreiben einer parallel_for_each-Schleife'
ms.date: 11/04/2016
helpviewer_keywords:
- writing a parallel_for_each loop [Concurrency Runtime]
- parallel_for_each function, example
ms.assetid: fa9c0ba6-ace0-4f88-8681-c7c1f52aff20
ms.openlocfilehash: 10c281b7db92e2706b20a1c7377fcdb9d924152d
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77141872"
---
# <a name="how-to-write-a-parallel_for_each-loop"></a>Gewusst wie: Schreiben einer parallel_for_each-Schleife

In diesem Beispiel wird gezeigt, wie der Parallelitäts [::p arallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) -Algorithmus verwendet wird, um die Anzahl von Primzahlen in einem [Std:: Array](../../standard-library/array-class-stl.md) -Objekt parallel zu berechnen.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird die Anzahl von Primzahlen in einem Array zweimal berechnet. Das Beispiel verwendet zunächst den [Std:: for_each](../../standard-library/algorithm-functions.md#for_each) -Algorithmus, um die Anzahl serialisiert zu berechnen. Anschließend wird die gleiche Aufgabe mit dem `parallel_for_each`-Algorithmus parallel ausgeführt. Das Beispiel gibt außerdem die Zeit, die zum Ausführen beider Berechnungen benötigt wird, in der Konsole aus.

[!code-cpp[concrt-parallel-count-primes#1](../../parallel/concrt/codesnippet/cpp/how-to-write-a-parallel-for-each-loop_1.cpp)]

Die folgende Beispielausgabe entspricht einem Ergebnis auf einem Computer mit vier Prozessoren.

```Output
serial version:
found 17984 prime numbers
took 6115 ms

parallel version:
found 17984 prime numbers
took 1653 ms
```

## <a name="compiling-the-code"></a>Kompilieren des Codes

Um den Code zu kompilieren, kopieren Sie ihn, und fügen Sie ihn in ein Visual Studio-Projekt ein, oder fügen Sie ihn in eine Datei mit dem Namen `parallel-count-primes.cpp` ein, und führen Sie dann den folgenden Befehl in einem Visual Studio-Eingabe Aufforderungs Fenster aus.

> **cl. exe/EHsc parallel-count-primes. cpp**

## <a name="robust-programming"></a>Robuste Programmierung

Der Lambdaausdruck, der im Beispiel an den `parallel_for_each`-Algorithmus übergeben wird, aktiviert mithilfe der `InterlockedIncrement`-Funktion parallele Iterationen der Schleife, um den Zähler gleichzeitig zu inkrementieren. Wenn Sie Funktionen wie z. B. `InterlockedIncrement` verwenden, um Zugriff auf freigegebene Ressourcen zu synchronisieren, kann es zu Leistungsengpässen im Code kommen. Sie können einen Sperr freien Synchronisierungs Mechanismus, z. b. die Klasse " [parallelcurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) ", verwenden, um den gleichzeitigen Zugriff auf freigegebene Ressourcen zu vermeiden. Ein Beispiel, in dem die `combinable`-Klasse auf diese Weise verwendet wird, finden Sie unter Gewusst [wie: verbessern der Leistung mithilfe von combinable](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md).

## <a name="see-also"></a>Weitere Informationen

[Parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md)<br/>
[Parallel_for_each-Funktion](reference/concurrency-namespace-functions.md#parallel_for_each)
