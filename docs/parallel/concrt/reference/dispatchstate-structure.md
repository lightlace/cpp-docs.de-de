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
ms.openlocfilehash: 69e00893373ccca6e2ed676fbb7f5a109c49efdf
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77143045"
---
# <a name="dispatchstate-structure"></a>DispatchState-Struktur

Die `DispatchState`-Struktur wird zur Zustandsübertragung auf die `IExecutionContext::Dispatch`-Methode verwendet. Sie beschreibt die Umstände, unter denen die `Dispatch`-Methode für eine `IExecutionContext`-Schnittstelle aufgerufen wird.

## <a name="syntax"></a>Syntax

```cpp
struct DispatchState;
```

## <a name="members"></a>Members

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[DispatchState::D ispatchstate](#ctor)|Erstellt ein neues `DispatchState`-Objekt.|

### <a name="public-data-members"></a>Öffentliche Datenelemente

|Name|BESCHREIBUNG|
|----------|-----------------|
|[DispatchState:: m_dispatchStateSize](#m_dispatchstatesize)|Größe dieser Struktur, die für die Versionsverwaltung verwendet wird.|
|[DispatchState:: m_fIsPreviousContextAsynchronouslyBlocked](#m_fispreviouscontextasynchronouslyblocked)|Gibt an, ob dieser Kontext die `Dispatch` Methode eingegeben hat, da der vorherige Kontext asynchron blockiert wurde. Dies wird nur im ums-Planungs Kontext verwendet, und wird auf den Wert `0` für alle anderen Ausführungs Kontexte festgelegt.|
|[DispatchState:: m_reserved](#m_reserved)|Bits, die für die Übergabe zukünftiger Informationen reserviert sind.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`DispatchState`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** concrtrm. h

**Namespace:** Parallelität

## <a name="ctor"></a>DispatchState::D ispatchstate-Konstruktor

Erstellt ein neues `DispatchState`-Objekt.

```cpp
DispatchState();
```

## <a name="m_dispatchstatesize"></a>DispatchState:: m_dispatchStateSize-Datenmember

Größe dieser Struktur, die für die Versionsverwaltung verwendet wird.

```cpp
unsigned long m_dispatchStateSize;
```

## <a name="m_fispreviouscontextasynchronouslyblocked"></a>DispatchState:: m_fIsPreviousContextAsynchronouslyBlocked-Datenmember

Gibt an, ob dieser Kontext die `Dispatch` Methode eingegeben hat, da der vorherige Kontext asynchron blockiert wurde. Dies wird nur im ums-Planungs Kontext verwendet, und wird auf den Wert `0` für alle anderen Ausführungs Kontexte festgelegt.

```cpp
unsigned int m_fIsPreviousContextAsynchronouslyBlocked : 1;
```

## <a name="m_reserved"></a>DispatchState:: m_reserved-Datenmember

Bits, die für die Übergabe zukünftiger Informationen reserviert sind.

```cpp
unsigned int m_reserved : 31;
```

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace](concurrency-namespace.md)
