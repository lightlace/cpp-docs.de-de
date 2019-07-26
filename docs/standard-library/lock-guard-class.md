---
title: lock_guard-Klasse
ms.date: 11/04/2016
f1_keywords:
- mutex/std::lock_guard
- mutex/std::lock_guard::lock_guard
ms.assetid: 57121f0d-9c50-481c-b971-54e64df864e0
ms.openlocfilehash: f59860c3aaa9ef7458fe5e30b85b119dede52c72
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68453854"
---
# <a name="lockguard-class"></a>lock_guard-Klasse

Stellt eine Vorlage dar, die zum Erstellen eines Objekts instanziiert werden kann, dessen Destruktor ein `mutex`-Objekt entsperrt.

## <a name="syntax"></a>Syntax

```cpp
template <class Mutex>
class lock_guard;
```

## <a name="remarks"></a>Hinweise

Das Vorlagenargument `Mutex` muss einem *Mutex-Typ* benennen.

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|Beschreibung|
|----------|-----------------|
|`lock_guard::mutex_type`|Synonym für das Vorlagenargument `Mutex`.|

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[lock_guard](#lock_guard)|Erstellt ein `lock_guard`-Objekt.|
|[lock_guard::~lock_guard Destruktor](#dtorlock_guard_destructor)|Entsperrt das `mutex`-Objekt, das an den Konstruktor übergeben wurde.|

## <a name="requirements"></a>Anforderungen

**Header:** \<mutex>

**Namespace:** std

## <a name="lock_guard"></a> lock_guard::lock_guard-Konstruktor

Erstellt ein `lock_guard`-Objekt.

```cpp
explicit lock_guard(mutex_type& Mtx);

lock_guard(mutex_type& Mtx, adopt_lock_t);
```

### <a name="parameters"></a>Parameter

*MTX*\
Ein *mutex type*-Objekt.

### <a name="remarks"></a>Hinweise

Der erste Konstruktor erstellt ein Objekt vom Typ `lock_guard` und sperrt *MTX*. Wenn *MTX* kein rekursiver Mutex ist, muss es entsperrt werden, wenn dieser Konstruktor aufgerufen wird.

Der zweite Konstruktor sperrt *MTX*nicht. *MTX* muss gesperrt werden, wenn dieser Konstruktor aufgerufen wird. Der Konstruktor löst keine Ausnahmen aus.

## <a name="dtorlock_guard_destructor"></a> lock_guard::~lock_guard-Destruktor

Entsperrt das `mutex`-Objekt, das an den Konstruktor übergeben wurde.

```cpp
~lock_guard() noexcept;
```

### <a name="remarks"></a>Hinweise

Wenn das `mutex`-Objekt nicht vorhanden ist, wenn der Destruktor ausgeführt wird, ist das Verhalten nicht definiert.

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)\
[\<mutex>](../standard-library/mutex.md)
