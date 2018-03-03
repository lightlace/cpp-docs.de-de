---
title: 'Vorgehensweise: Konvertieren einer OpenMP-Schleife, die Ausnahmebehandlung verwendet wird, zur Verwendung der Concurrency Runtime | Microsoft Docs'
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
- exception handling, converting from OpenMP to the Concurrency Runtime
- converting from OpenMP to the Concurrency Runtime, exception handling
ms.assetid: 03c28196-21ba-439e-8641-afab1c283e1a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d2964c629ce8a3a83799278ac822b589992b4995
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-convert-an-openmp-loop-that-uses-exception-handling-to-use-the-concurrency-runtime"></a>Gewusst wie: Konvertieren einer OpenMP-Schleife, in der die Ausnahmebehandlung verwendet wird, zur Verwendung der Concurrency Runtime
In diesem Beispiel wird veranschaulicht, wie das Konvertieren einer OpenMP [parallele](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[für](../../parallel/openmp/reference/for-openmp.md) Schleife, die Verwendung der Concurrency Runtime-Ausnahmebehandlungsmechanismus Ausnahmebehandlung ausführt.  
  
 In OpenMP müssen Ausnahmen in einem parallelen Bereich im gleichen Bereich und vom gleichen Thread abgefangen und behandelt werden. Eine Ausnahme, die den parallelen Bereich umgeht, wird vom Handler für nicht behandelte Ausnahmen abgefangen, der den Prozess standardmäßig beendet.  
  

 In der Concurrency Runtime, wenn Sie eine Ausnahme im Text einer Arbeitsfunktion auslöst, die Sie an eine Aufgabengruppe, z. B. übergeben eine [Concurrency:: task_group](reference/task-group-class.md) oder [Concurrency:: structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) -Objekt, oder an einen parallelen Algorithmus wie z. B. [Concurrency:: parallel_for](reference/concurrency-namespace-functions.md#parallel_for), die Common Language Runtime speichert diese Ausnahme und marshallt sie an den Kontext, der wartet, bis der Aufgabengruppe oder der Algorithmus, um den Vorgang abzuschließen. Der Wartekontext Aufgabengruppen, ist der Kontext, der aufruft [Concurrency:: task_group::](reference/task-group-class.md#wait), [structured_task_group](reference/structured-task-group-class.md#wait), [Concurrency::task_group::run_and _wait](reference/task-group-class.md#run_and_wait), oder [Concurrency::structured_task_group::run_and_wait](reference/structured-task-group-class.md#run_and_wait). Der Wartekontext eines parallelen Algorithmus ist der Kontext, von dem dieser Algorithmus aufgerufen wurde. Darüber hinaus werden von der Runtime auch alle aktiven Aufgaben in der Aufgabengruppe (sowie alle aktiven Aufgaben in untergeordneten Aufgabengruppen) beendet sowie alle noch nicht gestarteten Aufgaben verworfen.  


  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird veranschaulicht, wie Ausnahmen in einem OpenMP `parallel`-Bereich und in einem Aufruf von `parallel_for` behandelt werden. Die `do_work` Funktion führt eine speicherbelegungsanforderung aus, die nicht erfolgreich ist und daher löst eine Ausnahme vom Typ [Std:: bad_alloc](../../standard-library/bad-alloc-class.md). In der Version, die OpenMP verwendet, muss diese vom Thread, der diese Ausnahme auslöst, ebenfalls abgefangen werden. Mit anderen Worten muss die Ausnahme von jeder Iteration einer parallelen OpenMP-Schleife behandelt werden. In der Version mit der Concurrency Runtime wird eine Ausnahme, die von einem anderen Thread ausgelöst wird, vom Hauptthread abgefangen.  
  
 [!code-cpp[concrt-openmp#3](../../parallel/concrt/codesnippet/cpp/convert-an-openmp-loop-that uses-exception-handling_1.cpp)]  
  
 Folgende Ergebnisse werden zurückgegeben:  
  
```Output  
Using OpenMP...  
An error of type 'class std::bad_alloc' occurred.  
An error of type 'class std::bad_alloc' occurred.  
An error of type 'class std::bad_alloc' occurred.  
An error of type 'class std::bad_alloc' occurred.  
An error of type 'class std::bad_alloc' occurred.  
An error of type 'class std::bad_alloc' occurred.  
An error of type 'class std::bad_alloc' occurred.  
An error of type 'class std::bad_alloc' occurred.  
An error of type 'class std::bad_alloc' occurred.  
An error of type 'class std::bad_alloc' occurred.  
Using the Concurrency Runtime...  
An error of type 'class std::bad_alloc' occurred.  
```  
  
 In der Version in diesem Beispiel mit OpenMP tritt die Ausnahme in der jeweiligen Schleifeniteration auf und wird dort auch behandelt. In der Version mit der Concurrency Runtime wird die Ausnahme von der Laufzeit gespeichert, alle aktiven Aufgaben werden beendet, noch nicht gestartete Aufgaben werden verworfen, und die Ausnahme, die `parallel_for` aufruft, wird an den Kontext gemarshallt.  
  
 Wenn Sie möchten, dass die Version mit OpenMP nach dem Auftreten der Ausnahme beendet wird, können Sie ein boolesche Flag verwenden, um den Fehler gegenüber anderen Schleifeniterationen anzuzeigen. Wie im Beispiel im Thema [wie: Konvertieren einer OpenMP-Schleife, Abbruch verwendet, um die Verwendung der Concurrency Runtime](../../parallel/concrt/convert-an-openmp-loop-that-uses-cancellation.md), nachfolgende Schleifeniterationen würde wirkungslos, wenn das Flag festgelegt ist. Umgekehrt können Sie die Ausnahme, wenn die Schleife mit der Concurrency Runtime nach dem Auftreten der Ausnahme fortgesetzt werden soll, im Text der parallelen Schleife selbst behandeln.  
  
 Andere Komponenten der Concurrency Runtime, wie asynchrone Agents und einfache Aufgaben, transportieren keine Ausnahmen. Stattdessen werden unbehandelte Ausnahmen vom Handler für nicht behandelte Ausnahmen abgefangen, der den Prozess standardmäßig beendet. Weitere Informationen zur Behandlung von Ausnahmen finden Sie unter [Exception Handling](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).  
  
 Weitere Informationen zu `parallel_for` und anderen parallelen Algorithmen finden Sie unter [parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md).  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Kopieren Sie den Beispielcode und fügen Sie ihn in ein Visual Studio-Projekt, oder fügen Sie ihn in eine Datei mit dem Namen `concrt-omp-exceptions.cpp` und dann den folgenden Befehl in eine Visual Studio-Eingabeaufforderungsfenster ausführen.  
  
 **CL.exe/EHsc/OpenMP Concrt-Omp-exceptions.cpp**  
  
## <a name="see-also"></a>Siehe auch  
 [Migrieren von OpenMP zur Concurrency Runtime](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)   
 [Ausnahmebehandlung](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)   
 [Parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md)

