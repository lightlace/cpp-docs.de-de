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
ms.openlocfilehash: 079f1abe652d8c1610a084f5e1158cc5798d61c4
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69498296"
---
# <a name="srwlock-class"></a>SRWLock-Klasse

Stellt eine schlanke Lese-/Schreibsperre dar.

## <a name="syntax"></a>Syntax

```cpp
class SRWLock;
```

## <a name="remarks"></a>Hinweise

Eine schlanke Lese-/Schreibsperre wird zum Synchronisieren des Zugriffs über Threads auf ein Objekt oder eine Ressource verwendet. Weitere Informationen finden Sie unter [Synchronisierungs Funktionen](/windows/win32/Sync/synchronization-functions).

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

Name                | Beschreibung
------------------- | -------------------------------------------------------------------
`SyncLockExclusive` | Synonym für ein `SRWLock` Objekt, das im exklusiven Modus abgerufen wird.
`SyncLockShared`    | Synonym für ein `SRWLock` Objekt, das im freigegebenen Modus abgerufen wird.

### <a name="public-constructors"></a>Öffentliche Konstruktoren

Name                                     | Beschreibung
---------------------------------------- | --------------------------------------------------
[SRWLock::SRWLock](#srwlock-constructor) | Initialisiert eine neue Instanz der `SRWLock`-Klasse.
[SRWLOCK:: ~ SRWLOCK](#tilde-srwlock)      | Deinitialisiert eine Instanz der `SRWLock` -Klasse.

### <a name="public-methods"></a>Öffentliche Methoden

Name                                           | Beschreibung
---------------------------------------------- | -------------------------------------------------------------------------------------------------------
[SRWLock::LockExclusive](#lockexclusive)       | Ruft ein `SRWLock` -Objekt im exklusiven Modus ab.
[SRWLock::LockShared](#lockshared)             | Ruft ein `SRWLock` Objekt im freigegebenen Modus ab.
[SRWLock::TryLockExclusive](#trylockexclusive) | Versucht, ein `SRWLock` -Objekt im exklusiven Modus für das aktuelle oder das `SRWLock` angegebene-Objekt abzurufen.
[SRWLock::TryLockShared](#trylockshared)       | Versucht, ein `SRWLock` -Objekt im freigegebenen Modus für das aktuelle oder `SRWLock` das angegebene-Objekt abzurufen.

### <a name="protected-data-member"></a>Geschützter Datenmember

Name                                      | Beschreibung
----------------------------------------- | -----------------------------------------------------------------------
[SRWLock::SRWLock_](#srwlock-data-member) | Enthält die zugrunde liegende Sperr Variable für das `SRWLock` aktuelle-Objekt.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`SRWLock`

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers. h

**Namespace:** Microsoft:: WRL:: Wrapper

## <a name="tilde-srwlock"></a>SRWLOCK:: ~ SRWLOCK

Deinitialisiert eine Instanz der `SRWLock` -Klasse.

```cpp
~SRWLock();
```

## <a name="lockexclusive"></a>SRWLock::LockExclusive

Ruft ein `SRWLock` -Objekt im exklusiven Modus ab.

```cpp
SyncLockExclusive LockExclusive();

static SyncLockExclusive LockExclusive(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>Parameter

*lock*<br/>
Zeiger auf ein `SRWLock` -Objekt.

### <a name="return-value"></a>Rückgabewert

Ein `SRWLock` -Objekt im exklusiven Modus.

## <a name="lockshared"></a>SRWLock::LockShared

Ruft ein `SRWLock` Objekt im freigegebenen Modus ab.

```cpp
SyncLockShared LockShared();

static SyncLockShared LockShared(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>Parameter

*lock*<br/>
Zeiger auf ein `SRWLock` -Objekt.

### <a name="return-value"></a>Rückgabewert

Ein `SRWLock` -Objekt im freigegebenen Modus.

## <a name="srwlock-constructor"></a>SRWLock::SRWLock

Initialisiert eine neue Instanz der `SRWLock`-Klasse.

```cpp
SRWLock();
```

## <a name="srwlock-data-member"></a>SRWLock::SRWLock_

Enthält die zugrunde liegende Sperr Variable für das `SRWLock` aktuelle-Objekt.

```cpp
SRWLOCK SRWLock_;
```

## <a name="trylockexclusive"></a>SRWLock::TryLockExclusive

Versucht, ein `SRWLock` -Objekt im exklusiven Modus für das aktuelle oder das `SRWLock` angegebene-Objekt abzurufen. Wenn der Aufruf erfolgreich ist, übernimmt der aufrufende Thread den Besitz der Sperre.

```cpp
SyncLockExclusive TryLockExclusive();

static SyncLockExclusive TryLockExclusive(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>Parameter

*lock*<br/>
Zeiger auf ein `SRWLock` -Objekt.

### <a name="return-value"></a>Rückgabewert

Bei erfolgreicher Ausführung übernimmt `SRWLock` ein Objekt im exklusiven Modus, und der aufrufende Thread übernimmt den Besitz der Sperre. Andernfalls ein `SRWLock` Objekt, dessen Zustand ungültig ist.

## <a name="trylockshared"></a>SRWLock::TryLockShared

Versucht, ein `SRWLock` -Objekt im freigegebenen Modus für das aktuelle oder `SRWLock` das angegebene-Objekt abzurufen.

```cpp
WRL_NOTHROW SyncLockShared TryLockShared();
WRL_NOTHROW static SyncLockShared TryLockShared(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>Parameter

*lock*<br/>
Zeiger auf ein `SRWLock` -Objekt.

### <a name="return-value"></a>Rückgabewert

Bei erfolgreicher Ausführung übernimmt `SRWLock` ein Objekt im freigegebenen Modus und der aufrufende Thread den Besitz der Sperre. Andernfalls ein `SRWLock` Objekt, dessen Zustand ungültig ist.
