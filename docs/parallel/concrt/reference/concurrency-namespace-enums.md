---
title: Concurrency-Namespace-Enumerationen | Microsoft-Dokumentation
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
ms.openlocfilehash: 69b11a78d1be76895b9687d1423df74c51fe3d39
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46416694"
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
|`agent_done`|Die `agent` wurde ohne Abbruch abgeschlossen.|
|`agent_runnable`|Die `agent` gestartet wurde, jedoch nicht eingegeben seine `run` Methode.|
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
|`AGENTS_EVENT_END`|Verarbeitet ein Ereignistyp, der den Abschluss des einige darstellt.|
|`AGENTS_EVENT_LINK`|Ein Ereignistyp, der darstellt, das Verknüpfen von Nachrichtenblöcken|
|`AGENTS_EVENT_NAME`|Ein Ereignistyp, der den Namen für ein Objekt darstellt.|
|`AGENTS_EVENT_SCHEDULE`|Ein Ereignistyp, der darstellt, die Planung eines Prozesses|
|`AGENTS_EVENT_START`|Verarbeitet ein Ereignistyp, der die Initiierung einiger darstellt.|
|`AGENTS_EVENT_UNLINK`|Ein Ereignistyp, der darstellt, die Aufhebung der Zuordnung von Nachrichtenblöcken|

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
|`CONCRT_EVENT_BLOCK`|Ein Ereignistyp, der den Vorgang blockieren eines Kontexts darstellt.|
|`CONCRT_EVENT_DETACH`|Ein Ereignistyp, der der Vorgang, einen durch das Trennen von einem Planer darstellt.|
|`CONCRT_EVENT_END`|Ein Ereignistyp, der den Anfang ein Start/Ende Ereignispaar markiert.|
|`CONCRT_EVENT_GENERIC`|Ein Ereignistyp, der für verschiedene Ereignisse verwendet wird.|
|`CONCRT_EVENT_IDLE`|Ein Ereignistyp, der das Act eines Kontexts Leerlauf wechseln darstellt.|
|`CONCRT_EVENT_START`|Ein Ereignistyp, der den Anfang ein Start/Ende Ereignispaar markiert.|
|`CONCRT_EVENT_UNBLOCK`|Ein Ereignistyp, der der Vorgang zum Aufheben der Blockierung eines Kontexts darstellt.|
|`CONCRT_EVENT_YIELD`|Ein Ereignistyp, der der Vorgang, eine Rückgabe des Kontexts darstellt.|

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
|`InsideCriticalRegion`|Gibt an, dass der Kontext in einem kritischen Bereich ist. Wenn in einem kritischen Bereich, werden asynchrone Unterbrechungen vom Planer ausgeblendet. So eine Unterbrechung auftreten sollte, der Ressourcen-Manager gewartet wird, bis der Thread ausführbar werden und setzt ihn einfach fort, statt den Planer erneut aufzurufen. Alle sperren, die in so einem Bereich müssen mit äußerster Sorgfalt ausgeführt werden.|
|`InsideHyperCriticalRegion`|Gibt an, dass der Kontext in einem hyper-kritischen Bereich ist. Innerhalb einer Region äußerst wichtigen werden synchrone und asynchrone Unterbrechungen vom Planer ausgeblendet. Sollten Sie so eine Unterbrechung oder Blockierung auftritt, der Ressourcen-Manager gewartet wird, bis der Thread ausführbar werden und setzt ihn einfach fort, statt den Planer erneut aufzurufen. In so einem Bereich Sperren müssen Code, die außerhalb von solchen Bereichs ausgeführt wird nie freigegeben werden. Auf diese Weise wird zu einem unvorhersehbaren Deadlock.|
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
|`ProgressFeedbackDisabled`|Der Scheduler wird nicht von Statusinformationen sammeln. Neuverteilen von basiert ausschließlich auf Abonnementebene des zugrunde liegenden Hardwarethreads erfolgt. Weitere Informationen zu den Abonnementstufen, finden Sie unter [IExecutionResource:: CurrentSubscriptionLevel](IExecutionResource-structure.md).<br /><br /> Dieser Wert ist für die Verwendung von der Laufzeit reserviert.|
|`ProgressFeedbackEnabled`|Der Planer sammelt Informationen und übergibt sie an dem Ressourcen-Manager. Der Ressourcen-Manager wird diese statistischen Informationen zum Ausgleichen von Ressourcen im Auftrag der Planer zusätzlich die Abonnementstufe des zugrunde liegenden Hardwarethreads zu verwenden. Weitere Informationen zu den Abonnementstufen, finden Sie unter [IExecutionResource:: CurrentSubscriptionLevel](IExecutionResource-structure.md).|
##  <a name="join_type"></a>  Join_type-Enumeration

Der Typ eines `join`-Meldungsblocks.

```
enum join_type;
```
### <a name="values"></a>Werte

|Name|Beschreibung|
|----------|-----------------|
|`greedy`|Gierige `join` Meldungsblöcken sofort nach der Weitergabe eine Meldung empfangen. Dies ist effizienter, aber es hat die Möglichkeit für live-Sperre, abhängig von der Netzwerkkonfiguration.|
|`non_greedy`|Nicht gieriger `join` Meldungsblöcken Verschieben von Nachrichten, und versuchen Sie es, und nutzen müssen, nachdem alle angekommen sind. Diese sind garantiert funktioniert, aber langsamer.|

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
|`accepted`|Das Ziel akzeptiert die Meldung hat.|
|`declined`|Das Ziel hat die Nachricht nicht angenommen.|
|`missed`|Das Ziel versucht hat, um die Nachricht zu akzeptieren, aber es war nicht mehr verfügbar.|
|`postponed`|Das Ziel zurückgestellt die Meldung.|

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
|`ContextPriority`|Die Threadpriorität des Betriebssystems der einzelnen Kontexte im Planer. Wenn dieser Schlüssel, auf den Wert festgelegt ist `INHERIT_THREAD_PRIORITY` die Kontexte im Planer erben die Priorität des Threads, der den Planer erstellt hat.<br /><br /> Gültige Werte: einer der gültigen Werte für die Windows `SetThreadPriority` -Funktion und der spezielle Wert `INHERIT_THREAD_PRIORITY`<br /><br /> Standardwert: `THREAD_PRIORITY_NORMAL`|
|`ContextStackSize`|Die reservierte Stapelgröße jeden Kontext in den Scheduler in Kilobyte.<br /><br /> Gültige Werte: Positive ganze Zahlen<br /><br /> Standardwert: `0`, gibt an, dass der Standardwert des Prozesses, für die Stapelgröße verwendet werden.|
|`DynamicProgressFeedback`|Bestimmt, ob die Ressourcen für den Planer anhand statistischer Informationen gesammelt, die vom Planer oder nur basierend auf der Abonnementebene der zugrunde liegenden Hardwarethreads neu verteilt werden. Weitere Informationen finden Sie unter [DynamicProgressFeedbackType](#dynamicprogressfeedbacktype).<br /><br /> Gültige Werte: ein Mitglied der `DynamicProgressFeedbackType` Enumeration, entweder `ProgressFeedbackEnabled` oder `ProgressFeedbackDisabled`<br /><br /> Standardwert: `ProgressFeedbackEnabled`|
|`LocalContextCacheSize`|Wenn die `SchedulingProtocol` Richtlinienschlüssel festgelegt ist, auf den Wert `EnhanceScheduleGroupLocality`, gibt die maximale Anzahl von ausführbaren Kontexten zulässig pro virtueller Prozessor lokale Warteschlangen im zwischengespeichert werden. Solche Kontexte werden in der Regel nacheinander Last-in-First-Out (LIFO) für den virtuellen Prozessor ausgeführt werden, die sie ausführbar wird verursacht hat. Beachten Sie, dass dieser Schlüssel hat keine Bedeutung bei der `SchedulingProtocol` Schlüssel festgelegt ist, auf den Wert `EnhanceForwardProgress`.<br /><br /> Gültige Werte: positive ganze Zahlen<br /><br /> Standardwert: `8`|
|`MaxConcurrency`|Die vom Scheduler gewünschte maximale Parallelitätsebene. Der Ressourcen-Manager versucht, die anfänglich so viele virtuelle Prozessoren zugeordnet. Der spezielle Wert [MaxExecutionResources](concurrency-namespace-constants1.md#maxexecutionresources) gibt an, dass die gewünschte Parallelitätsebene die Anzahl der Hardwarethreads auf dem Computer identisch ist. Wenn der Wert für die angegebene `MinConcurrency` ist größer als die Anzahl der Hardwarethreads auf dem Computer und `MaxConcurrency` angegeben ist, als `MaxExecutionResources`, den Wert für `MaxConcurrency` wird ausgelöst, um übereinstimmen, was für festgelegt ist `MinConcurrency`.<br /><br /> Gültige Werte: Positive ganze Zahlen und der spezielle Wert `MaxExecutionResources`<br /><br /> Standardwert: `MaxExecutionResources`|
|`MaxPolicyElementKey`|Der maximale Elementschlüssel. Ein gültiges Element-Schlüssel.|
|`MinConcurrency`|Die minimale Parallelitätsebene, die auf dem Planer vom Ressourcen-Manager bereitgestellt werden muss. Die Anzahl der virtuellen Prozessoren zugewiesen, der einem Planer geht nie unter den Mindestwert. Der spezielle Wert [MaxExecutionResources](concurrency-namespace-constants1.md#maxexecutionresources) gibt an, dass die minimale Parallelitätsebene die Anzahl der Hardwarethreads auf dem Computer identisch ist. Wenn der Wert für die angegebene `MaxConcurrency` ist kleiner als die Anzahl der Hardwarethreads auf dem Computer und `MinConcurrency` angegeben ist, als `MaxExecutionResources`, den Wert für `MinConcurrency` sinken übereinstimmen, was für festgelegt ist `MaxConcurrency`.<br /><br /> Gültige Werte: positive ganze Zahlen und den Sonderwert `MaxExecutionResources`. Beachten Sie, dass für Scheduler-Richtlinien für die Erstellung der Concurrency Runtime-Planer, der Wert verwendet `0` ist ungültig.<br /><br /> Standardwert: `1`|
|`SchedulerKind`|Der Typ des Threads, die der Planer für zugrunde liegende Ausführungskontexte verwenden wird. Weitere Informationen finden Sie unter [SchedulerType](#schedulertype).<br /><br /> Gültige Werte: ein Mitglied der `SchedulerType` Enumeration, z. B. `ThreadScheduler`<br /><br /> Standardwert: `ThreadScheduler`. Dies führt zu Win32-Threads auf allen Betriebssystemen.|
|`SchedulingProtocol`|Beschreibt, welcher Planungsalgorithmus vom Planer verwendet wird. Weitere Informationen finden Sie unter [SchedulingProtocolType](#schedulingprotocoltype).<br /><br /> Gültige Werte: ein Mitglied der `SchedulingProtocolType` Enumeration, entweder `EnhanceScheduleGroupLocality` oder `EnhanceForwardProgress`<br /><br /> Standardwert: `EnhanceScheduleGroupLocality`|
|`TargetOversubscriptionFactor`|Vorläufige Anzahl virtueller Prozessoren pro Hardwarethread. Der Faktor für die Überzeichnung Ziel kann der Ressourcen-Manager, falls erforderlich, um zu erfüllen erhöht werden `MaxConcurrency` mit den Hardwarethreads auf dem Computer.<br /><br /> Gültige Werte: Positive ganze Zahlen<br /><br /> Standardwert: `1`|
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
|`EnhanceForwardProgress`|Der Planer, die nach dem Ausführen der einzelnen Aufgaben Roundrobin über Planungsgruppen bevorzugt werden. Entsperrt Kontexte werden in der Regel in einer Weise der First-in-First-Out (FIFO) geplant. Virtuelle Prozessoren Zwischenspeichern entsperrt Kontexten nicht.|
|`EnhanceScheduleGroupLocality`|Der Planer bevorzugt funktionieren weiterhin für Aufgaben in der aktuellen Planungsgruppe vor dem Wechsel zu einer anderen Planungsgruppe. Entsperrt Kontexte pro virtueller Prozessor zwischengespeichert werden und in der Regel in einer Weise der Last-in-First-Out (LIFO) geplant sind, durch den virtuellen Prozessor, der Blockierung aufgehoben hat.|

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
|`Blocking`|Gibt an, dass der aufrufende Thread kooperativ blockiert und werden ausschließlich des Aufrufers Besitz sollten erst anschließend erneut ausführen und andere Aktionen durchführt.|
|`Idle`|Gibt an, dass der aufrufende Thread vom Planer nicht mehr benötigt wird und an den Resource Manager zurückgegeben wird ist. Der Kontext der weitergeleitet wurde, ist nicht mehr vom Ressourcen-Manager verwendet werden können.|
|`Nesting`|Gibt an, dass der aufrufende Thread einen untergeordnetes Planer schachteln ist und durch den Aufrufer benötigt wird, um das Anfügen an einen anderen Planer.|

### <a name="remarks"></a>Hinweise

Einen Parameter vom Typ `SwitchingProxyState` an die Methode übergeben `IThreadProxy::SwitchTo` der Ressourcen-Manager anweisen, wie Sie den Threadproxy zu behandeln, die den Aufruf ausgeführt hat.

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
