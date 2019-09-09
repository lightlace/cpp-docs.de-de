---
title: Diagnosetools für die parallele Ausführung (Concurrency Runtime)
ms.date: 11/04/2016
helpviewer_keywords:
- Parallel Diagnostic Tools [Concurrency Runtime]
ms.assetid: b1a3f1d2-f5df-4f29-852e-906b3d8341fc
ms.openlocfilehash: 34b2421dfc53deeb35dcc659a8d555983e583737
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69510500"
---
# <a name="parallel-diagnostic-tools-concurrency-runtime"></a>Diagnosetools für die parallele Ausführung (Concurrency Runtime)

Visual Studio bietet umfangreiche Unterstützung für das Debuggen und die Profilerstellung in Multithreadanwendungen.

## <a name="debugging"></a>Debuggen

Der Visual Studio-Debugger umfasst das Fenster **parallele Stapel** , das Fenster **parallele Aufgaben** und das Fenster **parallele Überwachung** . Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Debuggen einer](/visualstudio/debugger/walkthrough-debugging-a-parallel-application) parallelen [Anwendung und Gewusst wie: Verwenden Sie das Fenster](/visualstudio/debugger/how-to-use-the-parallel-watch-window)parallele Überwachung.

## <a name="profiling"></a>Profilerstellung

Die Profil Erstellungs Tools bieten drei Datenansichten, in denen grafische, tabellarische und numerische Informationen darüber angezeigt werden, wie eine Multithreadanwendung mit sich selbst und mit anderen Programmen interagiert. Die Ansichten ermöglichen es Ihnen, schnell Bereiche zu identifizieren und von Punkten auf den grafischen anzeigen zu navigieren, um Stapel, Aufruf Sites und Quellcode aufzurufen. Weitere Informationen finden Sie unter [Parallelitätsschnellansicht](/visualstudio/profiling/concurrency-visualizer).

## <a name="event-tracing"></a>Ereignis Ablauf Verfolgung

Der Concurrency Runtime verwendet die [Ereignis Ablauf Verfolgung für Windows (Event Tracing for Windows](/windows/win32/ETW/event-tracing-portal) , etw), um Instrumentierungs Tools wie Profiler zu benachrichtigen, wenn verschiedene Ereignisse auftreten. Diese Ereignisse beziehen sich auf die Aktivierung oder Deaktivierung eines Zeit Planungs Moduls, wenn ein Kontext beginnt, endet, blockiert, entsperrt oder ergibt und wenn ein paralleler Algorithmus beginnt oder endet.

Tools [wie die](/visualstudio/profiling/concurrency-visualizer) Parallelitäts Schnellansicht nutzen diese Funktion. Daher müssen Sie in der Regel nicht direkt mit diesen Ereignissen arbeiten. Diese Ereignisse sind jedoch nützlich, wenn Sie einen benutzerdefinierten Profiler entwickeln oder wenn Sie Ereignis Ablauf Verfolgungs Tools wie [XPerf](https://go.microsoft.com/fwlink/p/?linkid=160628)verwenden.

Der Concurrency Runtime löst diese Ereignisse nur aus, wenn die Ablauf Verfolgung aktiviert ist. Wenden Sie die Funktion " [parallelcurrency:: EnableTracing](reference/concurrency-namespace-functions.md#enabletracing) " an, um die Ereignis Ablauf Verfolgung zu aktivieren, und die Funktion "Parallelität [::D isabletracing](reference/concurrency-namespace-functions.md#disabletracing) " zum Deaktivieren der

In der folgenden Tabelle werden die Ereignisse beschrieben, die die Laufzeit auslöst, wenn die Ereignis Ablauf Verfolgung aktiviert ist:

|event|Beschreibung|Wert|
|-----------|-----------------|-----------|
|[concurrency::ConcRT_ProviderGuid](reference/concurrency-namespace-constants1.md#concrt_providerguid)|Der ETW-Anbieter Bezeichner für die Concurrency Runtime.|`f7b697a3-4db5-4d3b-be71-c4d284e6592f`|
|[concurrency::ContextEventGuid](reference/concurrency-namespace-constants1.md#contexteventguid)|Markiert Ereignisse, die mit Kontexten verknüpft sind.|`5727a00f-50be-4519-8256-f7699871fecb`|
|[concurrency::PPLParallelForEventGuid](reference/concurrency-namespace-constants1.md#pplparallelforeventguid)|Markiert den Eingang und beendet den Aufruf des [parallelcurrency::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) -Algorithmus.|`31c8da6b-6165-4042-8b92-949e315f4d84`|
|[concurrency::PPLParallelForeachEventGuid](reference/concurrency-namespace-constants1.md#pplparallelforeacheventguid)|Markiert den Eingang und beendet den Aufruf des [parallelcurrency::p arallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) -Algorithmus.|`5cb7d785-9d66-465d-bae1-4611061b5434`|
|[concurrency::PPLParallelInvokeEventGuid](reference/concurrency-namespace-constants1.md#pplparallelinvokeeventguid)|Markiert den Eingang und beendet den Aufruf des [parallelcurrency::p arallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) -Algorithmus.|`d1b5b133-ec3d-49f4-98a3-464d1a9e4682`|
|[concurrency::SchedulerEventGuid](reference/concurrency-namespace-constants1.md#schedulereventguid)|Markiert Ereignisse, die mit dem [Taskplaner](../../parallel/concrt/task-scheduler-concurrency-runtime.md)verknüpft sind.|`e2091f8a-1e0a-4731-84a2-0dd57c8a5261`|
|[concurrency::VirtualProcessorEventGuid](reference/concurrency-namespace-constants1.md#virtualprocessoreventguid)|Markiert Ereignisse im Zusammenhang mit virtuellen Prozessoren.|`2f27805f-1676-4ecc-96fa-7eb09d44302f`|

Die Concurrency Runtime definiert die folgenden Ereignisse, stellt Sie aber derzeit nicht dar. Die Laufzeit reserviert diese Ereignisse für die zukünftige Verwendung:

- [concurrency::ConcRTEventGuid](reference/concurrency-namespace-constants1.md#concrteventguid)

- [concurrency::ScheduleGroupEventGuid](reference/concurrency-namespace-constants1.md#schedulereventguid)

- [concurrency::ChoreEventGuid](reference/concurrency-namespace-constants1.md#choreeventguid)

- [concurrency::LockEventGuid](reference/concurrency-namespace-constants1.md#lockeventguid)

- [concurrency::ResourceManagerEventGuid](reference/concurrency-namespace-constants1.md#resourcemanagereventguid)

Die [parallelcurrency:: ConcRT_EventType](reference/concurrency-namespace-enums.md#concrt_eventtype) -Enumeration gibt die möglichen Vorgänge an, die von einem Ereignis nachverfolgt werden. Beispielsweise löst die Laufzeit am Ende des `parallel_for` Algorithmus das `PPLParallelForEventGuid` -Ereignis aus und stellt als- `CONCRT_EVENT_START` Vorgang bereit. Bevor der `parallel_for` Algorithmus zurückgibt, löst die Laufzeit das `PPLParallelForEventGuid` -Ereignis erneut `CONCRT_EVENT_END` aus und stellt als-Vorgang bereit.

Im folgenden Beispiel wird veranschaulicht, wie die Ablauf Verfolgung für einen `parallel_for`-Rückruf aktiviert wird. Die Laufzeit führt den ersten-Rückruf nicht aus `parallel_for` , da die Ablauf Verfolgung nicht aktiviert ist. Der- `parallel_for`Befehl ermöglichtderLaufzeit,denzweiten-`EnableTracing` Befehl zu verfolgen.

[!code-cpp[concrt-etw#1](../../parallel/concrt/codesnippet/cpp/parallel-diagnostic-tools-concurrency-runtime_1.cpp)]

Die Laufzeit verfolgt, wie oft und `EnableTracing` `DisableTracing`aufgerufen werden. Wenn Sie mehrere Male aufzurufen `EnableTracing` , `DisableTracing` müssen Sie daher die gleiche Anzahl von vorkommen, um die Ablauf Verfolgung zu deaktivieren.

## <a name="see-also"></a>Siehe auch

[Concurrency Runtime](../../parallel/concrt/concurrency-runtime.md)
