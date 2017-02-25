---
title: "Gewusst wie: Erstellen einer Aufgabe, die nach einer Verz&#246;gerung abgeschlossen wird | Microsoft Docs"
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
  - "Task_completion_event-Klasse, Beispiel:"
  - "Erstellen Sie eine Aufgabe, die nach einer Verzögerung Beispiel [C++] abgeschlossen wird."
ms.assetid: 3fc0a194-3fdb-4eba-8b8a-b890981a985d
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Gewusst wie: Erstellen einer Aufgabe, die nach einer Verz&#246;gerung abgeschlossen wird
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dieses Beispiel zeigt, wie Sie die [Concurrency:: Task](../../parallel/concrt/reference/task-class-concurrency-runtime.md), [cancellation_token_source](../../parallel/concrt/reference/cancellation-token-source-class.md), [cancellation_token](../../parallel/concrt/reference/cancellation-token-class.md), [Concurrency:: task_completion_event](../../parallel/concrt/reference/task-completion-event-class.md), "Concurrency:: Timer", und [Concurrency:: Call](../../parallel/concrt/reference/call-class.md) Klassen zum Erstellen einer Aufgabe, die nach einer Verzögerung abgeschlossen wird. Diese Methode können Sie Schleifen erstellen, die gelegentlich Daten abrufen, Timeouts einführen, Verarbeitung von Benutzereingaben für einen vorab festgelegten Zeitraum verzögern und so weiter.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden die Funktionen `complete_after` und `cancel_after_timeout` dargestellt. Die `complete_after` -Funktion erstellt ein `task` -Objekt, das nach der angegebenen Verzögerung abgeschlossen wird. Verwendet ein `timer` Objekt und ein `call` festzulegende Objekt ein `task_completion_event` Objekt nach der angegebenen Verzögerung. Mithilfe der `task_completion_event` -Klasse, definieren Sie eine Aufgabe, die nach einem Thread abgeschlossen ist, oder eine andere Aufgabe signalisiert, dass ein Wert verfügbar ist. Wenn das Ereignis festgelegt ist, listeneraufgaben abgeschlossen und ihre Fortsetzungen geplant sind.  
  
> [!TIP]
>  Weitere Informationen zu den `timer` und `call` Klassen, die Teil der Asynchronous Agents Library sind, finden Sie unter [asynchrone Meldungsblöcke](../../parallel/concrt/asynchronous-message-blocks.md).  
  
 Die `cancel_after_timeout` Funktion baut auf der `complete_after` Funktion, um eine Aufgabe abbrechen, wenn die Aufgabe nicht vor einem angegebenen Timeout abgeschlossen wird. Die `cancel_after_timeout` Funktion werden zwei Aufgaben erstellt. Die erste Aufgabe gibt Erfolg und abgeschlossen wird, nachdem die angegebene Aufgabe abgeschlossen ist. die zweite Aufgabe gibt einen Fehler an und nach dem angegebenen Timeout abgeschlossen ist. Die `cancel_after_timeout` -Funktion erstellt eine Fortsetzungsaufgabe, die ausgeführt wird, wenn der Erfolg oder Misserfolg der Task abgeschlossen ist. Wenn der Fehler bei Vorgang zuerst ausgeführt wird, bricht die Fortsetzung die Tokenquelle, um die gesamte Aufgabe abzubrechen.  
  
 [!CODE [concrt-task-delay#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-task-delay#1)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel berechnet die Anzahl von Primzahlen im Bereich [0, 100000] mehrere Male. Der Vorgang schlägt fehl, wenn er nicht in einer bestimmten Zeit ausgeführt werden kann. Die `count_primes` Funktion veranschaulicht, wie die `cancel_after_timeout` Funktion. Es zählt die Anzahl der Brücken im angegebenen Bereich und schlägt fehl, wenn die Aufgabe nicht innerhalb der angegebenen Zeit abgeschlossen wird. Die `wmain` -Funktion ruft die `count_primes` Funktion mehrmals. Jedes Mal halbiert es das Zeitlimit überschritten. Das Programm beendet wird, nachdem der Vorgang nicht in der aktuellen Zeit abgeschlossen wird.  
  
 [!CODE [concrt-task-delay#2](../CodeSnippet/VS_Snippets_ConcRT/concrt-task-delay#2)]  
  
 Wenn Sie dieses Verfahren zum Abbrechen von Aufgaben nach einer Verzögerung verwenden, werden nicht gestartete Aufgaben nicht gestartet werden, nachdem die gesamte Aufgabe abgebrochen wurde. Es ist jedoch wichtig für lang ausgeführte Aufgaben rechtzeitig auf den Abbruch reagieren. In diesem Beispiel wird die `count_primes` -Methode ruft die [Concurrency:: is_task_cancellation_requested](../../misc/is-task-cancellation-requested-function.md) und `cancel_current_task` Funktionen auf den Abbruch reagieren. (Alternativ können Sie Aufrufen der [Concurrency:: interruption_point](../Topic/interruption_point%20Function.md) Funktion). Weitere Informationen zum Taskabbruch finden Sie unter [Abbruch](../../parallel/concrt/cancellation-in-the-ppl.md).  
  
## <a name="example"></a>Beispiel  
 Hier ist der vollständige Code für dieses Beispiel:  
  
 [!CODE [concrt-task-delay#3](../CodeSnippet/VS_Snippets_ConcRT/concrt-task-delay#3)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Um den Code zu kompilieren, kopieren Sie ihn und fügen Sie ihn in ein Visual Studio-Projekt bzw. Fügen Sie ihn in eine Datei mit dem Namen `task-delay.cpp` und dann den folgenden Befehl in einer Visual Studio-Eingabeaufforderungsfenster ausführen.  
  
 **CL.exe/EHsc Task-delay.cpp**  
  
## <a name="see-also"></a>Siehe auch  
 [Aufgabenparallelität](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [Task-Klasse (Concurrency Runtime)](../../parallel/concrt/reference/task-class-concurrency-runtime.md)   
 [Cancellation_token_source-Klasse](../../parallel/concrt/reference/cancellation-token-source-class.md)   
 [Cancellation_token-Klasse](../../parallel/concrt/reference/cancellation-token-class.md)   
 [Task_completion_event-Klasse](../../parallel/concrt/reference/task-completion-event-class.md)   
 [Is_task_cancellation_requested-Funktion](../../misc/is-task-cancellation-requested-function.md)   
 [Cancel_current_task-Funktion](../Topic/cancel_current_task%20Function.md)   
 [Interruption_point-Funktion](../Topic/interruption_point%20Function.md)   
 [Call-Klasse](../../parallel/concrt/reference/call-class.md)   
 [Asynchrone Nachrichtenblöcke](../../parallel/concrt/asynchronous-message-blocks.md)   
 [Abbruch](../../parallel/concrt/cancellation-in-the-ppl.md)