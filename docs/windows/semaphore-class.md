---
title: Semaphore-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Semaphore
- corewrappers/Microsoft::WRL::Wrappers::Semaphore::Lock
- corewrappers/Microsoft::WRL::Wrappers::Semaphore::operator=
- corewrappers/Microsoft::WRL::Wrappers::Semaphore::Semaphore
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Wrappers::Semaphore class
- Microsoft::WRL::Wrappers::Semaphore::Lock method
- Microsoft::WRL::Wrappers::Semaphore::operator= operator
- Microsoft::WRL::Wrappers::Semaphore::Semaphore, constructor
ms.assetid: ded53526-17b4-4381-9c60-ea5e77363db6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 78fa5b68bcb55f7d062c1732ab6c30fbe84c22d8
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48789214"
---
# <a name="semaphore-class"></a>Semaphore-Klasse

Stellt ein Synchronisierungsobjekt, das eine freigegebene Ressource steuert, die eine begrenzte Anzahl von Benutzern unterstützen können.

## <a name="syntax"></a>Syntax

```cpp
class Semaphore : public HandleT<HandleTraits::SemaphoreTraits>;
```

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

Name       | Beschreibung
---------- | ------------------------------------------------------
`SyncLock` | Ein Synonym für eine Klasse, die synchrone Sperren unterstützt.

### <a name="public-constructors"></a>Öffentliche Konstruktoren

Name                               | Beschreibung
---------------------------------- | ----------------------------------------------------
[Semaphore:: Semaphore](#semaphore) | Initialisiert eine neue Instanz der `Semaphore`-Klasse.

### <a name="public-methods"></a>Öffentliche Methoden

Name                     | Beschreibung
------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------
[Semaphore:: lock](#lock) | Wartet, bis das aktuelle Objekt, oder das Objekt, das das angegebene Handle zugeordnet ist, in den signalisierten Zustand oder das angegebene Timeoutintervall verstrichen ist.

### <a name="public-operators"></a>Öffentliche Operatoren

Name                                     | Beschreibung
---------------------------------------- | ---------------------------------------------------------------------------------------
[Semaphore:: =](#operator-assign) | Verschiebt das angegebene Handle von einem `Semaphore` -Objekt mit dem aktuellen `Semaphore` Objekt.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`Semaphore`

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="lock"></a>Semaphore:: lock

Wartet, bis das aktuelle Objekt, oder die `Semaphore` zugeordnete Objekt das angegebene Handle im signalisierten Zustand ist, oder das angegebene Timeoutintervall verstrichen.

```cpp
SyncLock Lock(
   DWORD milliseconds = INFINITE
);

static SyncLock Lock(
   HANDLE h,
   DWORD milliseconds = INFINITE
);
```

### <a name="parameters"></a>Parameter

*Millisekunden*<br/>
Das Timeoutintervall in Millisekunden. Der Standardwert ist UNENDLICH sein, was die unbegrenzt wartet.

*h*<br/>
Ein Handle für ein `Semaphore` Objekt.

### <a name="return-value"></a>Rückgabewert

Eine `Details::SyncLockWithStatusT<HandleTraits::SemaphoreTraits>`

## <a name="operator-assign"></a>Semaphore:: =

Verschiebt das angegebene Handle von einem `Semaphore` -Objekt mit dem aktuellen `Semaphore` Objekt.

```cpp
Semaphore& operator=(
   _Inout_ Semaphore&& h
);
```

### <a name="parameters"></a>Parameter

*h*<br/>
Rvalue-Verweis auf eine `Semaphore` Objekt.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das aktuelle `Semaphore` Objekt.

## <a name="semaphore"></a>Semaphore:: Semaphore

Initialisiert eine neue Instanz der `Semaphore`-Klasse.

```cpp
explicit Semaphore(
   HANDLE h
);

WRL_NOTHROW Semaphore(
   _Inout_ Semaphore&& h
);
```

### <a name="parameters"></a>Parameter

*h*<br/>
Ein Handle oder einen Rvalue-Verweis auf eine `Semaphore` Objekt.
