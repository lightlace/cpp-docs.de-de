---
title: Planungsgruppen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- schedule groups
ms.assetid: 03523572-5891-4d17-89ce-fa795605f28b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a61566878adc539af21e1645844eff27c5a8aec0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="schedule-groups"></a>Planungsgruppen
Dieses Dokument beschreibt die Rolle von Planungsgruppen in der Concurrency Runtime. Ein *Planungsgruppe* Verfügung oder werden verwandte Aufgaben gruppiert. Jedes Zeitplanungsmodul verfügt über eine oder mehrere Planungsgruppen. Verwenden Sie Planungsgruppen, wenn Sie ein hohes Maß an Lokalität zwischen den Aufgaben benötigen. Dies ist zum Beispiel dann der Fall, wenn es für eine Gruppe verwandter Aufgaben vorteilhaft ist, auf dem gleichen Prozessorknoten ausgeführt zu werden. Im Gegensatz dazu verwenden Sie Planerinstanzen, wenn Ihre Anwendung bestimmte Qualitätsprobleme Anforderungen, z. B. besitzt, wenn die Menge von Verarbeitungsressourcen zu beschränken, die eine Reihe von Tasks zugeordnet werden, sollen. Weitere Informationen zu Planerinstanzen, finden Sie unter [Planerinstanzen](../../parallel/concrt/scheduler-instances.md).  
  
> [!TIP]
>  Die Concurrency Runtime stellt einen Standardplaner bereit. Sie müssen daher keinen in Ihrer Anwendung erstellen. Da der Taskplaner Sie beim Optimieren der Leistung Ihrer Anwendungen unterstützt, empfiehlt es sich, dass die zu Beginn der [Parallel Patterns Library (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) oder [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md) Domänenmodus noch nicht mit der Concurrency Runtime.  
  
 Jede `Scheduler` Objekt verfügt über eine Standard-Planungsgruppe für jeden Knoten planen. Ein *Planung Knoten* ordnet die zugrunde liegende Systemtopologie. Erstellt die Laufzeit eine Planung Knoten "" bei jedem Prozessorpaket oder Non-Uniform Memory Architecture (NUMA), welcher Wert größer ist. Wenn Sie nicht explizit eine Aufgabe eine Planungsgruppe zuordnen, wählt das Zeitplanungsmodul der Gruppe aus, um die Aufgabe hinzuzufügen.  
  
 Die `SchedulingProtocol` -Planerrichtlinie wird die Reihenfolge, in der der Planer die Aufgaben in jeder Gruppe Zeitplan ausgeführt wird. Wenn `SchedulingProtocol` festgelegt ist, um `EnhanceScheduleGroupLocality` (Dies ist die Standardeinstellung), wählt der Taskplaner die nächste Aufgabe von der Planungsgruppe, die Funktion für aktiv ist, wenn die aktuelle Aufgabe beendet oder Kooperativ erzeugt. Der Taskplaner sucht die aktuellen Gruppe der Zeitplan für die Arbeit aus, bevor sie auf die nächste verfügbare Gruppen verschoben wird. Im Gegensatz dazu, dass bei `SchedulingProtocol` festgelegt ist, um `EnhanceForwardProgress`, wechselt der Planer zur nächsten Planungsgruppe, nachdem alle Aufgaben beendet oder ergibt. Ein Beispiel, in dem diese Richtlinien verglichen, finden Sie unter [Vorgehensweise: Verwenden Sie Planungsgruppen beeinflussen die Reihenfolge der Ausführung](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md).  
  

 Die Common Language Runtime verwendet die [Concurrency:: ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) -Klasse zur Darstellung von Planungsgruppen. Zum Erstellen einer `ScheduleGroup` -Objekt, rufen Sie die [ScheduleGroup](reference/currentscheduler-class.md#createschedulegroup) oder [Concurrency::Scheduler::CreateScheduleGroup](reference/scheduler-class.md#createschedulegroup) Methode. Die Common Language Runtime verwendet einen verweiszählung Mechanismus zur Steuerung der Lebensdauer des `ScheduleGroup` Objekte, wie mit `Scheduler` Objekte. Beim Erstellen einer `ScheduleGroup` -Objekt, die Common Language Runtime legt den Verweis auf einen Leistungsindikator. Die [Concurrency::ScheduleGroup::Reference](reference/schedulegroup-class.md#reference) Methode inkrementiert den Verweiszähler um eins. Die [Concurrency::ScheduleGroup::Release](reference/schedulegroup-class.md#release) Methode dekrementiert den Verweiszähler um eins.  
  
 Viele Typen in der Concurrency Runtime ermöglichen Sie ein Objekt zusammen mit einer Planungsgruppe zuordnen. Z. B. die [Concurrency:: Agent](../../parallel/concrt/reference/agent-class.md) Klasse und Message Block-Klassen wie [Concurrency:: unbounded_buffer](reference/unbounded-buffer-class.md), [Concurrency:: Join](../../parallel/concrt/reference/join-class.md), und Concurrency::[ Timer](reference/timer-class.md), geben Sie die überladene Versionen des Konstruktors, einer `ScheduleGroup` Objekt. Die Common Language Runtime verwendet die `Scheduler` -Objekt, das mit dieser verknüpft ist `ScheduleGroup` Objekt, um die Aufgabe zu planen.  
  
 Sie können auch die [Concurrency::ScheduleGroup::ScheduleTask](reference/schedulegroup-class.md#scheduletask) Methode, um eine einfache Aufgabe zu planen. Weitere Informationen zu einfachen Aufgaben finden Sie unter [einfache Aufgaben](../../parallel/concrt/lightweight-tasks.md).  

  
## <a name="example"></a>Beispiel  
 Ein Beispiel, verwendet zur Steuerung der Reihenfolge der Taskausführung Planungsgruppen, finden Sie unter [Vorgehensweise: Verwenden Sie Planungsgruppen beeinflussen die Reihenfolge der Ausführung](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Taskplaner](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [Planerinstanzen](../../parallel/concrt/scheduler-instances.md)   
 [Vorgehensweise: Beeinflussen der Ausführungsreihenfolge mithilfe von Zeitplangruppen](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md)

