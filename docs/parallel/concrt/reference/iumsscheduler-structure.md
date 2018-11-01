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
ms.openlocfilehash: 0fd1ed90ca30c9c9e6815bb05b516f24b4f9a164
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50513788"
---
# <a name="iumsscheduler-structure"></a>IUMSScheduler-Struktur

Eine Schnittstelle zu der Abstraktion eines Arbeitsplaners, der planbare Threads vom Ressourcen-Manager der Concurrency Runtime im Benutzermodus erwartet. Der Ressourcen-Manager verwendet diese Schnittstelle für die Kommunikation mit UMS-Threadplanern. Die `IUMSScheduler` -Schnittstelle erbt von der `IScheduler` -Schnittstelle.

## <a name="syntax"></a>Syntax

```
struct IUMSScheduler : public IScheduler;
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[IUMSScheduler::SetCompletionList](#setcompletionlist)|Weist eine `IUMSCompletionList` Schnittstelle, um ein UMS-Thread-Planer.|

## <a name="remarks"></a>Hinweise

Wenn Sie einen benutzerdefinierten Planer, der mit dem Resource Manager kommuniziert implementieren und UMS-Threads, die an der Planer statt der gewöhnlichen Win32-Threads übergegeben werden sollen, sollten Sie eine Implementierung bereitstellen der `IUMSScheduler` Schnittstelle. Darüber hinaus sollten Sie festlegen, den Richtlinienwert für den Scheduler-Richtlinienschlüssel `SchedulerKind` sein `UmsThreadDefault`. Wenn die Richtlinie UMS-Thread, gibt die `IScheduler` -Schnittstelle, die als Parameter übergeben wird die [IResourceManager:: RegisterScheduler](iresourcemanager-structure.md#registerscheduler) Methode muss eine `IUMSScheduler` Schnittstelle.

Der Ressourcen-Manager kann Sie nur auf Betriebssystemen UMS-Threads, die die UMS-Funktion übergeben. 64-Bit-Betriebssystemen mit Version Windows 7 und höher unterstützen UMS-Threads. Bei der Erstellung einer Planerrichtlinie mit der `SchedulerKind` Schlüssel festgelegt wird, auf den Wert `UmsThreadDefault` und die zugrunde liegende Plattform unterstützt keine UMS, den Wert des der `SchedulerKind` -Taste auf die Richtlinie wird auf den Wert geändert `ThreadScheduler`. Sie sollten immer wieder der Richtlinienwert lesen, bevor UMS-Threads erhalten möchte.

Die `IUMSScheduler` Schnittstelle ist ein Ende der einen bidirektionalen Kanal für die Kommunikation zwischen einem Planer und der Ressourcen-Manager. Das andere Ende wird dargestellt, durch die `IResourceManager` und `ISchedulerProxy` Schnittstellen, die vom Ressourcen-Manager implementiert werden.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[IScheduler](ischeduler-structure.md)

`IUMSScheduler`

## <a name="requirements"></a>Anforderungen

**Header:** concrtrm.h

**Namespace:** Parallelität

##  <a name="setcompletionlist"></a>  IUMSScheduler:: SetCompletionList-Methode

Weist eine `IUMSCompletionList` Schnittstelle, um ein UMS-Thread-Planer.

```
virtual void SetCompletionList(_Inout_ IUMSCompletionList* pCompletionList) = 0;
```

### <a name="parameters"></a>Parameter

*pCompletionList*<br/>
Die Vervollständigung Liste-Schnittstelle für das Zeitplanungsmodul. Es gibt eine einzelne Liste pro Zeitplanungsmodul.

### <a name="remarks"></a>Hinweise

Der Ressourcen-Manager wird diese Methode für einen Planer aufgerufen, der angibt, dass es UMS-Threads benötigt wird, nachdem der Scheduler eine anfängliche Zuordnung von Ressourcen angefordert hat. Der Planer können die `IUMSCompletionList` Schnittstelle, um zu bestimmen, wann UMS-Threadproxys Blockierung aufgehoben wurde. Es ist nur gültig, auf diese Schnittstelle über ein Threadproxy, der auf einem virtuellen Prozessorstamm zugewiesen, der UMS-Zeitplanungsmodul ausgeführt wird.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[PolicyElementKey](concurrency-namespace-enums.md)<br/>
[IScheduler-Struktur](ischeduler-structure.md)<br/>
[IUMSCompletionList-Struktur](iumscompletionlist-structure.md)<br/>
[IResourceManager-Struktur](iresourcemanager-structure.md)
