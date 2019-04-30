---
title: ISchedulerProxy-Struktur
ms.date: 11/04/2016
f1_keywords:
- ISchedulerProxy
- CONCRTRM/concurrency::ISchedulerProxy
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::BindContext
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::CreateOversubscriber
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::RequestInitialVirtualProcessors
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::Shutdown
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::SubscribeCurrentThread
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::UnbindContext
helpviewer_keywords:
- ISchedulerProxy structure
ms.assetid: af416973-7a1c-4c30-aa3b-4161c2aaea54
ms.openlocfilehash: 0dddd43a5b3e68992e41f0b95893303e57e7c7ff
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2019
ms.locfileid: "64346285"
---
# <a name="ischedulerproxy-structure"></a>ISchedulerProxy-Struktur

Die Schnittstelle, über die Planer mit dem Ressourcen-Manager der Concurrency Runtime kommunizieren, um die Ressourcenzuordnung auszuhandeln.

## <a name="syntax"></a>Syntax

```
struct ISchedulerProxy;
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[ISchedulerProxy::BindContext](#bindcontext)|Ordnet einen Ausführungskontext ein Threadproxy, wenn es nicht bereits einem zugeordnet ist.|
|[ISchedulerProxy::CreateOversubscriber](#createoversubscriber)|Erstellt einen neuen virtuellen Prozessorstamm im Hardware-Thread, der eine vorhandene Ausführungsressource zugeordnet.|
|[ISchedulerProxy::RequestInitialVirtualProcessors](#requestinitialvirtualprocessors)|Fordert eine anfängliche Zuordnung der Stämme virtueller Prozessoren an. Alle virtuellen Prozessorstamm versteht man die Möglichkeit, einen Thread auszuführen, die Arbeit für den Planer ausführen können.|
|[ISchedulerProxy::Shutdown](#shutdown)|Benachrichtigt den Ressourcen-Manager, dass der Planer beendet wird. Dies bewirkt, dass der Ressourcen-Manager alle Ressourcen, die an den Scheduler gewährt auch sofort manuell freigegeben.|
|[ISchedulerProxy::SubscribeCurrentThread](#subscribecurrentthread)|Registriert den aktuellen Thread mit der Resource Manager, es diesem Planer zugeordnet.|
|[ISchedulerProxy::UnbindContext](#unbindcontext)|Hebt die Zuordnung eines Threadproxys aus dem Ausführungskontext, der gemäß der `pContext` Parameter und gibt sie an den Thread des freien Pool-Factory zurück. Diese Methode kann nur auf einem Ausführungskontext, der über gebunden war aufgerufen werden die [BindContext](#bindcontext) Methode und noch nicht über wird gestartet wurde die `pContext` Parameter ein [IThreadProxy:: SwitchTo ](ithreadproxy-structure.md#switchto) Methodenaufruf.|

## <a name="remarks"></a>Hinweise

Der Ressourcen-Manager übergibt eine `ISchedulerProxy` Schnittstelle, um jedes Zeitplanungsmodul, das mit registriert die [IResourceManager:: RegisterScheduler](iresourcemanager-structure.md#registerscheduler) Methode.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`ISchedulerProxy`

## <a name="requirements"></a>Anforderungen

**Header:** concrtrm.h

**Namespace:** Parallelität

##  <a name="bindcontext"></a>  ISchedulerProxy:: BindContext-Methode

Ordnet einen Ausführungskontext ein Threadproxy, wenn es nicht bereits einem zugeordnet ist.

```
virtual void BindContext(_Inout_ IExecutionContext* pContext) = 0;
```

### <a name="parameters"></a>Parameter

*pContext*<br/>
Eine Schnittstelle zum Ausführungskontext, ein Threadproxy zugeordnet werden soll.

### <a name="remarks"></a>Hinweise

In der Regel die [IThreadProxy:: SwitchTo](ithreadproxy-structure.md#switchto) Methode bindet einen Threadproxy zu einem Ausführungskontext nach Bedarf. Es gibt jedoch Situationen es erforderlich ist, um einen Kontext im voraus, um sicherzustellen, dass binden die `SwitchTo` Methode wechselt zu einem bereits gebundenen Kontext. Dies ist der Fall für eine UMS Kontext planen, wie sie Methoden aufrufen kann, die Arbeitsspeicher zuweisen, und binden einen Threadproxy kann speicherbelegung umfassen, wenn ein Threadproxy im freien Pool der Threadproxy-Factory nicht sofort verfügbar ist.

`invalid_argument` wird ausgelöst, wenn der Parameter `pContext` hat den Wert `NULL`.

##  <a name="createoversubscriber"></a>  ISchedulerProxy:: CreateOversubscriber-Methode

Erstellt einen neuen virtuellen Prozessorstamm im Hardware-Thread, der eine vorhandene Ausführungsressource zugeordnet.

```
virtual IVirtualProcessorRoot* CreateOversubscriber(_Inout_ IExecutionResource* pExecutionResource) = 0;
```

### <a name="parameters"></a>Parameter

*pExecutionResource*<br/>
Ein `IExecutionResource` Schnittstelle, die die Hardwarethread darstellt, zu überzeichnen.

### <a name="return-value"></a>Rückgabewert

Eine `IVirtualProcessorRoot`-Schnittstelle.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode aus, wenn der Planer möchte, einen bestimmte Hardware-Thread für einen begrenzten Zeitraum zu überzeichnen. Nachdem Sie den virtuellen Prozessorstamm abgeschlossen haben, sollten Sie es an den Ressourcen-Manager zurückkehren, indem die [entfernen](iexecutionresource-structure.md#remove) Methode für die `IVirtualProcessorRoot` Schnittstelle.

Sie können auch einen vorhandenen virtuellen Prozessorstamm überzeichnen, da die `IVirtualProcessorRoot` Schnittstelle erbt von der `IExecutionResource` Schnittstelle.

##  <a name="requestinitialvirtualprocessors"></a>  ISchedulerProxy:: RequestInitialVirtualProcessors-Methode

Fordert eine anfängliche Zuordnung der Stämme virtueller Prozessoren an. Alle virtuellen Prozessorstamm versteht man die Möglichkeit, einen Thread auszuführen, die Arbeit für den Planer ausführen können.

```
virtual IExecutionResource* RequestInitialVirtualProcessors(bool doSubscribeCurrentThread) = 0;
```

### <a name="parameters"></a>Parameter

*doSubscribeCurrentThread*<br/>
Ob den aktuellen Thread abonnieren und bei der Ressourcenzuordnung für dieses Konto.

### <a name="return-value"></a>Rückgabewert

Die `IExecutionResource` Schnittstelle für den aktuellen Thread, wenn der Parameter `doSubscribeCurrentThread` hat den Wert **"true"**. Wenn der Wert ist **"false"**, die Methode gibt NULL zurück.

### <a name="remarks"></a>Hinweise

Bevor Sie ein Planer die Arbeit ausgeführt wird, sollten sie diese Methode verwenden, um Stämme virtueller Prozessoren aus Resource Manager anzufordern. Der Ressourcen-Manager greift auf die Richtlinie des Planers mit [GetPolicy](ischeduler-structure.md#getpolicy) und verwenden Sie die Werte für die Richtlinienschlüssel `MinConcurrency`, `MaxConcurrency` und `TargetOversubscriptionFactor` um zu bestimmen, wie viele Hardwarethreads Zuweisen der Scheduler zunächst und wie viele virtuelle Prozessorstämme für jeden Hardwarethread erstellen. Weitere Informationen zur Verwendung von Planerrichtlinien zum Bestimmen der anfänglichen Zuordnung eines Planers finden Sie unter [PolicyElementKey](concurrency-namespace-enums.md).

Der Ressourcen-Manager gewährt das Ressourcen durch Aufrufen der Methode, der einem Planer [AddVirtualProcessors](ischeduler-structure.md#addvirtualprocessors) mit einer Liste der Stämme virtueller Prozessoren. Die Methode wird in der Scheduler als Rückruf aufgerufen, vor dem Beenden dieser Methode.

Wenn der Planer Abonnement für den aktuellen Thread angefordert wird, indem der Parameter `doSubscribeCurrentThread` zu **"true"**, gibt die Methode eine `IExecutionResource` Schnittstelle. Das Abonnement muss zu einem späteren Zeitpunkt beendet werden, mithilfe der [IExecutionResource:: Remove](iexecutionresource-structure.md#remove) Methode.

Wenn Sie bestimmen, welche Hardwarethreads ausgewählt sind, versucht der Ressourcen-Manager, Prozessoraffinität-Knoten zu optimieren. Wenn Abonnements für den aktuellen Thread angefordert wird, ist dies ein Hinweis, der der aktuelle Thread zur Teilnahme an der Arbeit, die diesem Planer zugewiesen werden soll. In diesem Fall befinden die Stämme zugeordneten virtuellen Prozessoren auf dem Prozessorknoten, die, denen der aktuelle Thread auf, wenn möglich ausgeführt wird.

Das Abonnieren eines Threads die Abonnementstufe des zugrunde liegenden Hardwarethreads wird um eins erhöht. Die Abonnementstufe wird um eins verringert, wenn das Abonnement beendet wird. Weitere Informationen zu den Abonnementstufen, finden Sie unter [IExecutionResource:: CurrentSubscriptionLevel](iexecutionresource-structure.md#currentsubscriptionlevel).

##  <a name="shutdown"></a>  ISchedulerProxy:: Shutdown-Methode

Benachrichtigt den Ressourcen-Manager, dass der Planer beendet wird. Dies bewirkt, dass der Ressourcen-Manager alle Ressourcen, die an den Scheduler gewährt auch sofort manuell freigegeben.

```
virtual void Shutdown() = 0;
```

### <a name="remarks"></a>Hinweise

Alle `IExecutionContext` Schnittstellen für den Scheduler, erhalten durch das Abonnieren eines externen Threads, die mit den Methoden `ISchedulerProxy::RequestInitialVirtualProcessors` oder `ISchedulerProxy::SubscribeCurrentThread` an den Resource Manager zurückgegeben werden muss mit `IExecutionResource::Remove` vor ein Planer herunterfährt.

Wenn der Planer über eine deaktivierte virtuelle Prozessorstämme, müssen Sie Sie aktivieren, mit [IVirtualProcessorRoot:: Activate](ivirtualprocessorroot-structure.md#activate), und die Threadproxys darauf ausführen lassen die `Dispatch` Methode der Ausführung Kontexte, die sie weiterleiten, bevor Sie aufrufen `Shutdown` auf einem Scheduler-Proxy.

Es ist nicht erforderlich, für den Scheduler so, dass einzeln Zurückgeben aller der Stämme virtueller Prozessoren verfügen über Aufrufe von Ressourcen-Manager die `Remove` Methode, da alle virtuelle Prozessorstämme beim Herunterfahren auf der Ressourcen-Manager zurückgegeben werden.

##  <a name="subscribecurrentthread"></a>  ISchedulerProxy:: SubscribeCurrentThread-Methode

Registriert den aktuellen Thread mit der Resource Manager, es diesem Planer zugeordnet.

```
virtual IExecutionResource* SubscribeCurrentThread() = 0;
```

### <a name="return-value"></a>Rückgabewert

Die `IExecutionResource` Schnittstelle, die den aktuellen Thread in der Runtime darstellt.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode, der Ressourcen-Manager für den aktuellen Thread berücksichtigen Sie beim Zuordnen von Ressourcen zu Ihrem Planer und andere Planer Wunsch. Er ist besonders nützlich, wenn die Thread-Pläne zur Teilnahme an der Arbeitsprofils an Ihren Planer, zusammen mit der Stämme virtueller Prozessoren in die Warteschlange eingereiht, die der Planer vom Ressourcen-Manager erhält. Der Ressourcen-Manager verwendet Informationen, um unnötige Überzeichnung von Hardwarethreads auf dem System zu verhindern.

Die Ausführungsressource, die über diese Methode empfangen, der Ressourcen-Manager zurückgegeben werden soll mithilfe der [IExecutionResource:: Remove](iexecutionresource-structure.md#remove) Methode. Der aufrufende Thread das `Remove` Methode muss im gleichen Thread, der bereits zuvor aufgerufen werden die `SubscribeCurrentThread` Methode.

Das Abonnieren eines Threads die Abonnementstufe des zugrunde liegenden Hardwarethreads wird um eins erhöht. Die Abonnementstufe wird um eins verringert, wenn das Abonnement beendet wird. Weitere Informationen zu den Abonnementstufen, finden Sie unter [IExecutionResource:: CurrentSubscriptionLevel](iexecutionresource-structure.md#currentsubscriptionlevel).

##  <a name="unbindcontext"></a>  ISchedulerProxy:: UnbindContext-Methode

Hebt die Zuordnung eines Threadproxys aus dem Ausführungskontext, der gemäß der `pContext` Parameter und gibt sie an den Thread des freien Pool-Factory zurück. Diese Methode kann nur auf einem Ausführungskontext, der über gebunden war aufgerufen werden die [BindContext](#bindcontext) Methode und noch nicht über wird gestartet wurde die `pContext` Parameter ein [IThreadProxy:: SwitchTo ](ithreadproxy-structure.md#switchto) Methodenaufruf.

```
virtual void UnbindContext(_Inout_ IExecutionContext* pContext) = 0;
```

### <a name="parameters"></a>Parameter

*pContext*<br/>
Der Ausführungskontext aus der Threadproxy Zuordnung aufzuheben.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[IScheduler-Struktur](ischeduler-structure.md)<br/>
[IThreadProxy-Struktur](ithreadproxy-structure.md)<br/>
[IVirtualProcessorRoot-Struktur](ivirtualprocessorroot-structure.md)<br/>
[IResourceManager-Struktur](iresourcemanager-structure.md)
