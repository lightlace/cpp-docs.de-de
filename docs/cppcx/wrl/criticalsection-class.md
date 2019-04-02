---
title: CriticalSection-Klasse
ms.date: 09/24/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::cs_
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::IsValid
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::Lock
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::~CriticalSection
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::CriticalSection
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::TryLock
helpviewer_keywords:
- Microsoft::WRL::Wrappers::CriticalSection class
- Microsoft::WRL::Wrappers::CriticalSection::cs_ data member
- Microsoft::WRL::Wrappers::CriticalSection::IsValid method
- Microsoft::WRL::Wrappers::CriticalSection::Lock method
- Microsoft::WRL::Wrappers::CriticalSection::~CriticalSection, destructor
- Microsoft::WRL::Wrappers::CriticalSection::CriticalSection, constructor
- Microsoft::WRL::Wrappers::CriticalSection::TryLock method
ms.assetid: f2e0a024-71a3-4f6b-99ea-d93a4a608ac4
ms.openlocfilehash: dd34206741ba8fee8b283e22b6e8eefb3b3efb0e
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58785714"
---
# <a name="criticalsection-class"></a>CriticalSection-Klasse

Stellt ein kritisches Abschnittsobjekt dar.

## <a name="syntax"></a>Syntax

```cpp
class CriticalSection;
```

## <a name="members"></a>Member

### <a name="constructor"></a>Konstruktor

Name                                                        | Beschreibung
----------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------
[CriticalSection::CriticalSection](#criticalsection)        | Initialisiert ein Synchronisierungsobjekt, das ist vergleichbar mit dem ein Mutex-Objekt, aber nur die Threads eines einzelnen Prozesses verwendet werden kann.
[CriticalSection::~CriticalSection](#tilde-criticalsection) | Hebt die Initialisierung und zerstört die aktuelle `CriticalSection` Objekt.

### <a name="public-methods"></a>Öffentliche Methoden

Name                                 | Beschreibung
------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------
[CriticalSection::IsValid](#isvalid) | Gibt an, ob der aktuelle kritische Abschnitt gültig ist.
[CriticalSection::Lock](#lock)       | Wartet auf den Besitz des Objekts angegebenen kritischen Abschnitt. Gibt die Funktion zurück, wenn der aufrufende Thread den Besitz gewährt wird.
[CriticalSection::TryLock](#trylock) | Versucht, einen kritischen Abschnitt ohne Blockierung zu geben. Wenn der Aufruf erfolgreich ist, übernimmt der aufrufende Thread den kritischen Abschnitt.

### <a name="protected-data-members"></a>Geschützte Datenmember

Name                        | Beschreibung
--------------------------- | ----------------------------------------
[CriticalSection::cs_](#cs) | Deklariert einen Datenmember des kritischen Abschnitts.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`CriticalSection`

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="tilde-criticalsection"></a>CriticalSection::~CriticalSection

Hebt die Initialisierung und zerstört die aktuelle `CriticalSection` Objekt.

```cpp
WRL_NOTHROW ~CriticalSection();
```

## <a name="criticalsection"></a>CriticalSection::CriticalSection

Initialisiert ein Synchronisierungsobjekt, das ist vergleichbar mit dem ein Mutex-Objekt, aber nur die Threads eines einzelnen Prozesses verwendet werden kann.

```cpp
explicit CriticalSection(
   ULONG spincount = 0
);
```

### <a name="parameters"></a>Parameter

*spincount*<br/>
Die Spin-Anzahl für das Objekt des kritischen Abschnitts. Der Standardwert ist 0.

### <a name="remarks"></a>Hinweise

Weitere Informationen über kritische Abschnitte und Spincounts finden Sie unter den `InitializeCriticalSectionAndSpinCount` Funktion in der `Synchronization` Teil der Windows-API-Dokumentation.

## <a name="cs"></a>CriticalSection::cs_

Deklariert einen Datenmember des kritischen Abschnitts.

```cpp
CRITICAL_SECTION cs_;
```

### <a name="remarks"></a>Hinweise

Dieses Datenelement ist geschützt.

## <a name="isvalid"></a>CriticalSection::IsValid

Gibt an, ob der aktuelle kritische Abschnitt gültig ist.

```cpp
bool IsValid() const;
```

### <a name="return-value"></a>Rückgabewert

Immer in der Standardeinstellung gibt **"true"**.

## <a name="lock"></a>CriticalSection::Lock

Wartet auf den Besitz des Objekts angegebenen kritischen Abschnitt. Gibt die Funktion zurück, wenn der aufrufende Thread den Besitz gewährt wird.

```cpp
SyncLock Lock();

   static SyncLock Lock(
   _In_ CRITICAL_SECTION* cs
);
```

### <a name="parameters"></a>Parameter

*cs*<br/>
Ein Kritischer Abschnitt Benutzer angegebene-Objekt.

### <a name="return-value"></a>Rückgabewert

Eine Sperrobjekt, das verwendet werden kann, um den aktuellen kritischen Abschnitt zu entsperren.

### <a name="remarks"></a>Hinweise

Die erste `Lock` Funktion wirkt sich auf das aktuelle Objekt des kritischen Abschnitts. Die zweite `Lock` Funktion wirkt sich auf einen vom Benutzer angegebenen kritischen Abschnitt.

## <a name="trylock"></a>CriticalSection::TryLock

Versucht, einen kritischen Abschnitt ohne Blockierung zu geben. Wenn der Aufruf erfolgreich ist, übernimmt der aufrufende Thread den kritischen Abschnitt.

```cpp
SyncLock TryLock();

static SyncLock TryLock(
   _In_ CRITICAL_SECTION* cs
);
```

### <a name="parameters"></a>Parameter

*cs*<br/>
Ein Kritischer Abschnitt Benutzer angegebene-Objekt.

### <a name="return-value"></a>Rückgabewert

Einen Wert ungleich NULL, wenn der kritische Abschnitt erfolgreich eingegeben wird oder der aktuelle Thread besitzt bereits den kritischen Abschnitt. NULL, wenn ein anderer Thread den kritischen Abschnitt bereits im Besitz.

### <a name="remarks"></a>Hinweise

Die erste `TryLock` Funktion wirkt sich auf das aktuelle Objekt des kritischen Abschnitts. Die zweite `TryLock` Funktion wirkt sich auf einen vom Benutzer angegebenen kritischen Abschnitt.
