---
title: CNonStatelessWorker-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CNonStatelessWorker
- ATLUTIL/ATL::CNonStatelessWorker
- ATLUTIL/ATL::CNonStatelessWorker::RequestType
- ATLUTIL/ATL::CNonStatelessWorker::Execute
- ATLUTIL/ATL::CNonStatelessWorker::Initialize
- ATLUTIL/ATL::CNonStatelessWorker::Terminate
dev_langs:
- C++
helpviewer_keywords:
- CNonStatelessWorker class
ms.assetid: d00936c6-9e7d-49fb-b87d-417b963367d1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a4aa07273e68f0320823d258f324bb8631aef77a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46095598"
---
# <a name="cnonstatelessworker-class"></a>CNonStatelessWorker-Klasse

Empfängt Anforderungen aus dem Threadpool und übergibt sie an eine Worker-Objekt, das erstellt und zerstört wird bei jeder Anforderung.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
template <class Worker>
class CNonStatelessWorker
```

#### <a name="parameters"></a>Parameter

*Worker*<br/>
Eine Worker-Thread-Klasse, die mit der [Worker Archetyp](../../atl/reference/worker-archetype.md) geeignet, für die Verarbeitung von Anforderungen für in die Warteschlange [CThreadPool](../../atl/reference/cthreadpool-class.md).

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|Beschreibung|
|----------|-----------------|
|[CNonStatelessWorker::RequestType](#requesttype)|Implementierung von [WorkerArchetype::RequestType](worker-archetype.md#requesttype).|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CNonStatelessWorker::Execute](#execute)|Implementierung von [WorkerArchetype::Execute](worker-archetype.md#execute).|
|[CNonStatelessWorker::Initialize](#initialize)|Implementierung von [WorkerArchetype::Initialize](worker-archetype.md#initialize).|
|[CNonStatelessWorker::Terminate](#terminate)|Implementierung von [WorkerArchetype::Terminate](worker-archetype.md#terminate).|

## <a name="remarks"></a>Hinweise

Diese Klasse ist für die Verwendung mit einem einfachen Arbeitsthread [CThreadPool](../../atl/reference/cthreadpool-class.md). Diese Klasse stellt keine Funktionen zur Behandlung von Anforderung selbst bereit. Stattdessen eine Instanz instanziieren *Worker* pro Anforderung und delegiert die Implementierung der Methoden für diese Instanz.

Der Vorteil dieser Klasse ist, dass es sich um eine bequeme Möglichkeit, ändern Sie das Zustandsmodell für vorhandene Klassen von Worker-Threads bereitstellt. `CThreadPool` erstellt einen einzelnen Worker für die Lebensdauer des Threads, damit es, wenn die Workerklasse den Zustand enthält, sie über mehrere Anforderungen hinweg enthalten wird. Von dieser Klasse in einfach umschließt die `CNonStatelessWorker` Vorlage vor der Verwendung mit `CThreadPool`, die Lebensdauer des Workers und der Status ist auf eine einzelne Anforderung enthält.

## <a name="requirements"></a>Anforderungen

**Header:** "atlutil.h"

##  <a name="execute"></a>  CNonStatelessWorker::Execute

Implementierung von [WorkerArchetype::Execute](worker-archetype.md#execute).  

```
void Execute(
    Worker::RequestType request,
    void* pvWorkerParam,
    OVERLAPPED* pOverlapped);
```

### <a name="remarks"></a>Hinweise

Diese Methode erstellt eine Instanz der *Worker* -Klasse auf den Stapel und ruft [initialisieren](worker-archetype.md#initialize) für dieses Objekt. Wenn die Initialisierung erfolgreich ist, ruft diese Methode auch [Execute](worker-archetype.md#execute) und [Terminate](worker-archetype.md#terminate) für dasselbe Objekt.  

##  <a name="initialize"></a>  CNonStatelessWorker::Initialize

Implementierung von [WorkerArchetype::Initialize](worker-archetype.md#initialize).

```
BOOL Initialize(void* /* pvParam */) throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt immer "true" zurück.

### <a name="remarks"></a>Hinweise

Diese Klasse führt keine Initialisierungen `Initialize`.

##  <a name="requesttype"></a>  CNonStatelessWorker::RequestType

Implementierung von [WorkerArchetype::RequestType](worker-archetype.md#requesttype).

```
typedef Worker::RequestType RequestType;
```

### <a name="remarks"></a>Hinweise

Diese Klasse behandelt, denselben Typ von Arbeitselement wie die Klasse für den *Worker* Template-Parameter. Finden Sie unter [CNonStatelessWorker-Übersicht](../../atl/reference/cnonstatelessworker-class.md) Details.

##  <a name="terminate"></a>  CNonStatelessWorker::Terminate

Implementierung von [WorkerArchetype::Terminate](worker-archetype.md#terminate).

```
void Terminate(void* /* pvParam */) throw();
```

### <a name="remarks"></a>Hinweise

Diese Klasse führt keine Bereinigungen `Terminate`.

## <a name="see-also"></a>Siehe auch

[CThreadPool-Klasse](../../atl/reference/cthreadpool-class.md)<br/>
[Worker Archetype](../../atl/reference/worker-archetype.md)<br/>
[Klassen](../../atl/reference/atl-classes.md)
