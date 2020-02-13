---
title: Planerrichtlinien
ms.date: 11/04/2016
helpviewer_keywords:
- scheduler policies
ms.assetid: 58fb68bd-4a57-40a8-807b-6edb6f083cd9
ms.openlocfilehash: 0f90b461ecba702501c2f6919572dc828c80907f
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142282"
---
# <a name="scheduler-policies"></a>Planerrichtlinien

In diesem Dokument wird die Rolle der Scheduler-Richtlinien in der Concurrency Runtime beschrieben. Eine *Scheduler-Richtlinie* steuert die Strategie, die der Scheduler beim Verwalten von Aufgaben verwendet. Stellen Sie sich z. b. eine Anwendung vor, die zum Ausführen einiger Aufgaben bei `THREAD_PRIORITY_NORMAL` und andere Aufgaben benötigt, die bei `THREAD_PRIORITY_HIGHEST`ausgeführt werden müssen.  Sie können zwei Scheduler-Instanzen erstellen: einen, der die zu `THREAD_PRIORITY_NORMAL` `ContextPriority` Richtlinie angibt, und einen weiteren, der die gleiche Richtlinie angibt, die `THREAD_PRIORITY_HIGHEST`werden soll.

Mithilfe von Scheduler-Richtlinien können Sie die verfügbaren Verarbeitungs Ressourcen aufteilen und jedem Scheduler einen festgelegten Satz von Ressourcen zuweisen. Stellen Sie sich beispielsweise einen parallelen Algorithmus vor, der nicht über vier Prozessoren skaliert werden kann. Sie können eine Scheduler-Richtlinie erstellen, die die Aufgaben einschränkt, sodass nicht mehr als vier Prozessoren gleichzeitig verwendet werden.

> [!TIP]
> Der Concurrency Runtime stellt einen Standard Planer bereit. Daher müssen Sie keinen in Ihrer Anwendung erstellen. Da der Taskplaner Sie bei der Feinabstimmung der Leistung Ihrer Anwendungen unterstützt, empfehlen wir Ihnen, mit der [Parallel Patterns Library (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) oder der [Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md) zu beginnen, wenn Sie mit der Concurrency Runtime noch nicht vertraut sind.

Bei Verwendung der Parallelität [:: CurrentScheduler:: Create](reference/currentscheduler-class.md#create), [Concurrency:: Scheduler:: Create](reference/scheduler-class.md#create)oder [Concurrency:: Scheduler:: SetDefaultSchedulerPolicy](reference/scheduler-class.md#setdefaultschedulerpolicy) -Methode zum Erstellen einer planerinstanz geben Sie ein [Concurrency:: SchedulerPolicy](../../parallel/concrt/reference/schedulerpolicy-class.md) -Objekt an, das eine Auflistung von Schlüssel-Wert-Paaren enthält, die das Verhalten des Schedulers angeben. Der `SchedulerPolicy`-Konstruktor nimmt eine Variable Anzahl von Argumenten an. Das erste Argument ist die Anzahl der Richtlinien Elemente, die Sie angeben. Die übrigen Argumente sind Schlüssel-Wert-Paare für jedes Policy-Element. Im folgenden Beispiel wird ein `SchedulerPolicy`-Objekt erstellt, das drei Richtlinien Elemente angibt. Die Laufzeit verwendet Standardwerte für die nicht angegebenen Richtlinien Schlüssel.

[!code-cpp[concrt-scheduler-policy#2](../../parallel/concrt/codesnippet/cpp/scheduler-policies_1.cpp)]

Die Enumeration " [parallelcurrency::P olicyelementkey](reference/concurrency-namespace-enums.md#policyelementkey) " definiert die dem Taskplaner zugeordneten Richtlinien Schlüssel. In der folgenden Tabelle werden die Richtlinien Schlüssel und der Standardwert beschrieben, der von der Common Language Runtime für diese verwendet wird.

|Richtlinien Schlüssel|BESCHREIBUNG|Standardwert|
|----------------|-----------------|-------------------|
|`SchedulerKind`|Ein [parallelcurrency:: SchedulerType](reference/concurrency-namespace-enums.md#schedulertype) -Wert, der den Typ der Threads angibt, die zum Planen von Tasks verwendet werden sollen.|`ThreadScheduler` (normale Threads verwenden). Dies ist der einzige gültige Wert für diesen Schlüssel.|
|`MaxConcurrency`|Ein-`unsigned int` Wert, der die maximale Anzahl von Parallelitäts Ressourcen angibt, die vom Planer verwendet werden.|[Parallelität:: MaxExecutionResources](reference/concurrency-namespace-constants1.md#maxexecutionresources)|
|`MinConcurrency`|Ein `unsigned int` Wert, der die Mindestanzahl von Parallelitäts Ressourcen angibt, die vom Planer verwendet werden.|`1`|
|`TargetOversubscriptionFactor`|Ein `unsigned int` Wert, der angibt, wie viele Threads den einzelnen Verarbeitungs Ressourcen zuzuordnen sind.|`1`|
|`LocalContextCacheSize`|Ein `unsigned int` Wert, der die maximale Anzahl von Kontexten angibt, die in der lokalen Warteschlange jedes virtuellen Prozessors zwischengespeichert werden können.|`8`|
|`ContextStackSize`|Ein `unsigned int` Wert, der die Größe des Stapels in Kilobyte angibt, die für jeden Kontext reserviert werden soll.|`0` (Standard Stapelgröße verwenden)|
|`ContextPriority`|Ein `int`-Wert, der die Thread Priorität der einzelnen Kontexte angibt. Dies kann ein beliebiger Wert sein, den Sie an [SetThreadPriority](/windows/win32/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) oder `INHERIT_THREAD_PRIORITY`übergeben können.|`THREAD_PRIORITY_NORMAL`|

|`SchedulingProtocol`| Ein [parallelcurrency:: SchedulingProtocolType](reference/concurrency-namespace-enums.md#schedulingprotocoltype) -Wert, der den zu verwendenden Planungs Algorithmus angibt. |`EnhanceScheduleGroupLocality`| |`DynamicProgressFeedback`| Ein [parallelcurrency::D ynamicprogressfeedbacktype](reference/concurrency-namespace-enums.md#dynamicprogressfeedbacktype) -Wert, der angibt, ob Ressourcen entsprechend den Statistik basierten Statusinformationen ausgeglichen werden sollen.<br /><br /> **Hinweis** Legen Sie diese Richtlinie nicht auf `ProgressFeedbackDisabled` fest, da Sie für die Verwendung durch die Laufzeit reserviert ist.`ProgressFeedbackEnabled`|

Jeder Planer verwendet seine eigene Richtlinie, wenn er Tasks plant. Die Richtlinien, die einem Scheduler zugeordnet sind, wirken sich nicht auf das Verhalten anderer Planer aus. Außerdem können Sie die Scheduler-Richtlinie nicht ändern, nachdem Sie das `Scheduler`-Objekt erstellt haben.

> [!IMPORTANT]
> Verwenden Sie nur Scheduler-Richtlinien, um die Attribute für die von der Laufzeit erstellten Threads zu steuern. Ändern Sie nicht die Thread Affinität oder Priorität der Threads, die von der Laufzeit erstellt werden, da dies zu undefiniertem Verhalten führen kann.

Die Laufzeit erstellt einen Standard Planer für Sie, wenn Sie nicht explizit eine erstellen. Wenn Sie den Standard Planer in Ihrer Anwendung verwenden möchten, aber eine Richtlinie angeben möchten, die dieser Planer verwenden soll, müssen Sie die Methode " [parallelcurrency:: Scheduler:: SetDefaultSchedulerPolicy](reference/scheduler-class.md#setdefaultschedulerpolicy) " aufrufen, bevor Sie parallele Arbeiten planen. Wenn Sie die `Scheduler::SetDefaultSchedulerPolicy`-Methode nicht aufzurufen, verwendet die Common Language Runtime die Standardrichtlinien Werte aus der-Tabelle.

Verwenden Sie die [Concurrency:: CurrentScheduler:: GetPolicy](reference/currentscheduler-class.md#getpolicy) -Methode und die [Concurrency:: Scheduler:: GetPolicy](reference/scheduler-class.md#getpolicy) -Methode, um eine Kopie der Scheduler-Richtlinie abzurufen. Die Richtlinien Werte, die Sie von diesen Methoden erhalten, können sich von den Richtlinien Werten unterscheiden, die Sie beim Erstellen des Planers angeben.

## <a name="example"></a>Beispiel

Beispiele, in denen bestimmte Scheduler-Richtlinien zum Steuern des Verhaltens des Zeit Planungs Moduls verwendet werden, finden Sie unter Gewusst [wie: Angeben spezifischer Scheduler-Richtlinien](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md) und Gewusst [wie: Erstellen von Agents, die bestimmte planerrichtlinien verwenden](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md).

## <a name="see-also"></a>Weitere Informationen

[Aufgabenplanung](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[Vorgehensweise: Angeben von bestimmten Planerrichtlinien](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md)<br/>
[Vorgehensweise: Erstellen von Agents, die bestimmte Planerrichtlinien verwenden](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md)
