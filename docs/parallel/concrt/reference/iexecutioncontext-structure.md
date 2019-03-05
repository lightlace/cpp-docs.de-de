---
title: IExecutionContext-Struktur
ms.date: 11/04/2016
f1_keywords:
- IExecutionContext
- CONCRTRM/concurrency::IExecutionContext
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::Dispatch
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::GetId
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::GetProxy
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::GetScheduler
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::SetProxy
helpviewer_keywords:
- IExecutionContext structure
ms.assetid: f3108089-ecda-4b07-86db-3efae60c31e0
ms.openlocfilehash: 8c49df5a8c7f214b574b4f6118d182b63fec5dca
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57264962"
---
# <a name="iexecutioncontext-structure"></a>IExecutionContext-Struktur

Eine Schnittstelle zu einem Ausführungskontext, der auf einem angegebenen virtuellen Prozessor ausgeführt werden kann und einen gemeinsamen Kontextwechsel zulässt.

## <a name="syntax"></a>Syntax

```
struct IExecutionContext;
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[IExecutionContext::Dispatch](#dispatch)|Die Methode, die aufgerufen wird, wenn ein Threadproxy beginnt die Ausführung von eines bestimmten Ausführungskontexts. Dies dürfte die main-Worker-Routine für den Planer.|
|[IExecutionContext::GetId](#getid)|Gibt einen eindeutigen Bezeichner für den Ausführungskontext zurück.|
|[IExecutionContext::GetProxy](#getproxy)|Gibt eine Schnittstelle zurück, um den Threadproxy, der diesem Kontext ausgeführt wird.|
|[IExecutionContext::GetScheduler](#getscheduler)|Gibt eine Schnittstelle zum Planer Ausführungskontexts gehört.|
|[IExecutionContext::SetProxy](#setproxy)|Ordnet einen Threadproxy Ausführungskontexts. Der zugeordnete Threadproxy ruft diese Methode, unmittelbar vor dem Beginn des Kontexts ausführen `Dispatch` Methode.|

## <a name="remarks"></a>Hinweise

Wenn Sie einen benutzerdefinierten Planer, der mit der Concurrency Runtime-Ressourcen-Manager-Schnittstellen implementieren, müssen Sie zum Implementieren der `IExecutionContext` Schnittstelle. Führen Sie die Threads vom Ressourcen-Manager erstellt arbeiten für den Planer durch Ausführen der `IExecutionContext::Dispatch` Methode.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`IExecutionContext`

## <a name="requirements"></a>Anforderungen

**Header:** concrtrm.h

**Namespace:** Parallelität

##  <a name="dispatch"></a>  IExecutionContext:: Dispatch-Methode

Die Methode, die aufgerufen wird, wenn ein Threadproxy beginnt die Ausführung von eines bestimmten Ausführungskontexts. Dies dürfte die main-Worker-Routine für den Planer.

```
virtual void Dispatch(_Inout_ DispatchState* pDispatchState) = 0;
```

### <a name="parameters"></a>Parameter

*pDispatchState*<br/>
Ein Zeiger auf den Zustand, in dem dieser Ausführungskontext weitergeleitet wird. Weitere Informationen zum Status der Verteilung, finden Sie unter [DispatchState](dispatchstate-structure.md).

##  <a name="getid"></a>  IExecutionContext:: GetID-Methode

Gibt einen eindeutigen Bezeichner für den Ausführungskontext zurück.

```
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>Rückgabewert

Eine eindeutige ganzzahlige Bezeichner.

### <a name="remarks"></a>Hinweise

Verwenden Sie die Methode `GetExecutionContextId` einen eindeutigen Bezeichner für das Objekt abgerufen wird, implementiert die `IExecutionContext` Schnittstelle, die vor der Verwendung der Schnittstelle als Parameter für Methoden angegeben, der Ressourcen-Manager. Es wird erwartet, die den gleichen Bezeichner zurückzugeben bei der `GetId` Funktion wird aufgerufen.

Ein Bezeichner, die aus einer anderen Quelle erhalten könnte zu nicht definiertem Verhalten führen.

##  <a name="getproxy"></a>  IExecutionContext:: GetProxy-Methode

Gibt eine Schnittstelle zurück, um den Threadproxy, der diesem Kontext ausgeführt wird.

```
virtual IThreadProxy* GetProxy() = 0;
```

### <a name="return-value"></a>Rückgabewert

Eine `IThreadProxy`-Schnittstelle. Wenn der Ausführungskontext des Threadproxys mit einem Aufruf von nicht initialisiert wurde `SetProxy`, muss die Funktion zurückgeben `NULL`.

### <a name="remarks"></a>Hinweise

Der Ressourcen-Manager wird aufgerufen, die `SetProxy` Methode für einen Ausführungskontext mit einer `IThreadProxy` -Schnittstelle als Parameter, bevor Sie eingeben der `Dispatch` Methode für die im Kontext. Sie sollten dieses Argument zu speichern und in Aufrufen von zurückgeben `GetProxy()`.

##  <a name="getscheduler"></a>  IExecutionContext:: GetScheduler-Methode

Gibt eine Schnittstelle zum Planer Ausführungskontexts gehört.

```
virtual IScheduler* GetScheduler() = 0;
```

### <a name="return-value"></a>Rückgabewert

Eine `IScheduler`-Schnittstelle.

### <a name="remarks"></a>Hinweise

Sie sind erforderlich, um den Ausführungskontext mit einer gültigen initialisieren `IScheduler` Schnittstelle, die vor der Verwendung als Parameter für Methoden angegeben, der Ressourcen-Manager.

##  <a name="setproxy"></a>  IExecutionContext:: SetProxy-Methode

Ordnet einen Threadproxy Ausführungskontexts. Der zugeordnete Threadproxy ruft diese Methode, unmittelbar vor dem Beginn des Kontexts ausführen `Dispatch` Methode.

```
virtual void SetProxy(_Inout_ IThreadProxy* pThreadProxy) = 0;
```

### <a name="parameters"></a>Parameter

*pThreadProxy*<br/>
Eine Schnittstelle für den Threadproxy, der geben die `Dispatch` Methode in diesem Ausführungskontext.

### <a name="remarks"></a>Hinweise

Es wird erwartet, speichern Sie den Parameter `pThreadProxy` und bei einem Aufruf zurückgeben dem `GetProxy` Methode. Der Ressourcen-Manager wird sichergestellt, dass der Threadproxy, der den Ausführungskontext zugeordnete nicht geändert werden, während der Threadproxy ausgeführt wird die `Dispatch` Methode.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[IScheduler-Struktur](ischeduler-structure.md)<br/>
[IThreadProxy-Struktur](ithreadproxy-structure.md)
