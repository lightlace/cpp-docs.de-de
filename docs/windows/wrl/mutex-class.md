---
title: Mutex-Klasse
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Mutex
- corewrappers/Microsoft::WRL::Wrappers::Mutex::Lock
- corewrappers/Microsoft::WRL::Wrappers::Mutex::Mutex
- corewrappers/Microsoft::WRL::Wrappers::Mutex::operator=
helpviewer_keywords:
- Microsoft::WRL::Wrappers::Mutex class
- Microsoft::WRL::Wrappers::Mutex::Lock method
- Microsoft::WRL::Wrappers::Mutex::Mutex, constructor
- Microsoft::WRL::Wrappers::Mutex::operator= operator
ms.assetid: 682a0963-721c-46a2-8871-000e9997505b
ms.openlocfilehash: 93de43ac7e5314501d0391e2cde862ba32be0b4b
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "54337317"
---
# <a name="mutex-class"></a>Mutex-Klasse

Stellt ein Synchronisierungsobjekt, das ausschließlich auf eine freigegebene Ressource steuert.

## <a name="syntax"></a>Syntax

```cpp
class Mutex : public HandleT<HandleTraits::MutexTraits>;
```

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

Name       | Beschreibung
---------- | ------------------------------------------------------
`SyncLock` | Ein Synonym für eine Klasse, die synchrone Sperren unterstützt.

### <a name="public-constructor"></a>Öffentlicher Konstruktor

name                   | Beschreibung
---------------------- | ------------------------------------------------
[Mutex::Mutex](#mutex) | Initialisiert eine neue Instanz der `Mutex`-Klasse.

### <a name="public-members"></a>Öffentliche Member

name                 | Beschreibung
-------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------
[Mutex::Lock](#lock) | Wartet, bis das aktuelle Objekt, oder die `Mutex` Objekt verknüpft, die mit dem angegebenen Handle, Versionen, die den Mutex oder das angegebene Timeoutintervall verstrichen ist.

### <a name="public-operator"></a>Öffentlicher Operator

name                                 | Beschreibung
------------------------------------ | ---------------------------------------------------------------------------
[Mutex::operator=](#operator-assign) | Zugewiesen (bewegt) der angegebenen `Mutex` -Objekt mit dem aktuellen `Mutex` Objekt.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`Mutex`

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="lock"></a>Mutex::Lock

Wartet, bis das aktuelle Objekt, oder die `Mutex` Objekt verknüpft, die mit dem angegebenen Handle, Versionen, die den Mutex oder das angegebene Timeoutintervall verstrichen ist.

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

*milliseconds*<br/>
Das Timeoutintervall in Millisekunden. Der Standardwert ist UNENDLICH sein, was die unbegrenzt wartet.

*h*<br/>
Das Handle für ein `Mutex` Objekt.

### <a name="return-value"></a>Rückgabewert

## <a name="mutex"></a>Mutex::Mutex

Initialisiert eine neue Instanz der `Mutex`-Klasse.

```cpp
explicit Mutex(
   HANDLE h
);

Mutex(
   _Inout_ Mutex&& h
);
```

### <a name="parameters"></a>Parameter

*h*<br/>
Ein Handle oder einen Rvalue-Verweis auf ein Handle, um eine `Mutex` Objekt.

### <a name="remarks"></a>Hinweise

Der erste Konstruktor initialisiert ein `Mutex` Objekt aus dem angegebenen Handle. Der zweite Konstruktor initialisiert ein `Mutex` -Objekt aus dem angegebenen Handle, und klicken Sie dann wechselt der Besitz des Mutex, mit dem aktuellen `Mutex` Objekt.

## <a name="operator-assign"></a>Mutex::operator=

Zugewiesen (bewegt) der angegebenen `Mutex` -Objekt mit dem aktuellen `Mutex` Objekt.

```cpp
Mutex& operator=(
   _Inout_ Mutex&& h
);
```

### <a name="parameters"></a>Parameter

*h*<br/>
Ein Rvalue-Verweis auf eine `Mutex` Objekt.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das aktuelle `Mutex` Objekt.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter den **verschieben Semantik** Abschnitt [Rvalue-Verweisdeklarator: & &](../../cpp/rvalue-reference-declarator-amp-amp.md).
