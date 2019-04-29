---
title: 'Vorgehensweise: Mithilfe von combinable kombinieren'
ms.date: 11/04/2016
helpviewer_keywords:
- combinable class, example
- combining sets with combinable [Concurrency Runtime]
ms.assetid: 66ffe8e3-6bbb-4e9f-b790-b612922a68a7
ms.openlocfilehash: bf8a5bee65ea0ba1718c1d4d436b6af3e0b95961
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62345577"
---
# <a name="how-to-use-combinable-to-combine-sets"></a>Vorgehensweise: Mithilfe von combinable kombinieren

In diesem Thema wird gezeigt, wie Sie mit der [Concurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) Klasse, um den Satz von Primzahlen zu berechnen.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird die Primzahlengruppe zweimal berechnet. Jede Berechnung speichert das Ergebnis in einem [Std:: Bitset](../../standard-library/bitset-class.md) Objekt. Im Beispiel wird die Primzahlengruppe zunächst seriell und anschließend parallel berechnet. Das Beispiel gibt außerdem die Zeit, die zum Ausführen beider Berechnungen benötigt wird, in der Konsole aus.

Dieses Beispiel verwendet die [Concurrency:: parallel_for](reference/concurrency-namespace-functions.md#parallel_for) Algorithmus und ein `combinable` Objekt, das Thread-lokalen Threadgruppen. Anschließend wird mithilfe der [Concurrency:: combine_each](reference/combinable-class.md#combine_each) Methode, um die Thread-lokalen Gruppen in den letzten Satz kombinieren.

[!code-cpp[concrt-parallel-combine-primes#1](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-combine-sets_1.cpp)]

Die folgende Beispielausgabe entspricht einem Ergebnis auf einem Computer mit vier Prozessoren.

```Output
serial time: 312 ms

parallel time: 78 ms
```

## <a name="compiling-the-code"></a>Kompilieren des Codes

Kopieren Sie den Beispielcode und fügen Sie ihn in ein Visual Studio-Projekt, oder fügen Sie ihn in eine Datei mit dem Namen `parallel-combine-primes.cpp` und führen Sie dann den folgenden Befehl in einem Fenster von Visual Studio-Eingabeaufforderung.

**/ EHsc CL.exe Parallel-Combine-primes.cpp**

## <a name="see-also"></a>Siehe auch

[Parallele Container und Objekte](../../parallel/concrt/parallel-containers-and-objects.md)<br/>
[combinable-Klasse](../../parallel/concrt/reference/combinable-class.md)<br/>
[combinable:: combine_each-Methode](reference/combinable-class.md#combine_each)
