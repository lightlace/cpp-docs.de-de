---
title: 'Vorgehensweise: Paralleles Ausführen von Zuordnungs- und Reduzierungsoperationen'
ms.date: 11/04/2016
helpviewer_keywords:
- parallel_transform function, example
- parallel map and reduce, example
- parallel_reduce function, example
ms.assetid: 9d19fac0-4ab6-4380-a375-3b18eeb87720
ms.openlocfilehash: 599e46c05a91a1f2ea6e317fe024d3c98a78977f
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77141709"
---
# <a name="how-to-perform-map-and-reduce-operations-in-parallel"></a>Vorgehensweise: Paralleles Ausführen von Zuordnungs- und Reduzierungsoperationen

Dieses Beispiel zeigt, wie Sie die Parallelität [::p arallel_transform](reference/concurrency-namespace-functions.md#parallel_transform) und Parallelität [::p arallel_reduce](reference/concurrency-namespace-functions.md#parallel_reduce) Algorithmen und die Klasse "parallelcurrency [:: concurrent_unordered_map](../../parallel/concrt/reference/concurrent-unordered-map-class.md) " verwenden, um die Vorkommen von Wörtern in Dateien zu zählen.

Ein *Zuordnungs Vorgang wendet eine Funktion* auf jeden Wert in einer Sequenz an. Ein *Reduzierungs* Vorgang kombiniert die Elemente einer Sequenz zu einem Wert. Zum Ausführen von Zuordnungs-und Reduzierungs Vorgängen können Sie die C++ Standard Bibliothek " [Std:: Transform](../../standard-library/algorithm-functions.md#transform) " und " [Std:: akkumul"](../../standard-library/numeric-functions.md#accumulate) verwenden. Zur Verbesserung der Leistung bei vielen Problemen können Sie mit dem `parallel_transform`-Algorithmus parallel den Zuordnungsvorgang und mit dem `parallel_reduce`-Algorithmus parallel den Reduzierungsvorgang ausführen. In einigen Fällen können Sie mit `concurrent_unordered_map` die Zuordnung und Reduzierung in einem Vorgang durchführen.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird das Vorkommen von Wörtern in Dateien gezählt. Der Inhalt von zwei Dateien wird mithilfe von " [Std:: Vector](../../standard-library/vector-class.md) " dargestellt. Der Zuordnungsvorgang berechnet das Vorkommen von jedem Wort in jedem Vektor. Der Reduzierungsvorang zählt die Wörter in den zwei Vektoren zusammen.

[!code-cpp[concrt-parallel-map-reduce#1](../../parallel/concrt/codesnippet/cpp/how-to-perform-map-and-reduce-operations-in-parallel_1.cpp)]

## <a name="compiling-the-code"></a>Kompilieren des Codes

Um den Code zu kompilieren, kopieren Sie ihn, und fügen Sie ihn in ein Visual Studio-Projekt ein, oder fügen Sie ihn in eine Datei mit dem Namen `parallel-map-reduce.cpp` ein, und führen Sie dann den folgenden Befehl in einem Visual Studio-Eingabe Aufforderungs Fenster aus.

> **cl. exe/EHsc parallel-Map-Reduce. cpp**

## <a name="robust-programming"></a>Robuste Programmierung

In diesem Beispiel können Sie mit der in concurrent_unordered_map.h definierten `concurrent_unordered_map`-Klasse die Zuordnung und Reduzierung in einem Vorgang durchführen.

[!code-cpp[concrt-parallel-map-reduce#2](../../parallel/concrt/codesnippet/cpp/how-to-perform-map-and-reduce-operations-in-parallel_2.cpp)]

In der Regel wird nur die äußere oder die innere Schleife parallel ausgeführt. Führen Sie die innere Schleife parallel aus, wenn Sie über relativ wenige Dateien mit vielen Wörtern verfügen. Führen Sie die äußere Schleife parallel aus, wenn Sie über relativ viele Dateien mit wenigen Wörtern verfügen.

## <a name="see-also"></a>Weitere Informationen

[Parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md)<br/>
[parallel_transform-Funktion](reference/concurrency-namespace-functions.md#parallel_transform)<br/>
[parallel_reduce-Funktion](reference/concurrency-namespace-functions.md#parallel_reduce)<br/>
[concurrent_unordered_map-Klasse](../../parallel/concrt/reference/concurrent-unordered-map-class.md)
