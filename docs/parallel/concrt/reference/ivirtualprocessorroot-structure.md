---
title: IVirtualProcessorRoot-Struktur
ms.date: 11/04/2016
f1_keywords:
- IVirtualProcessorRoot
- CONCRTRM/concurrency::IVirtualProcessorRoot
- CONCRTRM/concurrency::IVirtualProcessorRoot::IVirtualProcessorRoot::Activate
- CONCRTRM/concurrency::IVirtualProcessorRoot::IVirtualProcessorRoot::Deactivate
- CONCRTRM/concurrency::IVirtualProcessorRoot::IVirtualProcessorRoot::EnsureAllTasksVisible
- CONCRTRM/concurrency::IVirtualProcessorRoot::IVirtualProcessorRoot::GetId
helpviewer_keywords:
- IVirtualProcessorRoot structure
ms.assetid: 5ef371b8-9e4f-4fef-bb0d-49099693dd2b
ms.openlocfilehash: 60757b0edea6b60d080c2175d4df4830ffec0cc3
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77139884"
---
# <a name="ivirtualprocessorroot-structure"></a>IVirtualProcessorRoot-Struktur

Eine Abstraktion für einen Hardwarethread, auf dem ein Threadproxy ausgeführt werden kann.

## <a name="syntax"></a>Syntax

```cpp
struct IVirtualProcessorRoot : public IExecutionResource;
```

## <a name="members"></a>Members

### <a name="public-methods"></a>Öffentliche Methoden

|Name|BESCHREIBUNG|
|----------|-----------------|
|[IVirtualProcessorRoot:: Aktivierung](#activate)|Bewirkt, dass der Thread Proxy, der der Ausführungs Kontext `pContext` Schnittstelle zugeordnet ist, mit der Ausführung auf diesem virtuellen Prozessor Stamm gestartet wird.|
|[IVirtualProcessorRoot::D eaktivierung](#deactivate)|Bewirkt, dass der Thread Proxy, der derzeit auf diesem virtuellen Prozessor Stamm ausgeführt wird, den Ausführungs Kontext nicht mehr sendet. Der Thread Proxy wird die Ausführung bei einem aufzurufenden `Activate` Methode fortsetzen.|
|[IVirtualProcessorRoot:: ensurealltasksvisible](#ensurealltasksvisible)|Bewirkt, dass die in der Speicher Hierarchie der einzelnen Prozessoren gespeicherten Daten für alle Prozessoren im System sichtbar werden. Dadurch wird sichergestellt, dass vor der Rückgabe der Methode ein vollständiger arbeitsspeicherfence auf allen Prozessoren ausgeführt wurde.|
|[IVirtualProcessorRoot:: GetId](#getid)|Gibt einen eindeutigen Bezeichner für den Stamm des virtuellen Prozessors zurück.|

## <a name="remarks"></a>Bemerkungen

Jedem virtuellen Prozessor Stamm ist eine Ausführungs Ressource zugeordnet. Die `IVirtualProcessorRoot`-Schnittstelle erbt von der [IExecutionResource](iexecutionresource-structure.md) -Schnittstelle. Mehrere virtuelle Prozessor Stämme entsprechen möglicherweise dem gleichen zugrunde liegenden Hardware Thread.

Der Ressourcen-Manager gibt Zeit Planungs Modulen virtuelle Prozessor Stämme als Reaktion auf Ressourcenanforderungen. Ein Planer kann einen virtuellen Prozessor Stamm zum Ausführen von Arbeiten verwenden, indem er ihn mit einem Ausführungs Kontext aktiviert.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[IExecutionResource](iexecutionresource-structure.md)

`IVirtualProcessorRoot`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** concrtrm. h

**Namespace:** Parallelität

## <a name="activate"></a>IVirtualProcessorRoot:: Aktivierungs-Methode

Bewirkt, dass der Thread Proxy, der der Ausführungs Kontext `pContext` Schnittstelle zugeordnet ist, mit der Ausführung auf diesem virtuellen Prozessor Stamm gestartet wird.

```cpp
virtual void Activate(_Inout_ IExecutionContext* pContext) = 0;
```

### <a name="parameters"></a>Parameter

*pContext*<br/>
Eine Schnittstelle zum Ausführungs Kontext, die auf diesem virtuellen Prozessor Stamm verteilt wird.

### <a name="remarks"></a>Bemerkungen

Der Ressourcen-Manager gibt einen Thread Proxy an, wenn dieser nicht mit der Ausführungs Kontext Schnittstelle verknüpft ist `pContext`

Die `Activate`-Methode kann verwendet werden, um mit der Ausführung von Arbeiten an einem neuen, vom Ressourcen-Manager zurückgegebenen Stamm des virtuellen Prozessors zu beginnen oder um den Thread Proxy in einem virtuellen Prozessor Stamm wieder aufzunehmen, der deaktiviert wurde oder gerade deaktiviert wird. Weitere Informationen zur Deaktivierung finden Sie unter [IVirtualProcessorRoot::D eaktivierung](#deactivate) . Wenn Sie einen deaktivierten virtuellen Prozessor Stamm fortsetzen, muss der Parameter `pContext` mit dem Parameter übereinstimmen, der zum Deaktivieren des virtuellen Prozessor Stamms verwendet wird.

Nachdem der Stamm eines virtuellen Prozessors zum ersten Mal aktiviert wurde, können nachfolgende Paare von Aufrufen von `Deactivate` und `Activate` aufeinander aufrüsten. Dies bedeutet, dass der Ressourcen-Manager einen `Activate`-empfangen kann, bevor er den `Deactivate`-Befehl empfängt, für den er gedacht war.

Wenn Sie einen virtuellen Prozessor Stamm aktivieren, signalisieren Sie den Ressourcen-Manager, dass dieser virtuelle Prozessor Stamm derzeit ausgelastet ist. Wenn Ihr Planer keine für diesen Stamm auszuführenden Aufgaben finden kann, wird erwartet, dass die `Deactivate`-Methode aufgerufen wird, um die Ressourcen-Manager zu informieren, dass sich der virtuelle Prozessor Stamm im Leerlauf befindet. Der Ressourcen-Manager verwendet diese Daten für den Lastenausgleich des Systems.

`invalid_argument` wird ausgelöst, wenn das Argument `pContext` den Wert `NULL`hat.

`invalid_operation` wird ausgelöst, wenn das Argument `pContext` den Ausführungs Kontext nicht darstellt, der zuletzt von diesem virtuellen Prozessor Stamm gesendet wurde.

Durch das Aktivieren eines virtuellen Prozessor Stamms wird die Abonnement Ebene des zugrunde liegenden Hardware Threads um 1 erhöht. Weitere Informationen zu Abonnement Ebenen finden Sie unter [IExecutionResource:: currentabonneptionlevel](iexecutionresource-structure.md#currentsubscriptionlevel).

## <a name="deactivate"></a>IVirtualProcessorRoot::D eaktivierungs Methode

Bewirkt, dass der Thread Proxy, der derzeit auf diesem virtuellen Prozessor Stamm ausgeführt wird, den Ausführungs Kontext nicht mehr sendet. Der Thread Proxy wird die Ausführung bei einem aufzurufenden `Activate` Methode fortsetzen.

```cpp
virtual bool Deactivate(_Inout_ IExecutionContext* pContext) = 0;
```

### <a name="parameters"></a>Parameter

*pContext*<br/>
Der Kontext, der zurzeit von diesem Stamm gesendet wird.

### <a name="return-value"></a>Rückgabewert

Ein boolescher Wert. Der Wert **true** gibt an, dass der Thread Proxy, der von der `Deactivate`-Methode zurückgegeben wurde, als Reaktion auf einen aufzurufenden `Activate`-Methode. Der Wert `false` gibt an, dass der Thread Proxy, der von der-Methode zurückgegeben wird, als Reaktion auf ein Benachrichtigungs Ereignis in der Ressourcen-Manager. In einem im Benutzermodus planbarer (ums) Thread Planer ist dies ein Hinweis darauf, dass Elemente in der Vervollständigungsliste des Schedulers angezeigt werden und der Scheduler diese verarbeiten muss.

### <a name="remarks"></a>Bemerkungen

Verwenden Sie diese Methode, um die Ausführung eines virtuellen Prozessor Stamms vorübergehend zu beenden, wenn Sie keine Arbeit im Scheduler finden. Ein Aufrufder `Deactivate`-Methode muss aus der `Dispatch`-Methode des Ausführungs Kontexts stammen, mit dem der virtuelle Prozessor Stamm zuletzt aktiviert wurde. Anders ausgedrückt: der Thread Proxy, der die `Deactivate` Methode aufruft, muss der Thread Proxy sein, der zurzeit auf dem Stamm des virtuellen Prozessors ausgeführt wird. Das Aufrufen der-Methode für einen virtuellen Prozessor Stamm, den Sie nicht ausführen, kann zu undefiniertem Verhalten führen.

Ein deaktivierter virtueller Prozessor Stamm kann mit einem aufzurufenden `Activate`-Methode reaktiviert werden, und zwar mit demselben Argument, das an die `Deactivate`-Methode übermittelt wurde. Der Planer ist dafür verantwortlich, sicherzustellen, dass Aufrufe der Methoden `Activate` und `Deactivate` gekoppelt sind, aber nicht in einer bestimmten Reihenfolge empfangen werden müssen. Der Ressourcen-Manager kann den Empfang eines Aufrufes `Activate`-Methode verarbeiten, bevor er einen aufzurufenden `Deactivate` Methode empfängt.

Wenn ein virtueller Prozessor Stamm erwacht und der Rückgabewert der `Deactivate`-Methode der Wert **false**ist, sollte der Planer die ums-Vervollständigungsliste über die `IUMSCompletionList::GetUnblockNotifications`-Methode Abfragen, diese Informationen ausführen und anschließend die `Deactivate`-Methode erneut aufzurufen. Dieser Wert sollte bis zu diesem Zeitpunkt wiederholt werden, wenn die `Deactivate`-Methode den Wert `true`zurückgibt.

`invalid_argument` wird ausgelöst, wenn das Argument `pContext` den Wert NULL aufweist.

`invalid_operation` wird ausgelöst, wenn der Stamm des virtuellen Prozessors nie aktiviert wurde, oder das Argument `pContext` den Ausführungs Kontext nicht darstellt, der zuletzt von diesem virtuellen Prozessor Stamm gesendet wurde.

Der Vorgang der Deaktivierung eines virtuellen Prozessor Stamms verringert die Abonnement Ebene des zugrunde liegenden Hardware Threads um 1. Weitere Informationen zu Abonnement Ebenen finden Sie unter [IExecutionResource:: currentabonneptionlevel](iexecutionresource-structure.md#currentsubscriptionlevel).

## <a name="ensurealltasksvisible"></a>IVirtualProcessorRoot:: ensurealltasksvisible-Methode

Bewirkt, dass die in der Speicher Hierarchie der einzelnen Prozessoren gespeicherten Daten für alle Prozessoren im System sichtbar werden. Dadurch wird sichergestellt, dass vor der Rückgabe der Methode ein vollständiger arbeitsspeicherfence auf allen Prozessoren ausgeführt wurde.

```cpp
virtual void EnsureAllTasksVisible(_Inout_ IExecutionContext* pContext) = 0;
```

### <a name="parameters"></a>Parameter

*pContext*<br/>
Der Kontext, der zurzeit von diesem virtuellen Prozessor Stamm gesendet wird.

### <a name="remarks"></a>Bemerkungen

Diese Methode kann nützlich sein, wenn Sie die Deaktivierung eines virtuellen Prozessor Stamms mit dem Hinzufügen neuer Aufgaben in den Scheduler synchronisieren möchten. Aus Leistungsgründen können Sie dem Scheduler Arbeitselemente hinzufügen, ohne eine Arbeitsspeicher Barriere auszuführen. Dies bedeutet, dass Arbeitselemente, die von einem Thread hinzugefügt werden, der auf einem Prozessor ausgeführt wird, nicht sofort für alle anderen Prozessoren sichtbar sind. Wenn Sie diese Methode in Verbindung mit der `Deactivate`-Methode verwenden, können Sie sicherstellen, dass Ihr Scheduler nicht alle seine virtuellen Prozessor Stämme deaktiviert, wenn Arbeitselemente in den Auflistungen des Schedulers vorhanden sind.

Ein Aufrufder `EnsureAllTasksVisibleThe`-Methode muss aus der `Dispatch`-Methode des Ausführungs Kontexts stammen, mit dem der virtuelle Prozessor Stamm zuletzt aktiviert wurde. Anders ausgedrückt: der Thread Proxy, der die `EnsureAllTasksVisible` Methode aufruft, muss der Thread Proxy sein, der zurzeit auf dem Stamm des virtuellen Prozessors ausgeführt wird. Das Aufrufen der-Methode für einen virtuellen Prozessor Stamm, den Sie nicht ausführen, kann zu undefiniertem Verhalten führen.

`invalid_argument` wird ausgelöst, wenn das Argument `pContext` den Wert `NULL`hat.

`invalid_operation` wird ausgelöst, wenn der Stamm des virtuellen Prozessors nie aktiviert wurde, oder das Argument `pContext` den Ausführungs Kontext nicht darstellt, der zuletzt von diesem virtuellen Prozessor Stamm gesendet wurde.

## <a name="getid"></a>IVirtualProcessorRoot:: GetId-Methode

Gibt einen eindeutigen Bezeichner für den Stamm des virtuellen Prozessors zurück.

```cpp
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>Rückgabewert

Ein ganzzahliger Bezeichner.

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace](concurrency-namespace.md)
