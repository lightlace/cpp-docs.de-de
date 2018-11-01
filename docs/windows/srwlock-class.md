---
title: SRWLock-Klasse
ms.date: 09/25/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::SRWLock
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::LockExclusive
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::LockShared
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::SRWLock
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::SRWLock_
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::~SRWLock
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::TryLockExclusive
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::TryLockShared
helpviewer_keywords:
- Microsoft::WRL::Wrappers::SRWLock class
- Microsoft::WRL::Wrappers::SRWLock::LockExclusive method
- Microsoft::WRL::Wrappers::SRWLock::LockShared method
- Microsoft::WRL::Wrappers::SRWLock::SRWLock, constructor
- Microsoft::WRL::Wrappers::SRWLock::SRWLock_ data member
- Microsoft::WRL::Wrappers::SRWLock::~SRWLock, destructor
- Microsoft::WRL::Wrappers::SRWLock::TryLockExclusive method
- Microsoft::WRL::Wrappers::SRWLock::TryLockShared method
ms.assetid: 4fa250e3-5f29-4b06-ac24-61b6c04ade93
ms.openlocfilehash: 6d4a504d9465c858af59a88cf0ef611bf88c3fde
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50579217"
---
# <a name="srwlock-class"></a>SRWLock-Klasse

Stellt eine slim Reader-/Writer-Sperre.

## <a name="syntax"></a>Syntax

```cpp
class SRWLock;
```

## <a name="remarks"></a>Hinweise

Eine slim Reader-/Writer-Sperre wird zum Synchronisieren des Zugriffs über Threads auf ein Objekt oder eine Ressource verwendet. Weitere Informationen finden Sie unter [Synchronisierungsfunktionen](/windows/desktop/Sync/synchronization-functions).

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

Name                | Beschreibung
------------------- | -------------------------------------------------------------------
`SyncLockExclusive` | Synonym für einen `SRWLock` -Objekt, das im exklusiven Modus abgerufen wird.
`SyncLockShared`    | Synonym für einen `SRWLock` -Objekt, das im freigegebenen Modus abgerufen wird.

### <a name="public-constructors"></a>Öffentliche Konstruktoren

Name                                     | Beschreibung
---------------------------------------- | --------------------------------------------------
[SRWLOCK:: SRWLOCK](#srwlock-constructor) | Initialisiert eine neue Instanz der `SRWLock`-Klasse.
[SRWLock:: ~ SRWLock](#tilde-srwlock)      | Hebt die Initialisierung einer Instanz von der `SRWLock` Klasse.

### <a name="public-methods"></a>Öffentliche Methoden

Name                                           | Beschreibung
---------------------------------------------- | -------------------------------------------------------------------------------------------------------
[SRWLOCK:: Lockexclusive](#lockexclusive)       | Ruft eine `SRWLock` Objekt im exklusiven Modus.
[SRWLOCK:: Lockshared](#lockshared)             | Ruft eine `SRWLock` Objekt im freigegebenen Modus.
[SRWLOCK:: Trylockexclusive](#trylockexclusive) | Versucht, für eine `SRWLock` Objekt im exklusiven Modus für den aktuellen oder angegebenen `SRWLock` Objekt.
[SRWLOCK:: Trylockshared](#trylockshared)       | Versucht, für eine `SRWLock` Objekt im freigegebenen Modus für den aktuellen oder angegebenen `SRWLock` Objekt.

### <a name="protected-data-member"></a>Geschützte Datenmember

name                                      | Beschreibung
----------------------------------------- | -----------------------------------------------------------------------
[SRWLOCK:: Srwlock_](#srwlock-data-member) | Enthält die zugrunde liegende Sperre-Variable für den aktuellen `SRWLock` Objekt.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`SRWLock`

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="tilde-srwlock"></a>SRWLock:: ~ SRWLock

Hebt die Initialisierung einer Instanz von der `SRWLock` Klasse.

```cpp
~SRWLock();
```

## <a name="lockexclusive"></a>SRWLOCK:: Lockexclusive

Ruft eine `SRWLock` Objekt im exklusiven Modus.

```cpp
SyncLockExclusive LockExclusive();

static SyncLockExclusive LockExclusive(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>Parameter

*lock*<br/>
Zeiger auf ein `SRWLock` Objekt.

### <a name="return-value"></a>Rückgabewert

Ein `SRWLock` Objekt im exklusiven Modus.

## <a name="lockshared"></a>SRWLOCK:: Lockshared

Ruft eine `SRWLock` Objekt im freigegebenen Modus.

```cpp
SyncLockShared LockShared();

static SyncLockShared LockShared(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>Parameter

*lock*<br/>
Zeiger auf ein `SRWLock` Objekt.

### <a name="return-value"></a>Rückgabewert

Ein `SRWLock` Objekt im freigegebenen Modus.

## <a name="srwlock-constructor"></a>SRWLOCK:: SRWLOCK

Initialisiert eine neue Instanz der `SRWLock`-Klasse.

```cpp
SRWLock();
```

## <a name="srwlock-data-member"></a>SRWLOCK:: Srwlock_

Enthält die zugrunde liegende Sperre-Variable für den aktuellen `SRWLock` Objekt.

```cpp
SRWLOCK SRWLock_;
```

## <a name="trylockexclusive"></a>SRWLOCK:: Trylockexclusive

Versucht, für eine `SRWLock` Objekt im exklusiven Modus für den aktuellen oder angegebenen `SRWLock` Objekt. Wenn der Aufruf erfolgreich ist, wird der aufrufende Thread den Besitz der Sperre.

```cpp
SyncLockExclusive TryLockExclusive();

static SyncLockExclusive TryLockExclusive(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>Parameter

*lock*<br/>
Zeiger auf ein `SRWLock` Objekt.

### <a name="return-value"></a>Rückgabewert

Bei erfolgreicher Ausführung einen `SRWLock` Objekt im exklusiven Modus und der aufrufende Thread übernimmt den Besitz der Sperre. Andernfalls ein `SRWLock` Objekt, dessen Status ungültig ist.

## <a name="trylockshared"></a>SRWLOCK:: Trylockshared

Versucht, für eine `SRWLock` Objekt im freigegebenen Modus für den aktuellen oder angegebenen `SRWLock` Objekt.

```cpp
WRL_NOTHROW SyncLockShared TryLockShared();
WRL_NOTHROW static SyncLockShared TryLockShared(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>Parameter

*lock*<br/>
Zeiger auf ein `SRWLock` Objekt.

### <a name="return-value"></a>Rückgabewert

Bei erfolgreicher Ausführung einen `SRWLock` Objekt im Modus für gemeinsame Nutzung und der aufrufende Thread übernimmt den Besitz der Sperre. Andernfalls ein `SRWLock` Objekt, dessen Status ungültig ist.
