---
title: 'Exemplarische Vorgehensweise: Verwenden der Concurrency Runtime in einer COM-aktivierte Anwendung | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Concurrency Runtime, use with COM
- COM, use with the Concurrency Runtime
ms.assetid: a7c798b8-0fc8-4bee-972f-22ef158f7f48
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1fd9f665f77ca5ae5311b034ee7afef6241ac489
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application"></a>Exemplarische Vorgehensweise: Verwenden der Concurrency Runtime in einer COM-Anwendung
Dieses Dokument veranschaulicht, wie die Concurrency Runtime in einer Anwendung verwendet werden kann, die das Component Object Model (COM) verwendet.  
  
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Lesen Sie die folgenden Dokumente, bevor Sie mit dieser exemplarischen Vorgehensweise beginnen:  
  
- [Aufgabenparallelität](../../parallel/concrt/task-parallelism-concurrency-runtime.md)  
  
- [Parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md)  
  
- [Asynchrone Agents](../../parallel/concrt/asynchronous-agents.md)  
  
- [Ausnahmebehandlung](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)  
  
 Weitere Informationen zu COM finden Sie unter [Component Object Model (COM)](http://msdn.microsoft.com/library/windows/desktop/ms680573).  
  
## <a name="managing-the-lifetime-of-the-com-library"></a>Verwalten der Lebensdauer der COM-Bibliothek  
 Obwohl für die Verwendung von COM mit der Concurrency Runtime die gleichen Prinzipien gelten wie bei anderen Parallelitätsmechanismen, können die folgenden Richtlinien hilfreich sein, um eine effektive Verwendung beider Bibliotheken zu erreichen.  
  
-   Ein Thread muss Aufrufen [CoInitializeEx](http://msdn.microsoft.com/library/windows/desktop/ms695279) , bevor sie die COM-Bibliothek verwendet.  
  
-   Ein Thread kann `CoInitializeEx` mehrmals aufrufen, solange bei jedem Aufruf die gleichen Argumente übergeben werden.  
  
-   Für jeden Aufruf von `CoInitializeEx`, ein Thread muss auch aufrufen [CoUninitialize](http://msdn.microsoft.com/library/windows/desktop/ms688715). Aufrufe von `CoInitializeEx` und `CoUninitialize` müssen also ausgeglichen sein.  
  
-   Um von einem Threadapartment zu einem anderen zu wechseln, muss ein Thread die COM-Bibliothek vollständig freigeben, bevor `CoInitializeEx` mit der neuen Threadingspezifikation aufgerufen wird.  
  
 Wenn Sie COM mit der Concurrency Runtime verwenden, gelten andere COM-Prinzipien. Zum Beispiel muss eine Anwendung, die ein Objekt in einem Singlethread-Apartment (STA) erstellt und das Objekt in einem anderen Apartment marshallt, außerdem eine Meldungsschleife zum Verarbeiten eingehender Meldungen bereitstellen. Beachten Sie dabei außerdem, dass das Marshalling von Objekten zwischen Apartments zu Leistungsverlust führen kann.  
  
### <a name="using-com-with-the-parallel-patterns-library"></a>Verwenden von COM mit der Parallel Patterns Library  
 Wenn Sie COM mit einer Komponente in der Parallel Patterns Library (PPL) verwenden, z. B. einer Aufgabengruppe oder einem parallelen Algorithmus, rufen Sie bei jeder Aufgabe oder Iteration `CoInitializeEx` auf, bevor Sie die COM-Bibliothek verwenden, und `CoUninitialize`, bevor die Aufgabe oder Iteration beendet wird. Im folgende Beispiel wird gezeigt, wie zum Verwalten der Lebensdauer der COM-Bibliothek mit einem [Concurrency:: structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) Objekt.  
  
 [!code-cpp[concrt-parallel-scripts#1](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_1.cpp)]  
  
 Sie müssen sicherstellen, dass die COM-Bibliothek ordnungsgemäß freigegeben wird, wenn eine Aufgabe oder ein paralleler Algorithmus abgebrochen wird, oder wenn der Aufgabentext eine Ausnahme auslöst. Aufrufe zu gewährleisten, dass die Aufgabe `CoUninitialize` verwenden, bevor er beendet wird, eine `try-finally` Block oder die *Resource Acquisition Is Initialization* (RAII)-Muster. Das folgende Beispiel gibt die COM-Bibliothek in einem `try-finally`-Block frei, wenn die Aufgabe abgeschlossen oder abgebrochen wird, oder wenn eine Ausnahme ausgelöst wird.  
  
 [!code-cpp[concrt-parallel-scripts#2](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_2.cpp)]  
  
 Das folgende Beispiel definiert mithilfe des RAII-Musters die `CCoInitializer`-Klasse, die die Lebensdauer der COM-Bibliothek in einem angegebenen Gültigkeitsbereich verwaltet.  
  
 [!code-cpp[concrt-parallel-scripts#3](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_3.cpp)]  
  
 Mithilfe der `CCoInitializer`-Klasse können Sie die COM-Bibliothek wie folgt automatisch freigeben, sobald die Aufgabe beendet wird.  
  
 [!code-cpp[concrt-parallel-scripts#4](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_4.cpp)]  
  
 Weitere Informationen über Abbrüche in der Concurrency Runtime finden Sie unter [Abbruch in der PPL](cancellation-in-the-ppl.md).  
  
### <a name="using-com-with-asynchronous-agents"></a>Verwenden von COM mit asynchronen Agents  

 Wenn Sie COM mit asynchronen Agents verwenden, rufen Sie `CoInitializeEx` vor der Verwendung von COM-Bibliothek in der [Concurrency::agent::run](reference/agent-class.md#run) -Methode des Agents. Rufen Sie anschließend `CoUninitialize` auf, bevor die `run`-Methode zurückkehrt. Verwenden Sie keine COM-Verwaltungsroutinen im Konstruktor oder Destruktor des Agents, und überschreiben Sie nicht die [Verwaltungsroutinen](reference/agent-class.md#start) oder [Concurrency:: Agent:: Fertig](reference/agent-class.md#done) Methoden, da diese Methoden sind wird aufgerufen, von einem anderen Thread als dem `run` Methode.  

  
 Das folgende Beispiel zeigt eine einfache Agent-Klasse mit dem Namen `CCoAgent`, die die COM-Bibliothek in der `run`-Methode verwaltet.  
  
 [!code-cpp[concrt-parallel-scripts#5](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_5.cpp)]  
  
 Ein vollständiges Beispiel wird später in dieser exemplarischen Vorgehensweise vorgestellt.  
  
### <a name="using-com-with-lightweight-tasks"></a>Verwenden von COM mit einfachen Aufgaben  
 Das Dokument [Taskplaner](../../parallel/concrt/task-scheduler-concurrency-runtime.md) beschreibt die Rolle einfacher Aufgaben in der Concurrency Runtime. Sie können COM genauso mit einer einfachen Aufgabe verwenden wie mit jeder Threadroutine, die Sie in der Windows-API an die `CreateThread`-Funktion übergeben. Dies wird im folgenden Beispiel gezeigt.  
  
 [!code-cpp[concrt-parallel-scripts#6](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_6.cpp)]  
  
## <a name="an-example-of-a-com-enabled-application"></a>Ein Beispiel für eine COM-aktivierte Anwendung  
 In diesem Abschnitt wird eine vollständige COM-aktivierte Anwendung, verwendet der `IScriptControl` Schnittstelle, um ein Skript auszuführen, die n berechnet<sup>th</sup> Fibonacci-Zahl. In diesem Beispiel wird das Skript zuerst im Hauptthread aufgerufen und anschließend die PPL und die Agents verwendet, um das Skript parallel aufzurufen.  
  
 Betrachten Sie die folgende Hilfsfunktion `RunScriptProcedure`, die eine Prozedur in einem `IScriptControl`-Objekt aufruft.  
  
 [!code-cpp[concrt-parallel-scripts#7](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_7.cpp)]  
  
 Die `wmain` -Funktion erstellt eine `IScriptControl` Objekt, fügt Skriptcode hinzu, die die n berechnet<sup>ten</sup> Fibonacci-Zahl, und ruft dann die `RunScriptProcedure` Funktion zum Ausführen dieses Skripts.  
  
 [!code-cpp[concrt-parallel-scripts#8](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_8.cpp)]  
  
### <a name="calling-the-script-from-the-ppl"></a>Aufrufen des Skripts in der PPL  

 Die folgende Funktion `ParallelFibonacci`, verwendet der [Concurrency:: parallel_for](reference/concurrency-namespace-functions.md#parallel_for) Algorithmus, um das Skript parallel aufzurufen. Diese Funktion verwendet die `CCoInitializer`-Klasse, um die Lebensdauer der COM-Bibliothek während jeder Iteration der Aufgabe zu verwalten.  

  
 [!code-cpp[concrt-parallel-scripts#9](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_9.cpp)]  
  
 Um die `ParallelFibonacci`-Funktion im Beispiel zu verwenden, fügen Sie den folgenden Code ein, bevor die `wmain`-Funktion zurückkehrt.  
  
 [!code-cpp[concrt-parallel-scripts#10](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_10.cpp)]  
  
### <a name="calling-the-script-from-an-agent"></a>Aufrufen des Skripts in einem Agent  
 Das folgende Beispiel zeigt die `FibonacciScriptAgent` -Klasse, die eine Skriptprozedur zum Berechnen der n ruft<sup>ten</sup> Fibonacci-Zahl. Die `FibonacciScriptAgent`-Klasse empfängt die Eingabewerte für die Skriptfunktion durch eine Meldungsübergabe vom Hauptprogramm. Die `run`-Methode verwaltet die Lebensdauer von der COM-Bibliothek während der Aufgabe.  
  
 [!code-cpp[concrt-parallel-scripts#11](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_11.cpp)]  
  
 Die folgende Funktion `AgentFibonacci` erstellt mehrere `FibonacciScriptAgent`-Objekte und verwendet die Meldungsübergabe, um mehrere Eingabewerte an diese Objekte zu senden.  
  
 [!code-cpp[concrt-parallel-scripts#12](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_12.cpp)]  
  
 Um die `AgentFibonacci`-Funktion im Beispiel zu verwenden, fügen Sie den folgenden Code ein, bevor die `wmain`-Funktion zurückkehrt.  
  
 [!code-cpp[concrt-parallel-scripts#13](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_13.cpp)]  
  
### <a name="the-complete-example"></a>Vollständiges Beispiel  
 Der folgende Code zeigt ein vollständiges Beispiel, in dem parallele Algorithmen und asynchrone Agents verwendet werden, um eine Skriptprozedur aufzurufen, die Fibonacci-Zahlen berechnet.  
  
 [!code-cpp[concrt-parallel-scripts#14](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_14.cpp)]  
  
 Das Beispiel erzeugt die folgende Beispielausgabe.  
  
```Output  
Main Thread:  
fib(15) = 610  
 
Parallel Fibonacci:  
fib(15) = 610  
fib(10) = 55  
fib(16) = 987  
fib(18) = 2584  
fib(11) = 89  
fib(17) = 1597  
fib(19) = 4181  
fib(12) = 144  
fib(13) = 233  
fib(14) = 377  
 
Agent Fibonacci:  
fib(30) = 832040  
fib(22) = 17711  
fib(10) = 55  
fib(12) = 144  
```  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Kopieren Sie den Beispielcode und fügen Sie ihn in ein Visual Studio-Projekt, oder fügen Sie ihn in eine Datei mit dem Namen `parallel-scripts.cpp` und dann den folgenden Befehl in eine Visual Studio-Eingabeaufforderungsfenster ausführen.  
  
 **CL.exe/EHsc / Parallel-scripts.cpp/Link ole32.lib**  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency Runtime Exemplarische Vorgehensweisen](../../parallel/concrt/concurrency-runtime-walkthroughs.md)   
 [Aufgabenparallelität](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [Parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md)   
 [Asynchrone Agents](../../parallel/concrt/asynchronous-agents.md)   
 [Ausnahmebehandlung](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)   
 [Abbruch in der PPL](cancellation-in-the-ppl.md)   
 [Taskplaner](../../parallel/concrt/task-scheduler-concurrency-runtime.md)

