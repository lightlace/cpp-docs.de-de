---
title: "Planerrichtlinien"
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
  - "Planerrichtlinien"
ms.assetid: 58fb68bd-4a57-40a8-807b-6edb6f083cd9
caps.latest.revision: 12
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# Planerrichtlinien
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In diesem Dokument wird die Rolle von Planerrichtlinien in der Concurrency Runtime beschrieben.  Mithilfe einer *Planerrichtlinie* können Sie die Strategie festlegen, die der Planer zum Verwalten von Aufgaben verwendet.  Betrachten Sie beispielsweise eine Anwendung, die mehrere Aufgaben, bei `THREAD_PRIORITY_NORMAL` auszuführen und andere Aufgaben erfordert, bei `THREAD_PRIORITY_HIGHEST` auszuführen.  Sie können zwei Planerinstanzen erstellen: ein, das der `ContextPriority` \- Richtlinie angibt, um ein `THREAD_PRIORITY_NORMAL` handeln und ein anderes, das dieselbe Richtlinie angibt, als `THREAD_PRIORITY_HIGHEST`.  
  
 Indem Sie Planerrichtlinien verwenden, können Sie die verfügbaren Verarbeitungsressourcen zu teilen und jedem Planer einen festen Ressourcensatz.  Nehmen Sie als Beispiel einen parallelen Algorithmus mit einer Skalierung von bis zu vier Prozessoren.  In diesem Fall können Sie eine Planerrichtlinie erstellen, die festlegt, dass zu keinem Zeitpunkt mehr als vier Prozessoren gleichzeitig für die Aufgaben verwendet werden.  
  
> [!TIP]
>  Die Concurrency Runtime stellt einen Standardplaner.  Deshalb müssen Sie in Ihrer Anwendung nicht erstellen.  Der Taskplaner ermöglicht eine genauere Steuerung der Leistung von Anwendungen. Aus diesem Grund wird empfohlen, mit der [Parallel Patterns Library \(PPL\)](../../parallel/concrt/parallel-patterns-library-ppl.md) oder der [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md) zu beginnen, wenn Sie noch nicht mit der Concurrency Runtime vertraut sind.  
  
 Wenn Sie [concurrency::CurrentScheduler::Create](../Topic/CurrentScheduler::Create%20Method.md), [concurrency::Scheduler::Create](../Topic/Scheduler::Create%20Method.md) oder [concurrency::Scheduler::SetDefaultSchedulerPolicy](../Topic/Scheduler::SetDefaultSchedulerPolicy%20Method.md)\-Methode verwenden, um eine Planerinstanz zu erstellen, erstellen Sie ein [concurrency::SchedulerPolicy](../../parallel/concrt/reference/schedulerpolicy-class.md)\-Objekt bereit, das eine Auflistung von Schlüssel\-\/Wertpaaren, die das Verhalten des Planers bestimmen.  Der `SchedulerPolicy`\-Konstruktor akzeptiert eine variable Anzahl von Argumenten.  Das erste Argument ist die Anzahl der Richtlinienelemente, die Sie angeben.  Die weiteren Argumente sind Schlüssel\-Wert\-Paare für jedes Richtlinienelement.  Im folgenden Beispiel wird ein `SchedulerPolicy`\-Objekt erstellt, das drei Richtlinienelemente angibt.  Die Laufzeitverwendungsstandardwerte ohne Wertangabe, die nicht angegeben werden.  
  
 [!CODE [concrt-scheduler-policy#2](../CodeSnippet/VS_Snippets_ConcRT/concrt-scheduler-policy#2)]  
  
 Die [concurrency::PolicyElementKey](../Topic/PolicyElementKey%20Enumeration.md)\-Enumeration werden die Richtlinienschlüssel definiert, die dem Taskplaner zugeordnet sind.  Die folgende Tabelle enthält eine Beschreibung der einzelnen Richtlinienschlüssel sowie die zugehörigen Standardwerte.  
  
|Richtlinienschlüssel|**Beschreibung**|Standardwert|  
|--------------------------|----------------------|------------------|  
|`SchedulerKind`|Ein [concurrency::SchedulerType](../Topic/SchedulerType%20Enumeration.md)\-Wert, der den Typ von Threads angibt, um zu verwenden, um Aufgaben zu planen.|`ThreadScheduler` \(Verwenden von normalen Threads\).  Dies ist der einzige gültige Wert für diesen Schlüssel.|  
|`MaxConcurrency`|Ein `unsigned int`\-Wert, der die maximale Anzahl an Parallelitätsressourcen angibt, die der Planer verwendet.|[concurrency::MaxExecutionResources](../Topic/MaxExecutionResources%20Constant.md)|  
|`MinConcurrency`|Ein `unsigned int`\-Wert, der die Mindestanzahl an Parallelitätsressourcen angibt, die der Planer verwendet.|`1`|  
|`TargetOversubscriptionFactor`|Ein `unsigned int`\-Wert, der angibt, wie viele Threads jeder Verarbeitungsressource zuzuordnen sind.|`1`|  
|`LocalContextCacheSize`|Ein `unsigned int`\-Wert, der die maximale Anzahl an Kontexten angibt, die in der lokalen Warteschlange jedes virtuellen Prozessors zwischengespeichert werden können.|`8`|  
|`ContextStackSize`|Ein `unsigned int`\-Wert, der die Größe des für jeden Kontext zu reservierenden Stapels in KB angibt.|`0` \= Standardstapelgröße verwenden|  
|`ContextPriority`|Ein `int`\-Wert, der die Threadpriorität der einzelnen Kontexte angibt.  Dies kann jeder Wert sein, der sich an [SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277) oder `INHERIT_THREAD_PRIORITY` übergeben lässt.|`THREAD_PRIORITY_NORMAL`|  
|`SchedulingProtocol`|Ein [concurrency::SchedulingProtocolType](../Topic/SchedulingProtocolType%20Enumeration.md)\-Wert, der dem Planungsalgorithmus angibt, um zu verwenden.|`EnhanceScheduleGroupLocality`|  
|`DynamicProgressFeedback`|Ein [concurrency::DynamicProgressFeedbackType](../Topic/DynamicProgressFeedbackType%20Enumeration.md)\-Wert, der angibt, ob Ressourcen anhand von statistikbasierten Statusinformationen neu verteilt.<br /><br /> **Notiz** Legen Sie diese Richtlinie nicht auf fest `ProgressFeedbackDisabled` da sie für die Laufzeit reserviert wird.|`ProgressFeedbackEnabled`|  
  
 Jeder Planer verwendet eine eigene Richtlinie beim Planen von Aufgaben.  Die Richtlinien, die einem Planer zugeordnet sind, nicht auf das Verhalten anderer Planer.  Nach dem Erstellen des `Scheduler`\-Objekts können Sie die Planerrichtlinie außerdem nicht mehr ändern.  
  
> [!IMPORTANT]
>  Steuern Sie die Attribute für Threads, die von der Laufzeit erstellt werden, nur mit Planerrichtlinien.  Ändern Sie keinesfalls die Affinität oder Priorität von Threads, die von der Laufzeit erstellt werden, da der möglicherweise nicht definiertes Verhalten verursachen.  
  
 Wenn Sie nicht explizit einen Standardplaner erstellen, wird dieser von der Laufzeit für Sie erstellt.  Wenn Sie den Standardplaner in der Anwendung verwenden, jedoch eine Richtlinie dafür angeben möchten, dass der Planer verwendet, rufen Sie die [concurrency::Scheduler::SetDefaultSchedulerPolicy](../Topic/Scheduler::SetDefaultSchedulerPolicy%20Method.md)\-Methode auf, bevor Sie eine parallele Verarbeitung planen.  Wenn Sie die `Scheduler::SetDefaultSchedulerPolicy`\-Methode nicht aufrufen, verwendet die Runtime die in der Tabelle aufgeführten Standardrichtlinienwerte.  
  
 Verwenden Sie die Methoden [concurrency::CurrentScheduler::GetPolicy](../Topic/CurrentScheduler::GetPolicy%20Method.md) und [concurrency::Scheduler::GetPolicy](../Topic/Scheduler::GetPolicy%20Method.md), um eine Kopie der Planerrichtlinie abrufen.  Die von diesen Methoden zurückgegebenen Richtlinienwerte können von den Richtlinienwerten abweichen, die Sie beim Erstellen des Planers angeben.  
  
## Beispiel  
 Um die Beispiele zu überprüfen die bestimmte Planerrichtlinien verwenden Steuerung des Planerverhaltens verwendet werden, finden Sie unter [Gewusst wie: Angeben von bestimmten Planerrichtlinien](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md) und [Gewusst wie: Erstellen von Agents, die bestimmte Planerrichtlinien verwenden](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md).  
  
## Siehe auch  
 [Taskplaner](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [Gewusst wie: Angeben von bestimmten Planerrichtlinien](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md)   
 [Gewusst wie: Erstellen von Agents, die bestimmte Planerrichtlinien verwenden](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md)