---
title: Concurrency-Namespace Enumerationen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a40e3b2d-ad21-4229-9880-2cfa84f7ab8f
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 8f7488ff07c9789e2d5f35056de390a5bc464f56
ms.openlocfilehash: ff187e827b2dd979466b746eee297235e6a6c0ca
ms.lasthandoff: 02/24/2017

---
# <a name="concurrency-namespace-enums"></a>Concurrency-Namespace-Enumerationen
||||  
|-|-|-|  
|[Agents_EventType-Enumeration](#agents_eventtype)|[ConcRT_EventType-Enumeration](#concrt_eventtype)|[Concrt_TraceFlags-Enumeration](#concrt_traceflags)|  
|[CriticalRegionType-Enumeration](#criticalregiontype)|[DynamicProgressFeedbackType-Enumeration](#dynamicprogressfeedbacktype)|[PolicyElementKey-Enumeration](#policyelementkey)|  
|[SchedulerType-Enumeration](#schedulertype)|[SchedulingProtocolType-Enumeration](#schedulingprotocoltype)|[SwitchingProxyState-Enumeration](#switchingproxystate)|  
|[WinRTInitializationType-Enumeration](#winrtinitializationtype)|[Agent_status-Enumeration](#agent_status)|[Join_type-Enumeration](#join_type)|  
|[Message_status-Enumeration](#message_status)|[Task_group_status-Enumeration](#task_group_status)|  
  
##  <a name="a-nameagentstatusa--agentstatus-enumeration"></a><a name="agent_status"></a>Agent_status-Enumeration  
 Die gültigen Zustände für einen `agent`.  
  
```
enum agent_status;
```  
### <a name="values"></a>Werte  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`agent_canceled`|Das `agent` wurde abgebrochen.|  
|`agent_created`|Die `agent` erstellt, jedoch nicht gestartet wurde.|  
|`agent_done`|Die `agent` ohne Abbruch beendet.|  
|`agent_runnable`|Die `agent` gestartet, aber nicht eingegeben wurde die `run` Methode.|  
|`agent_started`|Die `agent` wurde gestartet.|  

### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [asynchrone Agents](../../../parallel/concrt/asynchronous-agents.md).  

### <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h hinzu

##  <a name="a-nameagentseventtypea--agentseventtype-enumeration"></a><a name="agents_eventtype"></a>Agents_EventType-Enumeration  
 Die Typen von Ereignissen, die mit der von der Agents Library angebotenen Ablaufverfolgungsfunktionalität aufgezeichnet werden können  
  
```
enum Agents_EventType;
```  

### <a name="values"></a>Werte  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`AGENTS_EVENT_CREATE`|Ein Ereignistyp, der die Erstellung eines Objekts darstellt.|  
|`AGENTS_EVENT_DESTROY`|Ein Ereignistyp, der das Löschen eines Objekts darstellt.|  
|`AGENTS_EVENT_END`|Ein Ereignistyp, der den Abschluss der Verarbeitung|  
|`AGENTS_EVENT_LINK`|Ein Ereignistyp, der das Verknüpfen von Nachrichtenblöcken darstellt|  
|`AGENTS_EVENT_NAME`|Ein Ereignistyp, der den Namen für ein Objekt darstellt.|  
|`AGENTS_EVENT_SCHEDULE`|Ein Ereignistyp, der darstellt, die Planung eines Prozesses|  
|`AGENTS_EVENT_START`|Ein Ereignistyp, der die Initiierung von einigen darstellt verarbeiten|  
|`AGENTS_EVENT_UNLINK`|Ein Ereignistyp, der das Aufheben der Verknüpfung von Nachrichtenblöcken darstellt|  

### <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h hinzu

##  <a name="a-nameconcrteventtypea--concrteventtype-enumeration"></a><a name="concrt_eventtype"></a>ConcRT_EventType-Enumeration  
 Die Typen von Ereignissen, die mit der von der Concurrency Runtime angebotenen Ablaufverfolgungsfunktionalität aufgezeichnet werden können.  
  
```
enum ConcRT_EventType;
```  
### <a name="values"></a>Werte  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CONCRT_EVENT_ATTACH`|Ein Ereignistyp, der das Act, der das Anfügen an einen Planer darstellt.|  
|`CONCRT_EVENT_BLOCK`|Ein Ereignistyp, der Vorgang blockieren eines Kontexts darstellt.|  
|`CONCRT_EVENT_DETACH`|Ein Ereignistyp, der das Aufheben der Verknüpfung mit einen Planer darstellt.|  
|`CONCRT_EVENT_END`|Ein Ereignistyp, der den Beginn einer Start-/Endzeit Ereignispaar markiert.|  
|`CONCRT_EVENT_GENERIC`|Ein Ereignistyp, der für verschiedene Ereignisse verwendet wird.|  
|`CONCRT_EVENT_IDLE`|Ein Ereignistyp, der den Übergang eines Kontexts in Leerlauf darstellt.|  
|`CONCRT_EVENT_START`|Ein Ereignistyp, der den Beginn einer Start-/Endzeit Ereignispaar markiert.|  
|`CONCRT_EVENT_UNBLOCK`|Ein Ereignistyp, der das Aufheben der Blockierung eines Kontexts darstellt.|  
|`CONCRT_EVENT_YIELD`|Ein Ereignistyp, der das von einem Kontext Gewinnung darstellt.|  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h hinzu

##  <a name="a-nameconcrttraceflagsa--concrttraceflags-enumeration"></a><a name="concrt_traceflags"></a>Concrt_TraceFlags-Enumeration  
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

##  <a name="a-namecriticalregiontypea--criticalregiontype-enumeration"></a><a name="criticalregiontype"></a>CriticalRegionType-Enumeration  
 Der Typ eines kritischen Bereichs, in dem sich ein Kontext befindet.  
  
```
enum CriticalRegionType;
```  
### <a name="values"></a>Werte  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`InsideCriticalRegion`|Gibt an, dass der Kontext in einem wichtigen Bereich ist. Wenn in einem kritischen Bereich sind asynchrone Unterbrechungen vom Planer ausgeblendet. So eine Unterbrechung erfolgen sollte, der Ressourcen-Manager gewartet wird, bis der Thread ausführbar und setzt ihn einfach fort, statt den Planer erneut aufzurufen. Alle in so einem Bereich vorgenommenen Sperren müssen mit äußerster Sorgfalt durchgeführt werden.|  
|`InsideHyperCriticalRegion`|Gibt an, dass der Kontext in einem äußerst wichtigen Bereich ist. Synchrone und asynchrone Unterbrechungen werden in einem äußerst wichtigen Bereich vom Planer ausgeblendet. Falls so eine Unterbrechung oder Blockierung auftritt, der Ressourcen-Manager gewartet wird, bis der Thread ausführbar und setzt ihn einfach fort, statt den Planer erneut aufzurufen. In so einem Bereich vorgenommenen Sperren müssen niemals für Code, der außerhalb so eines Bereichs ausgeführt freigegeben werden. Auf diese Weise wird zu einem unvorhersehbaren Deadlock.|  
|`OutsideCriticalRegion`|Gibt an, dass der Kontext außerhalb eines wichtigen Bereichs ist.|  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** concrtrm.h 

##  <a name="a-namedynamicprogressfeedbacktypea--dynamicprogressfeedbacktype-enumeration"></a><a name="dynamicprogressfeedbacktype"></a>DynamicProgressFeedbackType-Enumeration  
 Wird von der `DynamicProgressFeedback`-Richtlinie verwendet, um zu beschreiben, ob Ressourcen für den Planer anhand statistischer Informationen neu verteilt werden, die vom Planer oder nur auf Grundlage virtueller Prozessoren erfasst wurden, die wegen der Aufrufe der `Activate`-Methode und der `Deactivate`-Methode für die `IVirtualProcessorRoot`-Schnittstelle in den und aus dem Leerlauf wechseln. Weitere Informationen über verfügbare Planerrichtlinien finden Sie unter [PolicyElementKey-Enumeration](concurrency-namespace-enums.md).  
  
```
enum DynamicProgressFeedbackType;
```  
### <a name="values"></a>Werte  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`ProgressFeedbackDisabled`|Der Planer ist keine Statusinformationen sammeln. Neuverteilen von ausschließlich auf Abonnementebene des zugrunde liegenden Hardwarethreads erfolgt basierend. Weitere Informationen zu Abonnementebenen finden Sie unter [IExecutionResource:: CurrentSubscriptionLevel](IExecutionResource-structure.md).<br /><br /> Dieser Wert ist für die Verwendung durch die Common Language Runtime reserviert.|  
|`ProgressFeedbackEnabled`|Der Planer erfasst Statusinformationen und übergibt sie an dem Ressourcen-Manager. Der Ressourcen-Manager nutzt diese statistischen Informationen, um Ressourcen im Auftrag des Planers zusätzlich zur Abonnementebene des zugrunde liegenden Hardwarethreads neu zu verteilen. Weitere Informationen zu Abonnementebenen finden Sie unter [IExecutionResource:: CurrentSubscriptionLevel](IExecutionResource-structure.md).|  
##  <a name="a-namejointypea--jointype-enumeration"></a><a name="join_type"></a>Join_type-Enumeration  
 Der Typ eines `join`-Meldungsblocks.  
  
```
enum join_type;
```  
### <a name="values"></a>Werte  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`greedy`|Gierige `join` Meldungsblöcken sofort nach der Weitergabe eine Meldung akzeptiert. Dies ist effizienter, aber hat die Möglichkeit für live-Sperre, abhängig von der Netzwerkkonfiguration.|  
|`non_greedy`|Nicht gierige `join` Meldungsblöcken Verschieben von Nachrichten und versuchen Sie es und nutzen Sie diese, nachdem alle angekommen sind. Diese sind garantiert funktioniert, aber langsamer.|  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** agents.h  

##  <a name="a-namemessagestatusa--messagestatus-enumeration"></a><a name="message_status"></a>Message_status-Enumeration  
 Die gültigen Antworten für das Angebot eines `message`-Objekts für einen Block.  
  
```
enum message_status;
```  
### <a name="values"></a>Werte  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`accepted`|Das Ziel hat die Meldung akzeptiert.|  
|`declined`|Das Ziel hat die Meldung nicht akzeptiert.|  
|`missed`|Das Ziel hat versucht, die Nachricht zu übernehmen, aber es war nicht mehr verfügbar.|  
|`postponed`|Das Ziel hat die Meldung aufgeschoben.|  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** agents.h  

##  <a name="a-namepolicyelementkeya--policyelementkey-enumeration"></a><a name="policyelementkey"></a>PolicyElementKey-Enumeration  
 Richtlinienschlüssel, die Aspekte des Planerverhaltens beschreiben. Jedes Richtlinienelement wird mit einem Schlüssel-Wert-Paar beschrieben. Weitere Informationen zu Planerrichtlinien und ihren Auswirkungen auf Planer finden Sie unter [Taskplaner](../../../parallel/concrt/task-scheduler-concurrency-runtime.md).  
  
```
enum PolicyElementKey;
```  
### <a name="values"></a>Werte  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`ContextPriority`|Die Betriebssystem-Threadpriorität der einzelnen Kontexte im Planer. Wenn dieser Schlüssel, auf den Wert festgelegt ist `INHERIT_THREAD_PRIORITY` erben die Kontexte im Planer die Priorität des Threads, der den Planer erstellt hat.<br /><br /> Gültige Werte: einer der gültigen Werte für den Windows- `SetThreadPriority` -Funktion und der besondere Wert`INHERIT_THREAD_PRIORITY`<br /><br /> Standardwert:`THREAD_PRIORITY_NORMAL`|  
|`ContextStackSize`|Die reservierte Stapelgröße jedes Kontexts im Planer in Kilobyte.<br /><br /> Gültige Werte: Positive ganze Zahlen<br /><br /> Standardwert: `0`, gibt an, dass der Standardwert für die Stapelgröße des Prozesses verwendet werden.|  
|`DynamicProgressFeedback`|Bestimmt, ob die Ressourcen für den Planer anhand statistischer Informationen gesammelt, die vom Planer oder nur auf Grundlage der Abonnementebene des zugrunde liegenden Hardwarethreads neu verteilt werden. Weitere Informationen finden Sie unter [DynamicProgressFeedbackType-Enumeration](#dynamicprogressfeedbacktype).<br /><br /> Gültige Werte: ein Mitglied der `DynamicProgressFeedbackType` Enumeration, entweder `ProgressFeedbackEnabled` oder`ProgressFeedbackDisabled`<br /><br /> Standardwert:`ProgressFeedbackEnabled`|  
|`LocalContextCacheSize`|Wenn die `SchedulingProtocol` Richtlinienschlüssel festgelegt ist, auf den Wert `EnhanceScheduleGroupLocality`, gibt die maximale Anzahl ausführbarer Kontexte pro virtueller Prozessor lokalen Warteschlangen im zwischengespeichert werden. Solche Kontexte werden in der Regel nacheinander Last in, First Out (LIFO) für den virtuellen Prozessor ausgeführt, die sie ausführbar geworden sind verursacht hat. Beachten Sie, dass dieser Richtlinienschlüssel keine Bedeutung bei der `SchedulingProtocol` Schlüsselsatz auf den Wert `EnhanceForwardProgress`.<br /><br /> Gültige Werte: positive ganze Zahlen<br /><br /> Standardwert:`8`|  
|`MaxConcurrency`|Die maximale vom Planer gewünschte Parallelitätsebene. Der Ressourcen-Manager versucht, diese vielen virtuelle Prozessoren anfänglich zuzuordnen. Der spezielle Wert [MaxExecutionResources](concurrency-namespace-constants1.md#maxexecutionresources) gibt an, dass die gewünschte Parallelitätsebene mit der Anzahl von Hardwarethreads auf dem Computer identisch ist. Wenn der Wert für angegeben `MinConcurrency` ist größer als die Anzahl der Hardwarethreads auf dem Computer und `MaxConcurrency` als angegeben `MaxExecutionResources`, den Wert der `MaxConcurrency` wird ausgelöst, um übereinstimmen, was für festgelegt ist `MinConcurrency`.<br /><br /> Gültige Werte: Positive ganze Zahlen und der besondere Wert`MaxExecutionResources`<br /><br /> Standardwert:`MaxExecutionResources`|  
|`MaxPolicyElementKey`|Der maximale Richtlinienelementschlüssel. Kein gültiger Elementschlüssel.|  
|`MinConcurrency`|Die minimale Parallelitätsebene, die auf dem Planer vom Ressourcen-Manager bereitgestellt werden muss. Die Anzahl virtueller Prozessoren, die einem Planer zugewiesen geht nie unter dem Mindestwert. Der spezielle Wert [MaxExecutionResources](concurrency-namespace-constants1.md#maxexecutionresources) gibt an, dass die minimale Parallelitätsebene mit der Anzahl von Hardwarethreads auf dem Computer identisch ist. Wenn der Wert für angegeben `MaxConcurrency` ist kleiner als die Anzahl der Hardwarethreads auf dem Computer und `MinConcurrency` angegeben ist, als `MaxExecutionResources`, den Wert der `MinConcurrency` wird verkleinert, was für festgelegt ist `MaxConcurrency`.<br /><br /> Gültige Werte: positive ganze Zahlen und der besondere Wert `MaxExecutionResources`. Beachten Sie, dass für Planerrichtlinien verwendet für die Erstellung der Concurrency Runtime-Planer, der Wert `0` ist ungültig.<br /><br /> Standardwert:`1`|  
|`SchedulerKind`|Der Typ der Threads, die der Planer für zugrunde liegende Ausführungskontexte verwenden wird. Weitere Informationen finden Sie unter [SchedulerType-Enumeration](#schedulertype).<br /><br /> Gültige Werte: ein Mitglied der `SchedulerType` -Enumeration, z. B.`ThreadScheduler`<br /><br /> Standardwert: `ThreadScheduler`. Dies führt zur Win32-Threads für alle Betriebssysteme.|  
|`SchedulingProtocol`|Beschreibt, welcher Planungsalgorithmus vom Planer verwendet wird. Weitere Informationen finden Sie unter [SchedulingProtocolType-Enumeration](#schedulingprotocoltype).<br /><br /> Gültige Werte: ein Mitglied der `SchedulingProtocolType` Enumeration, entweder `EnhanceScheduleGroupLocality` oder`EnhanceForwardProgress`<br /><br /> Standardwert:`EnhanceScheduleGroupLocality`|  
|`TargetOversubscriptionFactor`|Vorläufige Anzahl virtueller Prozessoren pro Hardwarethread. Der Zielüberzeichnungsfaktor erhöht werden kann der Ressourcen-Manager, bei Bedarf, um erfüllen `MaxConcurrency` mit den Hardwarethreads auf dem Computer.<br /><br /> Gültige Werte: Positive ganze Zahlen<br /><br /> Standardwert:`1`|  
|`WinRTInitialization`||  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h hinzu  

##  <a name="a-nameschedulertypea--schedulertype-enumeration"></a><a name="schedulertype"></a>SchedulerType-Enumeration  
 Wird von der `SchedulerKind`-Richtlinie verwendet, um den Typ der Threads zu beschreiben, die der Planer für zugrunde liegende Ausführungskontexte verwenden soll. Weitere Informationen über verfügbare Planerrichtlinien finden Sie unter [PolicyElementKey-Enumeration](concurrency-namespace-enums.md).  
  
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
  
##  <a name="a-nameschedulingprotocoltypea--schedulingprotocoltype-enumeration"></a><a name="schedulingprotocoltype"></a>SchedulingProtocolType-Enumeration  
 Wird von der `SchedulingProtocol`-Richtlinie verwendet, um zu beschreiben, welcher Planungsalgorithmus für den Planer verwendet wird. Weitere Informationen über verfügbare Planerrichtlinien finden Sie unter [PolicyElementKey-Enumeration](concurrency-namespace-enums.md).  
  
```
enum SchedulingProtocolType;
```  
### <a name="values"></a>Werte  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`EnhanceForwardProgress`|Der Planer bevorzugt Round-Robin-zwischen Planungsgruppen nach der Ausführung jeder Aufgabe. Entsperrt Kontexte sind in der Regel in einer First in, First Out (FIFO) Weise geplant. Virtuelle Prozessoren zwischengespeichert entsperrt Kontexten nicht.|  
|`EnhanceScheduleGroupLocality`|Der Planer bevorzugt weiterhin auf Vorgänge innerhalb der aktuellen Planungsgruppe bevor Sie zu einer anderen Planungsgruppe verschieben. Entsperrt Kontexte pro virtuellem Prozessor zwischengespeichert werden und in der Regel in einer Last in, First Out (LIFO) Weise geplant sind, durch den virtuellen Prozessor, der Blockierung aufgehoben hat.|  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h hinzu  
 
##  <a name="a-nameswitchingproxystatea--switchingproxystate-enumeration"></a><a name="switchingproxystate"></a>SwitchingProxyState-Enumeration  
 Wird verwendet, um den Zustand zu bezeichnen, in dem sich ein Threadproxy befindet, wenn er einen kooperativen Kontextwechsel zu einem anderen Threadproxy ausführt.  
  
```
enum SwitchingProxyState;
```  
### <a name="values"></a>Werte  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`Blocking`|Gibt an, dass der aufrufende Thread kooperativ blockiert und sollte ausschließlich im Besitz des Aufrufers erst später erneut ausführen und andere Aktionen durchführt.|  
|`Idle`|Gibt an, dass der aufrufende Thread nicht mehr vom Planer benötigt wird und der Ressourcen-Manager zurückgegeben wird. Der Kontext, der weitergeleitet wurde, ist nicht mehr vom Ressourcen-Manager genutzt werden können.|  
|`Nesting`|Gibt an, dass der aufrufende Thread einen untergeordneten Planer schachtelt und Anfügen an einen anderen Planer vom Aufrufer erforderlich ist.|  

### <a name="remarks"></a>Hinweise  
 Ein Parameter vom Typ `SwitchingProxyState` wird an die Methode übergebenen `IThreadProxy::SwitchTo` der Ressourcen-Manager anweisen, wie den Threadproxy behandelt, die den Aufruf ausgeführt hat.  
  
 Weitere Informationen zur Verwendung dieses Typs finden Sie unter [IThreadProxy:: SwitchTo](ithreadproxy-structure.md#switchto).  
  
##  <a name="a-nametaskgroupstatusa--taskgroupstatus-enumeration"></a><a name="task_group_status"></a>Task_group_status-Enumeration  
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

##  <a name="a-namewinrtinitializationtypea--winrtinitializationtype-enumeration"></a><a name="winrtinitializationtype"></a>WinRTInitializationType-Enumeration  
 Wird von der `WinRTInitialization`-Richtlinie verwendet, um zu beschreiben, ob und wie die Windows Runtime auf Planerthreads für eine Anwendung initialisiert wird, die auf Windows-Betriebssystemen ab Version 8 ausgeführt wird. Weitere Informationen über verfügbare Planerrichtlinien finden Sie unter [PolicyElementKey-Enumeration](concurrency-namespace-enums.md).  
  
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

