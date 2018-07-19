---
title: Einfache Aufgaben | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- lightweight tasks
ms.assetid: b6dcfc7a-9fa9-4144-96a6-2845ea272017
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d602f83cfe2da6bc1506e07720d3ef021ebce04a
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33687412"
---
# <a name="lightweight-tasks"></a>Einfache Aufgaben
Dieses Dokument beschreibt die Rolle einfacher Aufgaben in der Concurrency Runtime. Ein *einfache Aufgabe* ist eine Aufgabe, die Sie direkt aus Planen einer `concurrency::Scheduler` oder `concurrency::ScheduleGroup` Objekt. Eine einfache Aufgabe ähnelt der Funktion, die Sie für die Windows-API bereitstellen [CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453) Funktion. Aus diesem Grund sind einfache Aufgaben hilfreich beim Anpassen von vorhandenen Codes, um die Planungsfunktionalität der Concurrency Runtime verwenden. Die Concurrency Runtime selbst verwendet einfache Aufgaben, Planen asynchrone Agents und Senden von Nachrichten zwischen asynchrone Meldungsblöcke.  
  
> [!TIP]
>  Die Concurrency Runtime stellt einen Standardplaner bereit. Sie müssen daher keinen in Ihrer Anwendung erstellen. Da der Taskplaner Sie beim Optimieren der Leistung Ihrer Anwendungen unterstützt, empfiehlt es sich, dass die zu Beginn der [Parallel Patterns Library (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) oder [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md) Domänenmodus noch nicht mit der Concurrency Runtime.  
  
 Einfache Aufgaben erfordern einen geringeren Aufwand als asynchrone Agents und Aufgabengruppen. Z. B. informiert die Common Language Runtime Sie nicht, wenn eine einfache Aufgabe beendet ist. Darüber hinaus die Common Language Runtime werden keine abfangen oder Ausnahmen behandelt, die aus einer einfachen Aufgabe ausgelöst werden. Weitere Informationen zur Behandlung von Ausnahmen und einfache Aufgaben finden Sie unter [Exception Handling](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).  
  
 Es wird empfohlen, Sie eine robustere Funktionen wie Aufgabengruppen verwenden und parallele Algorithmen, da sie Sie leichter können komplexe Aufgaben in weitere grundlegende diejenigen gliedern, für die meisten Aufgaben. Weitere Informationen zu Gruppen finden Sie unter [Aufgabenparallelität](../../parallel/concrt/task-parallelism-concurrency-runtime.md). Weitere Informationen zu parallelen Algorithmen finden Sie unter [parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md).  
  
 Um eine einfache Aufgabe zu erstellen, rufen die [Concurrency::ScheduleGroup::ScheduleTask](reference/schedulegroup-class.md#scheduletask), [Concurrency::CurrentScheduler::ScheduleTask](reference/currentscheduler-class.md#scheduletask), oder [Concurrency::Scheduler::ScheduleTask ](reference/scheduler-class.md#scheduletask) Methode. Warten Sie auf Fertig stellen eine einfache Aufgabe warten, übergeordneten Zeitplanungsmoduls Herunterfahren, oder verwenden einen Synchronisierungsmechanismus wie z. B. eine [Concurrency:: Event](../../parallel/concrt/reference/event-class.md) Objekt.  
  
## <a name="example"></a>Beispiel  
 Ein Beispiel, das veranschaulicht, wie vorhandener Code zum Verwenden einer einfachen Aufgabe angepasst wird, finden Sie unter [Exemplarische Vorgehensweise: Anpassen von vorhandenen Code zum Verwenden von einfachen Aufgaben](../../parallel/concrt/walkthrough-adapting-existing-code-to-use-lightweight-tasks.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Taskplaner](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [Exemplarische Vorgehensweise: Anpassen von vorhandenem Code für die Verwendung einfacher Aufgaben](../../parallel/concrt/walkthrough-adapting-existing-code-to-use-lightweight-tasks.md)

