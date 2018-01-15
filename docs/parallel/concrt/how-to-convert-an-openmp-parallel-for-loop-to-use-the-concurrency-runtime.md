---
title: 'Vorgehensweise: Konvertieren einer OpenMP-Parallel for-Schleife zur Verwendung der Concurrency Runtime | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- converting from OpenMP to the Concurrency Runtime, parallel for loops
- converting from OpenMP to the Concurrency Runtime, parallel loops
- parallel for loops, converting from OpenMP to the Concurrency Runtime
- parallel loops, converting from OpenMP to the Concurrency Runtime
ms.assetid: d8a7b656-f86c-456e-9c5d-a7d52f94646e
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a27e07884b4ada54f694136ea2fbca474c9d214d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime"></a>Gewusst wie: Konvertieren einer parallel-for-Schleife in OpenMP zur Verwendung der Concurrency Runtime

In diesem Beispiel wird veranschaulicht, wie eine einfache Schleife konvertiert, die die OpenMP verwendet [parallele](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel) und [für](../../parallel/openmp/reference/for-openmp.md) Anweisungen zur Verwendung der Concurrency Runtime [Concurrency:: parallel_for](reference/concurrency-namespace-functions.md#parallel_for) Algorithmus.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird die Anzahl der Primzahlen in einem Array von Zufallswerten sowohl mit OpenMP als auch mit der Concurrency Runtime berechnet.  
  
 [!code-cpp[concrt-openmp#1](../../parallel/concrt/codesnippet/cpp/how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime_1.cpp)]  
  
 Folgende Ergebnisse werden zurückgegeben:  
  
```Output  
Using OpenMP...  
found 107254 prime numbers.  
Using the Concurrency Runtime...  
found 107254 prime numbers.  
```  
  
 Der `parallel_for`-Algorithmus und OpenMP 3.0 lassen als Indextyp einen ganzzahligen Typ mit Vorzeichen und einen ganzzahligen Typ ohne Vorzeichen zu. Der `parallel_for`-Algorithmus stellt außerdem sicher, dass der angegebene Bereich bei einem Typ mit Vorzeichen keinen Überlauf verursacht. Version 2.0 und 2.5 von OpenMP lassen nur ganzzahlige Indextypen mit Vorzeichen zu. In OpenMP wird außerdem der Indexbereich nicht überprüft.  
  
 Die Version dieses Beispiels mit der Concurrency Runtime wird auch verwendet eine [Concurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) -Objekt anstelle von der [atomic](../../parallel/openmp/reference/atomic.md) Direktive versehen, ohne dass den Wert dieses Indikators erhöht Synchronisierung.  
  
 Weitere Informationen zu `parallel_for` und anderen parallelen Algorithmen finden Sie unter [parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md). Weitere Informationen zu den `combinable` Klasse, finden Sie unter [parallele Container und Objekte](../../parallel/concrt/parallel-containers-and-objects.md).  
  
## <a name="example"></a>Beispiel  

 In diesem Beispiel wird das vorherige geändert zum Bearbeiten einer [Std:: Array](../../standard-library/array-class-stl.md) -Objekt anstelle eines systemeigenen Arrays. Da OpenMP, Version 2.0 und 2.5 zulassen für ganzzahlige Indextypen mit Vorzeichen nur in einem `parallel_for` aufbauen können keine Iteratoren Zugriff auf die Elemente eines C++-Standardbibliothek Containers parallel. Die Parallel Patterns Library (PPL) stellt die [Concurrency:: parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) -Algorithmus, der Aufgaben, parallel auf einen iterativen Container wie z. B. die von der C++-Standardbibliothek bereitgestellten ausführt. Er verwendet die gleiche Partitionierungslogik wie der `parallel_for`-Algorithmus. Die `parallel_for_each` -Algorithmus ähnelt der C++-Standardbibliothek [Std:: for_each](../../standard-library/algorithm-functions.md#for_each) -Algorithmus, außer dass die `parallel_for_each` -Algorithmus die Aufgaben gleichzeitig ausführt.  
  
 [!code-cpp[concrt-openmp#10](../../parallel/concrt/codesnippet/cpp/how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime_2.cpp)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Kopieren Sie den Beispielcode und fügen Sie ihn in ein Visual Studio-Projekt, oder fügen Sie ihn in eine Datei mit dem Namen `concrt-omp-count-primes.cpp` und dann den folgenden Befehl in eine Visual Studio-Eingabeaufforderungsfenster ausführen.  
  
 **CL.exe/EHsc/OpenMP Concrt-Omp-Count-primes.cpp**  
  
## <a name="see-also"></a>Siehe auch  
 [Migrieren von OpenMP zur Concurrency Runtime](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)   
 [Parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md)   
 [Parallele Container und Objekte](../../parallel/concrt/parallel-containers-and-objects.md)

