---
title: 'Vorgehensweise: Erstellen Sie eine Aufgabe, die nach einer Verzögerung abgeschlossen wird. | Microsoft-Dokumentation'
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
ms.openlocfilehash: 417562d515cb968b392c4480ddfd55c03ae494d1
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46422570"
---
# <a name="how-to-create-a-task-that-completes-after-a-delay"></a>Gewusst wie: Erstellen einer Aufgabe, die nach einer Verzögerung abgeschlossen wird

Dieses Beispiel zeigt, wie Sie mit der [Concurrency:: Task](../../parallel/concrt/reference/task-class.md), [Concurrency:: cancellation_token_source](../../parallel/concrt/reference/cancellation-token-source-class.md), [Concurrency:: cancellation_token](../../parallel/concrt/reference/cancellation-token-class.md), [ Concurrency:: task_completion_event](../../parallel/concrt/reference/task-completion-event-class.md), [Concurrency:: Timer](../../parallel/concrt/reference/timer-class.md), und [Concurrency:: Call](../../parallel/concrt/reference/call-class.md) Klassen zum Erstellen einer Aufgabe, die nach einer Verzögerung abgeschlossen wird. Sie können diese Methode verwenden, um Schleifen zu erstellen, die gelegentlich Daten abrufen, Timeouts führen, Behandlung von Benutzereingaben für einen zuvor festgelegten Zeitraum verzögern und so weiter.

## <a name="example"></a>Beispiel

Im folgenden Beispiel werden die Funktionen `complete_after` und `cancel_after_timeout` dargestellt. Die `complete_after` -Funktion erstellt eine `task` -Objekt, das nach der angegebenen Verzögerung abgeschlossen wird. Verwendet eine `timer` Objekt und ein `call` Objekt zum Festlegen einer `task_completion_event` Objekt nach der angegebenen Verzögerung. Mithilfe der `task_completion_event` -Klasse, Sie können eine Aufgabe, die nach einem Thread abgeschlossen wird oder eine andere Aufgabe signalisiert, dass ein Wert verfügbar ist. Wenn das Ereignis festgelegt wird, listeneraufgaben abgeschlossen und ihre Fortsetzungen geplant ist.

> [!TIP]
>  Weitere Informationen zu den `timer` und `call` Klassen, die Teil der Asynchronous Agents Library sind, finden Sie unter [asynchrone Meldungsblöcke](../../parallel/concrt/asynchronous-message-blocks.md).

Die `cancel_after_timeout` Funktion baut auf den `complete_after` Funktion, um eine Aufgabe abbrechen, wenn diese Aufgabe nicht vor einem angegebenen Timeout abgeschlossen wird. Die `cancel_after_timeout` Funktion erstellt zwei Aufgaben. Die erste Aufgabe gibt Erfolg und abgeschlossen wird, nachdem die angegebene Aufgabe abgeschlossen ist; der zweite Task gibt Fehler und nach dem angegebenen Timeout abgeschlossen ist. Die `cancel_after_timeout` Funktion erstellt eine Fortsetzungsaufgabe, die ausgeführt wird, wenn die Aufgabe erfolgreich oder fehlerhaft abgeschlossen ist. Wenn der Task Fehler zuerst ausgeführt wird, bricht die Fortsetzung die Tokenquelle, um die gesamte Aufgabe abzubrechen.

[!code-cpp[concrt-task-delay#1](../../parallel/concrt/codesnippet/cpp/how-to-create-a-task-that-completes-after-a-delay_1.cpp)]

## <a name="example"></a>Beispiel

Das folgende Beispiel berechnet die Anzahl von Primzahlen, die im Bereich [0, 100000] mehrmals. Der Vorgang schlägt fehl, wenn er nicht innerhalb eines bestimmten Zeitraums abgeschlossen ist. Die `count_primes` Funktion veranschaulicht, wie die `cancel_after_timeout` Funktion. Es zählt die Anzahl der Primzahlen wie folgt im angegebenen Bereich und schlägt fehl, wenn der Task nicht in der angegebenen Zeit abgeschlossen wird. Die `wmain` Funktionsaufrufe der `count_primes` Funktion mehrmals. Jedes Mal halbiert es das Zeitlimit. Nach Abschluss des Programms, nachdem der Vorgang nicht innerhalb des aktuellen Zeitlimits abgeschlossen ist.

[!code-cpp[concrt-task-delay#2](../../parallel/concrt/codesnippet/cpp/how-to-create-a-task-that-completes-after-a-delay_2.cpp)]

Wenn Sie dieses Verfahren zum Abbrechen von Aufgaben nach einer Verzögerung verwenden, werden nicht gestartete Aufgaben nicht gestartet werden, nachdem die gesamte Aufgabe abgebrochen wird. Allerdings ist es wichtig, dass lang andauernde Aufgaben rechtzeitig auf den Abbruch zu reagieren. Weitere Informationen zum Taskabbruch finden Sie unter [Abbruch in der PPL](cancellation-in-the-ppl.md).

## <a name="example"></a>Beispiel

Hier ist der vollständige Code für dieses Beispiel aus:

[!code-cpp[concrt-task-delay#3](../../parallel/concrt/codesnippet/cpp/how-to-create-a-task-that-completes-after-a-delay_3.cpp)]

## <a name="compiling-the-code"></a>Kompilieren des Codes

Um den Code zu kompilieren, kopieren Sie ihn und fügen Sie ihn in ein Visual Studio-Projekt ein, oder fügen Sie ihn in eine Datei mit dem Namen `task-delay.cpp` und führen Sie dann den folgenden Befehl in einem Fenster von Visual Studio-Eingabeaufforderung.

**CL.exe/EHsc Task-delay.cpp**

## <a name="see-also"></a>Siehe auch

[Aufgabenparallelität](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[task-Klasse (Concurrency Runtime)](../../parallel/concrt/reference/task-class.md)<br/>
[cancellation_token_source-Klasse](../../parallel/concrt/reference/cancellation-token-source-class.md)<br/>
[cancellation_token-Klasse](../../parallel/concrt/reference/cancellation-token-class.md)<br/>
[task_completion_event-Klasse](../../parallel/concrt/reference/task-completion-event-class.md)<br/>
[timer-Klasse](../../parallel/concrt/reference/timer-class.md)<br/>
[call-Klasse](../../parallel/concrt/reference/call-class.md)<br/>
[Asynchrone Nachrichtenblöcke](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[Abbruch in der PPL](cancellation-in-the-ppl.md)

