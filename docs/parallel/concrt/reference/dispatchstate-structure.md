---
title: DispatchState-Struktur
ms.date: 11/04/2016
f1_keywords:
- DispatchState
- CONCRTRM/concurrency::DispatchState
- CONCRTRM/concurrency::DispatchState::DispatchState::DispatchState
- CONCRTRM/concurrency::DispatchState::DispatchState::m_dispatchStateSize
- CONCRTRM/concurrency::DispatchState::DispatchState::m_fIsPreviousContextAsynchronouslyBlocked
- CONCRTRM/concurrency::DispatchState::DispatchState::m_reserved
helpviewer_keywords:
- DispatchState structure
ms.assetid: 8c52546e-1650-48a0-985f-7e4a0fc26a90
ms.openlocfilehash: 4c15fc0ba9c78d8b6416cd88480c8ada6e3febf1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50603562"
---
# <a name="dispatchstate-structure"></a>DispatchState-Struktur

Die `DispatchState`-Struktur wird zur Zustandsübertragung auf die `IExecutionContext::Dispatch`-Methode verwendet. Sie beschreibt die Umstände, unter denen die `Dispatch`-Methode für eine `IExecutionContext`-Schnittstelle aufgerufen wird.

## <a name="syntax"></a>Syntax

```
struct DispatchState;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[DispatchState::DispatchState](#ctor)|Erstellt ein neues `DispatchState`-Objekt.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[DispatchState::m_dispatchStateSize](#m_dispatchstatesize)|Die Größe dieser Struktur, die für die versionsverwaltung verwendet wird.|
|[DispatchState::m_fIsPreviousContextAsynchronouslyBlocked](#m_fispreviouscontextasynchronouslyblocked)|Gibt an, ob die diesem Kontext gewechselt hat die `Dispatch` Methode asynchron der vorherige Kontext zu blockiert. Dies ist nur für die UMS Planungskontext verwendet und auf den Wert festgelegt ist `0` für allen anderen Ausführungskontexten.|
|[DispatchState::m_reserved](#m_reserved)|Bits reserviert für zukünftige Informationen.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`DispatchState`

## <a name="requirements"></a>Anforderungen

**Header:** concrtrm.h

**Namespace:** Parallelität

##  <a name="ctor"></a>  DispatchState:: DispatchState-Konstruktor

Erstellt ein neues `DispatchState`-Objekt.

```
DispatchState();
```

##  <a name="m_dispatchstatesize"></a>  DispatchState:: M_dispatchstatesize-Datenmember

Die Größe dieser Struktur, die für die versionsverwaltung verwendet wird.

```
unsigned long m_dispatchStateSize;
```

##  <a name="m_fispreviouscontextasynchronouslyblocked"></a>  DispatchState:: M_fispreviouscontextasynchronouslyblocked-Datenmember

Gibt an, ob die diesem Kontext gewechselt hat die `Dispatch` Methode asynchron der vorherige Kontext zu blockiert. Dies ist nur für die UMS Planungskontext verwendet und auf den Wert festgelegt ist `0` für allen anderen Ausführungskontexten.

```
unsigned int m_fIsPreviousContextAsynchronouslyBlocked : 1;
```

##  <a name="m_reserved"></a>  DispatchState:: M_reserved-Datenmember

Bits reserviert für zukünftige Informationen.

```
unsigned int m_reserved : 31;
```

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)
