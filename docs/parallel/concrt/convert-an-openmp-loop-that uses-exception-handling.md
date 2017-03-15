---
title: "Gewusst wie: Konvertieren einer OpenMP-Schleife, in der die Ausnahmebehandlung verwendet wird, zur Verwendung der Concurrency Runtime"
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
  - "Ausnahmebehandlung, Konvertieren von OpenMP in Concurrency Runtime"
  - "Konvertieren von OpenMP in Concurrency Runtime, Ausnahmebehandlung"
ms.assetid: 03c28196-21ba-439e-8641-afab1c283e1a
caps.latest.revision: 11
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Konvertieren einer OpenMP-Schleife, in der die Ausnahmebehandlung verwendet wird, zur Verwendung der Concurrency Runtime
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In diesem Beispiel wird veranschaulicht, wie eine OpenMP [parallel](../../parallel/openmp/reference/parallel.md)\_[for](../../parallel/openmp/reference/for-openmp.md)\-Schleife für die Ausnahmebehandlung konvertiert wird, um den Mechanismus zur Ausnahmebehandlung in der Concurrency Runtime zu verwenden.  
  
 In OpenMP müssen Ausnahmen in einem parallelen Bereich im gleichen Bereich und vom gleichen Thread abgefangen und behandelt werden.  Eine Ausnahme, die den parallelen Bereich umgeht, wird vom Handler für nicht behandelte Ausnahmen abgefangen, der den Prozess standardmäßig beendet.  
  
 In der Concurrency Runtime wird die im Text einer Arbeitsfunktion ausgelöste Ausnahme, die Sie an eine Aufgabengruppe wie ein [concurrency::task\_group](../Topic/task_group%20Class.md)\-Objekt oder ein [concurrency::structured\_task\_group](../../parallel/concrt/reference/structured-task-group-class.md)\-Objekt oder an einen parallelen Algorithmus wie [concurrency::parallel\_for](../Topic/parallel_for%20Function.md) übergeben, von der Runtime gespeichert und an den Kontext gemarshallt, der darauf wartet, dass die Aufgabengruppe oder der Algorithmus abgeschlossen werden.  Der Wartekontext einer Aufgabengruppe ist der Kontext, der eines der folgenden Objekte aufruft: [concurrency::task\_group::wait](../Topic/task_group::wait%20Method.md), [concurrency::structured\_task\_group::wait](../Topic/structured_task_group::wait%20Method.md), [concurrency::task\_group::run\_and\_wait](../Topic/task_group::run_and_wait%20Method.md) oder [concurrency::structured\_task\_group::run\_and\_wait](../Topic/structured_task_group::run_and_wait%20Method.md).  Der Wartekontext eines parallelen Algorithmus ist der Kontext, von dem dieser Algorithmus aufgerufen wurde.  Darüber hinaus werden von der Runtime auch alle aktiven Aufgaben in der Aufgabengruppe \(sowie alle aktiven Aufgaben in untergeordneten Aufgabengruppen\) beendet sowie alle noch nicht gestarteten Aufgaben verworfen.  
  
## Beispiel  
 In diesem Beispiel wird veranschaulicht, wie Ausnahmen in einem OpenMP `parallel`\-Bereich und in einem Aufruf von `parallel_for` behandelt werden.  Die `do_work`\-Funktion führt eine Speicherbelegungsanforderung aus, die nicht erfolgreich ist und daher eine Ausnahme vom Typ [std::bad\_alloc](../../standard-library/bad-alloc-class.md) auslöst.  In der Version, die OpenMP verwendet, muss diese vom Thread, der diese Ausnahme auslöst, ebenfalls abgefangen werden.  Mit anderen Worten muss die Ausnahme von jeder Iteration einer parallelen OpenMP\-Schleife behandelt werden.  In der Version mit der Concurrency Runtime wird eine Ausnahme, die von einem anderen Thread ausgelöst wird, vom Hauptthread abgefangen.  
  
 [!CODE [concrt-openmp#3](../CodeSnippet/VS_Snippets_ConcRT/concrt-openmp#3)]  
  
 Folgende Ergebnisse werden zurückgegeben:  
  
  **Using OpenMP...**  
**An error of type 'class std::bad\_alloc' occurred.**  
**An error of type 'class std::bad\_alloc' occurred.**  
**An error of type 'class std::bad\_alloc' occurred.**  
**An error of type 'class std::bad\_alloc' occurred.**  
**An error of type 'class std::bad\_alloc' occurred.**  
**An error of type 'class std::bad\_alloc' occurred.**  
**An error of type 'class std::bad\_alloc' occurred.**  
**An error of type 'class std::bad\_alloc' occurred.**  
**An error of type 'class std::bad\_alloc' occurred.**  
**An error of type 'class std::bad\_alloc' occurred.**  
**Using the Concurrency Runtime...**  
**An error of type 'class std::bad\_alloc' occurred.** In der Version in diesem Beispiel mit OpenMP tritt die Ausnahme in der jeweiligen Schleifeniteration auf und wird dort auch behandelt.  In der Version mit der Concurrency Runtime wird die Ausnahme von der Laufzeit gespeichert, alle aktiven Aufgaben werden beendet, noch nicht gestartete Aufgaben werden verworfen, und die Ausnahme, die `parallel_for` aufruft, wird an den Kontext gemarshallt.  
  
 Wenn Sie möchten, dass die Version mit OpenMP nach dem Auftreten der Ausnahme beendet wird, können Sie ein boolesche Flag verwenden, um den Fehler gegenüber anderen Schleifeniterationen anzuzeigen.  Wie im Beispiel im Thema [Gewusst wie: Konvertieren einer OpenMP\-Schleife mit Abbruch zur Verwendung der Concurrency Runtime](../../parallel/concrt/convert-an-openmp-loop-that-uses-cancellation.md) veranschaulicht, hätten nachfolgene Schleifeninterationen keine Auswirkung, wenn das Flag festgelegt ist.  Umgekehrt können Sie die Ausnahme, wenn die Schleife mit der Concurrency Runtime nach dem Auftreten der Ausnahme fortgesetzt werden soll, im Text der parallelen Schleife selbst behandeln.  
  
 Andere Komponenten der Concurrency Runtime, wie asynchrone Agents und einfache Aufgaben, transportieren keine Ausnahmen.  Stattdessen werden unbehandelte Ausnahmen vom Handler für nicht behandelte Ausnahmen abgefangen, der den Prozess standardmäßig beendet.  Weitere Informationen zur Behandlung von Ausnahmen finden Sie unter [Ausnahmebehandlung](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).  
  
 Weitere Informationen zu `parallel_for` und anderen parallelen Algorithmen finden Sie unter [Parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md).  
  
## Kompilieren des Codes  
 Kopieren Sie den Beispielcode, und fügen Sie ihn in ein Visual Studio\-Projekt ein. Alternativ dazu können Sie ihn auch in eine Datei mit dem Namen `concrt-omp-exceptions.cpp` einfügen und dann folgenden Befehl in einem Visual Studio\-Eingabeaufforderungsfenster ausführen.  
  
 **cl.exe \/EHsc \/openmp concrt\-omp\-exceptions.cpp**  
  
## Siehe auch  
 [Migrieren von OpenMP zur Concurrency Runtime](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)   
 [Ausnahmebehandlung](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)   
 [Parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md)