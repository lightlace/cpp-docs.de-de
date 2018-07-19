---
title: 'Vorgehensweise: Erstellen einer Aufgabe, die nach einer Verzögerung abgeschlossen wird. | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- task_completion_event class, example
- create a task that completes after a delay, example [C++]
ms.assetid: 3fc0a194-3fdb-4eba-8b8a-b890981a985d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fca1ba3874f02b44f96fd795b531536a23c8d462
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33688410"
---
# <a name="how-to-create-a-task-that-completes-after-a-delay"></a>Gewusst wie: Erstellen einer Aufgabe, die nach einer Verzögerung abgeschlossen wird
Dieses Beispiel zeigt, wie die [Concurrency:: Task](../../parallel/concrt/reference/task-class.md), [cancellation_token_source](../../parallel/concrt/reference/cancellation-token-source-class.md), [cancellation_token](../../parallel/concrt/reference/cancellation-token-class.md), [ Concurrency:: task_completion_event](../../parallel/concrt/reference/task-completion-event-class.md), [Concurrency:: Timer](../../parallel/concrt/reference/timer-class.md), und [Call](../../parallel/concrt/reference/call-class.md) Klassen, die eine Aufgabe zu erstellen, die nach einer Verzögerung abgeschlossen wird. Sie können diese Methode verwenden, Schleifen zu erstellen, die gelegentlich Daten abrufen, Timeouts einführen, die Verarbeitung von Benutzereingaben für einen zuvor festgelegten Zeitraum verzögern und so weiter.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden die Funktionen `complete_after` und `cancel_after_timeout` dargestellt. Die `complete_after` -Funktion erstellt eine `task` -Objekt, das nach Ablauf der angegebenen Verzögerung abgeschlossen wird. Verwendet eine `timer` Objekt und ein `call` festzulegende Objekt eine `task_completion_event` Objekt nach der angegebenen Verzögerung. Mithilfe der `task_completion_event` -Klasse, definieren Sie eine Aufgabe, die nach einem Thread abgeschlossen wird oder eine andere Aufgabe signalisiert, dass ein Wert verfügbar ist. Wenn das Ereignis festgelegt ist, listeneraufgaben abgeschlossen und ihre Fortsetzungen geplant sind.  
  
> [!TIP]
>  Weitere Informationen zu den `timer` und `call` Klassen, die Teil der Asynchronous Agents Library sind, finden Sie unter [asynchrone Meldungsblöcke](../../parallel/concrt/asynchronous-message-blocks.md).  
  
 Die `cancel_after_timeout` Funktion baut auf den `complete_after` Funktion, um eine Aufgabe abbrechen, wenn diese Aufgabe nicht vor dem angegebenen Timeout abgeschlossen wird. Die `cancel_after_timeout` Funktion erstellt zwei Aufgaben. Die erste Aufgabe gibt die erfolgreiche Ausführung und nach die angegebene Aufgabe abgeschlossen wird. der zweite Task weisen auf Fehler hin und nach dem angegebenen Timeout abgeschlossen wird. Die `cancel_after_timeout` -Funktion erstellt eine Fortsetzungsaufgabe, die ausgeführt wird, wenn der Erfolg oder Misserfolg Aufgabe abgeschlossen ist. Wenn der Task Fehler erste abgeschlossen wird, bricht die Fortsetzung der Tokenquelle, um die gesamte Aufgabe abbrechen ab.  
  
 [!code-cpp[concrt-task-delay#1](../../parallel/concrt/codesnippet/cpp/how-to-create-a-task-that-completes-after-a-delay_1.cpp)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel berechnet die Anzahl von Primzahlen im Bereich [0, 100000] mehrmals. Der Vorgang schlägt fehl, wenn er nicht innerhalb eines bestimmten Zeitlimits abgeschlossen ist. Die `count_primes` Funktion veranschaulicht, wie die `cancel_after_timeout` Funktion. Zählt die Anzahl der Primzahlen wie folgt im angegebenen Bereich, und schlägt fehl, wenn der Task nicht in der angegebenen Zeit abgeschlossen wird. Die `wmain` Funktionsaufrufe, die `count_primes` mehrmals-Funktion. In jedem Fall halbiert es das Zeitlimit überschreiten. Das Programm beendet wird, nachdem der Vorgang nicht in der aktuellen Zeit abgeschlossen wird.  
  
 [!code-cpp[concrt-task-delay#2](../../parallel/concrt/codesnippet/cpp/how-to-create-a-task-that-completes-after-a-delay_2.cpp)]  
  
 Wenn Sie diese Technik verwenden, um die Aufgaben nach einer Verzögerung "Abbrechen", beginnt noch nicht gestartete Aufgaben nicht, nachdem die gesamte Aufgabe abgebrochen wird. Allerdings ist es wichtig, für die lang andauernden Aufgaben rechtzeitig auf den Abbruch zu reagieren. Weitere Informationen zu den Aufgabenabbruch, finden Sie unter [Abbruch in der PPL](cancellation-in-the-ppl.md).  
  
## <a name="example"></a>Beispiel  
 Hier wird der vollständige Code für dieses Beispiel aus:  
  
 [!code-cpp[concrt-task-delay#3](../../parallel/concrt/codesnippet/cpp/how-to-create-a-task-that-completes-after-a-delay_3.cpp)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Um den Code zu kompilieren, kopieren Sie ihn und fügen Sie ihn in ein Visual Studio-Projekt ein, oder fügen Sie ihn in eine Datei mit dem Namen `task-delay.cpp` und dann den folgenden Befehl in eine Visual Studio-Eingabeaufforderungsfenster ausführen.  
  
 **CL.exe/EHsc / Task-delay.cpp**  
  
## <a name="see-also"></a>Siehe auch  
 [Aufgabenparallelität](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [Aufgabenklasse (Concurrency Runtime)](../../parallel/concrt/reference/task-class.md)   
 [Cancellation_token_source-Klasse](../../parallel/concrt/reference/cancellation-token-source-class.md)   
 [Cancellation_token-Klasse](../../parallel/concrt/reference/cancellation-token-class.md)   
 [Task_completion_event-Klasse](../../parallel/concrt/reference/task-completion-event-class.md)   
 [Timer-Klasse](../../parallel/concrt/reference/timer-class.md)   
 [Call-Klasse](../../parallel/concrt/reference/call-class.md)   
 [Asynchrone Nachrichtenblöcke](../../parallel/concrt/asynchronous-message-blocks.md)   
 [Abbruch in der PPL](cancellation-in-the-ppl.md)

