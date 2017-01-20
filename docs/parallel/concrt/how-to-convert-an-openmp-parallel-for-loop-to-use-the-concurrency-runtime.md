---
title: "Gewusst wie: Konvertieren einer parallel-for-Schleife in OpenMP zur Verwendung der Concurrency Runtime"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Konvertierung von OpenMP in die Concurrency Runtime, parallele for-Schleifen"
  - "Konvertierung von OpenMP in die Concurrency Runtime, parallele Schleifen"
  - "Parallele for-Schleifen, Konvertierung von OpenMP in die Concurrency Runtime"
  - "Parallele Schleifen, Konvertierung von OpenMP in die Concurrency Runtime"
ms.assetid: d8a7b656-f86c-456e-9c5d-a7d52f94646e
caps.latest.revision: 13
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Konvertieren einer parallel-for-Schleife in OpenMP zur Verwendung der Concurrency Runtime
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dieses Beispiel veranschaulicht, wie eine einfache Schleife, in der die [parallel](../../parallel/openmp/reference/parallel.md)\-Direktive und die [for](../../parallel/openmp/reference/for-openmp.md)\-Direktive von OpenMP verwendet werden, für die Verwendung des [concurrency::parallel\_for](../Topic/parallel_for%20Function.md)\-Algorithmus der Concurrency Runtime konvertiert wird.  
  
## Beispiel  
 In diesem Beispiel wird die Anzahl der Primzahlen in einem Array von Zufallswerten sowohl mit OpenMP als auch mit der Concurrency Runtime berechnet.  
  
 [!CODE [concrt-openmp#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-openmp#1)]  
  
 Folgende Ergebnisse werden zurückgegeben:  
  
  **Using OpenMP...**  
**found 107254 prime numbers.**  
**Using the Concurrency Runtime...**  
**found 107254 prime numbers.** Der `parallel_for`\-Algorithmus und OpenMP 3.0 lassen als Indextyp einen ganzzahligen Typ mit Vorzeichen und einen ganzzahligen Typ ohne Vorzeichen zu.  Der `parallel_for`\-Algorithmus stellt außerdem sicher, dass der angegebene Bereich bei einem Typ mit Vorzeichen keinen Überlauf verursacht.  Version 2.0 und 2.5 von OpenMP lassen nur ganzzahlige Indextypen mit Vorzeichen zu.  In OpenMP wird außerdem der Indexbereich nicht überprüft.  
  
 In der Version dieses Beispiels mit der Concurrency Runtime wird außerdem statt der [atomic](../../parallel/openmp/reference/atomic.md)\-Direktive ein [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md)\-Objekt verwendet, um den Zählerwert zu erhöhen, ohne dass Synchronisierung erforderlich ist.  
  
 Weitere Informationen zu `parallel_for` und anderen parallelen Algorithmen finden Sie unter [Parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md).  Weitere Informationen über die `combinable`\-Klasse finden Sie unter [Parallele Container und Objekte](../../parallel/concrt/parallel-containers-and-objects.md).  
  
## Beispiel  
 Dieses Beispiel unterscheidet sich vom vorherigen Beispiel darin, dass statt eines systemeigenen Arrays ein [std::array](../../standard-library/array-class-stl.md)\-Objekt verwendet wird.  Da in OpenMP, Version 2.0 und 2.5, ganzzahlige Indextypen mit Vorzeichen nur in einem `parallel` `for`\-Konstrukt zulässig sind, können Sie für den parallelen Zugriff auf die Elemente eines STL \(Standard Template Library\)\-Containers keine Iteratoren verwenden.  Die Parallel Patterns Library \(PPL\) stellt den [concurrency::parallel\_for\_each](../Topic/parallel_for_each%20Function.md)\-Algorithmus bereit, der Aufgaben für einen iterativen Container, z. B. einen STL\-Container, parallel ausführt.  Er verwendet die gleiche Partitionierungslogik wie der `parallel_for`\-Algorithmus.  Der `parallel_for_each`\-Algorithmus ähnelt dem [std::for\_each](../Topic/for_each.md)\-Algorithmus der STL, mit dem Unterschied, dass der `parallel_for_each`\-Algorithmus die Aufgaben gleichzeitig ausführt.  
  
 [!CODE [concrt-openmp#10](../CodeSnippet/VS_Snippets_ConcRT/concrt-openmp#10)]  
  
## Kompilieren des Codes  
 Kopieren Sie den Beispielcode, und fügen Sie ihn in ein Visual Studio\-Projekt ein. Alternativ dazu können Sie ihn auch in eine Datei mit dem Namen `concrt-omp-count-primes.cpp` einfügen und dann folgenden Befehl in einem Visual Studio\-Eingabeaufforderungsfenster ausführen.  
  
 **cl.exe \/EHsc \/openmp concrt\-omp\-count\-primes.cpp**  
  
## Siehe auch  
 [Migrieren von OpenMP zur Concurrency Runtime](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)   
 [Parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md)   
 [Parallele Container und Objekte](../../parallel/concrt/parallel-containers-and-objects.md)