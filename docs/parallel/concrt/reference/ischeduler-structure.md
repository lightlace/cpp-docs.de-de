---
title: IScheduler-Struktur
ms.date: 11/04/2016
f1_keywords:
- IScheduler
- CONCRTRM/concurrency::IScheduler
- CONCRTRM/concurrency::IScheduler::IScheduler::AddVirtualProcessors
- CONCRTRM/concurrency::IScheduler::IScheduler::GetId
- CONCRTRM/concurrency::IScheduler::IScheduler::GetPolicy
- CONCRTRM/concurrency::IScheduler::IScheduler::NotifyResourcesExternallyBusy
- CONCRTRM/concurrency::IScheduler::IScheduler::NotifyResourcesExternallyIdle
- CONCRTRM/concurrency::IScheduler::IScheduler::RemoveVirtualProcessors
- CONCRTRM/concurrency::IScheduler::IScheduler::Statistics
helpviewer_keywords:
- IScheduler structure
ms.assetid: 471de85a-2b1a-4b6d-ab81-2eff2737161e
ms.openlocfilehash: dd280884ab106bcf878b06c94e2ea3d0d99be2e8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50603215"
---
# <a name="ischeduler-structure"></a>IScheduler-Struktur

Eine Schnittstelle zu der Abstraktion eines Arbeitsplaners. Der Ressourcen-Manager der Concurrency Runtime kommuniziert mithilfe dieser Schnittstelle mit Arbeitsplanern.

## <a name="syntax"></a>Syntax

```
struct IScheduler;
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[IScheduler:: AddVirtualProcessors](#addvirtualprocessors)|Stellt einen Zeitplan mit einem Satz der Stämme virtueller Prozessoren für die Verwendung bereit. Jede `IVirtualProcessorRoot` Schnittstelle darstellt, das Recht, einen einzelnen Thread auszuführen, die Aufgaben für den Scheduler ausführen können.|
|[IScheduler::GetId](#getid)|Gibt einen eindeutigen Bezeichner für den Planer zurück.|
|[IScheduler:: GetPolicy](#getpolicy)|Gibt eine Kopie des Planers-Richtlinie. Weitere Informationen zu Planerrichtlinien, finden Sie unter [SchedulerPolicy](schedulerpolicy-class.md).|
|[IScheduler:: NotifyResourcesExternallyBusy](#notifyresourcesexternallybusy)|Benachrichtigt diesen Planer, der die Hardwarethreads durch die Menge der Stämme virtueller Prozessoren im Array dargestellt `ppVirtualProcessorRoots` jetzt von anderen Planern verwendet werden.|
|[IScheduler:: NotifyResourcesExternallyIdle](#notifyresourcesexternallyidle)|Benachrichtigt diesen Planer, der die Hardwarethreads durch die Menge der Stämme virtueller Prozessoren im Array dargestellt `ppVirtualProcessorRoots` werden nicht von anderen Planern verwendet wird.|
|[IScheduler::RemoveVirtualProcessors](#removevirtualprocessors)|Initiiert die Entfernung der Stämme virtueller Prozessoren, die zuvor auf diesem Planer zugeordnet wurden.|
|[IScheduler:: STATISTICS](#statistics)|Enthält Informationen, die im Zusammenhang mit der Aufgabe Eingang und Abschluss von Sätzen, und ändern Sie in der Länge der Warteschlange für einen Planer.|

## <a name="remarks"></a>Hinweise

Wenn Sie einen benutzerdefinierten Planer, die mit dem Ressourcen-Manager zu kommunizieren implementieren, sollten Sie eine Implementierung bereitstellen der `IScheduler` Schnittstelle. Diese Schnittstelle ist ein Ende einer bidirektionalen Kanal für die Kommunikation zwischen einem Planer und der Ressourcen-Manager. Das andere Ende wird dargestellt, durch die `IResourceManager` und `ISchedulerProxy` Schnittstellen, die vom Ressourcen-Manager implementiert werden.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`IScheduler`

## <a name="requirements"></a>Anforderungen

**Header:** concrtrm.h

**Namespace:** Parallelität

##  <a name="addvirtualprocessors"></a>  IScheduler:: AddVirtualProcessors-Methode

Stellt einen Zeitplan mit einem Satz der Stämme virtueller Prozessoren für die Verwendung bereit. Jede `IVirtualProcessorRoot` Schnittstelle darstellt, das Recht, einen einzelnen Thread auszuführen, die Aufgaben für den Scheduler ausführen können.

```
virtual void AddVirtualProcessors(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```

### <a name="parameters"></a>Parameter

*ppVirtualProcessorRoots*<br/>
Ein Array von `IVirtualProcessorRoot` Stammelemente Schnittstellen, die den virtuellen Prozessor darstellt, an den Scheduler hinzugefügt wird.

*count*<br/>
Die Anzahl der `IVirtualProcessorRoot` Schnittstellen im Array.

### <a name="remarks"></a>Hinweise

Die Ressourcen-Manager ruft die `AddVirtualProcessor` Methode, um einen anfänglichen Satz der Stämme virtueller Prozessoren, der einem Planer zu erteilen. Es könnte auch die Methode, um Stämme virtueller Prozessoren an den Scheduler hinzufügen, wenn sie Ressourcen für Planer lastausgleichsvorgang aufrufen.

##  <a name="getid"></a>  IScheduler:: GetID-Methode

Gibt einen eindeutigen Bezeichner für den Planer zurück.

```
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>Rückgabewert

Eine eindeutige ganzzahlige Bezeichner.

### <a name="remarks"></a>Hinweise

Verwenden Sie die [GetSchedulerId](concurrency-namespace-functions.md) Funktion einen eindeutigen Bezeichner für das Objekt abgerufen wird, implementiert die `IScheduler` Schnittstelle, die vor der Verwendung der Schnittstelle als Parameter für Methoden angegeben, der Ressourcen-Manager. Es wird erwartet, die den gleichen Bezeichner zurückzugeben bei der `GetId` Funktion wird aufgerufen.

Ein Bezeichner, die aus einer anderen Quelle erhalten könnte zu nicht definiertem Verhalten führen.

##  <a name="getpolicy"></a>  IScheduler:: GetPolicy-Methode

Gibt eine Kopie des Planers-Richtlinie. Weitere Informationen zu Planerrichtlinien, finden Sie unter [SchedulerPolicy](schedulerpolicy-class.md).

```
virtual SchedulerPolicy GetPolicy() const = 0;
```

### <a name="return-value"></a>Rückgabewert

Eine Kopie des Planers-Richtlinie.

##  <a name="notifyresourcesexternallybusy"></a>  IScheduler:: NotifyResourcesExternallyBusy-Methode

Benachrichtigt diesen Planer, der die Hardwarethreads durch die Menge der Stämme virtueller Prozessoren im Array dargestellt `ppVirtualProcessorRoots` jetzt von anderen Planern verwendet werden.

```
virtual void NotifyResourcesExternallyBusy(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```

### <a name="parameters"></a>Parameter

*ppVirtualProcessorRoots*<br/>
Ein Array von `IVirtualProcessorRoot` Schnittstellen, die auf dem anderen Planer ausgelastet Hardwarethreads zugeordnet.

*count*<br/>
Die Anzahl der `IVirtualProcessorRoot` Schnittstellen im Array.

### <a name="remarks"></a>Hinweise

Es ist möglich, für einen bestimmten Hardware-Thread, mehrere Zeitpläne, die zur selben Zeit zugewiesen werden soll. Ein Grund hierfür ist möglicherweise, dass nicht genügend Hardwarethreads auf dem System, um die minimale Parallelität für alle Zeitplanungsmodule zu erfüllen, ohne die gemeinsame Nutzung von Ressourcen vorhanden sind. Eine andere Möglichkeit ist, dass Ressourcen vorübergehend auf andere Planer zugeordnet sind, wenn der besitzende Planer, nicht über die virtuelle Prozessorstämme auf diesem Hardwarethread deaktiviert verwendet wird.

Die Abonnementstufe des einen Hardwarethread ist gekennzeichnet durch die Anzahl der abonnierten Threads und aktiviert Stämme virtueller Prozessoren, die diese Hardwarethread zugeordnet. Aus Sicht eines bestimmten Planers ist die externe Abonnementstufe des einen Hardwarethread den Teil des Abonnements, die, dem andere Planer beitragen. Benachrichtigungen, dass Ressourcen extern ausgelastet sind an einen Planer gesendet, wenn externe Abonnementebene für einen Hardwarethread von 0 (null), in das positive Gebiet verschoben wird.

Benachrichtigungen über diese Methode nur an Zeitplanungsmodule, die eine Richtlinie gesendet werden, in denen der Wert für die `MinConcurrency` Richtlinienschlüssel ist gleich dem Wert für die `MaxConcurrency` Richtlinienschlüssel. Weitere Informationen zu Planerrichtlinien, finden Sie unter [SchedulerPolicy](schedulerpolicy-class.md).

Ein Planer, der für Benachrichtigungen ist qualifiziert, ruft einen Satz der ersten Benachrichtigungen bei der Erstellung, informiert sie, ob die Ressourcen, die sie gerade zugewiesen wurde extern ausgelastet oder im Leerlauf sind.

##  <a name="notifyresourcesexternallyidle"></a>  IScheduler:: NotifyResourcesExternallyIdle-Methode

Benachrichtigt diesen Planer, der die Hardwarethreads durch die Menge der Stämme virtueller Prozessoren im Array dargestellt `ppVirtualProcessorRoots` werden nicht von anderen Planern verwendet wird.

```
virtual void NotifyResourcesExternallyIdle(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```

### <a name="parameters"></a>Parameter

*ppVirtualProcessorRoots*<br/>
Ein Array von `IVirtualProcessorRoot` Schnittstellen Hardwarethreads auf dem anderen Planer im Leerlauf zugeordnet.

*count*<br/>
Die Anzahl der `IVirtualProcessorRoot` Schnittstellen im Array.

### <a name="remarks"></a>Hinweise

Es ist möglich, für einen bestimmten Hardware-Thread, mehrere Zeitpläne, die zur selben Zeit zugewiesen werden soll. Ein Grund hierfür ist möglicherweise, dass nicht genügend Hardwarethreads auf dem System, um die minimale Parallelität für alle Zeitplanungsmodule zu erfüllen, ohne die gemeinsame Nutzung von Ressourcen vorhanden sind. Eine andere Möglichkeit ist, dass Ressourcen vorübergehend auf andere Planer zugeordnet sind, wenn der besitzende Planer, nicht über die virtuelle Prozessorstämme auf diesem Hardwarethread deaktiviert verwendet wird.

Die Abonnementstufe des einen Hardwarethread ist gekennzeichnet durch die Anzahl der abonnierten Threads und aktiviert Stämme virtueller Prozessoren, die diese Hardwarethread zugeordnet. Aus Sicht eines bestimmten Planers ist die externe Abonnementstufe des einen Hardwarethread den Teil des Abonnements, die, dem andere Planer beitragen. Benachrichtigungen, dass Ressourcen extern ausgelastet sind an einen Planer gesendet, wenn die externe Abonnementebene für einen Hardwarethread auf 0 (null), von einer vorherigen positive Wert fällt.

Benachrichtigungen über diese Methode nur an Zeitplanungsmodule, die eine Richtlinie gesendet werden, in denen der Wert für die `MinConcurrency` Richtlinienschlüssel ist gleich dem Wert für die `MaxConcurrency` Richtlinienschlüssel. Weitere Informationen zu Planerrichtlinien, finden Sie unter [SchedulerPolicy](schedulerpolicy-class.md).

Ein Planer, der für Benachrichtigungen ist qualifiziert, ruft einen Satz der ersten Benachrichtigungen bei der Erstellung, informiert sie, ob die Ressourcen, die sie gerade zugewiesen wurde extern ausgelastet oder im Leerlauf sind.

##  <a name="removevirtualprocessors"></a>  IScheduler:: RemoveVirtualProcessors-Methode

Initiiert die Entfernung der Stämme virtueller Prozessoren, die zuvor auf diesem Planer zugeordnet wurden.

```
virtual void RemoveVirtualProcessors(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```

### <a name="parameters"></a>Parameter

*ppVirtualProcessorRoots*<br/>
Ein Array von `IVirtualProcessorRoot` Schnittstellen, die der Stämme virtueller Prozessoren zu entfernenden darstellen.

*count*<br/>
Die Anzahl der `IVirtualProcessorRoot` Schnittstellen im Array.

### <a name="remarks"></a>Hinweise

Die Ressourcen-Manager ruft die `RemoveVirtualProcessors` Methode, um einen Anfangssatz der Stämme virtueller Prozessoren von einem Planer zu entfernen. Der Scheduler wird erwartet, zum Aufrufen der [entfernen](iexecutionresource-structure.md#remove) Methode für jede Schnittstelle, wenn sie die virtuelle Prozessorstämme mehr benötigt wird. Verwenden Sie keine `IVirtualProcessorRoot` Schnittstelle, wenn Sie aufgerufen haben die `Remove` Methode auf.

Der Parameter `ppVirtualProcessorRoots` verweist auf ein Array von Schnittstellen. In der Gruppe der Stämme virtueller Prozessoren, die entfernt werden, nie die Stämme aktiviert wurden zurückgegeben werden kann, mithilfe der `Remove` Methode. Die Stammelemente, die aktiviert wurden und entweder Arbeit ausführen, oder wurden deaktiviert und die Arbeit auf den Empfang warten, die asynchron zurückgegeben werden soll. Der Scheduler muss jeder Versuch, den virtuellen Prozessorstamm so schnell wie möglich zu entfernen. Entfernen der Stämme virtueller Prozessoren verzögern kann dazu führen, dass unbeabsichtigte Überzeichnung innerhalb des Planers.

##  <a name="statistics"></a>  IScheduler:: Statistics-Methode

Enthält Informationen, die im Zusammenhang mit der Aufgabe Eingang und Abschluss von Sätzen, und ändern Sie in der Länge der Warteschlange für einen Planer.

```
virtual void Statistics(
    _Out_ unsigned int* pTaskCompletionRate,
    _Out_ unsigned int* pTaskArrivalRate,
    _Out_ unsigned int* pNumberOfTasksEnqueued) = 0;
```

### <a name="parameters"></a>Parameter

*pTaskCompletionRate*<br/>
Die Anzahl der Aufgaben, die vom Scheduler seit dem letzten Aufruf dieser Methode abgeschlossen wurden.

*pTaskArrivalRate*<br/>
Die Anzahl der Aufgaben, die seit dem letzten Aufruf dieser Methode im Scheduler angekommen sind.

*pNumberOfTasksEnqueued*<br/>
Die Gesamtanzahl von Aufgaben in allen Scheduler-Warteschlangen.

### <a name="remarks"></a>Hinweise

Diese Methode wird vom Ressourcen-Manager aufgerufen, um Statistiken für einen Planer zu sammeln. Die Statistiken, die hier gesammelt dienen zum Steuern des dynamischen Feedback-Algorithmen, um zu bestimmen, wenn der Planer mehr Ressourcen zuweisen geeignet ist und wann Ressourcen entfernt werden sollen. Die vom Scheduler bereitgestellten Werte dürfen optimistische und ist nicht unbedingt die aktuelle Anzahl korrekt widerspiegelt.

Sie sollten diese Methode implementieren, wenn der Ressourcen-Manager als Aufgabe Eingang Feedback über solche Dinge zu verwenden, um zu bestimmen, wie Sie ausgleichen von Ressourcen zwischen dem Planer und andere Planer mit dem Ressourcen-Manager registriert werden sollen. Wenn Sie keine Statistiken zu sammeln möchten, können Sie festlegen, dass den Richtlinienschlüssel `DynamicProgressFeedback` auf den Wert `DynamicProgressFeedbackDisabled` des Planers Richtlinie und die Ressource-Manager nicht ruft diese Methode wurde für den Planer.

In statistische Informationen vorhanden ist Verwenden der Ressourcen-Manager-Thread-Abonnementstufen Hardware Ressource Zuordnung und Migration Entscheidungen zu treffen. Weitere Informationen zu den Abonnementstufen, finden Sie unter [IExecutionResource:: CurrentSubscriptionLevel](iexecutionresource-structure.md#currentsubscriptionlevel).

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[PolicyElementKey](concurrency-namespace-enums.md)<br/>
[SchedulerPolicy-Klasse](schedulerpolicy-class.md)<br/>
[IExecutionContext-Struktur](iexecutioncontext-structure.md)<br/>
[IThreadProxy-Struktur](ithreadproxy-structure.md)<br/>
[IVirtualProcessorRoot-Struktur](ivirtualprocessorroot-structure.md)<br/>
[IResourceManager-Struktur](iresourcemanager-structure.md)
