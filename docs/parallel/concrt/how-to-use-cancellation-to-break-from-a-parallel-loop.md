---
title: 'Vorgehensweise: Verwenden eines Abbruchs zum Verlassen einer Parallel-Schleife'
ms.date: 11/04/2016
helpviewer_keywords:
- writing a parallel search algorithm [Concurrency Runtime]
- parallel search algorithm, writing [Concurrency Runtime]
ms.assetid: 421cd2de-f058-465f-b890-dd8fcc0df273
ms.openlocfilehash: 21907de6c5625f7774ae788cef0449ac49107e40
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142135"
---
# <a name="how-to-use-cancellation-to-break-from-a-parallel-loop"></a>Vorgehensweise: Verwenden eines Abbruchs zum Verlassen einer Parallel-Schleife

In diesem Beispiel wird gezeigt, wie der Abbruch verwendet wird, um einen grundlegenden parallelen Suchalgorithmus zu implementieren.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird der Abbruch verwendet, um nach einem Element in einem Array zu suchen. Die `parallel_find_any`-Funktion verwendet den Parallelitäts [::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) -Algorithmus und die Funktion " [parallelcurrency:: run_with_cancellation_token](reference/concurrency-namespace-functions.md#run_with_cancellation_token) ", um nach der Position zu suchen, die den angegebenen Wert enthält. Wenn die parallele Schleife den Wert findet, wird die Methode " [parallelcurrency:: cancellation_token_source:: Cancel](reference/cancellation-token-source-class.md#cancel) " aufgerufen, um die zukünftige Arbeit abzubrechen.

[!code-cpp[concrt-parallel-array-search#1](../../parallel/concrt/codesnippet/cpp/how-to-use-cancellation-to-break-from-a-parallel-loop_1.cpp)]

Der Algorithmus "Parallelität [::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) " agiert gleichzeitig. Daher werden die Vorgänge nicht in einer vorab festgelegten Reihenfolge durchgeführt. Wenn das Array mehrere Instanzen des Werts enthält, kann das Ergebnis eine beliebige Position sein.

## <a name="compiling-the-code"></a>Kompilieren des Codes

Kopieren Sie den Beispielcode, und fügen Sie ihn in ein Visual Studio-Projekt ein, oder fügen Sie ihn in eine Datei mit dem Namen `parallel-array-search.cpp` ein, und führen Sie dann den folgenden Befehl in einem Visual Studio-Eingabe Aufforderungs Fenster aus.

> **cl. exe/EHsc parallel-Array-Search. cpp**

## <a name="see-also"></a>Weitere Informationen

[Abbruch in der PPL](cancellation-in-the-ppl.md)<br/>
[Parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md)<br/>
[parallel_for-Funktion](reference/concurrency-namespace-functions.md#parallel_for)<br/>
[cancellation_token_source-Klasse](../../parallel/concrt/reference/cancellation-token-source-class.md)
