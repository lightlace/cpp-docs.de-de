---
title: 'Gewusst wie: Schreiben einer Parallel_for_each-Schleife | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- writing a parallel_for_each loop [Concurrency Runtime]
- parallel_for_each function, example
ms.assetid: fa9c0ba6-ace0-4f88-8681-c7c1f52aff20
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4c68afa77c46e4d57ef01984b44ecb6f4951494a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46427081"
---
# <a name="how-to-write-a-parallelforeach-loop"></a>Gewusst wie: Schreiben einer parallel_for_each-Schleife

Dieses Beispiel zeigt, wie Sie mit der [Concurrency:: parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) Algorithmus zum Berechnen der Anzahl von Primzahlen in einem [Std:: Array](../../standard-library/array-class-stl.md) -Objekt parallel.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird die Anzahl von Primzahlen in einem Array zweimal berechnet. Im Beispiel wird zuerst mit der [Std:: for_each](../../standard-library/algorithm-functions.md#for_each) Algorithmus, um die Anzahl der seriell berechnet. Anschließend wird die gleiche Aufgabe mit dem `parallel_for_each`-Algorithmus parallel ausgeführt. Das Beispiel gibt außerdem die Zeit, die zum Ausführen beider Berechnungen benötigt wird, in der Konsole aus.

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

Um den Code zu kompilieren, kopieren Sie ihn und fügen Sie ihn in ein Visual Studio-Projekt ein, oder fügen Sie ihn in eine Datei mit dem Namen `parallel-count-primes.cpp` und führen Sie dann den folgenden Befehl in einem Fenster von Visual Studio-Eingabeaufforderung.

**/ EHsc CL.exe Parallel-Count-primes.cpp**

## <a name="robust-programming"></a>Stabile Programmierung

Der Lambda-Ausdruck, der im Beispiel an den `parallel_for_each`-Algorithmus übergeben wird, aktiviert mithilfe der `InterlockedIncrement`-Funktion parallele Iterationen der Schleife, um den Zähler gleichzeitig zu inkrementieren. Wenn Sie Funktionen wie z. B. `InterlockedIncrement` verwenden, um Zugriff auf freigegebene Ressourcen zu synchronisieren, kann es zu Leistungsengpässen im Code kommen. Sie verwenden einen sperrenfreien Synchronisierungsmechanismus, z. B. die [Concurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) -Klasse, um den gleichzeitigen Zugriff auf freigegebene Ressourcen zu vermeiden. Ein Beispiel für die Verwendung der `combinable` -Klasse auf diese Weise, finden Sie unter [Vorgehensweise: mithilfe von combinable zum Verbessern der Leistung](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md).

## <a name="see-also"></a>Siehe auch

[Parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md)<br/>
[Parallel_for_each-Funktion](reference/concurrency-namespace-functions.md#parallel_for_each)

