---
title: IUMSThreadProxy-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- IUMSThreadProxy
- CONCRTRM/concurrency::IUMSThreadProxy
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::EnterCriticalRegion
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::EnterHyperCriticalRegion
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::ExitCriticalRegion
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::ExitHyperCriticalRegion
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::GetCriticalRegionType
dev_langs:
- C++
helpviewer_keywords:
- IUMSThreadProxy structure
ms.assetid: 61c69b7e-5c37-4048-bcb4-e75c536afd86
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 573bee042788f03278abc78fbc541c933d693907
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46417383"
---
# <a name="iumsthreadproxy-structure"></a>IUMSThreadProxy-Struktur

Eine Abstraktion für einen Thread der Ausführung. Wenn dem Planer im Benutzermodus planbare (UMS) Threads gewährt werden sollen, legen Sie den Wert für das Planerrichtlinienelement `SchedulerKind` auf `UmsThreadDefault` fest, und implementieren Sie die `IUMSScheduler`-Schnittstelle. UMS-Threads werden nur unter 64-Bit-Betriebssystemen mit Version Windows 7 und höher unterstützt.

## <a name="syntax"></a>Syntax

```
struct IUMSThreadProxy : public IThreadProxy;
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[IUMSThreadProxy:: EnterCriticalRegion](#entercriticalregion)|Wird aufgerufen, um einen kritischen Bereich eingeben. In einem kritischen Bereich, berücksichtigt der Planer nicht asynchronen blockierende Vorgänge, die während des Bereichs stattfinden. Dies bedeutet, dass das Zeitplanungsmodul nicht für Seitenfehler, Threadunterbrechungen, asynchrone Kernelprozeduraufrufe (APCs) und So weiter, ein UMS-Thread erneut geöffnet wird.|
|[IUMSThreadProxy:: EnterHyperCriticalRegion](#enterhypercriticalregion)|Wird aufgerufen, um eine äußerst wichtigen Region einzugeben. In einem äußerst wichtigen Bereich, berücksichtigt der Planer nicht blockierende Vorgänge, die während des Bereichs stattfinden. Dies bedeutet, dass der Planer nicht erneut geöffnet wird für die Funktionsaufrufe, Sperre Abruf versuchen, welcher Block, Seitenfehlern, thread-Unterbrechungen, asynchrone Kernelprozeduraufrufe (APCs), und so weiter, für eine UMS Thread, blockiert.|
|[IUMSThreadProxy:: ExitCriticalRegion](#exitcriticalregion)|Wird aufgerufen, um einen kritischen Bereich zu verlassen.|
|[IUMSThreadProxy:: ExitHyperCriticalRegion](#exithypercriticalregion)|Wird aufgerufen, um einen äußerst wichtigen Bereich zu verlassen.|
|[IUMSThreadProxy::GetCriticalRegionType](#getcriticalregiontype)|Gibt zurück, welche Art von kritischen Bereich innerhalb der Threadproxy befindet. Da sich wichtige Bereiche eine Obermenge von kritischen Bereich sind, wenn der Code eingegeben hat, einen kritischen Bereich, und klicken Sie dann eine äußerst wichtigen Region `InsideHyperCriticalRegion` zurückgegeben werden.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[IThreadProxy](ithreadproxy-structure.md)

`IUMSThreadProxy`

## <a name="requirements"></a>Anforderungen

**Header:** concrtrm.h

**Namespace:** Parallelität

##  <a name="entercriticalregion"></a>  IUMSThreadProxy:: EnterCriticalRegion-Methode

Wird aufgerufen, um einen kritischen Bereich eingeben. In einem kritischen Bereich, berücksichtigt der Planer nicht asynchronen blockierende Vorgänge, die während des Bereichs stattfinden. Dies bedeutet, dass das Zeitplanungsmodul nicht für Seitenfehler, Threadunterbrechungen, asynchrone Kernelprozeduraufrufe (APCs) und So weiter, ein UMS-Thread erneut geöffnet wird.

```
virtual int EnterCriticalRegion() = 0;
```

### <a name="return-value"></a>Rückgabewert

Die neue Tiefe eines kritischen Bereichs. Kritische Bereiche sind wiedereintrittsfähig.

##  <a name="enterhypercriticalregion"></a>  IUMSThreadProxy:: EnterHyperCriticalRegion-Methode

Wird aufgerufen, um eine äußerst wichtigen Region einzugeben. In einem äußerst wichtigen Bereich, berücksichtigt der Planer nicht blockierende Vorgänge, die während des Bereichs stattfinden. Dies bedeutet, dass der Planer nicht erneut geöffnet wird für die Funktionsaufrufe, Sperre Abruf versuchen, welcher Block, Seitenfehlern, thread-Unterbrechungen, asynchrone Kernelprozeduraufrufe (APCs), und so weiter, für eine UMS Thread, blockiert.

```
virtual int EnterHyperCriticalRegion() = 0;
```

### <a name="return-value"></a>Rückgabewert

Die neue Tiefe eines hyper-kritischen Bereichs. Hyper-kritische Bereiche sind wiedereintrittsfähig.

### <a name="remarks"></a>Hinweise

Der Scheduler muss besonders vorsichtig, welche Methoden, die er aufruft und Sperren in Bereichen erhält. Wenn Code in solchen Bereichs auf eine Sperre, die von einem Element gehalten wird, dass der Planer blockiert für die Planung verantwortlich ist, kann Deadlock zur Folge haben.

##  <a name="exitcriticalregion"></a>  IUMSThreadProxy:: ExitCriticalRegion-Methode

Wird aufgerufen, um einen kritischen Bereich zu verlassen.

```
virtual int ExitCriticalRegion() = 0;
```

### <a name="return-value"></a>Rückgabewert

Die neue Tiefe eines kritischen Bereichs. Kritische Bereiche sind wiedereintrittsfähig.

##  <a name="exithypercriticalregion"></a>  IUMSThreadProxy:: ExitHyperCriticalRegion-Methode

Wird aufgerufen, um einen äußerst wichtigen Bereich zu verlassen.

```
virtual int ExitHyperCriticalRegion() = 0;
```

### <a name="return-value"></a>Rückgabewert

Die neue Tiefe eines hyper-kritischen Bereichs. Hyper-kritische Bereiche sind wiedereintrittsfähig.

##  <a name="getcriticalregiontype"></a>  IUMSThreadProxy:: GetCriticalRegionType-Methode

Gibt zurück, welche Art von kritischen Bereich innerhalb der Threadproxy befindet. Da sich wichtige Bereiche eine Obermenge von kritischen Bereich sind, wenn der Code eingegeben hat, einen kritischen Bereich, und klicken Sie dann eine äußerst wichtigen Region `InsideHyperCriticalRegion` zurückgegeben werden.

```
virtual CriticalRegionType GetCriticalRegionType() const = 0;
```

### <a name="return-value"></a>Rückgabewert

Der Typ des kritischen Bereichs, die der Threadproxy befindet.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[IUMSScheduler-Struktur](iumsscheduler-structure.md)
