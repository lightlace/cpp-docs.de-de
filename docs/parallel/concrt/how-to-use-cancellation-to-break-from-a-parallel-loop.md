---
title: 'Vorgehensweise: Verwenden eines Abbruchs zum Verlassen einer Parallel-Schleife | Microsoft Docs'
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
ms.openlocfilehash: b1b5153c225c3bb3a67be4265cf8303da2121c2b
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33696291"
---
# <a name="how-to-use-cancellation-to-break-from-a-parallel-loop"></a>Gewusst wie: Verwenden eines Abbruchs zum Verlassen einer Parallel-Schleife
In diesem Beispiel wird gezeigt, wie auf den Abbruch zu verwenden, um eine grundlegende paralleler Suchalgorithmus implementiert wird.  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird Abbruch, nach einem Element in einem Array gesucht werden soll. Die `parallel_find_any` Funktion verwendet die [Concurrency:: parallel_for](reference/concurrency-namespace-functions.md#parallel_for) Algorithmus und die [Concurrency:: run_with_cancellation_token](reference/concurrency-namespace-functions.md#run_with_cancellation_token) Funktion, für die Position gesucht werden soll, die den angegebenen Wert enthält. Wenn den Wert von die parallele Schleife gefunden wird, ruft er die [Concurrency::cancellation_token_source::cancel](reference/cancellation-token-source-class.md#cancel) Methode, um zukünftige Arbeitsvorgänge abzubrechen.  


  
 [!code-cpp[concrt-parallel-array-search#1](../../parallel/concrt/codesnippet/cpp/how-to-use-cancellation-to-break-from-a-parallel-loop_1.cpp)]  
  

 Die [Concurrency:: parallel_for](reference/concurrency-namespace-functions.md#parallel_for) Algorithmus fungiert gleichzeitig. Aus diesem Grund ist es nicht die Vorgänge in einer vordefinierten Reihenfolge ausführen. Wenn das Array mehrere Instanzen des Werts enthält, kann das Ergebnis eines seiner Positionen sein.  

  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Kopieren Sie den Beispielcode und fügen Sie ihn in ein Visual Studio-Projekt, oder fügen Sie ihn in eine Datei mit dem Namen `parallel-array-search.cpp` und dann den folgenden Befehl in eine Visual Studio-Eingabeaufforderungsfenster ausführen.  
  
 **/ EHsc / CL.exe Parallel-Array-search.cpp**  
  
## <a name="see-also"></a>Siehe auch  
 [Abbruch in der PPL](cancellation-in-the-ppl.md)   
 [Parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md)   
 [Parallel_for-Funktion](reference/concurrency-namespace-functions.md#parallel_for)   
 [cancellation_token_source-Klasse](../../parallel/concrt/reference/cancellation-token-source-class.md)
