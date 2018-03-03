---
title: 'Vorgehensweise: Konvertieren einer OpenMP-Schleife, die keine Reduction-Variable verwendet wird, um die Verwendung der Concurrency Runtime | Microsoft Docs'
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
- converting from OpenMP to the Concurrency Runtime, reduction variables
- reduction variables, converting from OpenMP to the Concurrency Runtime
ms.assetid: 96623f36-5e57-4d3f-8c13-669e6cd535b1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f218bbc47fa33e6cc9546d032311417d9e10d554
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-convert-an-openmp-loop-that-uses-a-reduction-variable-to-use-the-concurrency-runtime"></a>Gewusst wie: Konvertieren einer OpenMP-Schleife, in der eine reduction-Variable verwendet wird, zur Verwendung der Concurrency Runtime
In diesem Beispiel wird veranschaulicht, wie das Konvertieren einer OpenMP [parallele](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[für](../../parallel/openmp/reference/for-openmp.md) -Schleife, verwendet der [Verringerung](../../parallel/openmp/reference/reduction.md) -Klausel, um die Verwendung der Concurrency Runtime.  
  
 Mit der OpenMP-`reduction`-Klausel können Sie eine oder mehrere private Variablen im Thread angeben, auf die am Ende des parallelen Bereichs ein Reduzierungsvorgang angewendet wird. OpenMP enthält einen Satz vordefinierter Reduzierungsoperatoren. Jede Reduzierungsvariable muss ein Skalar sein (z. B. `int`, `long` und `float`). OpenMP definiert außerdem einige Einschränkungen für die Verwendung von Reduzierungsvariablen in einem parallelen Bereich.  
  
 Die Parallel Patterns Library (PPL) stellt die [Concurrency:: combinable](../../parallel/concrt/reference/combinable-class.md) -Klasse, die wiederverwendbaren lokalen Threadspeicher bietet, mit dem Sie differenzierte Berechnungen ausführen, und klicken Sie dann zu einer endgültigen zusammenführen Ergebnis. Die `combinable`-Klasse ist eine Vorlage, die sowohl auf skalare als auch auf komplexe Typen angewendet wird. Verwenden der `combinable` -Klasse unterberechnungen im Text eines parallelen Konstrukts aus, und rufen Sie anschließend die [Combine](reference/combinable-class.md#combine) oder [combine_each](reference/combinable-class.md#combine_each) Methode, um das Endergebnis zu erzeugen. Die `combine` und `combine_each` -Methode akzeptieren jeweils eine *combine-Funktion* , wie jedes Elementpaar kombiniert angibt. Daher ist die `combinable`-Klasse nicht auf einen festen Satz von Reduzierungsoperatoren beschränkt.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird mit OpenMP und der Concurrency Runtime die Summe der ersten 35 Fibonacci-Zahlen berechnet.  
  
 [!code-cpp[concrt-openmp#7](../../parallel/concrt/codesnippet/cpp/convert-an-openmp-loop-that-uses-a-reduction-variable_1.cpp)]  
  
 Folgende Ergebnisse werden zurückgegeben:  
  
```Output  
Using OpenMP...  
The sum of the first 35 Fibonacci numbers is 14930351.  
Using the Concurrency Runtime...  
The sum of the first 35 Fibonacci numbers is 14930351.  
```  
  
 Weitere Informationen zu den `combinable` Klasse, finden Sie unter [parallele Container und Objekte](../../parallel/concrt/parallel-containers-and-objects.md).  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Kopieren Sie den Beispielcode und fügen Sie ihn in ein Visual Studio-Projekt, oder fügen Sie ihn in eine Datei mit dem Namen `concrt-omp-fibonacci-reduction.cpp` und dann den folgenden Befehl in eine Visual Studio-Eingabeaufforderungsfenster ausführen.  
  
 **CL.exe/EHsc/OpenMP Concrt-Omp-Fibonacci-reduction.cpp**  
  
## <a name="see-also"></a>Siehe auch  
 [Migrieren von OpenMP zur Concurrency Runtime](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)   
 [Parallele Container und Objekte](../../parallel/concrt/parallel-containers-and-objects.md)

