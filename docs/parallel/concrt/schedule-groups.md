---
title: Planungsgruppen
ms.date: 11/04/2016
helpviewer_keywords:
- schedule groups
ms.assetid: 03523572-5891-4d17-89ce-fa795605f28b
ms.openlocfilehash: febcc0a9c7af75801962ea6be687ce87cc5501d4
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57295972"
---
# <a name="schedule-groups"></a>Planungsgruppen

Dieses Dokument beschreibt die Rolle von Planungsgruppen, in der Concurrency Runtime. Ein *Planungsgruppe* Planungsgruppe oder gruppiert, Verwandte Aufgaben. Jedes Zeitplanungsmodul verfügt über eine oder mehrere Planungsgruppen. Verwenden Sie Planungsgruppen, wenn Sie ein hohes Maß an Lokalität zwischen den Aufgaben benötigen. Dies ist zum Beispiel dann der Fall, wenn es für eine Gruppe verwandter Aufgaben vorteilhaft ist, auf dem gleichen Prozessorknoten ausgeführt zu werden. Im Gegensatz dazu verwenden Sie Planerinstanzen, wenn Ihre Anwendung spezifischen qualitätsanforderungen, z. B. besitzt, wenn die Menge an Verarbeitungsressourcen zu beschränken, die eine Reihe von Tasks zugeordnet werden, sollen. Weitere Informationen zu Planerinstanzen, finden Sie unter [Planerinstanzen](../../parallel/concrt/scheduler-instances.md).

> [!TIP]
>  Die Concurrency Runtime stellt einen Standardplaner bereit. Sie müssen daher keinen in Ihrer Anwendung erstellen. Da der Taskplaner die Leistung Ihrer Anwendungen optimieren können, es wird empfohlen, zunächst die [Parallel Patterns Library (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) oder [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md) möchten noch nicht mit der Concurrency Runtime.

Jede `Scheduler` Objekt verfügt über eine Standard-Schedule-Gruppe für jeden Knoten planen. Ein *Knoten planen* ordnet die zugrunde liegende Systemtopologie. Die Common Language Runtime erstellt werden soll, eine Planung für jedes Prozessorpaket oder Non-Uniform Memory Architecture (NUMA) Knoten, welcher Wert größer ist. Wenn Sie nicht explizit eine Aufgabe eine Planungsgruppe zuordnen, wählt das Zeitplanungsmodul der Gruppe aus, um die Aufgabe hinzuzufügen.

Die `SchedulingProtocol` Planerrichtlinie wirkt sich auf die Reihenfolge, in dem der Scheduler die Aufgaben in jeder Gruppe Zeitplan ausgeführt wird. Wenn `SchedulingProtocol` nastaven NA hodnotu `EnhanceScheduleGroupLocality` (Dies ist die Standardeinstellung), wählt der Taskplaner die nächste Aufgabe aus der Planungsgruppe, an dem er arbeiten wird, wenn die aktuelle Aufgabe beendet oder Kooperativ zurückgehalten. Der Planer sucht die aktuellen Gruppe der Zeitplan für die Arbeit, bevor sie auf die nächste verfügbare Gruppe verschoben. Im Gegensatz dazu, wann `SchedulingProtocol` nastaven NA hodnotu `EnhanceForwardProgress`, wechselt der Planer zur nächsten Planungsgruppe, nachdem jede Aufgabe beendet oder erzeugt. Ein Beispiel, in dem diese Richtlinien verglichen, finden Sie unter [Vorgehensweise: Der Ausführungsreihenfolge mithilfe von Zeitplangruppen](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md).

Die Common Language Runtime verwendet die [Concurrency:: ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) Klasse Planungsgruppen darstellen. Zum Erstellen einer `ScheduleGroup` Objekt, rufen Sie die [:: CurrentScheduler:: CreateScheduleGroup](reference/currentscheduler-class.md#createschedulegroup) oder [Concurrency::Scheduler::CreateScheduleGroup](reference/scheduler-class.md#createschedulegroup) Methode. Die Runtime verwendet einen Mechanismus zum Zählen von verweisen, um die Steuerung der Lebensdauer des `ScheduleGroup` Objekte, wie mit `Scheduler` Objekte. Bei der Erstellung einer `ScheduleGroup` Objekt ist, wird die Laufzeit legt den Verweis auf einen Leistungsindikator. Die [Concurrency::ScheduleGroup::Reference](reference/schedulegroup-class.md#reference) Methode inkrementiert den Verweiszähler um eins. Die [Concurrency::ScheduleGroup::Release](reference/schedulegroup-class.md#release) -Methode dekrementiert den Verweiszähler um eins.

Viele Typen in der Concurrency Runtime können Sie die Zuordnung eines Objekts zusammen mit einer Zeitplan-Gruppe. Z. B. die [Concurrency:: Agent](../../parallel/concrt/reference/agent-class.md) -Klasse und Message-Block Klassen wie z. B. [Concurrency:: unbounded_buffer](reference/unbounded-buffer-class.md), [Concurrency:: Join](../../parallel/concrt/reference/join-class.md), und Concurrency::[ Timer](reference/timer-class.md), geben Sie die überladene Versionen des Konstruktors, einer `ScheduleGroup` Objekt. Die Common Language Runtime verwendet die `Scheduler` -Objekt, das mit dieser verknüpft ist `ScheduleGroup` Objekt, das die Aufgabe zu planen.

Sie können auch die [Concurrency::ScheduleGroup::ScheduleTask](reference/schedulegroup-class.md#scheduletask) Methode, um eine einfache Aufgabe zu planen. Weitere Informationen zu einfachen Aufgaben finden Sie unter [einfache Aufgaben](../../parallel/concrt/lightweight-tasks.md).

## <a name="example"></a>Beispiel

Ein Beispiel, verwendet zur Steuerung der Reihenfolge der aufgabenausführung Planungsgruppen, finden Sie unter [Vorgehensweise: Der Ausführungsreihenfolge mithilfe von Zeitplangruppen](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md).

## <a name="see-also"></a>Siehe auch

[Aufgabenplanung](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[Planerinstanzen](../../parallel/concrt/scheduler-instances.md)<br/>
[Vorgehensweise: Beeinflussen der Ausführungsreihenfolge mithilfe von Planungsgruppen](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md)
