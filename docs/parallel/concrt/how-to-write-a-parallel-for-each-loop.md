---
title: 'Vorgehensweise: Schreiben einer Parallel_for_each-Schleife | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- writing a parallel_for_each loop [Concurrency Runtime]
- parallel_for_each function, example
ms.assetid: fa9c0ba6-ace0-4f88-8681-c7c1f52aff20
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 179fa4b055b4743303f5d72ebec851a1d10def93
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-write-a-parallelforeach-loop"></a>Gewusst wie: Schreiben einer parallel_for_each-Schleife
Dieses Beispiel zeigt, wie die [Concurrency:: parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) Algorithmus berechnet die Anzahl von Primzahlen in einem [Std:: Array](../../standard-library/array-class-stl.md) -Objekt parallel.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Anzahl von Primzahlen in einem Array zweimal berechnet. Im Beispiel wird zunächst mit der [Std:: for_each](../../standard-library/algorithm-functions.md#for_each) Algorithmus, um die Anzahl der seriell berechnet. Anschließend wird die gleiche Aufgabe mit dem `parallel_for_each`-Algorithmus parallel ausgeführt. Das Beispiel gibt außerdem die Zeit, die zum Ausführen beider Berechnungen benötigt wird, in der Konsole aus.  
  
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
 Um den Code zu kompilieren, kopieren Sie ihn und fügen Sie ihn in ein Visual Studio-Projekt ein, oder fügen Sie ihn in eine Datei mit dem Namen `parallel-count-primes.cpp` und dann den folgenden Befehl in eine Visual Studio-Eingabeaufforderungsfenster ausführen.  
  
 **/ EHsc / CL.exe Parallel-Count-primes.cpp**  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Der Lambda-Ausdruck, der im Beispiel an den `parallel_for_each`-Algorithmus übergeben wird, aktiviert mithilfe der `InterlockedIncrement`-Funktion parallele Iterationen der Schleife, um den Zähler gleichzeitig zu inkrementieren. Wenn Sie Funktionen wie z. B. `InterlockedIncrement` verwenden, um Zugriff auf freigegebene Ressourcen zu synchronisieren, kann es zu Leistungsengpässen im Code kommen. Sie können z. B. einen sperrenfreien Synchronisierungsmechanismus verwenden, wird die [Concurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) Klasse, um den gleichzeitigen Zugriff auf freigegebene Ressourcen zu vermeiden. Ein Beispiel, verwendet der `combinable` finden Sie auf diese Weise-Klasse [wie: Verbessern der Leistung mithilfe von combinable](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md)   
 [Parallel_for_each-Funktion](reference/concurrency-namespace-functions.md#parallel_for_each)


