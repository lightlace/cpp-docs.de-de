---
title: 'Vorgehensweise: Verwenden eines Abbruchs zum Verlassen einer Parallel-Schleife | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- writing a parallel search algorithm [Concurrency Runtime]
- parallel search algorithm, writing [Concurrency Runtime]
ms.assetid: 421cd2de-f058-465f-b890-dd8fcc0df273
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9172132f0bdaabea9d6959a3f947d7b50d5261da
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46417331"
---
# <a name="how-to-use-cancellation-to-break-from-a-parallel-loop"></a>Gewusst wie: Verwenden eines Abbruchs zum Verlassen einer Parallel-Schleife

Dieses Beispiel zeigt, wie Sie den Abbruch zu verwenden, um eine grundlegende paralleler Suchalgorithmus implementiert wird.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird die Abbruch für ein Element in einem Array zu suchen. Die `parallel_find_any` Funktion verwendet die [Concurrency:: parallel_for](reference/concurrency-namespace-functions.md#parallel_for) Algorithmus und die [Concurrency:: run_with_cancellation_token](reference/concurrency-namespace-functions.md#run_with_cancellation_token) Funktion, die für die Position zu suchen, die den angegebenen Wert enthält. Wenn den Wert von die parallele Schleife gefunden wird, ruft er die [Concurrency::cancellation_token_source::cancel](reference/cancellation-token-source-class.md#cancel) Methode, um zukünftige Arbeitsvorgänge abzubrechen.

[!code-cpp[concrt-parallel-array-search#1](../../parallel/concrt/codesnippet/cpp/how-to-use-cancellation-to-break-from-a-parallel-loop_1.cpp)]

Die [Concurrency:: parallel_for](reference/concurrency-namespace-functions.md#parallel_for) Algorithmus fungiert gleichzeitig. Aus diesem Grund ist es nicht die Vorgänge in einer vordefinierten Reihenfolge ausführen. Wenn das Array, mehrere Instanzen des Werts enthält, kann das Ergebnis eines der Positionen sein.

## <a name="compiling-the-code"></a>Kompilieren des Codes

Kopieren Sie den Beispielcode und fügen Sie ihn in ein Visual Studio-Projekt, oder fügen Sie ihn in eine Datei mit dem Namen `parallel-array-search.cpp` und führen Sie dann den folgenden Befehl in einem Fenster von Visual Studio-Eingabeaufforderung.

**/ EHsc CL.exe Parallel-Array-search.cpp**

## <a name="see-also"></a>Siehe auch

[Abbruch in der PPL](cancellation-in-the-ppl.md)<br/>
[Parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md)<br/>
[Parallel_for-Funktion](reference/concurrency-namespace-functions.md#parallel_for)<br/>
[cancellation_token_source-Klasse](../../parallel/concrt/reference/cancellation-token-source-class.md)
