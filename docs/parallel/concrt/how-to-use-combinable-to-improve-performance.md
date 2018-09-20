---
title: 'Gewusst wie: mithilfe von combinable zum Verbessern der Leistung | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- combinable class, example
- improving parallel performance with combinable [Concurrency Runtime]
ms.assetid: fa730580-1c94-4b2d-8aec-57c91dc0497e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 22425ac212ee2bfb52354044b1a6193b6a9cd11a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46432087"
---
# <a name="how-to-use-combinable-to-improve-performance"></a>Gewusst wie: Verbessern der Leistung mithilfe von combinable

Dieses Beispiel zeigt, wie Sie mit der [Concurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) Klasse zum Berechnen der Summe der Zahlen in einem [Std:: Array](../../standard-library/array-class-stl.md) -Objekt, das um Primzahlen handelt. Die `combinable`-Klasse steigert die Leistung, indem sie Freigabezustand ausschließt.

> [!TIP]
>  In einigen Fällen parallele Zuordnung ([Concurrency:: parallel_transform](reference/concurrency-namespace-functions.md#parallel_transform)) und reduzieren ([Concurrency:: Parallel_reduce](reference/concurrency-namespace-functions.md#parallel_reduce)) zu leistungsverbesserungen über `combinable`. Ein Beispiel, verwendet Map- und reduce-Vorgänge aus, um die gleichen Ergebnisse wie in diesem Beispiel zu erzeugen, finden Sie unter [parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird die [Std:: Accumulate](../../standard-library/numeric-functions.md#accumulate) Funktion, um die Summe der Elemente in einem Array zu berechnen, die Primzahlen sind. In diesem Beispiel ist `a` ein `array`-Objekt, und die `is_prime`-Funktion bestimmt, ob sein Eingabewert eine Primzahl ist.

[!code-cpp[concrt-parallel-sum-of-primes#1](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-improve-performance_1.cpp)]

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt einen naiven Weg, das vorherige Beispiel zu parallelisieren. Dieses Beispiel verwendet die [Concurrency:: parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) Algorithmus, um das Array parallel zu verarbeiten und eine [Concurrency:: critical_section](../../parallel/concrt/reference/critical-section-class.md) Objekt zum Synchronisieren des Zugriffs auf die `prime_sum` Variable . Dieses Beispiel skaliert nicht, da jeder Thread warten muss, bis die freigegebene Ressource verfügbar wird.

[!code-cpp[concrt-parallel-sum-of-primes#2](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-improve-performance_2.cpp)]

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird ein `combinable`-Objekt zum Steigern der Leistung des vorherigen Beispiels verwendet. In diesem Beispiel sind keine Synchronisierungsobjekte erforderlich. Es skaliert, da das `combinable`-Objekt dafür sorgt, dass jeder Thread seine Aufgabe unabhängig ausführt.

Ein `combinable`-Objekt wird in der Regel in zwei Schritten verwendet. Erzeugen Sie zuerst eine Reihe von differenzierten Berechnungen, indem Sie Arbeiten parallel ausführen. Fassen Sie danach die Berechnungen in einem Endergebnis zusammen (oder reduzieren Sie sie). Dieses Beispiel verwendet die [Concurrency::combinable::local](reference/combinable-class.md#local) Methode, um einen Verweis auf die lokale Summe zu erhalten. Anschließend wird mithilfe der [Concurrency::combinable::combine](reference/combinable-class.md#combine) Methode und eine [Std:: plus](../../standard-library/plus-struct.md) Objekt, das die lokalen Berechnungen zum Endergebnis kombinieren.

[!code-cpp[concrt-parallel-sum-of-primes#3](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-improve-performance_3.cpp)]

## <a name="example"></a>Beispiel

Im folgenden vollständigen Beispiel wird die Summe von Primzahlen sowohl seriell als auch parallel berechnet. Das Beispiel gibt die Zeit, die zum Ausführen beider Berechnungen benötigt wird, in der Konsole aus.

[!code-cpp[concrt-parallel-sum-of-primes#4](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-improve-performance_4.cpp)]

Die folgende Beispielausgabe entspricht einem Ergebnis auf einem Computer mit vier Prozessoren.

```Output
1709600813
serial time: 6178 ms

1709600813
parallel time: 1638 ms
```

## <a name="compiling-the-code"></a>Kompilieren des Codes

Um den Code zu kompilieren, kopieren Sie ihn und fügen Sie ihn in ein Visual Studio-Projekt ein, oder fügen Sie ihn in eine Datei mit dem Namen `parallel-sum-of-primes.cpp` und führen Sie dann den folgenden Befehl in einem Fenster von Visual Studio-Eingabeaufforderung.

**CL.exe/EHsc Parallel-Sum-of-primes.cpp**

## <a name="robust-programming"></a>Stabile Programmierung

Ein Beispiel, verwendet Map- und reduce-Vorgänge aus, um die gleichen Ergebnisse zu erzielen, finden Sie unter [parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md).

## <a name="see-also"></a>Siehe auch

[Parallele Container und Objekte](../../parallel/concrt/parallel-containers-and-objects.md)<br/>
[combinable-Klasse](../../parallel/concrt/reference/combinable-class.md)<br/>
[critical_section-Klasse](../../parallel/concrt/reference/critical-section-class.md)
