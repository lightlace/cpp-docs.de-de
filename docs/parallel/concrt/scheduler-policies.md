---
title: Mithilfe von Planerrichtlinien | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- scheduler policies
ms.assetid: 58fb68bd-4a57-40a8-807b-6edb6f083cd9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7d9c855260df34290d01f1eeeee89e8bfe8988de
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="scheduler-policies"></a>Planerrichtlinien
Dieses Dokument beschreibt die Rolle von Planerrichtlinien in der Concurrency Runtime. Ein *Planerrichtlinie* steuert die Strategie, die der Planer zum Verwalten von Aufgaben verwendet. Betrachten Sie beispielsweise eine Anwendung, müssen einige Aufgaben an auszuführende `THREAD_PRIORITY_NORMAL` und andere Aufgaben an auszuführende `THREAD_PRIORITY_HIGHEST`.  Sie können zwei Planerinstanzen erstellen: einen, der angibt, die `ContextPriority` -Richtlinie mit `THREAD_PRIORITY_NORMAL` und ein anderes, der angibt, die gleiche Richtlinie, um `THREAD_PRIORITY_HIGHEST`.  
  
 Mithilfe von Planerrichtlinien können Sie die verfügbaren Verarbeitungsressourcen zu teilen und jedes Zeitplanungsmodul einen festen Satz von Ressourcen zuweisen. Betrachten Sie beispielsweise einen parallelen Algorithmus, der nicht mehr als vier Prozessoren skaliert werden kann. Sie können eine Planerrichtlinie erstellen, die beschränkt die Aufgaben aus, um nicht mehr als vier Prozessoren gleichzeitig verwendet werden können.  
  
> [!TIP]
>  Die Concurrency Runtime stellt einen Standardplaner bereit. Aus diesem Grund müssen Sie in Ihrer Anwendung zu erstellen. Da der Taskplaner Sie beim Optimieren der Leistung Ihrer Anwendungen unterstützt, empfiehlt es sich, dass die zu Beginn der [Parallel Patterns Library (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) oder [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md) Domänenmodus noch nicht mit der Concurrency Runtime.  
  
 Bei Verwendung der [CurrentScheduler](reference/currentscheduler-class.md#create), [Scheduler](reference/scheduler-class.md#create), oder [SetDefaultSchedulerPolicy](reference/scheduler-class.md#setdefaultschedulerpolicy) Methode, um eine Planerinstanz zu erstellen, geben Sie einen [Concurrency:: SchedulerPolicy](../../parallel/concrt/reference/schedulerpolicy-class.md) Objekt, das eine Auflistung von Schlüssel-Wert-Paare enthält, die das Verhalten des Zeitplanungsmoduls angeben. Die `SchedulerPolicy` Konstruktor eine Variable Anzahl von Argumenten akzeptiert. Das erste Argument ist die Anzahl der Gruppenrichtlinien-Elemente, die Sie angeben. Die übrigen Argumente sind Schlüssel-Wert-Paare für jedes Richtlinienelement. Das folgende Beispiel erstellt eine `SchedulerPolicy` Objekt, das drei Richtlinienelemente angibt. Die Common Language Runtime verwendet die Standardwerte für die Richtlinienschlüssel, die nicht angegeben werden.  

  
 [!code-cpp[concrt-scheduler-policy#2](../../parallel/concrt/codesnippet/cpp/scheduler-policies_1.cpp)]  
  

 Die [Concurrency:: PolicyElementKey](reference/concurrency-namespace-enums.md#policyelementkey) -Enumeration definiert die Richtlinienschlüssel, die mit dem Taskplaner verknüpft sind. Die folgende Tabelle beschreibt die Richtlinienschlüssel und der Standardwert, den die Common Language Runtime für jede von ihnen verwendet.  
  
|Richtlinienschlüssel|Beschreibung|Standardwert|  
|----------------|-----------------|-------------------|  
|`SchedulerKind`|Ein [concurrency::SchedulerType](reference/concurrency-namespace-enums.md#schedulertype) Wert, der den Typ der Threads Planen von Aufgaben zu verwendende angibt.|`ThreadScheduler` (Verwenden von normalen Threads). Dies ist der einzige gültige Wert für diesen Schlüssel.|  
|`MaxConcurrency`|Ein `unsigned int` Wert, der die maximale Anzahl von Parallelitätsressourcen angibt, die der Planer verwendet.|[Concurrency::MaxExecutionResources](reference/concurrency-namespace-constants1.md#maxexecutionresources)|  
|`MinConcurrency`|Ein `unsigned int` Wert, der die minimale Anzahl von Parallelitätsressourcen angibt, die der Planer verwendet.|`1`|  
|`TargetOversubscriptionFactor`|Ein `unsigned int` Wert, der angibt, wie viele threads jeder Verarbeitungsressource zuzuordnen.|`1`|  
|`LocalContextCacheSize`|Ein `unsigned int` Wert, der die maximale Anzahl von Kontexten, die zwischengespeichert werden, können in der lokalen Warteschlange jedes virtuellen Prozessors angibt.|`8`|  
|`ContextStackSize`|Ein `unsigned int` Wert, der angibt, die Größe des Stapels in KB, für jeden Kontext reserviert werden soll.|`0` (verwenden Sie die Standardgröße des Stapel)|  
|`ContextPriority`|Ein `int` Wert, der die Threadpriorität unterschiedlichen Kontexten angibt. Dies kann sich auf alle Werte, die Sie übergeben können [SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277) oder `INHERIT_THREAD_PRIORITY`.|`THREAD_PRIORITY_NORMAL`|  

|`SchedulingProtocol`| Ein [Concurrency:: SchedulingProtocolType](reference/concurrency-namespace-enums.md#schedulingprotocoltype) Wert, der angibt, die zu verwendenden Planungsalgorithmus. |`EnhanceScheduleGroupLocality`|  
|`DynamicProgressFeedback`| Ein [DynamicProgressFeedbackType](reference/concurrency-namespace-enums.md#dynamicprogressfeedbacktype) Wert, der angibt, ob Ressourcen entsprechend Statistiken basierende Statusinformationen zu erhalten soll.<br /><br /> **Hinweis** legen Sie diese Richtlinie nicht auf `ProgressFeedbackDisabled` , da er für die Verwendung von der Runtime reserviert wurde. |`ProgressFeedbackEnabled`|  

  
 Jedes Zeitplanungsmodul verwendet eine eigene Richtlinie aus, wenn es Aufgaben plant. Die Richtlinien, die einem Zeitplanungsmodul zugeordnet sind wirken sich nicht auf das Verhalten anderer Planer aus. Sie können nicht zusätzlich die Planerrichtlinie ändern, nach der Erstellung der `Scheduler` Objekt.  
  
> [!IMPORTANT]
>  Verwenden Sie nur mithilfe von Planerrichtlinien, um die Attribute für Threads steuern, die die Common Language Runtime erstellt. Ändern Sie die Threadaffinität "oder" Priorität der Threads, die von der Laufzeit erstellt werden, da, die nicht definiertem Verhalten führen möglicherweise nicht.  
  
 Die Common Language Runtime erstellt einen Standardplaner für Sie aus, wenn nicht explizit erstellt werden. Wenn Sie Standardplaner in Ihrer Anwendung verwenden möchten, aber Sie geben Sie eine Richtlinie für diesen Planer zu verwenden, rufen Sie möchten die [SetDefaultSchedulerPolicy](reference/scheduler-class.md#setdefaultschedulerpolicy) -Methode auf, bevor Sie parallelen Arbeitsvorgänge planen. Wenn Sie nicht Aufrufen der `Scheduler::SetDefaultSchedulerPolicy` -Methode, die Common Language Runtime verwendet die Standardrichtlinie aus der Tabelle Werte.  
  
 Verwenden der [Concurrency::CurrentScheduler::GetPolicy](reference/currentscheduler-class.md#getpolicy) und [Concurrency::Scheduler::GetPolicy](reference/scheduler-class.md#getpolicy) Methoden, um eine Kopie der Planerrichtlinie abzurufen. Sie von diesen Methoden erhalten können von der Werte für Aktivierungsrichtlinien unterscheiden sich die Richtlinienwerte, die Sie bei der Erstellung des Planers angeben.  
  
## <a name="example"></a>Beispiel  
 Um Beispiele zu untersuchen, die bestimmte Planerrichtlinien verwenden, um das Verhalten des Zeitplanungsmoduls steuern, finden Sie unter [Vorgehensweise: Angeben von bestimmten Planerrichtlinien](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md) und [Vorgehensweise: Erstellen von Agents, verwenden Sie bestimmte Planerrichtlinien](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Taskplaner](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [Vorgehensweise: Angeben von bestimmten Planerrichtlinien](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md)   
 [Vorgehensweise: Erstellen von Agents, die bestimmte Planerrichtlinien verwenden](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md)

