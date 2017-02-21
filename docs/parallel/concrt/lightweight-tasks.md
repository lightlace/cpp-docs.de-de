---
title: "Einfache Aufgaben | Microsoft Docs"
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
  - "Einfache Aufgaben"
ms.assetid: b6dcfc7a-9fa9-4144-96a6-2845ea272017
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Einfache Aufgaben
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dieses Dokument beschreibt die Rolle einfacher Aufgaben in der Concurrency Runtime.  Als *einfache Aufgabe* werden Aufgaben bezeichnet, die Sie direkt über ein `concurrency::Scheduler`\-Objekt oder ein `concurrency::ScheduleGroup`\-Objekt planen.  Eine einfache Aufgabe ähnelt der Funktion, die Sie für die [CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453)\-Funktion der Windows\-API bereitstellen.  Aus diesem Grund sind einfache Aufgaben nützlich, wenn Sie vorhandenen Code anpassen, um die Planungsfunktionalität der Concurrency Runtime zu verwenden.  Die Concurrency Runtime verwendet einfache Aufgaben, um asynchrone Agents zu planen und Meldungen zwischen asynchronen Meldungsblöcken zu senden.  
  
> [!TIP]
>  Die Concurrency Runtime stellt einen Standardplaner bereit. Es ist daher nicht erforderlich, einen Planer in der Anwendung zu erstellen.  Der Taskplaner ermöglicht eine genauere Steuerung der Leistung von Anwendungen. Aus diesem Grund wird empfohlen, mit der [Parallel Patterns Library \(PPL\)](../../parallel/concrt/parallel-patterns-library-ppl.md) oder der [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md) zu beginnen, wenn Sie noch nicht mit der Concurrency Runtime vertraut sind.  
  
 Für einfache Aufgaben ist weniger Aufwand erforderlich als für asynchrone Agents und Aufgabengruppen.  Sie werden beispielsweise nicht informiert, wenn eine einfache Aufgabe beendet ist.  Außerdem werden bei der Ausführung einfacher Aufgaben ausgelöste Ausnahmen von der Runtime nicht erfasst bzw. behandelt.  Weitere Informationen zur Ausnahmebehandlung und zu einfachen Aufgaben finden Sie unter [Ausnahmebehandlung](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).  
  
 Für die meisten Aufgaben empfiehlt sich die Verwendung robusterer Funktionen \(z. B. Aufgabengruppen und parallele Algorithmen\), da sich komplexe Aufgaben hiermit besser in einfachere Aufgaben unterteilen lassen.  Weitere Informationen zu Aufgabengruppen finden Sie unter [Aufgabenparallelität](../../parallel/concrt/task-parallelism-concurrency-runtime.md).  Weitere Informationen zu parallelen Algorithmen finden Sie unter [Parallele Algorithmen](../../parallel/concrt/parallel-algorithms.md).  
  
 Um eine einfache Aufgabe zu erstellen, rufen Sie [concurrency::ScheduleGroup::ScheduleTask](../Topic/ScheduleGroup::ScheduleTask%20Method.md), [concurrency::CurrentScheduler::ScheduleTask](../Topic/CurrentScheduler::ScheduleTask%20Method.md) oder [concurrency::Scheduler::ScheduleTask](../Topic/Scheduler::ScheduleTask%20Method.md)\-Methode auf.  Um das Ende einer einfachen Aufgabe abzuwarten, warten Sie, bis der übergeordnete Planer beendet wird, beenden oder einen Synchronisierungsmechanismus wie ein [concurrency::event](../../parallel/concrt/reference/event-class.md)\-Objekt zu verwenden.  
  
## Beispiel  
 Ein Beispiel zur Anpassung von vorhandenem Code zur Verwendung einer einfachen Aufgabe finden Sie unter [Exemplarische Vorgehensweise: Anpassen von vorhandenem Code für die Verwendung einfacher Aufgaben](../../parallel/concrt/walkthrough-adapting-existing-code-to-use-lightweight-tasks.md).  
  
## Siehe auch  
 [Taskplaner](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [Exemplarische Vorgehensweise: Anpassen von vorhandenem Code für die Verwendung einfacher Aufgaben](../../parallel/concrt/walkthrough-adapting-existing-code-to-use-lightweight-tasks.md)