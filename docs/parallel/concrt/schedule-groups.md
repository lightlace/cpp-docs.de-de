---
title: Planungsgruppen
ms.date: 11/04/2016
helpviewer_keywords:
- schedule groups
ms.assetid: 03523572-5891-4d17-89ce-fa795605f28b
ms.openlocfilehash: 1765c10f4cf8fe499aed1a140d2bba1ecaaf2300
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142308"
---
# <a name="schedule-groups"></a>Planungsgruppen

In diesem Dokument wird die Rolle von Zeit Plan Gruppen im Concurrency Runtime beschrieben. Eine Zeit *Plan Gruppe* verknüpft zusammen gehörige Aufgaben oder gruppiert diese. Jeder Planer verfügt über eine oder mehrere Zeit Plan Gruppen. Verwenden Sie Planungsgruppen, wenn Sie ein hohes Maß an Lokalität zwischen den Aufgaben benötigen. Dies ist zum Beispiel dann der Fall, wenn es für eine Gruppe verwandter Aufgaben vorteilhaft ist, auf dem gleichen Prozessorknoten ausgeführt zu werden. Verwenden Sie im Gegensatz dazu Scheduler-Instanzen, wenn Ihre Anwendung über bestimmte Qualitätsanforderungen verfügt, z. b. Wenn Sie die Menge der Verarbeitungs Ressourcen begrenzen möchten, die einem Satz von Tasks zugeordnet sind. Weitere Informationen zu planerinstanzen finden Sie unter [Scheduler-Instanzen](../../parallel/concrt/scheduler-instances.md).

> [!TIP]
> Die Concurrency Runtime stellt einen Standardplaner bereit. Sie müssen daher keinen in Ihrer Anwendung erstellen. Da der Taskplaner Sie bei der Feinabstimmung der Leistung Ihrer Anwendungen unterstützt, empfehlen wir Ihnen, mit der [Parallel Patterns Library (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) oder der [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md) zu beginnen, wenn Sie mit der Concurrency Runtime noch nicht vertraut sind.

Jedes `Scheduler` Objekt verfügt über eine standardmäßige Zeit Plan Gruppe für jeden Zeit Planungs Knoten. Ein *Planungs Knoten* ist der zugrunde liegenden System Topologie zugeordnet. Die Laufzeit erstellt einen Planungs Knoten für jedes Prozessor Paket oder einen nicht einheitlichen Speicherarchitektur Knoten (NUMA), je nachdem, welcher Wert größer ist. Wenn Sie eine Aufgabe nicht explizit einer Zeit Plan Gruppe zuordnen, wählt der Planer die Gruppe aus, der die Aufgabe hinzugefügt werden soll.

Die `SchedulingProtocol` Scheduler-Richtlinie wirkt sich auf die Reihenfolge aus, in der der Scheduler die Tasks in jeder Zeit Plan Gruppe ausführt. Wenn `SchedulingProtocol` auf `EnhanceScheduleGroupLocality` festgelegt ist (Dies ist die Standardeinstellung), wählt der Taskplaner den nächsten Task in der Zeit Plan Gruppe aus, an der er arbeitet, wenn die aktuelle Aufgabe abgeschlossen ist oder kooperativ ergibt. Der Taskplaner durchsucht die aktuelle Zeit Plan Gruppe nach Arbeit, bevor Sie zur nächsten verfügbaren Gruppe wechselt. Wenn `SchedulingProtocol` auf `EnhanceForwardProgress`festgelegt ist, wechselt der Planer umgekehrt zur nächsten Zeit Plan Gruppe, nachdem die einzelnen Aufgaben abgeschlossen oder ausgegeben wurden. Ein Beispiel, das diese Richtlinien vergleicht, finden Sie unter Gewusst [wie: Verwenden von Zeit Plan Gruppen zum beeinflussen der Ausführungsreihenfolge](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md).

Die Laufzeit verwendet die Klasse " [parallelcurrency:: ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) " zur Darstellung von Zeit Plan Gruppen. Um ein `ScheduleGroup`-Objekt zu erstellen, rufen Sie die [Concurrency:: CurrentScheduler:: up-ScheduleGroup](reference/currentscheduler-class.md#createschedulegroup) -Methode oder die [Concurrency:: Scheduler:: aufgabenschedulegroup](reference/scheduler-class.md#createschedulegroup) -Methode auf. Die Laufzeit verwendet einen Mechanismus zur Verweis Zählung, um die Lebensdauer von `ScheduleGroup` Objekten zu steuern, ebenso wie bei `Scheduler` Objekten. Wenn Sie ein `ScheduleGroup` Objekt erstellen, legt die Laufzeit den Verweis Zählers auf einen fest. Die Methode " [parallelcurrency:: ScheduleGroup:: Reference](reference/schedulegroup-class.md#reference) " erhöht den Verweis Zählers um 1. Die Methode " [parallelcurrency:: ScheduleGroup:: Release](reference/schedulegroup-class.md#release) " Dekremente den Verweis Zählers um 1.

Viele Typen in der Concurrency Runtime ermöglichen Ihnen, ein Objekt einer Zeit Plan Gruppe zuzuordnen. Die Klassen " [parallelcurrency:: Agent](../../parallel/concrt/reference/agent-class.md) " und "Message Block", z. b. " [parallelcurrency:: Unbounded_buffer](reference/unbounded-buffer-class.md)", " [parallelcurrency:: Join](../../parallel/concrt/reference/join-class.md)" und "parallelcurrency::[Timer](reference/timer-class.md)", stellen überladene Versionen des Konstruktors bereit, die ein `ScheduleGroup` Objekt akzeptieren. Die Laufzeit verwendet das `Scheduler` Objekt, das diesem `ScheduleGroup` Objekt zugeordnet ist, um die Aufgabe zu planen.

Sie können auch die [parallelcurrency:: ScheduleGroup:: ScheduleTask](reference/schedulegroup-class.md#scheduletask) -Methode verwenden, um eine leichte Aufgabe zu planen. Weitere Informationen zu Lightweight-Aufgaben finden Sie unter [Lightweight-Aufgaben](../../parallel/concrt/lightweight-tasks.md).

## <a name="example"></a>Beispiel

Ein Beispiel für die Verwendung von Zeit Plan Gruppen zum Steuern der Reihenfolge der Task Ausführung finden Sie unter Gewusst [wie: Verwenden von Zeit Plan Gruppen zum beeinflussen der Ausführungsreihenfolge](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md).

## <a name="see-also"></a>Weitere Informationen

[Aufgabenplanung](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[Planerinstanzen](../../parallel/concrt/scheduler-instances.md)<br/>
[Vorgehensweise: Beeinflussen der Ausführungsreihenfolge mithilfe von Zeitplangruppen](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md)
