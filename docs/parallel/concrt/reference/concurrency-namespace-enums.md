---
title: Concurrency-Namespace Enumerationen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CONCRT/concurrency::Agents_EventType
- CONCRT/concurrency::Concrt_TraceFlags
- CONCRT/concurrency::CriticalRegionType
- CONCRT/concurrency::PolicyElementKey
- CONCRT/concurrency::SchedulerType
- CONCRT/concurrency::SwitchingProxyState
- CONCRT/concurrency::WinRTInitializationType
- CONCRT/concurrency::join_type
- CONCRT/concurrency::message_status Enumeration
dev_langs:
- C++
ms.assetid: a40e3b2d-ad21-4229-9880-2cfa84f7ab8f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 068aa89c10e92203ce0e826e3aaca101f4786cbb
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33695261"
---
# <a name="concurrency-namespace-enums"></a>Concurrency-Namespace-Enumerationen
||||  
|-|-|-|  
|[Agents_EventType](#agents_eventtype)|[ConcRT_EventType](#concrt_eventtype)|[Concrt_TraceFlags](#concrt_traceflags)|  
|[CriticalRegionType](#criticalregiontype)|[DynamicProgressFeedbackType](#dynamicprogressfeedbacktype)|[PolicyElementKey](#policyelementkey)|  
|[SchedulerType](#schedulertype)|[SchedulingProtocolType](#schedulingprotocoltype)|[SwitchingProxyState](#switchingproxystate)|  
|[WinRTInitializationType](#winrtinitializationtype)|[agent_status](#agent_status)|[join_type](#join_type)|  
|[message_status](#message_status)|[task_group_status](#task_group_status)|  
  
##  <a name="agent_status"></a>  Agent_status-Enumeration  
 Die gültigen Zustände für einen `agent`.  
  
```
enum agent_status;
```  
### <a name="values"></a>Werte  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`agent_canceled`|Das `agent` wurde abgebrochen.|  
|`agent_created`|Die `agent` erstellt, jedoch nicht gestartet wurde.|  
|`agent_done`|Die `agent` wurde ohne Abbruchs abgeschlossen.|  
|`agent_runnable`|Die `agent` gestartet wurde, aber nicht eingegeben seine `run` Methode.|  
|`agent_started`|Die `agent` wurde gestartet.|  

### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [asynchrone Agents](../../../parallel/concrt/asynchronous-agents.md).  

### <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h hinzu

##  <a name="agents_eventtype"></a>  Agents_EventType-Enumeration  
 Die Typen von Ereignissen, die mit der von der Agents Library angebotenen Ablaufverfolgungsfunktionalität aufgezeichnet werden können  
  
```
enum Agents_EventType;
```  

### <a name="values"></a>Werte  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`AGENTS_EVENT_CREATE`|Ein Ereignistyp, der die Erstellung eines Objekts darstellt.|  
|`AGENTS_EVENT_DESTROY`|Ein Ereignistyp, der das Löschen eines Objekts darstellt.|  
|`AGENTS_EVENT_END`|Ein Ereignistyp, der den Abschluss des einige darstellt verarbeiten|  
|`AGENTS_EVENT_LINK`|Ein Ereignistyp, der die Verknüpfung der Meldungsblöcke darstellt|  
|`AGENTS_EVENT_NAME`|Ein Ereignistyp, der den Namen für ein Objekt darstellt.|  
|`AGENTS_EVENT_SCHEDULE`|Ein Ereignistyp, der darstellt, die Planung eines Prozesses|  
|`AGENTS_EVENT_START`|Ein Ereignistyp, die für die Initiierung von einigen verarbeiten|  
|`AGENTS_EVENT_UNLINK`|Ein Ereignistyp, der das Aufheben der Verknüpfung der Meldungsblöcke darstellt|  

### <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h hinzu

##  <a name="concrt_eventtype"></a>  ConcRT_EventType-Enumeration  
 Die Typen von Ereignissen, die mit der von der Concurrency Runtime angebotenen Ablaufverfolgungsfunktionalität aufgezeichnet werden können.  
  
```
enum ConcRT_EventType;
```  
### <a name="values"></a>Werte  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CONCRT_EVENT_ATTACH`|Ein Ereignistyp, der das Act, der das Anfügen an einen Planer darstellt.|  
|`CONCRT_EVENT_BLOCK`|Ein Ereignistyp, der der Vorgang des Blockieren eines Kontexts darstellt.|  
|`CONCRT_EVENT_DETACH`|Ein Ereignistyp, der der Vorgang eine durch das Trennen von einem Planer darstellt.|  
|`CONCRT_EVENT_END`|Ein Ereignistyp, der den Anfang des ein Ereignispaar Start/Ende markiert.|  
|`CONCRT_EVENT_GENERIC`|Ein Ereignistyp, der für verschiedene Ereignisse verwendet wird.|  
|`CONCRT_EVENT_IDLE`|Ein Ereignistyp, der das Act eines Kontexts Leerlauf darstellt.|  
|`CONCRT_EVENT_START`|Ein Ereignistyp, der den Anfang des ein Ereignispaar Start/Ende markiert.|  
|`CONCRT_EVENT_UNBLOCK`|Ein Ereignistyp, der der Vorgang zum Aufheben der Blockierung von eines Kontexts darstellt.|  
|`CONCRT_EVENT_YIELD`|Ein Ereignistyp, der einen Kontext und gibt der Vorgang darstellt.|  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h hinzu **Namespace:** Parallelität

##  <a name="concrt_traceflags"></a>  Concrt_TraceFlags-Enumeration  
 Ablaufverfolgungskennzeichen für die Ereignistypen  
  
```
enum Concrt_TraceFlags;
```  
### <a name="values"></a>Werte  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`AgentEventFlag`||  
|`AllEventsFlag`||  
|`ContextEventFlag`||  
|`PPLEventFlag`||  
|`ResourceManagerEventFlag`||  
|`SchedulerEventFlag`||  
|`VirtualProcessorEventFlag`||

### <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h hinzu

##  <a name="criticalregiontype"></a>  CriticalRegionType-Enumeration  
 Der Typ eines kritischen Bereichs, in dem sich ein Kontext befindet.  
  
```
enum CriticalRegionType;
```  
### <a name="values"></a>Werte  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`InsideCriticalRegion`|Gibt an, dass der Kontext in einem wichtigen Bereich ist. In einem kritischen Bereich werden asynchrone Eingangsseite vom Planer ausgeblendet. So eine Unterbrechung sollte erfolgen, der Ressourcen-Manager gewartet wird, für den Thread ausführbar werden, und es einfach fortsetzen, statt den Planer erneut aufzurufen. Alle sperren, die in solchen Bereichs müssen mit Sorgfalt ausgeführt werden.|  
|`InsideHyperCriticalRegion`|Gibt an, dass der Kontext in einem hyper-wichtigen Bereich ist. Synchrone und asynchrone Eingangsseite werden in einem hyper-wichtigen Bereich vom Planer ausgeblendet. Sollten Sie so eine Unterbrechung oder Blockierung auftritt, der Ressourcen-Manager gewartet wird, für den Thread ausführbar werden, und es einfach fortsetzen, statt den Planer erneut aufzurufen. In so einem Bereich Sperren müssen niemals für Code außerhalb eines solchen Bereichs ausgeführt freigegeben werden. Auf diese Weise wird zu einem unvorhersehbaren Deadlock.|  
|`OutsideCriticalRegion`|Gibt an, dass der Kontext außerhalb eines wichtigen Bereichs ist.|  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** concrtrm.h 

##  <a name="dynamicprogressfeedbacktype"></a>  DynamicProgressFeedbackType-Enumeration  
 Wird von der `DynamicProgressFeedback`-Richtlinie verwendet, um zu beschreiben, ob Ressourcen für den Planer anhand statistischer Informationen neu verteilt werden, die vom Planer oder nur auf Grundlage virtueller Prozessoren erfasst wurden, die wegen der Aufrufe der `Activate`-Methode und der `Deactivate`-Methode für die `IVirtualProcessorRoot`-Schnittstelle in den und aus dem Leerlauf wechseln. Weitere Informationen über verfügbare Planerrichtlinien finden Sie unter [PolicyElementKey](concurrency-namespace-enums.md).  
  
```
enum DynamicProgressFeedbackType;
```  
### <a name="values"></a>Werte  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`ProgressFeedbackDisabled`|Der Planer erfasst nur die Statusinformationen zu erhalten. Neuverteilen ist ausschließlich auf Abonnementebene der zugrunde liegenden Hardwarethread beruhen. Weitere Informationen zu Abonnementebenen finden Sie unter [IExecutionResource:: CurrentSubscriptionLevel](IExecutionResource-structure.md).<br /><br /> Dieser Wert wird von der Laufzeit für die Verwendung reserviert.|  
|`ProgressFeedbackEnabled`|Der Planer erfasst Statusinformationen und übergibt sie an dem Ressourcen-Manager. Der Ressourcen-Manager wird diese statistischen Informationen, um im Auftrag der Planer neben Abonnementebene des zugrunde liegenden Hardwarethreads Ressourcenausgleich nutzen. Weitere Informationen zu Abonnementebenen finden Sie unter [IExecutionResource:: CurrentSubscriptionLevel](IExecutionResource-structure.md).|  
##  <a name="join_type"></a>  Join_type-Enumeration  
 Der Typ eines `join`-Meldungsblocks.  
  
```
enum join_type;
```  
### <a name="values"></a>Werte  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`greedy`|Gierige `join` Meldungsblöcken sofort nach der Weitergabe eine Meldung akzeptiert. Dies ist jedoch effizienter, aber die Gefahr von live-Sperre, abhängig von der Netzwerkkonfiguration wurde.|  
|`non_greedy`|Nicht gieriger `join` Meldungsblöcken Verschieben von Nachrichten, und versuchen Sie es, und nutzen müssen, nachdem alle angekommen sind. Diese sind notwendigerweise auch funktionsfähig, aber verlangsamt.|  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** agents.h  

##  <a name="message_status"></a>  Message_status-Enumeration  
 Die gültigen Antworten für das Angebot eines `message`-Objekts für einen Block.  
  
```
enum message_status;
```  
### <a name="values"></a>Werte  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`accepted`|Das Ziel hat die Meldung akzeptiert.|  
|`declined`|Das Ziel hat die Nachricht nicht akzeptiert.|  
|`missed`|Das Ziel hat versucht, die Nachricht akzeptiert, aber es war nicht mehr verfügbar.|  
|`postponed`|Das Ziel verschoben, sodass die Nachricht.|  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** agents.h  

##  <a name="policyelementkey"></a>  PolicyElementKey-Enumeration  
 Richtlinienschlüssel, die Aspekte des Planerverhaltens beschreiben. Jedes Richtlinienelement wird mit einem Schlüssel-Wert-Paar beschrieben. Weitere Informationen zu Planerrichtlinien und deren Auswirkungen auf Planer finden Sie unter [Taskplaner](../../../parallel/concrt/task-scheduler-concurrency-runtime.md).  
  
```
enum PolicyElementKey;
```  
### <a name="values"></a>Werte  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`ContextPriority`|Die Betriebssystem-Threadpriorität der einzelnen Kontexte im Planer. Wenn dieser Schlüssel, auf den Wert festgelegt ist `INHERIT_THREAD_PRIORITY` erben die Kontexte im Planer die Priorität des Threads, der den Planer erstellt hat.<br /><br /> Gültige Werte: einer der gültigen Werte für den Windows- `SetThreadPriority` -Funktion und der spezielle Wert `INHERIT_THREAD_PRIORITY`<br /><br /> Standardwert: `THREAD_PRIORITY_NORMAL`|  
|`ContextStackSize`|Die reservierte Stapelgröße der einzelnen Kontexte im Planer in Kilobyte.<br /><br /> Gültige Werte: Positive ganze Zahlen<br /><br /> Standardwert: `0`, gibt an, dass der Standardwert für die Stapelgröße des Prozesses verwendet werden.|  
|`DynamicProgressFeedback`|Bestimmt, ob die Ressourcen für den Planer anhand statistischer Informationen gesammelt, die vom Planer oder nur basierend auf der Abonnementebene des zugrunde liegenden Hardwarethreads neu verteilt werden. Weitere Informationen finden Sie unter [DynamicProgressFeedbackType](#dynamicprogressfeedbacktype).<br /><br /> Gültige Werte: ein Mitglied der `DynamicProgressFeedbackType` Enumeration, entweder `ProgressFeedbackEnabled` oder `ProgressFeedbackDisabled`<br /><br /> Standardwert: `ProgressFeedbackEnabled`|  
|`LocalContextCacheSize`|Wenn die `SchedulingProtocol` Richtlinienschlüssel festgelegt ist, auf den Wert `EnhanceScheduleGroupLocality`, gibt die maximale Anzahl ausführbarer Kontexte zulässig pro virtueller Prozessor lokale Warteschlangen in zwischengespeichert werden. Solche Kontexte werden in der Regel nacheinander Last in First Out (LIFO) für den virtuellen Prozessor ausgeführt werden, die ausführbar wird damit verursacht hat. Beachten Sie, dass dieser Richtlinienschlüssel hat keine Bedeutung bei der `SchedulingProtocol` Schlüssel festgelegt ist, auf den Wert `EnhanceForwardProgress`.<br /><br /> Gültige Werte: nicht Negative ganze Zahlen<br /><br /> Standardwert: `8`|  
|`MaxConcurrency`|Die maximale vom Planer gewünschte Parallelitätsebene. Der Ressourcen-Manager versucht, anfänglich so viele virtuelle Prozessoren reserviert werden. Der spezielle Wert [MaxExecutionResources](concurrency-namespace-constants1.md#maxexecutionresources) gibt an, dass die gewünschte Parallelitätsebene mit der Anzahl von Hardwarethreads auf dem Computer identisch ist. Wenn der Wert für die angegebene `MinConcurrency` ist größer als die Anzahl von Hardwarethreads auf dem Computer und `MaxConcurrency` angegeben ist, als `MaxExecutionResources`, den Wert für `MaxConcurrency` wird ausgelöst, um übereinstimmen, was für festgelegt ist `MinConcurrency`.<br /><br /> Gültige Werte: Positive ganze Zahlen und der spezielle Wert `MaxExecutionResources`<br /><br /> Standardwert: `MaxExecutionResources`|  
|`MaxPolicyElementKey`|Der maximale Richtlinienelementschlüssel. Eine gültige Element-Schlüssel.|  
|`MinConcurrency`|Die minimale Parallelitätsebene, die auf dem Planer vom Ressourcenmanager bereitgestellt werden müssen. Die Anzahl virtueller Prozessoren, die einem Planer zugewiesen wird nie unter dem Mindestwert gesendet. Der spezielle Wert [MaxExecutionResources](concurrency-namespace-constants1.md#maxexecutionresources) gibt an, dass die minimale Parallelitätsebene mit der Anzahl von Hardwarethreads auf dem Computer identisch ist. Wenn der Wert für die angegebene `MaxConcurrency` ist kleiner als die Anzahl von Hardwarethreads auf dem Computer und `MinConcurrency` angegeben ist, als `MaxExecutionResources`, den Wert für `MinConcurrency` gesenkt werden, um übereinstimmen, was für festgelegt ist `MaxConcurrency`.<br /><br /> Gültige Werte: nicht Negative ganze Zahlen und der spezielle Wert `MaxExecutionResources`. Beachten Sie, dass für verwendet für die Erstellung der Concurrency Runtime-Planern, den Wert mithilfe von Planerrichtlinien `0` ist ungültig.<br /><br /> Standardwert: `1`|  
|`SchedulerKind`|Der Typ der Threads, die der Planer für zugrunde liegende Ausführungskontexte verwenden wird. Weitere Informationen finden Sie unter [SchedulerType](#schedulertype).<br /><br /> Gültige Werte: ein Mitglied der `SchedulerType` -Enumeration, z. B. `ThreadScheduler`<br /><br /> Standardwert: `ThreadScheduler`. Dies führt zur Win32-Threads auf allen Betriebssystemen.|  
|`SchedulingProtocol`|Beschreibt, welcher Planungsalgorithmus vom Planer verwendet wird. Weitere Informationen finden Sie unter [SchedulingProtocolType](#schedulingprotocoltype).<br /><br /> Gültige Werte: ein Mitglied der `SchedulingProtocolType` Enumeration, entweder `EnhanceScheduleGroupLocality` oder `EnhanceForwardProgress`<br /><br /> Standardwert: `EnhanceScheduleGroupLocality`|  
|`TargetOversubscriptionFactor`|Vorläufige Anzahl virtueller Prozessoren pro Hardwarethread. Faktor für die Ziel-Überzeichnung kann vom Ressourcen-Manager, bei Bedarf, um erfüllen erhöht werden `MaxConcurrency` mit dem Zuordnen von Hardwarethreads auf dem Computer.<br /><br /> Gültige Werte: Positive ganze Zahlen<br /><br /> Standardwert: `1`|  
|`WinRTInitialization`||  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h hinzu  

##  <a name="schedulertype"></a>  SchedulerType-Enumeration  
 Wird von der `SchedulerKind`-Richtlinie verwendet, um den Typ der Threads zu beschreiben, die der Planer für zugrunde liegende Ausführungskontexte verwenden soll. Weitere Informationen über verfügbare Planerrichtlinien finden Sie unter [PolicyElementKey](concurrency-namespace-enums.md).  
  
```
enum SchedulerType;
``` 

### <a name="values"></a>Werte  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`ThreadScheduler`|Gibt eine explizite Anforderung von regulären Win32-Threads an.|  
|`UmsThreadDefault`|Im Benutzermodus planbare (UMS) Threads werden in der Concurrency Runtime in Visual Studio 2013 nicht unterstützt. Das Verwenden von `UmsThreadDefault` als ein Wert für die `SchedulerType`-Richtlinie führt zu keinem Fehler. Ein Planer, der mit dieser Richtlinie erstellt wurde, wird jedoch standardmäßig Win32-Threads verwenden.|  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h hinzu  
  
##  <a name="schedulingprotocoltype"></a>  SchedulingProtocolType-Enumeration  
 Wird von der `SchedulingProtocol`-Richtlinie verwendet, um zu beschreiben, welcher Planungsalgorithmus für den Planer verwendet wird. Weitere Informationen über verfügbare Planerrichtlinien finden Sie unter [PolicyElementKey](concurrency-namespace-enums.md).  
  
```
enum SchedulingProtocolType;
```  
### <a name="values"></a>Werte  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`EnhanceForwardProgress`|Der Planer bevorzugt Roundrobin-Verfahren über Planungsgruppen nach der Ausführung von jeder Aufgabe. Entsperrt Kontexte sind in der Regel in einer First in First Out (FIFO)-Weise geplant. Virtuelle Prozessoren Zwischenspeichern entsperrt Kontexten nicht.|  
|`EnhanceScheduleGroupLocality`|Der Planer bevorzugt weiterhin auf Vorgänge innerhalb der aktuellen Planungsgruppe ausgeführt werden soll, vor dem Wechsel in einer anderen Planungsgruppe. Entsperrt Kontexten pro virtueller Prozessor zwischengespeichert werden und in der Regel in einer Weise der Last in First Out (LIFO) geplant sind, durch den virtuellen Prozessor, der Blockierung aufgehoben hat.|  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h hinzu  
 
##  <a name="switchingproxystate"></a>  SwitchingProxyState-Enumeration  
 Wird verwendet, um den Zustand zu bezeichnen, in dem sich ein Threadproxy befindet, wenn er einen kooperativen Kontextwechsel zu einem anderen Threadproxy ausführt.  
  
```
enum SwitchingProxyState;
```  
### <a name="values"></a>Werte  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`Blocking`|Gibt an, dass der aufrufende Thread kooperativ blockiert und sollte ausschließlich im Besitz des Aufrufers erst danach erneut ausführen und andere Aktion ausgeführt.|  
|`Idle`|Gibt an, dass der aufrufende Thread nicht mehr werden vom Zeitplanungsmodul benötigt und zum Ressourcen-Manager zurückgegeben wird. Der Kontext, der weitergeleitet wurde ist nicht mehr vom Ressourcen-Manager genutzt werden können.|  
|`Nesting`|Gibt an, dass der aufrufende Thread einen untergeordneten Planer schachteln ist und das Anfügen an einen anderen Planer vom Aufrufer erforderlich ist.|  

### <a name="remarks"></a>Hinweise  
 Einen Parameter vom Typ `SwitchingProxyState` an die Methode übergeben `IThreadProxy::SwitchTo` der Ressourcen-Manager angewiesen, wie den Threadproxy behandelt werden sollen, die den Aufruf ausgeführt hat.  
  
 Weitere Informationen zur Verwendung dieses Typs finden Sie unter [IThreadProxy:: SwitchTo](ithreadproxy-structure.md#switchto).  
  
##  <a name="task_group_status"></a>  Task_group_status-Enumeration  
 Beschreibt den Ausführungsstatus eines `task_group`-Objekts oder eines `structured_task_group`-Objekts. Ein Wert dieses Typs wird von zahlreichen Methoden zurückgegeben, die auf den Abschluss von Aufgaben warten, die für eine Aufgabengruppe geplant wurden.  
  
```
enum task_group_status;
```  
### <a name="values"></a>Werte  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`canceled`|Das `task_group`- oder `structured_task_group`-Objekt wurde abgebrochen. Eine oder mehrere Aufgaben wurden möglicherweise nicht ausgeführt.|  
|`completed`|Die für das `task_group`-Objekt oder das `structured_task_group`-Objekt in die Warteschlange gestellten Aufgaben wurden erfolgreich abgeschlossen.|  
|`not_complete`|Die für das `task_group`-Objekt in die Warteschlange gestellten Aufgaben wurden nicht abgeschlossen. Beachten Sie, dass dieser Wert gegenwärtig von der Concurrency Runtime nicht zurückgegeben wird.|  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** pplinterface.h  

##  <a name="winrtinitializationtype"></a>  WinRTInitializationType-Enumeration  
 Wird von der `WinRTInitialization`-Richtlinie verwendet, um zu beschreiben, ob und wie die Windows Runtime auf Planerthreads für eine Anwendung initialisiert wird, die auf Windows-Betriebssystemen ab Version 8 ausgeführt wird. Weitere Informationen über verfügbare Planerrichtlinien finden Sie unter [PolicyElementKey](concurrency-namespace-enums.md).  
  
```
enum WinRTInitializationType;
```  
### <a name="values"></a>Werte  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`DoNotInitializeWinRT`|Wenn die Anwendung auf Windows 8 oder neueren Betriebssystemen ausgeführt wird, initialisieren Threads innerhalb des Planers nicht Windows-Runtime.|  
|`InitializeWinRTAsMTA`|Wenn die Anwendung unter Windows 8 oder neueren Betriebssystemen ausgeführt wird, initialisiert jeder Thread innerhalb des Planers Windows-Runtime und deklariert, dass er Teil des Multithread-Apartments ist.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h hinzu  

## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)
