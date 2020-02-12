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
ms.openlocfilehash: 45d65a5e16121d39233c3ceb801933aa1f5a5f8e
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77138915"
---
# <a name="iexecutioncontext-structure"></a>IExecutionContext-Struktur

Eine Schnittstelle zu einem Ausführungskontext, der auf einem angegebenen virtuellen Prozessor ausgeführt werden kann und einen gemeinsamen Kontextwechsel zulässt.

## <a name="syntax"></a>Syntax

```cpp
struct IExecutionContext;
```

## <a name="members"></a>Members

### <a name="public-methods"></a>Öffentliche Methoden

|Name|BESCHREIBUNG|
|----------|-----------------|
|[IExecutionContext::D ispatch](#dispatch)|Die Methode, die aufgerufen wird, wenn ein Thread Proxy mit dem Ausführen eines bestimmten Ausführungs Kontexts beginnt. Dies sollte die Haupt Arbeitsroutine für Ihren Scheduler sein.|
|[IExecutionContext:: GetId](#getid)|Gibt einen eindeutigen Bezeichner für den Ausführungs Kontext zurück.|
|[IExecutionContext:: GetProxy](#getproxy)|Gibt eine Schnittstelle zum Thread Proxy zurück, der diesen Kontext ausführt.|
|[IExecutionContext:: getscheduler](#getscheduler)|Gibt eine Schnittstelle zum Scheduler zurück, zu dem dieser Ausführungs Kontext gehört.|
|[IExecutionContext:: SetProxy](#setproxy)|Ordnet diesem Ausführungs Kontext einen Thread Proxy zu. Der zugehörige Thread Proxy ruft diese Methode direkt vor der Ausführung der `Dispatch`-Methode des Kontexts auf.|

## <a name="remarks"></a>Bemerkungen

Wenn Sie einen benutzerdefinierten Planer implementieren, der mit dem Ressourcen-Manager des Concurrency Runtime eine Schnittstelle erstellt, müssen Sie die `IExecutionContext`-Schnittstelle implementieren. Die von der Ressourcen-Manager erstellten Threads führen im Auftrag Ihres Zeit Planungs Moduls Aufgaben aus, indem Sie die `IExecutionContext::Dispatch`-Methode ausführen.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`IExecutionContext`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** concrtrm. h

**Namespace:** Parallelität

## <a name="dispatch"></a>IExecutionContext::D ispatch-Methode

Die Methode, die aufgerufen wird, wenn ein Thread Proxy mit dem Ausführen eines bestimmten Ausführungs Kontexts beginnt. Dies sollte die Haupt Arbeitsroutine für Ihren Scheduler sein.

```cpp
virtual void Dispatch(_Inout_ DispatchState* pDispatchState) = 0;
```

### <a name="parameters"></a>Parameter

*pdispatchstate*<br/>
Ein Zeiger auf den Zustand, in dem dieser Ausführungs Kontext gesendet wird. Weitere Informationen zum Verteilungs Status finden Sie unter [DispatchState](dispatchstate-structure.md).

## <a name="getid"></a>IExecutionContext:: GetId-Methode

Gibt einen eindeutigen Bezeichner für den Ausführungs Kontext zurück.

```cpp
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>Rückgabewert

Eine eindeutige ganzzahlige Kennung.

### <a name="remarks"></a>Bemerkungen

Verwenden Sie die-Methode `GetExecutionContextId`, um einen eindeutigen Bezeichner für das Objekt zu erhalten, das die `IExecutionContext` Schnittstelle implementiert, bevor Sie die-Schnittstelle als Parameter für Methoden verwenden, die vom Ressourcen-Manager bereitgestellt werden. Es wird erwartet, dass Sie denselben Bezeichner zurückgeben, wenn die `GetId`-Funktion aufgerufen wird.

Ein Bezeichner aus einer anderen Quelle kann zu undefiniertem Verhalten führen.

## <a name="getproxy"></a>IExecutionContext:: GetProxy-Methode

Gibt eine Schnittstelle zum Thread Proxy zurück, der diesen Kontext ausführt.

```cpp
virtual IThreadProxy* GetProxy() = 0;
```

### <a name="return-value"></a>Rückgabewert

Eine `IThreadProxy`-Schnittstelle. Wenn der Thread Proxy des Ausführungs Kontexts nicht mit einem-`SetProxy`initialisiert wurde, muss die Funktion `NULL`zurückgeben.

### <a name="remarks"></a>Bemerkungen

Der Ressourcen-Manager ruft die `SetProxy`-Methode in einem Ausführungs Kontext auf, wobei eine `IThreadProxy`-Schnittstelle als Parameter verwendet wird, bevor die `Dispatch`-Methode für den im Kontext eingegeben wird. Es wird erwartet, dass Sie dieses Argument speichern und bei Aufrufen von `GetProxy()`zurückgeben.

## <a name="getscheduler"></a>IExecutionContext:: getscheduler-Methode

Gibt eine Schnittstelle zum Scheduler zurück, zu dem dieser Ausführungs Kontext gehört.

```cpp
virtual IScheduler* GetScheduler() = 0;
```

### <a name="return-value"></a>Rückgabewert

Eine `IScheduler`-Schnittstelle.

### <a name="remarks"></a>Bemerkungen

Sie müssen den Ausführungs Kontext mit einer gültigen `IScheduler`-Schnittstelle initialisieren, bevor Sie ihn als Parameter für Methoden verwenden, die vom Ressourcen-Manager bereitgestellt werden.

## <a name="setproxy"></a>IExecutionContext:: SetProxy-Methode

Ordnet diesem Ausführungs Kontext einen Thread Proxy zu. Der zugehörige Thread Proxy ruft diese Methode direkt vor der Ausführung der `Dispatch`-Methode des Kontexts auf.

```cpp
virtual void SetProxy(_Inout_ IThreadProxy* pThreadProxy) = 0;
```

### <a name="parameters"></a>Parameter

*pthreadproxy*<br/>
Eine Schnittstelle zum Thread Proxy, der in diesem Ausführungs Kontext in die `Dispatch` Methode eingegeben werden soll.

### <a name="remarks"></a>Bemerkungen

Es wird erwartet, dass Sie den Parameter `pThreadProxy` speichern und ihn bei einem Aufrufen der `GetProxy`-Methode zurückgeben. Der Ressourcen-Manager stellt sicher, dass der dem Ausführungs Kontext zugeordnete Thread Proxy nicht geändert wird, während der Thread Proxy die `Dispatch`-Methode ausführt.

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[IScheduler-Struktur](ischeduler-structure.md)<br/>
[IThreadProxy-Struktur](ithreadproxy-structure.md)
