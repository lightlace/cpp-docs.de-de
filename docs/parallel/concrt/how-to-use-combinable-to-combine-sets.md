---
title: 'Vorgehensweise: Kombinieren von Gruppen mithilfe von combinable'
ms.date: 11/04/2016
helpviewer_keywords:
- combinable class, example
- combining sets with combinable [Concurrency Runtime]
ms.assetid: 66ffe8e3-6bbb-4e9f-b790-b612922a68a7
ms.openlocfilehash: 7ccbb3e8bad5c4d3b6f4177afbfdba3e200681a5
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142120"
---
# <a name="how-to-use-combinable-to-combine-sets"></a>Vorgehensweise: Kombinieren von Gruppen mithilfe von combinable

In diesem Thema wird gezeigt, wie die Klasse " [parallelcurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) " verwendet wird, um den Satz von Primzahlen zu berechnen.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird die Primzahlengruppe zweimal berechnet. Jede Berechnung speichert das Ergebnis in einem [Std:: Bitset](../../standard-library/bitset-class.md) -Objekt. Im Beispiel wird die Primzahlengruppe zunächst seriell und anschließend parallel berechnet. Das Beispiel gibt außerdem die Zeit, die zum Ausführen beider Berechnungen benötigt wird, in der Konsole aus.

In diesem Beispiel werden die Parallelität [::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) -Algorithmus und ein `combinable`-Objekt verwendet, um Thread lokale Datasets zu generieren. Anschließend wird mithilfe der Methode " [parallelcurrency:: combinable:: combine_each](reference/combinable-class.md#combine_each) " die Thread lokalen Sätze in der endgültigen Menge kombiniert.

[!code-cpp[concrt-parallel-combine-primes#1](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-combine-sets_1.cpp)]

Die folgende Beispielausgabe entspricht einem Ergebnis auf einem Computer mit vier Prozessoren.

```Output
serial time: 312 ms

parallel time: 78 ms
```

## <a name="compiling-the-code"></a>Kompilieren des Codes

Kopieren Sie den Beispielcode, und fügen Sie ihn in ein Visual Studio-Projekt ein, oder fügen Sie ihn in eine Datei mit dem Namen `parallel-combine-primes.cpp` ein, und führen Sie dann den folgenden Befehl in einem Visual Studio-Eingabe Aufforderungs Fenster aus.

> **cl. exe/EHsc parallel-Combine-primes. cpp**

## <a name="see-also"></a>Weitere Informationen

[Parallele Container und Objekte](../../parallel/concrt/parallel-containers-and-objects.md)<br/>
[combinable-Klasse](../../parallel/concrt/reference/combinable-class.md)<br/>
[combinable:: Combine_each-Methode](reference/combinable-class.md#combine_each)
