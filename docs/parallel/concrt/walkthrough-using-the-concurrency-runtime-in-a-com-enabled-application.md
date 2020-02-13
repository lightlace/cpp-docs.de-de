---
title: 'Exemplarische Vorgehensweise: Verwenden der Concurrency Runtime in einer COM-Anwendung'
ms.date: 04/25/2019
helpviewer_keywords:
- Concurrency Runtime, use with COM
- COM, use with the Concurrency Runtime
ms.assetid: a7c798b8-0fc8-4bee-972f-22ef158f7f48
ms.openlocfilehash: faa072ab2b5973ace0f0ca138dcedffa56044213
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77140626"
---
# <a name="walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application"></a>Exemplarische Vorgehensweise: Verwenden der Concurrency Runtime in einer COM-Anwendung

Dieses Dokument veranschaulicht, wie die Concurrency Runtime in einer Anwendung verwendet werden kann, die das Component Object Model (COM) verwendet.

## <a name="prerequisites"></a>Voraussetzungen

Lesen Sie die folgenden Dokumente, bevor Sie mit dieser exemplarischen Vorgehensweise beginnen:

- [Aufgaben Parallelität](../../parallel/concrt/task-parallelism-concurrency-runtime.md)

- [Parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md)

- [Asynchrone Agents](../../parallel/concrt/asynchronous-agents.md)

- [Behandlung von Ausnahmen](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)

Weitere Informationen zu com finden Sie unter [Component Object Model (com)](/windows/win32/com/component-object-model--com--portal).

## <a name="managing-the-lifetime-of-the-com-library"></a>Verwalten der Lebensdauer der COM-Bibliothek

Obwohl für die Verwendung von COM mit der Concurrency Runtime die gleichen Prinzipien gelten wie bei anderen Parallelitätsmechanismen, können die folgenden Richtlinien hilfreich sein, um eine effektive Verwendung beider Bibliotheken zu erreichen.

- Ein Thread muss [CoInitializeEx](/windows/win32/api/combaseapi/nf-combaseapi-coinitializeex) aufrufen, bevor er die com-Bibliothek verwendet.

- Ein Thread kann `CoInitializeEx` mehrmals aufrufen, solange bei jedem Aufruf die gleichen Argumente übergeben werden.

- Für jeden `CoInitializeEx`-Aufrufe muss ein Thread auch " [CallInitialize](/windows/win32/api/combaseapi/nf-combaseapi-couninitialize)" aufruft. Aufrufe von `CoInitializeEx` und `CoUninitialize` müssen also ausgeglichen sein.

- Um von einem Threadapartment zu einem anderen zu wechseln, muss ein Thread die COM-Bibliothek vollständig freigeben, bevor `CoInitializeEx` mit der neuen Threadingspezifikation aufgerufen wird.

Wenn Sie COM mit der Concurrency Runtime verwenden, gelten andere COM-Prinzipien. Zum Beispiel muss eine Anwendung, die ein Objekt in einem Singlethread-Apartment (STA) erstellt und das Objekt in einem anderen Apartment marshallt, außerdem eine Meldungsschleife zum Verarbeiten eingehender Meldungen bereitstellen. Beachten Sie dabei außerdem, dass das Marshalling von Objekten zwischen Apartments zu Leistungsverlust führen kann.

### <a name="using-com-with-the-parallel-patterns-library"></a>Verwenden von COM mit der Parallel Patterns Library

Wenn Sie COM mit einer Komponente in der Parallel Patterns Library (PPL) verwenden, z. B. einer Aufgabengruppe oder einem parallelen Algorithmus, rufen Sie bei jeder Aufgabe oder Iteration `CoInitializeEx` auf, bevor Sie die COM-Bibliothek verwenden, und `CoUninitialize`, bevor die Aufgabe oder Iteration beendet wird. Das folgende Beispiel zeigt, wie die Lebensdauer der com-Bibliothek mit einem [parallelcurrency:: structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) -Objekt verwaltet wird.

[!code-cpp[concrt-parallel-scripts#1](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_1.cpp)]

Sie müssen sicherstellen, dass die COM-Bibliothek ordnungsgemäß freigegeben wird, wenn eine Aufgabe oder ein paralleler Algorithmus abgebrochen wird, oder wenn der Aufgabentext eine Ausnahme auslöst. Um sicherzustellen, dass der Task vor dem Beenden `CoUninitialize` aufruft, verwenden Sie einen `try-finally` Block oder das RAII-Muster ( *Resource Acquisition Is Initialization* ). Das folgende Beispiel gibt die COM-Bibliothek in einem `try-finally`-Block frei, wenn die Aufgabe abgeschlossen oder abgebrochen wird, oder wenn eine Ausnahme ausgelöst wird.

[!code-cpp[concrt-parallel-scripts#2](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_2.cpp)]

Das folgende Beispiel definiert mithilfe des RAII-Musters die `CCoInitializer`-Klasse, die die Lebensdauer der COM-Bibliothek in einem angegebenen Gültigkeitsbereich verwaltet.

[!code-cpp[concrt-parallel-scripts#3](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_3.cpp)]

Mithilfe der `CCoInitializer`-Klasse können Sie die COM-Bibliothek wie folgt automatisch freigeben, sobald die Aufgabe beendet wird.

[!code-cpp[concrt-parallel-scripts#4](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_4.cpp)]

Weitere Informationen zum Abbruch in der Concurrency Runtime finden Sie unter [Abbruch in der ppl](cancellation-in-the-ppl.md).

### <a name="using-com-with-asynchronous-agents"></a>Verwenden von COM mit asynchronen Agents

Wenn Sie com mit asynchronen Agents verwenden, wird `CoInitializeEx` aufgerufen, bevor Sie die com-Bibliothek in der Methode " [parallelcurrency:: Agent:: Run](reference/agent-class.md#run) " für den Agent verwenden. Rufen Sie anschließend `CoUninitialize` auf, bevor die `run`-Methode zurückkehrt. Verwenden Sie keine com-Verwaltungsroutinen im Konstruktor oder Dekonstruktor des Agents, und überschreiben Sie die Methoden " [parallelcurrency:: Agent:: Start](reference/agent-class.md#start) " oder " [parallelcurrency:: Agent::d One](reference/agent-class.md#done) " nicht, da diese Methoden von einem anderen Thread aufgerufen werden als die `run` Methode.

Das folgende Beispiel zeigt eine einfache Agent-Klasse mit dem Namen `CCoAgent`, die die COM-Bibliothek in der `run`-Methode verwaltet.

[!code-cpp[concrt-parallel-scripts#5](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_5.cpp)]

Ein vollständiges Beispiel wird später in dieser exemplarischen Vorgehensweise vorgestellt.

### <a name="using-com-with-lightweight-tasks"></a>Verwenden von COM mit einfachen Aufgaben

Im Dokument [Taskplaner](../../parallel/concrt/task-scheduler-concurrency-runtime.md) wird die Rolle von Lightweight-Aufgaben in der Concurrency Runtime beschrieben. Sie können COM genauso mit einer einfachen Aufgabe verwenden wie mit jeder Threadroutine, die Sie in der Windows-API an die `CreateThread`-Funktion übergeben. Dies wird im folgenden Beispiel gezeigt.

[!code-cpp[concrt-parallel-scripts#6](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_6.cpp)]

## <a name="an-example-of-a-com-enabled-application"></a>Ein Beispiel für eine COM-aktivierte Anwendung

In diesem Abschnitt wird eine vollständige com-aktivierte Anwendung gezeigt, die die `IScriptControl`-Schnittstelle verwendet, um ein Skript auszuführen, das<sup>die n-</sup> te "fbonacci"-Zahl In diesem Beispiel wird das Skript zuerst im Hauptthread aufgerufen und anschließend die PPL und die Agents verwendet, um das Skript parallel aufzurufen.

Betrachten Sie die folgende Hilfsfunktion `RunScriptProcedure`, die eine Prozedur in einem `IScriptControl`-Objekt aufruft.

[!code-cpp[concrt-parallel-scripts#7](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_7.cpp)]

Die `wmain`-Funktion erstellt ein `IScriptControl` Objekt, fügt diesem Skriptcode hinzu, mit dem die<sup>n-</sup> te "fbonacci"-Zahl berechnet wird, und ruft dann die `RunScriptProcedure`-Funktion auf, um das Skript auszuführen.

[!code-cpp[concrt-parallel-scripts#8](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_8.cpp)]

### <a name="calling-the-script-from-the-ppl"></a>Aufrufen des Skripts in der PPL

Die folgende Funktion, `ParallelFibonacci`, verwendet den Parallelitäts [::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) -Algorithmus, um das Skript parallel aufzurufen. Diese Funktion verwendet die `CCoInitializer`-Klasse, um die Lebensdauer der COM-Bibliothek während jeder Iteration der Aufgabe zu verwalten.

[!code-cpp[concrt-parallel-scripts#9](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_9.cpp)]

Um die `ParallelFibonacci`-Funktion im Beispiel zu verwenden, fügen Sie den folgenden Code ein, bevor die `wmain`-Funktion zurückkehrt.

[!code-cpp[concrt-parallel-scripts#10](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_10.cpp)]

### <a name="calling-the-script-from-an-agent"></a>Aufrufen des Skripts in einem Agent

Das folgende Beispiel zeigt die `FibonacciScriptAgent`-Klasse, die eine Skript Prozedur aufruft, um<sup>die n-</sup> te "fbonacci"-Zahl zu berechnen. Die `FibonacciScriptAgent`-Klasse empfängt die Eingabewerte für die Skriptfunktion durch eine Meldungsübergabe vom Hauptprogramm. Die `run`-Methode verwaltet die Lebensdauer von der COM-Bibliothek während der Aufgabe.

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

Kopieren Sie den Beispielcode, und fügen Sie ihn in ein Visual Studio-Projekt ein, oder fügen Sie ihn in eine Datei mit dem Namen `parallel-scripts.cpp` ein, und führen Sie dann den folgenden Befehl in einem Visual Studio-Eingabe Aufforderungs Fenster aus.

> **cl. exe/EHsc parallel-Scripts. cpp/Link ole32. lib**

## <a name="see-also"></a>Weitere Informationen

[Exemplarische Vorgehensweisen für die Concurrency Runtime](../../parallel/concrt/concurrency-runtime-walkthroughs.md)<br/>
[Aufgaben Parallelität](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[Parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md)<br/>
[Asynchrone Agents](../../parallel/concrt/asynchronous-agents.md)<br/>
[Behandlung von Ausnahmen](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)<br/>
[Abbruch in der PPL](cancellation-in-the-ppl.md)<br/>
[Aufgabenplanung](../../parallel/concrt/task-scheduler-concurrency-runtime.md)
