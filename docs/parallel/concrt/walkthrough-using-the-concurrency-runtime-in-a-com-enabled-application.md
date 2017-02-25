---
title: "Exemplarische Vorgehensweise: Verwenden der Concurrency Runtime in einer COM-Anwendung | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Concurrency Runtime, Verwenden mit COM"
  - "COM, Verwenden mit Concurrency Runtime"
ms.assetid: a7c798b8-0fc8-4bee-972f-22ef158f7f48
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Exemplarische Vorgehensweise: Verwenden der Concurrency Runtime in einer COM-Anwendung
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dieses Dokument veranschaulicht, wie die Concurrency Runtime in einer Anwendung verwendet werden kann, die das Component Object Model \(COM\) verwendet.  
  
## Vorbereitungsmaßnahmen  
 Lesen Sie die folgenden Dokumente, bevor Sie mit dieser exemplarischen Vorgehensweise beginnen:  
  
-   [Aufgabenparallelität](../../parallel/concrt/task-parallelism-concurrency-runtime.md)  
  
-   [Parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md)  
  
-   [Asynchrone Agents](../../parallel/concrt/asynchronous-agents.md)  
  
-   [Ausnahmebehandlung](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)  
  
 Weitere Informationen zu COM finden Sie unter [Component Object Model \(COM\)](http://msdn.microsoft.com/library/windows/desktop/ms680573).  
  
## Verwalten der Lebensdauer der COM\-Bibliothek  
 Obwohl für die Verwendung von COM mit der Concurrency Runtime die gleichen Prinzipien gelten wie bei anderen Parallelitätsmechanismen, können die folgenden Richtlinien hilfreich sein, um eine effektive Verwendung beider Bibliotheken zu erreichen.  
  
-   Ein Thread muss [CoInitializeEx](http://msdn.microsoft.com/library/windows/desktop/ms695279) aufrufen, bevor er die COM\-Bibliothek verwendet.  
  
-   Ein Thread kann `CoInitializeEx` mehrmals aufrufen, solange bei jedem Aufruf die gleichen Argumente übergeben werden.  
  
-   Für jeden Aufruf von `CoInitializeEx` muss ein Thread auch [CoUninitialize](http://msdn.microsoft.com/library/windows/desktop/ms688715) aufrufen.  Aufrufe von `CoInitializeEx` und `CoUninitialize` müssen also ausgeglichen sein.  
  
-   Um von einem Threadapartment zu einem anderen zu wechseln, muss ein Thread die COM\-Bibliothek vollständig freigeben, bevor `CoInitializeEx` mit der neuen Threadingspezifikation aufgerufen wird.  
  
 Wenn Sie COM mit der Concurrency Runtime verwenden, gelten andere COM\-Prinzipien.  Zum Beispiel muss eine Anwendung, die ein Objekt in einem Singlethread\-Apartment \(STA\) erstellt und das Objekt in einem anderen Apartment marshallt, außerdem eine Meldungsschleife zum Verarbeiten eingehender Meldungen bereitstellen.  Beachten Sie dabei außerdem, dass das Marshalling von Objekten zwischen Apartments zu Leistungsverlust führen kann.  
  
### Verwenden von COM mit der Parallel Patterns Library  
 Wenn Sie COM mit einer Komponente in der Parallel Patterns Library \(PPL\) verwenden, z. B. einer Aufgabengruppe oder einem parallelen Algorithmus, rufen Sie bei jeder Aufgabe oder Iteration `CoInitializeEx` auf, bevor Sie die COM\-Bibliothek verwenden, und `CoUninitialize`, bevor die Aufgabe oder Iteration beendet wird.  Im folgenden Beispiel wird gezeigt, wie die Lebensdauer der COM\-Bibliothek mit einem [concurrency::structured\_task\_group](../../parallel/concrt/reference/structured-task-group-class.md)\-Objekt verwaltet wird.  
  
 [!CODE [concrt-parallel-scripts#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-parallel-scripts#1)]  
  
 Sie müssen sicherstellen, dass die COM\-Bibliothek ordnungsgemäß freigegeben wird, wenn eine Aufgabe oder ein paralleler Algorithmus abgebrochen wird, oder wenn der Aufgabentext eine Ausnahme auslöst.  Um zu gewährleisten, dass die Aufgabe vor ihrer Beendigung `CoUninitialize` aufruft, verwenden Sie einen `try-finally`\-Block oder das RAII \(*Resource Acquisition Is Initialization*\)\-Muster.  Das folgende Beispiel gibt die COM\-Bibliothek in einem `try-finally`\-Block frei, wenn die Aufgabe abgeschlossen oder abgebrochen wird, oder wenn eine Ausnahme ausgelöst wird.  
  
 [!CODE [concrt-parallel-scripts#2](../CodeSnippet/VS_Snippets_ConcRT/concrt-parallel-scripts#2)]  
  
 Das folgende Beispiel definiert mithilfe des RAII\-Musters die `CCoInitializer`\-Klasse, die die Lebensdauer der COM\-Bibliothek in einem angegebenen Gültigkeitsbereich verwaltet.  
  
 [!CODE [concrt-parallel-scripts#3](../CodeSnippet/VS_Snippets_ConcRT/concrt-parallel-scripts#3)]  
  
 Mithilfe der `CCoInitializer`\-Klasse können Sie die COM\-Bibliothek wie folgt automatisch freigeben, sobald die Aufgabe beendet wird.  
  
 [!CODE [concrt-parallel-scripts#4](../CodeSnippet/VS_Snippets_ConcRT/concrt-parallel-scripts#4)]  
  
 Weitere Informationen zu Abbrüchen in der Concurrency Runtime finden Sie unter [Abbruch](../../parallel/concrt/cancellation-in-the-ppl.md).  
  
### Verwenden von COM mit asynchronen Agents  
 Wenn Sie COM mit asynchronen Agents verwenden, rufen Sie `CoInitializeEx` auf, bevor Sie die COM\-Bibliothek in der [concurrency::agent::run](../Topic/agent::run%20Method.md)\-Methode des Agents verwenden.  Rufen Sie anschließend `CoUninitialize` auf, bevor die `run`\-Methode zurückkehrt.  Verwenden Sie keine COM\-Verwaltungsroutinen im Konstruktor oder Destruktor des Agents, und überschreiben Sie nicht die [concurrency::agent::start](../Topic/agent::start%20Method.md)\-Methode oder die [concurrency::agent::done](../Topic/agent::done%20Method.md)\-Methode, da diese Methoden von einem anderen Thread aufgerufen werden als die `run`\-Methode.  
  
 Das folgende Beispiel zeigt eine einfache Agent\-Klasse mit dem Namen `CCoAgent`, die die COM\-Bibliothek in der `run`\-Methode verwaltet.  
  
 [!CODE [concrt-parallel-scripts#5](../CodeSnippet/VS_Snippets_ConcRT/concrt-parallel-scripts#5)]  
  
 Ein vollständiges Beispiel wird später in dieser exemplarischen Vorgehensweise vorgestellt.  
  
### Verwenden von COM mit einfachen Aufgaben  
 Das Dokument [Taskplaner](../../parallel/concrt/task-scheduler-concurrency-runtime.md) beschreibt die Rolle einfacher Aufgaben in der Concurrency Runtime.  Sie können COM genauso mit einer einfachen Aufgabe verwenden wie mit jeder Threadroutine, die Sie in der Windows\-API an die `CreateThread`\-Funktion übergeben.  Dies wird im folgenden Beispiel gezeigt.  
  
 [!CODE [concrt-parallel-scripts#6](../CodeSnippet/VS_Snippets_ConcRT/concrt-parallel-scripts#6)]  
  
## Ein Beispiel für eine COM\-aktivierte Anwendung  
 Dieser Abschnitt zeigt eine vollständige COM\-aktivierte Anwendung, die die `IScriptControl`\-Schnittstelle verwendet, um ein Skript auszuführen, mit dem die n<sup>te</sup> Fibonacci\-Zahl berechnet wird.  In diesem Beispiel wird das Skript zuerst im Hauptthread aufgerufen und anschließend die PPL und die Agents verwendet, um das Skript parallel aufzurufen.  
  
 Betrachten Sie die folgende Hilfsfunktion `RunScriptProcedure`, die eine Prozedur in einem `IScriptControl`\-Objekt aufruft.  
  
 [!CODE [concrt-parallel-scripts#7](../CodeSnippet/VS_Snippets_ConcRT/concrt-parallel-scripts#7)]  
  
 Die `wmain`\-Funktion erstellt ein `IScriptControl`\-Objekt, fügt Skriptcode hinzu, der die n<sup>te</sup> Fibonacci\-Zahl berechnet, und ruft dann die `RunScriptProcedure`\-Funktion auf, um das Skript auszuführen.  
  
 [!CODE [concrt-parallel-scripts#8](../CodeSnippet/VS_Snippets_ConcRT/concrt-parallel-scripts#8)]  
  
### Aufrufen des Skripts in der PPL  
 Die folgende Funktion `ParallelFibonacci` ruft das Skript mithilfe des [concurrency::parallel\_for](../Topic/parallel_for%20Function.md)\-Algorithmus parallel auf.  Diese Funktion verwendet die `CCoInitializer`\-Klasse, um die Lebensdauer der COM\-Bibliothek während jeder Iteration der Aufgabe zu verwalten.  
  
 [!CODE [concrt-parallel-scripts#9](../CodeSnippet/VS_Snippets_ConcRT/concrt-parallel-scripts#9)]  
  
 Um die `ParallelFibonacci`\-Funktion im Beispiel zu verwenden, fügen Sie den folgenden Code ein, bevor die `wmain`\-Funktion zurückkehrt.  
  
 [!CODE [concrt-parallel-scripts#10](../CodeSnippet/VS_Snippets_ConcRT/concrt-parallel-scripts#10)]  
  
### Aufrufen des Skripts in einem Agent  
 Im folgenden Beispiel wird die `FibonacciScriptAgent`\-Klasse veranschaulicht, die eine Skriptprozedur aufruft, um die n<sup>te</sup> Fibonacci\-Zahl zu berechnen.  Die `FibonacciScriptAgent`\-Klasse empfängt die Eingabewerte für die Skriptfunktion durch eine Meldungsübergabe vom Hauptprogramm.  Die `run`\-Methode verwaltet die Lebensdauer von der COM\-Bibliothek während der Aufgabe.  
  
 [!CODE [concrt-parallel-scripts#11](../CodeSnippet/VS_Snippets_ConcRT/concrt-parallel-scripts#11)]  
  
 Die folgende Funktion `AgentFibonacci` erstellt mehrere `FibonacciScriptAgent`\-Objekte und verwendet die Meldungsübergabe, um mehrere Eingabewerte an diese Objekte zu senden.  
  
 [!CODE [concrt-parallel-scripts#12](../CodeSnippet/VS_Snippets_ConcRT/concrt-parallel-scripts#12)]  
  
 Um die `AgentFibonacci`\-Funktion im Beispiel zu verwenden, fügen Sie den folgenden Code ein, bevor die `wmain`\-Funktion zurückkehrt.  
  
 [!CODE [concrt-parallel-scripts#13](../CodeSnippet/VS_Snippets_ConcRT/concrt-parallel-scripts#13)]  
  
### Vollständiges Beispiel  
 Der folgende Code zeigt ein vollständiges Beispiel, in dem parallele Algorithmen und asynchrone Agents verwendet werden, um eine Skriptprozedur aufzurufen, die Fibonacci\-Zahlen berechnet.  
  
 [!CODE [concrt-parallel-scripts#14](../CodeSnippet/VS_Snippets_ConcRT/concrt-parallel-scripts#14)]  
  
 Das Beispiel erzeugt die folgende Beispielausgabe.  
  
  **Main Thread:**  
**fib\(15\) \= 610**  
**Parallel Fibonacci:**  
**fib\(15\) \= 610**  
**fib\(10\) \= 55**  
**fib\(16\) \= 987**  
**fib\(18\) \= 2584**  
**fib\(11\) \= 89**  
**fib\(17\) \= 1597**  
**fib\(19\) \= 4181**  
**fib\(12\) \= 144**  
**fib\(13\) \= 233**  
**fib\(14\) \= 377**  
**Agent Fibonacci:**  
**fib\(30\) \= 832040**  
**fib\(22\) \= 17711**  
**fib\(10\) \= 55**  
**fib\(12\) \= 144**   
## Kompilieren des Codes  
 Kopieren Sie den Beispielcode, und fügen Sie ihn in ein Visual Studio\-Projekt ein. Alternativ dazu können Sie ihn auch in eine Datei mit dem Namen `parallel-scripts.cpp` einfügen und dann folgenden Befehl in einem Visual Studio\-Eingabeaufforderungsfenster ausführen.  
  
 **cl.exe \/EHsc parallel\-scripts.cpp \/link ole32.lib**  
  
## Siehe auch  
 [Exemplarische Vorgehensweisen für die Concurrency Runtime](../../parallel/concrt/concurrency-runtime-walkthroughs.md)   
 [Aufgabenparallelität](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [Parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md)   
 [Asynchrone Agents](../../parallel/concrt/asynchronous-agents.md)   
 [Ausnahmebehandlung](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)   
 [Abbruch](../../parallel/concrt/cancellation-in-the-ppl.md)   
 [Taskplaner](../../parallel/concrt/task-scheduler-concurrency-runtime.md)