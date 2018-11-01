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
ms.openlocfilehash: 6e3f874aa7c20494483172d7c7c3efee362cf6a1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50569870"
---
# <a name="ivirtualprocessorroot-structure"></a>IVirtualProcessorRoot-Struktur

Eine Abstraktion für einen Hardwarethread, auf dem ein Threadproxy ausgeführt werden kann.

## <a name="syntax"></a>Syntax

```
struct IVirtualProcessorRoot : public IExecutionResource;
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[IVirtualProcessorRoot::Activate](#activate)|Bewirkt, dass den Threadproxy Execution Context-Schnittstelle zugeordneten `pContext` Starten der Ausführung auf diesem virtuellen Prozessorstamm.|
|[IVirtualProcessorRoot::Deactivate](#deactivate)|Bewirkt, dass den Threadproxy, der gerade auf diesem virtuellen Prozessorstamm zu beenden, verteilen den Ausführungskontext ausgeführt. Der Threadproxy wird fortgesetzt, die Ausführung bei einem Aufruf von der `Activate` Methode.|
|[IVirtualProcessorRoot::EnsureAllTasksVisible](#ensurealltasksvisible)|Bewirkt, dass Daten in der gesamten Speicherhierarchie der einzelnen Prozessoren für alle Prozessoren im System sichtbar werden. Dadurch wird sichergestellt, dass es sich bei ein vollständigen Arbeitsspeicher-Fence auf allen Prozessoren ausgeführt wurde, bevor die Methode zurückgibt.|
|[IVirtualProcessorRoot::GetId](#getid)|Gibt einen eindeutigen Bezeichner für den virtuellen Prozessorstamm zurück.|

## <a name="remarks"></a>Hinweise

Alle virtuellen Prozessorstamm verfügt über eine zugeordnete Ausführungsressource. Die `IVirtualProcessorRoot` Schnittstelle erbt von der [IExecutionResource](iexecutionresource-structure.md) Schnittstelle. Die gleichen zugrunde liegenden Hardwarethread können mehrere virtuelle Prozessorstämme entsprechen.

Der Ressourcen-Manager virtuelle Prozessorstämme Zeitplanungsmodule als Reaktion auf Anforderungen für Ressourcen gewährt. Ein Planer können einen virtuellen Prozessorstamm Aufgaben durchführen, indem sie mit einem Ausführungskontext aktivieren.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[IExecutionResource](iexecutionresource-structure.md)

`IVirtualProcessorRoot`

## <a name="requirements"></a>Anforderungen

**Header:** concrtrm.h

**Namespace:** Parallelität

##  <a name="activate"></a>  IVirtualProcessorRoot:: Activate-Methode

Bewirkt, dass den Threadproxy Execution Context-Schnittstelle zugeordneten `pContext` Starten der Ausführung auf diesem virtuellen Prozessorstamm.

```
virtual void Activate(_Inout_ IExecutionContext* pContext) = 0;
```

### <a name="parameters"></a>Parameter

*pContext*<br/>
Eine Schnittstelle zum Ausführungskontext, der auf diesem virtuellen Prozessorstamm gesendet werden.

### <a name="remarks"></a>Hinweise

Wenn diese nicht Execution Context-Schnittstelle zugeordnet ist, stellt der Ressourcen-Manager einen Threadproxy bereit. `pContext`

Die `Activate` Methode kann verwendet werden, Starten der Ausführung von Aufgaben auf einem neuen virtuellen Prozessorstamm zurückgegeben, der Ressourcen-Manager oder den Threadproxy auf einem virtuellen Prozessorstamm fortsetzen, die deaktiviert wurde oder zu deaktivieren. Finden Sie unter [IVirtualProcessorRoot:: Deactivate](#deactivate) für Weitere Informationen zur Deaktivierung. Wenn Sie einen deaktivierten virtuellen Prozessorstamm, der Parameter fortgesetzt werden `pContext` müssen als Parameter verwendet, um den virtuellen Prozessorstamm deaktivieren identisch sein.

Sobald ein virtueller Prozessorstamm aktiviert wurde zum ersten Mal, nachfolgende Paare von Aufrufen an `Deactivate` und `Activate` kann dieser Wettlauf abgenommen miteinander. Dies bedeutet, es ist zulässig, für das Resource Manager erhalten Sie einen Aufruf von `Activate` vor dem Empfang der `Deactivate` aufrufen, die er vorgesehen war.

Wenn Sie einen virtuellen Prozessorstamm aktivieren, signalisieren, dass diese virtuellen Prozessorstamm derzeit mit der Arbeit beschäftigt ist, an den Resource Manager. Wenn der Planer alle auf diesem Stamm auszuführende Arbeit findet, es wird erwartet, rufen Sie die `Deactivate` Methode, die den Ressourcen-Manager zu informieren, dass der virtuelle Prozessorstamm im Leerlauf befindet. Der Ressourcen-Manager verwendet diese Daten für den Lastenausgleich des Systems.

`invalid_argument` wird ausgelöst, wenn das Argument `pContext` hat den Wert `NULL`.

`invalid_operation` wird ausgelöst, wenn das Argument `pContext` stellt den Ausführungskontext, der von diesem virtuellen Prozessorstamm zuletzt weitergeleitet wurde keine dar.

Die Aktivierung von einem virtuellen Prozessorstamm Abonnementebene des zugrunde liegenden Hardwarethreads wird um eins erhöht. Weitere Informationen zu den Abonnementstufen, finden Sie unter [IExecutionResource:: CurrentSubscriptionLevel](iexecutionresource-structure.md#currentsubscriptionlevel).

##  <a name="deactivate"></a>  IVirtualProcessorRoot:: Deactivate-Methode

Bewirkt, dass den Threadproxy, der gerade auf diesem virtuellen Prozessorstamm zu beenden, verteilen den Ausführungskontext ausgeführt. Der Threadproxy wird fortgesetzt, die Ausführung bei einem Aufruf von der `Activate` Methode.

```
virtual bool Deactivate(_Inout_ IExecutionContext* pContext) = 0;
```

### <a name="parameters"></a>Parameter

*pContext*<br/>
Der Kontext, der derzeit von diesem Stamm weitergeleitet wird.

### <a name="return-value"></a>Rückgabewert

Ein boolescher Wert. Der Wert **"true"** gibt an, dass der Threadproxy zurückgegeben der `Deactivate` -Methode in der Antwort auf einen Aufruf der `Activate` Methode. Der Wert `false` gibt an, dass der Threadproxy von der Methode als Reaktion auf ein Benachrichtigungsereignis im Ressourcen-Manager zurückgegeben. Auf einem im Benutzermodus planbare (UMS) Threadplaner bedeutet dies, dass Elemente in der Vervollständigungsliste des Planers erschienen sind, und der Scheduler erforderlich ist, um sie zu behandeln.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode, einen virtuellen Prozessorstamm ausgeführt, wenn Sie keine arbeiten, in Ihre Scheduler finden vorübergehend zu beenden. Ein Aufruf der `Deactivate` Methode darf stammen aus der `Dispatch` Methode des Ausführungskontexts, der der virtuellen Prozessorstamm zuletzt aktiviert wurde. Das heißt, der Threadproxy Aufrufen der `Deactivate` Methode muss die sein, der derzeit auf dem virtuellen Prozessorstamm ausgeführt wird. Aufrufen der Methode auf einem virtuellen Prozessorstamm, die, dem Sie nicht auf ausgeführt werden, kann dies zu nicht definiertem Verhalten führen.

Ein deaktivierter virtueller Prozessorstamm möglicherweise durch einen Aufruf von reaktiviert werden die `Activate` Methode, mit dem gleichen Argument, das in übergeben wurde, die `Deactivate` Methode. Der Planer ist dafür verantwortlich, sicherzustellen, dass Aufrufe der `Activate` und `Deactivate` Methoden kombiniert werden, aber sie sind nicht erforderlich, um in einer bestimmten Reihenfolge empfangen werden. Der Ressourcen-Manager kann einen Anruf zu verarbeiten. die `Activate` -Methode auf, bevor er einen Aufruf empfängt die `Deactivate` Methode, die er vorgesehen war.

Wenn es sich bei ein virtuellen Prozessorstamm aktiviert und der Rückgabewert der `Deactivate` Methode ist der Wert **"false"**, das Zeitplanungsmodul, sollten die UMS-Vervollständigungsliste über Abfragen die `IUMSCompletionList::GetUnblockNotifications` -Methode, diese Informationen nutzen und dann Rufen Sie anschließend die `Deactivate` -Methode erneut auf. Dies sollte wiederholt werden, solange die `Deactivate` -Methode gibt den Wert `true`.

`invalid_argument` wird ausgelöst, wenn das Argument `pContext` den Wert NULL aufweist.

`invalid_operation` wird ausgelöst, wenn der virtuelle Prozessorstamm nie aktiviert wurde, oder das Argument `pContext` stellt den Ausführungskontext, der von diesem virtuellen Prozessorstamm zuletzt weitergeleitet wurde keine dar.

Das Deaktivieren von einem virtuellen Prozessorstamm wird die Abonnementstufe des zugrunde liegenden Hardwarethreads um eins verringert. Weitere Informationen zu den Abonnementstufen, finden Sie unter [IExecutionResource:: CurrentSubscriptionLevel](iexecutionresource-structure.md#currentsubscriptionlevel).

##  <a name="ensurealltasksvisible"></a>  IVirtualProcessorRoot:: EnsureAllTasksVisible-Methode

Bewirkt, dass Daten in der gesamten Speicherhierarchie der einzelnen Prozessoren für alle Prozessoren im System sichtbar werden. Dadurch wird sichergestellt, dass es sich bei ein vollständigen Arbeitsspeicher-Fence auf allen Prozessoren ausgeführt wurde, bevor die Methode zurückgibt.

```
virtual void EnsureAllTasksVisible(_Inout_ IExecutionContext* pContext) = 0;
```

### <a name="parameters"></a>Parameter

*pContext*<br/>
Der Kontext, der derzeit von diesem virtuellen Prozessorstamm weitergeleitet wird.

### <a name="remarks"></a>Hinweise

Möglicherweise diese Methode nützlich bei der Deaktivierung von einem virtuellen Prozessorstamm durch das Hinzufügen neuer Anwendungen nicht in der Planer synchronisiert werden soll. Aus Gründen der Leistung können Sie entscheiden, auf dem Planer Arbeitselemente hinzufügen, ohne eine Arbeitsspeicherbarriere, d. h. Arbeitsaufgaben hinzugefügt, die von einem Thread, der auf einem Prozessor ausgeführt wurden, nicht sofort für alle anderen Prozessoren sichtbar sind. Mit dieser Methode in Verbindung mit der `Deactivate` Stammelemente Methode können Sie sicherstellen, dass der Planer alle seinen virtuellen Prozessor nicht deaktivieren, wird, während von Arbeitselementen im des Planers Sammlungen vorhanden sind.

Ein Aufruf der `EnsureAllTasksVisibleThe` Methode darf stammen aus der `Dispatch` Methode des Ausführungskontexts, der der virtuellen Prozessorstamm zuletzt aktiviert wurde. Das heißt, der Threadproxy Aufrufen der `EnsureAllTasksVisible` Methode muss die sein, der derzeit auf dem virtuellen Prozessorstamm ausgeführt wird. Aufrufen der Methode auf einem virtuellen Prozessorstamm, die, dem Sie nicht auf ausgeführt werden, kann dies zu nicht definiertem Verhalten führen.

`invalid_argument` wird ausgelöst, wenn das Argument `pContext` hat den Wert `NULL`.

`invalid_operation` wird ausgelöst, wenn der virtuelle Prozessorstamm nie aktiviert wurde, oder das Argument `pContext` stellt den Ausführungskontext, der von diesem virtuellen Prozessorstamm zuletzt weitergeleitet wurde keine dar.

##  <a name="getid"></a>  IVirtualProcessorRoot:: GetID-Methode

Gibt einen eindeutigen Bezeichner für den virtuellen Prozessorstamm zurück.

```
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>Rückgabewert

Ein ganzzahliger Bezeichner.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)
