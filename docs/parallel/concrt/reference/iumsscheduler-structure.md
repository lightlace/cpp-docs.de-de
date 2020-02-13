---
title: IUMSScheduler-Struktur
ms.date: 11/04/2016
f1_keywords:
- IUMSScheduler
- CONCRTRM/concurrency::IUMSScheduler
- CONCRTRM/concurrency::IUMSScheduler::IUMSScheduler::SetCompletionList
helpviewer_keywords:
- IUMSScheduler structure
ms.assetid: 3a500225-4e02-4849-bb56-d744865f5870
ms.openlocfilehash: 45df744a9850510006e4bf887c8ed61b000a8e5c
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77139993"
---
# <a name="iumsscheduler-structure"></a>IUMSScheduler-Struktur

Eine Schnittstelle zu der Abstraktion eines Arbeitsplaners, der planbare Threads vom Ressourcen-Manager der Concurrency Runtime im Benutzermodus erwartet. Der Ressourcen-Manager verwendet diese Schnittstelle für die Kommunikation mit UMS-Threadplanern. Die `IUMSScheduler` -Schnittstelle erbt von der `IScheduler` -Schnittstelle.

## <a name="syntax"></a>Syntax

```cpp
struct IUMSScheduler : public IScheduler;
```

## <a name="members"></a>Members

### <a name="public-methods"></a>Öffentliche Methoden

|Name|BESCHREIBUNG|
|----------|-----------------|
|[IUMSScheduler:: SetCompletionList](#setcompletionlist)|Weist einem ums-Thread Planer eine `IUMSCompletionList`-Schnittstelle zu.|

## <a name="remarks"></a>Bemerkungen

Wenn Sie einen benutzerdefinierten Planer implementieren, der mit dem Ressourcen-Manager kommuniziert, und Sie möchten, dass UMS-Threads anstelle von normalen Win32-Threads an den Scheduler übergeben werden, sollten Sie eine Implementierung der `IUMSScheduler` Schnittstelle bereitstellen. Außerdem sollten Sie den Richtlinien Wert für den Schlüssel `SchedulerKind` der Scheduler-Richtlinie so festlegen, dass er `UmsThreadDefault`wird. Wenn die Richtlinie ums-Thread angibt, muss die `IScheduler`-Schnittstelle, die als Parameter an die [IResourceManager:: RegisterScheduler](iresourcemanager-structure.md#registerscheduler) -Methode übergeben wird, eine `IUMSScheduler`-Schnittstelle sein.

Der Ressourcen-Manager ist in der Lage, die Threads nur auf Betriebssystemen mit dem ums-Feature zu übergeben. 64-Bit-Betriebssysteme mit Version Windows 7 und höher unterstützen Threads. Wenn Sie eine Scheduler-Richtlinie erstellen, bei der der `SchedulerKind` Key auf den Wert festgelegt ist `UmsThreadDefault` und die zugrunde liegende Plattform keine ums unterstützt, wird der Wert des `SchedulerKind` Schlüssels für diese Richtlinie in den Wert `ThreadScheduler`geändert. Sie sollten diesen Richtlinien Wert immer zurück lesen, bevor Sie den Empfang von UMS-Threads erwarten.

Die `IUMSScheduler`-Schnittstelle ist ein Ende eines bidirektionalen Kommunikationskanals zwischen einem Scheduler und dem Ressourcen-Manager. Das andere Ende wird durch die `IResourceManager`-und `ISchedulerProxy`-Schnittstellen dargestellt, die vom Ressourcen-Manager implementiert werden.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[IScheduler](ischeduler-structure.md)

`IUMSScheduler`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** concrtrm. h

**Namespace:** Parallelität

## <a name="setcompletionlist"></a>IUMSScheduler:: SetCompletionList-Methode

Weist einem ums-Thread Planer eine `IUMSCompletionList`-Schnittstelle zu.

```cpp
virtual void SetCompletionList(_Inout_ IUMSCompletionList* pCompletionList) = 0;
```

### <a name="parameters"></a>Parameter

*pcompletionlist*<br/>
Die Vervollständigungs Listen-Schnittstelle für den Scheduler. Pro Scheduler ist eine einzelne Liste vorhanden.

### <a name="remarks"></a>Bemerkungen

Der Ressourcen-Manager ruft diese Methode für einen Planer auf, der angibt, dass es sich um Threads handelt, nachdem der Scheduler eine anfängliche Zuordnung von Ressourcen angefordert hat. Der Planer kann die `IUMSCompletionList`-Schnittstelle verwenden, um zu bestimmen, wann die Blockierung der ums-Thread Proxys Der Zugriff auf diese Schnittstelle ist nur über einen Thread Proxy zulässig, der auf einem virtuellen Prozessor Stamm ausgeführt wird, der dem ums-Scheduler zugewiesen ist.

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[PolicyElementKey](concurrency-namespace-enums.md)<br/>
[IScheduler-Struktur](ischeduler-structure.md)<br/>
[IUMSCompletionList-Struktur](iumscompletionlist-structure.md)<br/>
[IResourceManager-Struktur](iresourcemanager-structure.md)
