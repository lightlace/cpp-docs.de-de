---
title: 'Vorgehensweise: Konvertieren einer OpenMP-Schleife, die Abbruch zur Verwendung der Concurrency Runtime verwendet | Microsoft Docs'
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
- converting from OpenMP to the Concurrency Runtime, cancellation
- cancellation, converting from OpenMP to the Concurrency Runtime
ms.assetid: 4b0b3c33-bfa9-4e96-ae08-aef245a39cbb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d3c4d37dfe5182e375e7581d6f5ef8188b922e5d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-convert-an-openmp-loop-that-uses-cancellation-to-use-the-concurrency-runtime"></a>Gewusst wie: Konvertieren einer OpenMP-Schleife mit Abbruch zur Verwendung der Concurrency Runtime
Bei einigen parallelen Schleifen müssen nicht alle Iterationen ausgeführt werden. Beispielsweise kann ein Algorithmus, mit dem nach einem Wert gesucht wird, beendet werden, sobald der Wert gefunden wurde. OpenMP stellt keinen Mechanismus bereit, um aus einer parallelen Schleife auszubrechen. Sie können jedoch einen booleschen Wert oder ein Flag verwenden, damit die Iteration einer Schleife angeben kann, dass der gesuchte Wert gefunden wurde. Die Concurrency Runtime stellt Funktionen bereit, mit denen eine Aufgabe andere Aufgaben abbrechen kann, die noch nicht gestartet wurden.  
  
 In diesem Beispiel wird veranschaulicht, wie das Konvertieren einer OpenMP [parallele](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[für](../../parallel/openmp/reference/for-openmp.md) -Schleife, die für die Ausführung aller Iterationen nicht benötigt wird, mit der Concurrency Runtime-Abbruchmechanismus.  
  
## <a name="example"></a>Beispiel  

 In diesem Beispiel wird mit OpenMP und der Concurrency Runtime eine parallele Version des implementiert die [Std:: any_of](../../standard-library/algorithm-functions.md#any_of) Algorithmus. In der OpenMP-Version in diesem Beispiel wird mit einem Flag die Erfüllung der Bedingung für alle parallelen Schleifeniterationen koordiniert. Die Version, die die Concurrency Runtime verwendet die [Concurrency::structured_task_group::cancel](reference/structured-task-group-class.md#cancel) -Methode der Gesamtvorgang beendet, wenn die Bedingung erfüllt ist.  

  
 [!code-cpp[concrt-openmp#2](../../parallel/concrt/codesnippet/cpp/convert-an-openmp-loop-that-uses-cancellation_1.cpp)]  
  
 Folgende Ergebnisse werden zurückgegeben:  
  
```Output  
Using OpenMP...  
9114046 is in the array.  
Using the Concurrency Runtime...  
9114046 is in the array.  
```  
  
 In der Version mit OpenMP werden, auch wenn das Flag festgelegt ist, alle Schleifeniterationen ausgeführt. Bei einer Aufgabe mit untergeordneten Aufgaben müsste das Flag darüber hinaus auch für diese verfügbar sein, um den Abbruch des Vorgangs zu signalisieren. In der Concurrency Runtime wird beim Abbrechen einer Aufgabengruppe die gesamte Arbeitsstruktur einschließlich der untergeordneten Aufgaben von der Laufzeit abgebrochen. Die [Concurrency:: parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) -Algorithmus führt Aufgaben arbeiten ausführen. Wenn die Stammaufgabe durch eine Iteration der Schleife abgebrochen wird, wird daher die gesamte Struktur der Berechnung abgebrochen. Wenn eine Arbeitsstruktur abgebrochen wird, werden von der Laufzeit keine neuen Aufgaben gestartet. Aufgaben, die bereits gestartet wurden, wird von der Laufzeit jedoch eine Fertigstellung ermöglicht. Aktive Schleifeniterationen können im Falle des `parallel_for_each`-Algorithmus also ihre Ressourcen bereinigen.  
  
 Im Beispiel kann das Ergebnis in beiden Versionen durch mehrere Schleifeniterationen parallel festgelegt und der Gesamtvorgang kann abgebrochen werden, wenn das Array mehr als eine Kopie des gesuchten Werts enthält. Mit einem Synchronisierungsprimitiven wie einem kritischen Abschnitt können Sie ggf. sicherstellen, dass Arbeiten nur von einer Aufgabe ausgeführt werden, wenn eine Bedingung erfüllt ist.  
  
 Sie können Aufgaben mit der PPL auch mit der Ausnahmebehandlung abbrechen. Weitere Informationen über Abbrüche finden Sie unter [Abbruch in der PPL](cancellation-in-the-ppl.md).  
  
 Weitere Informationen zu `parallel_for_each` und anderen parallelen Algorithmen finden Sie unter [parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md).  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Kopieren Sie den Beispielcode und fügen Sie ihn in ein Visual Studio-Projekt, oder fügen Sie ihn in eine Datei mit dem Namen `concrt-omp-parallel-any-of.cpp` und dann den folgenden Befehl in eine Visual Studio-Eingabeaufforderungsfenster ausführen.  
  
 **CL.exe/EHsc/OpenMP Concrt-Omp-Parallel-any-of.cpp**  
  
## <a name="see-also"></a>Siehe auch  
 [Migrieren von OpenMP zur Concurrency Runtime](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)   
 [Abbruch in der PPL](cancellation-in-the-ppl.md)   
 [Parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md)

