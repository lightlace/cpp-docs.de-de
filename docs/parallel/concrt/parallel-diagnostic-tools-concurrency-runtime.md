---
title: "Diagnosetools (Concurrency Runtime) für parallele | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: Parallel Diagnostic Tools [Concurrency Runtime]
ms.assetid: b1a3f1d2-f5df-4f29-852e-906b3d8341fc
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2e85ee1a0c250cf67f2a379ccad8c11a99b96f76
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="parallel-diagnostic-tools-concurrency-runtime"></a>Diagnosetools für die parallele Ausführung (Concurrency Runtime)
[!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)] bietet umfangreiche Unterstützung für das Debuggen und die Profilerstellung in Multithreadanwendungen.  
  
## <a name="debugging"></a>Debuggen  
 Der Visual Studio-Debugger beinhaltet die **parallele Stapel** Fenster **Parallele Aufgaben** Fenster und **parallele Überwachung** Fenster. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Debuggen einer parallelen Anwendung](/visualstudio/debugger/walkthrough-debugging-a-parallel-application) und [wie: Verwenden des parallelen Überwachungsfensters](/visualstudio/debugger/how-to-use-the-parallel-watch-window).  
  
## <a name="profiling"></a>Profilerstellung  
 Die Profilerstellungstools bieten drei Ansichten, in denen grafischer, tabellarischer und numerische Informationen zur Interaktion einer Multithreadanwendung mit sich selbst und für andere Programme angezeigt. Die Sichten ermöglichen es Ihnen, schnell Problembereiche zu identifizieren, und Navigieren von Punkten auf zeigt der grafische aufrufen, Stapel, rufen Sie Websites und Quellcode. Weitere Informationen finden Sie unter [Parallelitätsschnellansicht](/visualstudio/profiling/concurrency-visualizer).  
  
## <a name="event-tracing"></a>Ereignisablaufverfolgung  
 Die Concurrency Runtime verwendet [Event Tracing for Windows](http://msdn.microsoft.com/library/windows/desktop/bb968803) (ETW), um Instrumentation-Tools, z. B. Profiler zu benachrichtigen, wenn verschiedene Ereignisse auftreten. Dazu gehören ein Planer aktiviert oder deaktiviert wird, wenn ein Kontext beginnt, beendet, blockiert, Blockierung aufgehoben wird oder ergibt und bei ein paralleler Algorithmus beginnt oder endet.  
  
 Tools, z. B. die [Concurrency Visualizer](/visualstudio/profiling/concurrency-visualizer) Nutzen dieser Funktionalität; aus diesem Grund, Sie haben für gewöhnlich keine direkt mit diesen Ereignissen arbeiten. Diese Ereignisse sind jedoch hilfreich, wenn Sie einen benutzerdefinierten Profiler entwickeln oder aber wenn Sie z. B. Ereignisablaufverfolgungstools verwenden [Xperf](http://go.microsoft.com/fwlink/linkid=160628).  
  
 Die Concurrency Runtime löst diese Ereignisse nur, wenn Ablaufverfolgung aktiviert ist. Rufen Sie die [concurrency::EnableTracing](reference/concurrency-namespace-functions.md#enabletracing) Funktion, um ereignisablaufverfolgung zu ermöglichen und die [concurrency::DisableTracing](reference/concurrency-namespace-functions.md#disabletracing) Funktion zum Deaktivieren der Ablaufverfolgung.  
  
 Die folgende Tabelle beschreibt die Ereignisse, die die Laufzeit löst aus, wenn die ereignisablaufverfolgung aktiviert ist:  
  
|Ereignis|Beschreibung|Wert|  
|-----------|-----------------|-----------|  

|[Concurrency::ConcRT_ProviderGuid](reference/concurrency-namespace-constants1.md#concrt_providerguid)| Der ETW-Anbieter-Bezeichner für die Concurrency Runtime. |`f7b697a3-4db5-4d3b-be71-c4d284e6592f`|  
|[Concurrency::ContextEventGuid](reference/concurrency-namespace-constants1.md#contexteventguid)| Kennzeichnet Ereignisse, die auf Kontexte beziehen. |`5727a00f-50be-4519-8256-f7699871fecb`|  
|[Concurrency::PPLParallelForEventGuid](reference/concurrency-namespace-constants1.md#pplparallelforeventguid)| Markiert den Beginn und beenden, um Aufrufe an die [Concurrency:: parallel_for](reference/concurrency-namespace-functions.md#parallel_for) Algorithmus. |`31c8da6b-6165-4042-8b92-949e315f4d84`|  
|[Concurrency::PPLParallelForeachEventGuid](reference/concurrency-namespace-constants1.md#pplparallelforeacheventguid)| Markiert den Beginn und beenden, um Aufrufe an die [Concurrency:: parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) Algorithmus. |`5cb7d785-9d66-465d-bae1-4611061b5434`|  
|[Concurrency::PPLParallelInvokeEventGuid](reference/concurrency-namespace-constants1.md#pplparallelinvokeeventguid)| Markiert den Beginn und beenden, um Aufrufe an die [Concurrency:: parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) Algorithmus. |`d1b5b133-ec3d-49f4-98a3-464d1a9e4682`|  
|[Concurrency::SchedulerEventGuid](reference/concurrency-namespace-constants1.md#schedulereventguid)| Ereignisse, die zusammengehören kennzeichnet die [Taskplaner](../../parallel/concrt/task-scheduler-concurrency-runtime.md). |`e2091f8a-1e0a-4731-84a2-0dd57c8a5261`|  
|[Concurrency::VirtualProcessorEventGuid](reference/concurrency-namespace-constants1.md#virtualprocessoreventguid)| Kennzeichnet Ereignisse, die auf virtuelle Prozessoren beziehen. |`2f27805f-1676-4ecc-96fa-7eb09d44302f`|  
  
 Die Concurrency Runtime definiert, aber derzeit löst keine, die folgenden Ereignisse. Die Common Language Runtime reserviert diese Ereignisse für die zukünftige Verwendung:  
  
-   [Concurrency::ConcRTEventGuid](reference/concurrency-namespace-constants1.md#concrteventguid)  
  
-   [Concurrency::ScheduleGroupEventGuid](reference/concurrency-namespace-constants1.md#schedulereventguid)  
  
-   [Concurrency::ChoreEventGuid](reference/concurrency-namespace-constants1.md#choreeventguid)  
  
-   [Concurrency::LockEventGuid](reference/concurrency-namespace-constants1.md#lockeventguid)  
  
-   [Concurrency::ResourceManagerEventGuid](reference/concurrency-namespace-constants1.md#resourcemanagereventguid)  
  
 Die [Concurrency:: ConcRT_EventType](reference/concurrency-namespace-enums.md#concrt_eventtype) Enumeration gibt an, der möglichen Vorgänge, die ein Ereignis protokolliert. Beispielsweise am Eingang der `parallel_for` Algorithmus, löst die Laufzeit die `PPLParallelForEventGuid` Ereignis sowie `CONCRT_EVENT_START` als den Vorgang. Vor der `parallel_for` Algorithmus zurückgibt, löst die Laufzeit erneut die `PPLParallelForEventGuid` Ereignis sowie `CONCRT_EVENT_END` als den Vorgang.  
  
 Im folgende Beispiel wird veranschaulicht, wie zum Aktivieren der Ablaufverfolgung für einen Aufruf `parallel_for`. Die Laufzeit ist nicht der erste Aufruf von trace `parallel_for` da tracing nicht aktiviert. Der Aufruf von `EnableTracing` ermöglicht es die Laufzeit für die Ablaufverfolgung des zweiten Aufrufs von `parallel_for`.  
  
 [!code-cpp[concrt-etw#1](../../parallel/concrt/codesnippet/cpp/parallel-diagnostic-tools-concurrency-runtime_1.cpp)]  
  
 Die Laufzeit verfolgt die Anzahl der Aufrufe `EnableTracing` und `DisableTracing`. Deshalb beim Aufrufen `EnableTracing` mehrere Male, die Sie aufrufen müssen `DisableTracing` die gleiche Anzahl von Zeiten aus, um die Ablaufverfolgung zu deaktivieren.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency Runtime](../../parallel/concrt/concurrency-runtime.md)

