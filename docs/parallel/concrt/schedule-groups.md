---
title: "Planungsgruppen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Planungsgruppen"
ms.assetid: 03523572-5891-4d17-89ce-fa795605f28b
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Planungsgruppen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dieses Dokument beschreibt die Rolle von Planungsgruppen in der Concurrency Runtime. Ein *Planungsgruppe* Planungsgruppe oder fasst verwandte Aufgaben zusammen. Jeder Planer weist mindestens eine Planungsgruppe. Verwenden Sie Planungsgruppen, wenn Sie ein hohes Maß an Lokalität zwischen den Aufgaben benötigen. Dies ist zum Beispiel dann der Fall, wenn es für eine Gruppe verwandter Aufgaben vorteilhaft ist, auf dem gleichen Prozessorknoten ausgeführt zu werden. Verwenden Sie hingegen Planerinstanzen, wenn Ihre Anwendung spezifischen Anforderungen, z. B. besitzt, wenn die Verarbeitungsressourcen begrenzen, die eine Reihe von Aufgaben zugewiesen werden, sollen. Weitere Informationen zu Planerinstanzen finden Sie unter [Planerinstanzen](../../parallel/concrt/scheduler-instances.md).  
  
> [!TIP]
>  Die Concurrency Runtime stellt einen Standardplaner bereit. Sie müssen daher keinen in Ihrer Anwendung erstellen. Da der Taskplaner Sie die Leistung einer Anwendung optimieren können, wird empfohlen, dass Sie mit beginnen die [Parallel Patterns Library (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) oder [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md) wenn Sie mit der Concurrency Runtime sind.  
  
 Jedes `Scheduler` Objekt verfügt über eine Standard-Planungsgruppe für jeden Knoten planen. Ein *Knoten planen* ordnet das zugrunde liegende Systemtopologie. Eine Planung für jedes Prozessorpaket oder Non-Uniform Memory Architecture (NUMA) Knoten von der Laufzeit erstellt, welcher Wert größer ist. Wenn Sie nicht explizit einen Task einer Planungsgruppe zuordnen, wählt das Zeitplanungsmodul welche Gruppe die Aufgabe hinzugefügt.  
  
 Die `SchedulingProtocol` -Planerrichtlinie wird die Reihenfolge, in der der Planer die Aufgaben in den einzelnen Planungsgruppen ausführt. Wenn `SchedulingProtocol` Wert `EnhanceScheduleGroupLocality` (Dies ist die Standardeinstellung), wählt der Taskplaner die nächste Aufgabe aus der Planungsgruppe, auf die Verarbeitung erfolgt, wenn die aktuelle Aufgabe beendet oder Kooperativ zurückgehalten. Der Taskplaner sucht die aktuellen Planungsgruppe für die Arbeit, bevor sie in die nächste verfügbare Gruppe verschoben. Umgekehrt, wenn `SchedulingProtocol` Wert `EnhanceForwardProgress`, wechselt der Planer zur nächsten Planungsgruppe, nachdem alle Aufgaben beendet oder erzeugt. Ein Beispiel, in dem diese Richtlinien verglichen werden, finden Sie unter [Gewusst wie: Verwenden von Planungsgruppen Einfluss Reihenfolge der Ausführung](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md).  
  
 Die Common Language Runtime verwendet die [Concurrency:: ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) Klasse Planungsgruppen darstellen. Erstellen einer `ScheduleGroup` Objekt, rufen Sie die [:: CurrentScheduler:: CreateScheduleGroup](../Topic/CurrentScheduler::CreateScheduleGroup%20Method.md) oder [Concurrency::Scheduler::CreateScheduleGroup](../Topic/Scheduler::CreateScheduleGroup%20Method.md) Methode. Die Common Language Runtime verwendet einen Mechanismus zum Zählen von Verweisen zur Steuerung der Lebensdauer des `ScheduleGroup` Objekte, wie mit `Scheduler` Objekte. Beim Erstellen einer `ScheduleGroup` -Objekt, die Common Language Runtime legt den Verweis auf einen Leistungsindikator. Die [Concurrency::ScheduleGroup::Reference](../Topic/ScheduleGroup::Reference%20Method.md) Methode inkrementiert den Verweiszähler um eins. Die [Concurrency::ScheduleGroup::Release](../Topic/ScheduleGroup::Release%20Method.md) -Methode dekrementiert den Verweiszähler um eins.  
  
 Viele Typen in der Concurrency Runtime ermöglichen die Zuordnung eines Objekts einer Planungsgruppe. Z. B. die [Concurrency:: Agent](../../parallel/concrt/reference/agent-class.md) Klasse und Message Block-Klassen wie [Concurrency:: unbounded_buffer](../Topic/unbounded_buffer%20Class.md), [Concurrency:: Join](../../parallel/concrt/reference/join-class.md), und Parallelität::[Zeitgeber](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/d5d4c847-5ad6-4c7f-b35b-d0b6f446d8b4/locales/en-US), überladene Versionen des Konstruktors, bieten ein `ScheduleGroup` Objekt. Die Common Language Runtime verwendet die `Scheduler` -Objekt, das zugeordnet ist `ScheduleGroup` Objekt, um die Aufgabe zu planen.  
  
 Sie können auch die [Concurrency::ScheduleGroup::ScheduleTask](../Topic/ScheduleGroup::ScheduleTask%20Method.md) Methode, um eine einfache Aufgabe planen. Weitere Informationen zu einfachen Aufgaben finden Sie unter [einfache Aufgaben](../../parallel/concrt/lightweight-tasks.md).  
  
## <a name="example"></a>Beispiel  
 Ein Beispiel, verwendet Gruppen zum Steuern der Ausführung der Aufgabe planen, finden Sie unter [Gewusst wie: Verwenden von Planungsgruppen Einfluss Reihenfolge der Ausführung](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Taskplaner](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [Planerinstanzen](../../parallel/concrt/scheduler-instances.md)   
 [Gewusst wie: beeinflussen der Ausführungsreihenfolge mithilfe](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md)

