---
title: "Diagnosetools f&#252;r die parallele Ausf&#252;hrung (Concurrency Runtime) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Diagnosetools für die parallele Ausführung [Concurrency Runtime]"
ms.assetid: b1a3f1d2-f5df-4f29-852e-906b3d8341fc
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# Diagnosetools f&#252;r die parallele Ausf&#252;hrung (Concurrency Runtime)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)] bietet umfangreiche Unterstützung für das Debuggen und die Profilerstellung in Multithreadanwendungen.  
  
## Debuggen  
 Der Visual Studio\-Debugger beinhaltet das Fenster **Parallele Stapel**, das Fenster **Parallele Aufgaben** und das Fenster **Parallele Überwachung**.  Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Debuggen einer parallelen Anwendung](../Topic/Walkthrough:%20Debugging%20a%20Parallel%20Application.md) und [Gewusst wie: Verwenden des parallelen Überwachungsfensters](../Topic/How%20to:%20Use%20the%20Parallel%20Watch%20Window.md).  
  
## Profilerstellung  
 Die Profilerstellungstools stellen drei Datenansichten bereit, in denen grafische, tabellarische und numerische Informationen darüber angezeigt werden, wie eine Multithreadanwendung mit sich und mit anderen Programmen interagiert.  In den Ansichten können Sie schnell problematische Bereiche erkennen und von Punkten in den grafischen Anzeigen zu Aufruflisten, Aufrufsites und Quellcode navigieren.  Weitere Informationen finden Sie unter [Parallelitätsschnellansicht](../Topic/Concurrency%20Visualizer.md).  
  
## Ereignisablaufverfolgung  
 Die Concurrency Runtime verwendet die [Ereignisablaufverfolgung für Windows](http://msdn.microsoft.com/library/windows/desktop/bb968803) \(Event Tracing for Windows, ETW\), um Instrumentationstools, z. B. Profiler, über Ereignisse zu benachrichtigen.  Zu diesen Ereignissen zählen z. B. das Aktivieren oder Deaktivieren eines Planers, das Starten, Beenden, Blockieren, Aufheben der Blockierung oder Zurückhalten eines Kontexts und das Starten oder Beenden eines parallelen Algorithmus.  
  
 Diese Funktionalität wird von Tools wie dem [Parallelitätsschnellansicht](../Topic/Concurrency%20Visualizer.md) genutzt. Deshalb müssen Sie normalerweise nicht direkt mit diesen Ereignissen arbeiten.  Diese Ereignisse sind jedoch hilfreich, wenn Sie einen benutzerdefinierten Profiler entwickeln oder wenn Sie Ereignisablaufverfolgungstools, z [Xperf](http://go.microsoft.com/fwlink/?LinkID=160628) verwenden.  
  
 Die Concurrency Runtime löst diese Ereignisse nur aus, wenn die Ablaufverfolgung aktiviert ist.  Rufen Sie die [Concurrency::EnableTracing](../Topic/EnableTracing%20Function.md)\-Funktion auf, um die Ereignisablaufverfolgung und die [Concurrency::DisableTracing](../Topic/DisableTracing%20Function.md)\-Funktion zu aktivieren, um sie zu deaktivieren.  
  
 In der folgenden Tabelle werden die Ereignisse beschrieben, die von der Laufzeit ausgelöst werden, wenn die Ereignisablaufverfolgung aktiviert ist:  
  
|Ereignis|**Beschreibung**|Wert|  
|--------------|----------------------|----------|  
|[concurrency::ConcRT\_ProviderGuid](../Topic/ConcRT_ProviderGuid%20Constant.md)|Der ETW\-Anbieterbezeichner für die Concurrency Runtime.|`f7b697a3-4db5-4d3b-be71-c4d284e6592f`|  
|[concurrency::ContextEventGuid](../Topic/ContextEventGuid%20Constant.md)|Markiert Ereignisse, die sich auf Kontexte beziehen.|`5727a00f-50be-4519-8256-f7699871fecb`|  
|[concurrency::PPLParallelForEventGuid](../Topic/PPLParallelForEventGuid%20Constant.md)|Markiert den Beginn und das Ende von Aufrufen zu den [concurrency::parallel\_for](../Topic/parallel_for%20Function.md) \- Algorithmus.|`31c8da6b-6165-4042-8b92-949e315f4d84`|  
|[concurrency::PPLParallelForeachEventGuid](../Topic/PPLParallelForeachEventGuid%20Constant.md)|Markiert den Beginn und das Ende von Aufrufen zu den [concurrency::parallel\_for\_each](../Topic/parallel_for_each%20Function.md) \- Algorithmus.|`5cb7d785-9d66-465d-bae1-4611061b5434`|  
|[concurrency::PPLParallelInvokeEventGuid](../Topic/PPLParallelInvokeEventGuid%20Constant.md)|Markiert den Beginn und das Ende von Aufrufen zu den [concurrency::parallel\_invoke](../Topic/parallel_invoke%20Function.md) \- Algorithmus.|`d1b5b133-ec3d-49f4-98a3-464d1a9e4682`|  
|[concurrency::SchedulerEventGuid](../Topic/SchedulerEventGuid%20Constant.md)|Markiert Ereignisse, die sich auf den [Taskplaner](../../parallel/concrt/task-scheduler-concurrency-runtime.md) beziehen.|`e2091f8a-1e0a-4731-84a2-0dd57c8a5261`|  
|[concurrency::VirtualProcessorEventGuid](../Topic/VirtualProcessorEventGuid%20Constant.md)|Markiert Ereignisse, die sich auf virtuelle Prozessoren beziehen.|`2f27805f-1676-4ecc-96fa-7eb09d44302f`|  
  
 Die Concurrency Runtime definiert die folgenden Ereignisse, löst sie derzeit jedoch nicht aus.  Die folgenden Ereignisse sind für die zukünftige Verwendung durch die Laufzeit reserviert:  
  
-   [concurrency::ConcRTEventGuid](../Topic/ConcRTEventGuid%20Constant.md)  
  
-   [concurrency::ScheduleGroupEventGuid](../Topic/SchedulerEventGuid%20Constant.md)  
  
-   [concurrency::ChoreEventGuid](../Topic/ChoreEventGuid%20Constant.md)  
  
-   [concurrency::LockEventGuid](../Topic/LockEventGuid%20Constant.md)  
  
-   [concurrency::ResourceManagerEventGuid](../Topic/ResourceManagerEventGuid%20Constant.md)  
  
 Die [concurrency::ConcRT\_EventType](../Topic/ConcRT_EventType%20Enumeration.md)\-Enumeration gibt die möglichen Vorgänge an, die von einem Ereignis nachverfolgt.  Beispielsweise löst die Laufzeit bei Beginn des `parallel_for`\-Algorithmus das `PPLParallelForEventGuid` \-Ereignis aus und stellt `CONCRT_EVENT_START` als Vorgang bereit.  Bevor der `parallel_for`\-Algorithmus beendet wird, löst die Laufzeit erneut das `PPLParallelForEventGuid`\-Ereignis aus und stellt `CONCRT_EVENT_END` als Vorgang bereit.  
  
 Das folgende Beispiel veranschaulicht, wie die Ablaufverfolgung für einen Aufruf von `parallel_for` aktiviert wird.  Die Laufzeit verfolgt den ersten Aufruf von `parallel_for` nicht nach, da keine Ablaufverfolgung aktiviert ist.  Der Aufruf von `EnableTracing` aktiviert die Ablaufverfolgung des zweiten Aufrufs von `parallel_for` durch die Laufzeit.  
  
 [!CODE [concrt-etw#1](../CodeSnippet/VS_Snippets_ConcRT/concrt-etw#1)]  
  
 Die Laufzeit verfolgt die Anzahl der Aufrufe von `EnableTracing` und `DisableTracing` nach.  Daher müssen Sie zum Deaktivieren der Ablaufverfolgung `DisableTracing` so oft aufrufen, wie Sie `EnableTracing` aufrufen.  
  
## Siehe auch  
 [Concurrency Runtime](../../parallel/concrt/concurrency-runtime.md)