---
title: IUMSThreadProxy-Struktur
ms.date: 11/04/2016
f1_keywords:
- IUMSThreadProxy
- CONCRTRM/concurrency::IUMSThreadProxy
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::EnterCriticalRegion
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::EnterHyperCriticalRegion
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::ExitCriticalRegion
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::ExitHyperCriticalRegion
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::GetCriticalRegionType
helpviewer_keywords:
- IUMSThreadProxy structure
ms.assetid: 61c69b7e-5c37-4048-bcb4-e75c536afd86
ms.openlocfilehash: f4fb43a4223cad8cc63049d2a0f8345e48b90f17
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77139961"
---
# <a name="iumsthreadproxy-structure"></a>IUMSThreadProxy-Struktur

Eine Abstraktion für einen Thread der Ausführung. Wenn dem Planer im Benutzermodus planbare (UMS) Threads gewährt werden sollen, legen Sie den Wert für das Planerrichtlinienelement `SchedulerKind` auf `UmsThreadDefault` fest, und implementieren Sie die `IUMSScheduler`-Schnittstelle. UMS-Threads werden nur unter 64-Bit-Betriebssystemen mit Version Windows 7 und höher unterstützt.

## <a name="syntax"></a>Syntax

```cpp
struct IUMSThreadProxy : public IThreadProxy;
```

## <a name="members"></a>Members

### <a name="public-methods"></a>Öffentliche Methoden

|Name|BESCHREIBUNG|
|----------|-----------------|
|[Iumsthloproxy:: entercriticalregion](#entercriticalregion)|Wird aufgerufen, um einen kritischen Bereich einzugeben. In einer kritischen Region werden vom Scheduler keine asynchronen Blockierungs Vorgänge beobachtet, die während der Region durchgeführt werden. Dies bedeutet, dass der Scheduler für einen ums-Thread nicht erneut für Seiten Fehler, Thread Suspendierungen, Kernel-asynchrone Prozedur Aufrufe (APCs) usw. eingegeben wird.|
|[Iumsthloproxy:: EnterHyperCriticalRegion](#enterhypercriticalregion)|Wird aufgerufen, um einen hyperkritischen Bereich einzugeben. Im Rahmen eines hyperkritischen Bereichs werden vom Scheduler keine blockierenden Vorgänge beobachtet, die während des Bereichs auftreten. Dies bedeutet, dass der Scheduler nicht erneut zum Blockieren von Funktionsaufrufen, bei einem Sperr Abruf versucht wird, die Blockierung, Seiten Fehler, Thread Suspendierungen, asynchrone Kernel Prozedur Aufrufe (APCs) usw. für einen ums-Thread ausführen.|
|[Iumsthlesproxy:: ExitCriticalRegion](#exitcriticalregion)|Wird aufgerufen, um einen kritischen Bereich zu beenden.|
|[Iumsthloproxy:: ExitHyperCriticalRegion](#exithypercriticalregion)|Wird aufgerufen, um einen hyperkritischen Bereich zu beenden.|
|[Iumsthlesproxy:: getcriticalregiontype](#getcriticalregiontype)|Gibt die Art der kritischen Region zurück, in der sich der Thread Proxy befindet. Da es sich bei den hyperkritischen Regionen um eine übergeordnete Gruppe kritischer Regionen handelt, wird `InsideHyperCriticalRegion` zurückgegeben, wenn Code eine kritische Region und dann eine hyperkritische Region eingegeben hat.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[IThreadProxy](ithreadproxy-structure.md)

`IUMSThreadProxy`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** concrtrm. h

**Namespace:** Parallelität

## <a name="entercriticalregion"></a>Iumsthlesproxy:: entercriticalregion-Methode

Wird aufgerufen, um einen kritischen Bereich einzugeben. In einer kritischen Region werden vom Scheduler keine asynchronen Blockierungs Vorgänge beobachtet, die während der Region durchgeführt werden. Dies bedeutet, dass der Scheduler für einen ums-Thread nicht erneut für Seiten Fehler, Thread Suspendierungen, Kernel-asynchrone Prozedur Aufrufe (APCs) usw. eingegeben wird.

```cpp
virtual int EnterCriticalRegion() = 0;
```

### <a name="return-value"></a>Rückgabewert

Die neue Tiefe des kritischen Bereichs. Kritische Bereiche sind Wiedereinstiegs fähig.

## <a name="enterhypercriticalregion"></a>Iumsthlesproxy:: EnterHyperCriticalRegion-Methode

Wird aufgerufen, um einen hyperkritischen Bereich einzugeben. Im Rahmen eines hyperkritischen Bereichs werden vom Scheduler keine blockierenden Vorgänge beobachtet, die während des Bereichs auftreten. Dies bedeutet, dass der Scheduler nicht erneut zum Blockieren von Funktionsaufrufen, bei einem Sperr Abruf versucht wird, die Blockierung, Seiten Fehler, Thread Suspendierungen, asynchrone Kernel Prozedur Aufrufe (APCs) usw. für einen ums-Thread ausführen.

```cpp
virtual int EnterHyperCriticalRegion() = 0;
```

### <a name="return-value"></a>Rückgabewert

Die neue Tiefe der hyperkritischen Region. Hyperkritische Regionen sind Wiedereinstiegs fähig.

### <a name="remarks"></a>Bemerkungen

Der Planer muss besonders sorgfältig darauf achten, welche Methoden er aufruft und welche Sperren er in solchen Regionen erhält. Wenn Code in einem solchen Bereich bei einer Sperre blockiert wird, die von dem Planer für die Planung zuständig ist, kann der Deadlock folgen.

## <a name="exitcriticalregion"></a>Iumsthlesproxy:: ExitCriticalRegion-Methode

Wird aufgerufen, um einen kritischen Bereich zu beenden.

```cpp
virtual int ExitCriticalRegion() = 0;
```

### <a name="return-value"></a>Rückgabewert

Die neue Tiefe des kritischen Bereichs. Kritische Bereiche sind Wiedereinstiegs fähig.

## <a name="exithypercriticalregion"></a>Iumsthlesproxy:: ExitHyperCriticalRegion-Methode

Wird aufgerufen, um einen hyperkritischen Bereich zu beenden.

```cpp
virtual int ExitHyperCriticalRegion() = 0;
```

### <a name="return-value"></a>Rückgabewert

Die neue Tiefe der hyperkritischen Region. Hyperkritische Regionen sind Wiedereinstiegs fähig.

## <a name="getcriticalregiontype"></a>Iumsthlesproxy:: getcriticalregiontype-Methode

Gibt die Art der kritischen Region zurück, in der sich der Thread Proxy befindet. Da es sich bei den hyperkritischen Regionen um eine übergeordnete Gruppe kritischer Regionen handelt, wird `InsideHyperCriticalRegion` zurückgegeben, wenn Code eine kritische Region und dann eine hyperkritische Region eingegeben hat.

```cpp
virtual CriticalRegionType GetCriticalRegionType() const = 0;
```

### <a name="return-value"></a>Rückgabewert

Der Typ der kritischen Region, in der sich der Thread Proxy befindet.

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[IUMSScheduler-Struktur](iumsscheduler-structure.md)
