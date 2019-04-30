---
title: Diagnosetools für die parallele Ausführung (Concurrency Runtime)
ms.date: 11/04/2016
helpviewer_keywords:
- Parallel Diagnostic Tools [Concurrency Runtime]
ms.assetid: b1a3f1d2-f5df-4f29-852e-906b3d8341fc
ms.openlocfilehash: 2af1898312a4f448d618fcfc4e43ea93f5f0bc76
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2019
ms.locfileid: "64346315"
---
# <a name="parallel-diagnostic-tools-concurrency-runtime"></a>Diagnosetools für die parallele Ausführung (Concurrency Runtime)

Visual Studio bietet umfangreiche Unterstützung für das Debuggen und die Profilerstellung in Multithreadanwendungen.

## <a name="debugging"></a>Debuggen

Der Visual Studio-Debugger beinhaltet die **parallele Stapel** Fenster **Parallele Aufgaben** Fenster und **parallele Überwachung** Fenster. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Debuggen einer parallelen Anwendung](/visualstudio/debugger/walkthrough-debugging-a-parallel-application) und [Vorgehensweise: Verwenden Sie das parallele Überwachungsfenster](/visualstudio/debugger/how-to-use-the-parallel-watch-window).

## <a name="profiling"></a>Profilerstellung

Die Profilerstellungstools bieten drei Datenansichten, die grafischer, tabellarischer und numerische Informationen zur Interaktion einer Multithreadanwendung mit sich selbst und mit anderen Programmen anzeigen. Die Ansichten ermöglichen es Ihnen, schnell Problembereiche zu identifizieren, und rufen zum Navigieren zwischen den Punkten auf der grafischen angezeigt, auf dem Stapel, rufen Websites und Quellcode. Weitere Informationen finden Sie unter [Parallelitätsschnellansicht](/visualstudio/profiling/concurrency-visualizer).

## <a name="event-tracing"></a>Ereignisablaufverfolgung

Die Concurrency Runtime [Ereignisablaufverfolgung für Windows-Ereignis](/windows/desktop/ETW/event-tracing-portal) (ETW), um Instrumentation-Tools, z. B. den Profiler zu benachrichtigen, wenn verschiedene Ereignisse eintreten. Diese Ereignisse enthalten, wenn ein Planer aktiviert oder deaktiviert wird, wenn ein Kontext beginnt, beendet, blockiert, Blockierung aufgehoben wird oder ergibt und bei ein paralleler Algorithmus beginnt oder endet.

Tools, z. B. die [Concurrency Visualizer](/visualstudio/profiling/concurrency-visualizer) nutzen diese Funktionalität; aus diesem Grund, Sie in der Regel müssen nicht direkt mit diesen Ereignissen arbeiten. Diese Ereignisse sind jedoch hilfreich, wenn Sie einen benutzerdefinierten Profiler entwickeln oder wenn Sie Ereignis-Ablaufverfolgungstools wie z. B. [Xperf](http://go.microsoft.com/fwlink/p/?linkid=160628).

Die Concurrency Runtime löst diese Ereignisse nur, wenn Ablaufverfolgung aktiviert ist. Rufen Sie die [concurrency::EnableTracing](reference/concurrency-namespace-functions.md#enabletracing) Funktion, um die ereignisablaufverfolgung aktivieren und die [concurrency::DisableTracing](reference/concurrency-namespace-functions.md#disabletracing) Funktion zum Deaktivieren der Ablaufverfolgung.

Die folgende Tabelle beschreibt die Ereignisse, die von der Laufzeit ausgelöst, wenn die ereignisablaufverfolgung aktiviert ist:

|event|Beschreibung|Wert|
|-----------|-----------------|-----------|
|[concurrency::ConcRT_ProviderGuid](reference/concurrency-namespace-constants1.md#concrt_providerguid)|Der ETW-Anbieter-Bezeichner für die Concurrency Runtime.|`f7b697a3-4db5-4d3b-be71-c4d284e6592f`|
|[concurrency::ContextEventGuid](reference/concurrency-namespace-constants1.md#contexteventguid)|Markiert die Ereignisse, die auf Kontexte beziehen.|`5727a00f-50be-4519-8256-f7699871fecb`|
|[concurrency::PPLParallelForEventGuid](reference/concurrency-namespace-constants1.md#pplparallelforeventguid)|Markiert den Beginn und Ende von Aufrufen der [Concurrency:: parallel_for](reference/concurrency-namespace-functions.md#parallel_for) Algorithmus.|`31c8da6b-6165-4042-8b92-949e315f4d84`|
|[concurrency::PPLParallelForeachEventGuid](reference/concurrency-namespace-constants1.md#pplparallelforeacheventguid)|Markiert den Beginn und Ende von Aufrufen der [Concurrency:: parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) Algorithmus.|`5cb7d785-9d66-465d-bae1-4611061b5434`|
|[concurrency::PPLParallelInvokeEventGuid](reference/concurrency-namespace-constants1.md#pplparallelinvokeeventguid)|Markiert den Beginn und Ende von Aufrufen der [Concurrency:: parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) Algorithmus.|`d1b5b133-ec3d-49f4-98a3-464d1a9e4682`|
|[concurrency::SchedulerEventGuid](reference/concurrency-namespace-constants1.md#schedulereventguid)|Markiert die Ereignisse, die im Zusammenhang mit der [Taskplaner](../../parallel/concrt/task-scheduler-concurrency-runtime.md).|`e2091f8a-1e0a-4731-84a2-0dd57c8a5261`|
|[concurrency::VirtualProcessorEventGuid](reference/concurrency-namespace-constants1.md#virtualprocessoreventguid)|Markiert die Ereignisse, die auf virtuelle Prozessoren beziehen.|`2f27805f-1676-4ecc-96fa-7eb09d44302f`|

Die Concurrency Runtime definiert, aber derzeit Ereignisse nicht ausgelöst werden, die folgenden. Die Laufzeit sind diese Ereignisse für die zukünftige Verwendung reserviert:

- [concurrency::ConcRTEventGuid](reference/concurrency-namespace-constants1.md#concrteventguid)

- [concurrency::ScheduleGroupEventGuid](reference/concurrency-namespace-constants1.md#schedulereventguid)

- [concurrency::ChoreEventGuid](reference/concurrency-namespace-constants1.md#choreeventguid)

- [concurrency::LockEventGuid](reference/concurrency-namespace-constants1.md#lockeventguid)

- [concurrency::ResourceManagerEventGuid](reference/concurrency-namespace-constants1.md#resourcemanagereventguid)

Die [Concurrency:: ConcRT_EventType](reference/concurrency-namespace-enums.md#concrt_eventtype) -Enumeration gibt an, die möglichen Vorgänge, die ein Ereignis nachverfolgt. Z. B. am Eingang der `parallel_for` -Algorithmus, löst die Laufzeit die `PPLParallelForEventGuid` Ereignis sowie `CONCRT_EVENT_START` wie der Vorgang. Vor der `parallel_for` Algorithmus zurückgibt, löst die Laufzeit erneut die `PPLParallelForEventGuid` Ereignis sowie `CONCRT_EVENT_END` als Vorgang.

Im folgende Beispiel wird veranschaulicht, wie Sie zum Aktivieren der Ablaufverfolgung für einen Aufruf von `parallel_for`. Die Laufzeit ist nicht der erste Aufruf verfolgen `parallel_for` da Ablaufverfolgung nicht aktiviert. Der Aufruf von `EnableTracing` ermöglicht der Laufzeit, den zweiten Aufruf von Ablaufverfolgung `parallel_for`.

[!code-cpp[concrt-etw#1](../../parallel/concrt/codesnippet/cpp/parallel-diagnostic-tools-concurrency-runtime_1.cpp)]

Die Laufzeit verfolgt die Anzahl der Male, die Sie aufrufen `EnableTracing` und `DisableTracing`. Aus diesem Grund Aufrufen `EnableTracing` mehrere Versuche, die Sie aufrufen müssen `DisableTracing` die gleiche Anzahl an, wie oft, um die Ablaufverfolgung zu deaktivieren.

## <a name="see-also"></a>Siehe auch

[Concurrency Runtime](../../parallel/concrt/concurrency-runtime.md)
