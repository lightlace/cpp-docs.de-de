---
title: 'Vorgehensweise: Verbessern der Leistung mithilfe von combinable'
ms.date: 11/04/2016
helpviewer_keywords:
- combinable class, example
- improving parallel performance with combinable [Concurrency Runtime]
ms.assetid: fa730580-1c94-4b2d-8aec-57c91dc0497e
ms.openlocfilehash: db27a791b2b92102118606712db4cbd2920f9619
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142440"
---
# <a name="how-to-use-combinable-to-improve-performance"></a>Vorgehensweise: Verbessern der Leistung mithilfe von combinable

In diesem Beispiel wird gezeigt, wie die Klasse " [parallelcurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) " verwendet wird, um die Summe der Zahlen in einem " [Std:: Array](../../standard-library/array-class-stl.md) "-Objekt zu berechnen, die Primzahlen sind. Die `combinable`-Klasse steigert die Leistung, indem sie Freigabezustand ausschließt.

> [!TIP]
> In einigen Fällen kann eine parallele Zuordnung (Parallelität[::p arallel_transform](reference/concurrency-namespace-functions.md#parallel_transform)) und reduce (Parallelität[:: parallel_reduce](reference/concurrency-namespace-functions.md#parallel_reduce)) Leistungsverbesserungen gegenüber `combinable`bereitstellen. Ein Beispiel, in dem Map-und Reduce-Vorgänge verwendet werden, um die gleichen Ergebnisse wie dieses Beispiel zu erzielen, finden Sie unter [parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md).

## <a name="example---accumulate"></a>Beispiel: kumulieren

Im folgenden Beispiel wird die [Std:: akkumul-](../../standard-library/numeric-functions.md#accumulate) Funktion verwendet, um die Summe der Elemente in einem Array zu berechnen, die Primzahlen sind. In diesem Beispiel ist `a` ein `array`-Objekt, und die `is_prime`-Funktion bestimmt, ob sein Eingabewert eine Primzahl ist.

[!code-cpp[concrt-parallel-sum-of-primes#1](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-improve-performance_1.cpp)]

## <a name="example---parallel_for_each"></a>Beispiel-parallel_for_each

Das folgende Beispiel zeigt einen naiven Weg, das vorherige Beispiel zu parallelisieren. In diesem Beispiel wird der [parallelcurrency::p arallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) -Algorithmus verwendet, um das Array parallel und ein [parallelcurrency:: CRITICAL_SECTION](../../parallel/concrt/reference/critical-section-class.md) -Objekt zu verarbeiten, um den Zugriff auf die `prime_sum` Variable zu synchronisieren. Dieses Beispiel skaliert nicht, da jeder Thread warten muss, bis die freigegebene Ressource verfügbar wird.

[!code-cpp[concrt-parallel-sum-of-primes#2](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-improve-performance_2.cpp)]

## <a name="example---combinable"></a>Beispiel: combinable

Im folgenden Beispiel wird ein `combinable`-Objekt zum Steigern der Leistung des vorherigen Beispiels verwendet. In diesem Beispiel sind keine Synchronisierungsobjekte erforderlich. Es skaliert, da das `combinable`-Objekt dafür sorgt, dass jeder Thread seine Aufgabe unabhängig ausführt.

Ein `combinable`-Objekt wird in der Regel in zwei Schritten verwendet. Erzeugen Sie zuerst eine Reihe von differenzierten Berechnungen, indem Sie Arbeiten parallel ausführen. Fassen Sie danach die Berechnungen in einem Endergebnis zusammen (oder reduzieren Sie sie). In diesem Beispiel wird die Methode " [parallelcurrency:: combinable:: local](reference/combinable-class.md#local) " verwendet, um einen Verweis auf die lokale Summe zu erhalten. Anschließend werden die lokalen Berechnungen mithilfe der [parallelcurrency:: combinable:: Combine](reference/combinable-class.md#combine) -Methode und eines [Std::p lus](../../standard-library/plus-struct.md) -Objekts in das Endergebnis integriert.

[!code-cpp[concrt-parallel-sum-of-primes#3](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-improve-performance_3.cpp)]

## <a name="example---serial-and-parallel"></a>Beispiel: seriell und parallel

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

Um den Code zu kompilieren, kopieren Sie ihn, und fügen Sie ihn in ein Visual Studio-Projekt ein, oder fügen Sie ihn in eine Datei mit dem Namen `parallel-sum-of-primes.cpp` ein, und führen Sie dann den folgenden Befehl in einem Visual Studio-Eingabe Aufforderungs Fenster aus.

> **cl. exe/EHsc parallel-Sum-of-primes. cpp**

## <a name="robust-programming"></a>Robuste Programmierung

Ein Beispiel, in dem Map-und Reduce-Vorgänge verwendet werden, um die gleichen Ergebnisse zu erzielen, finden Sie unter [parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md).

## <a name="see-also"></a>Weitere Informationen

[Parallele Container und Objekte](../../parallel/concrt/parallel-containers-and-objects.md)<br/>
[combinable-Klasse](../../parallel/concrt/reference/combinable-class.md)<br/>
[critical_section-Klasse](../../parallel/concrt/reference/critical-section-class.md)
