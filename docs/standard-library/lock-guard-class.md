---
title: lock_guard-Klasse
ms.date: 11/04/2016
f1_keywords:
- mutex/std::lock_guard
- mutex/std::lock_guard::lock_guard
ms.assetid: 57121f0d-9c50-481c-b971-54e64df864e0
ms.openlocfilehash: 45a01c5fdd431bcfad1eeb5ab0531c11c89e9767
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62413137"
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

*Mtx*<br/>
Ein *mutex type*-Objekt.

### <a name="remarks"></a>Hinweise

Der erste Konstruktor konstruiert ein Objekt des Typs `lock_guard` und Sperren *Mtx*. Wenn *Mtx* ist keiner rekursiven Mutex entspricht, muss dieses entsperrt werden, wenn dieser Konstruktor aufgerufen wird.

Der zweite Konstruktor sperrt nicht *Mtx*. *Mtx* muss gesperrt werden, wenn dieser Konstruktor aufgerufen wird. Der Konstruktor löst keine Ausnahmen aus.

## <a name="dtorlock_guard_destructor"></a> lock_guard::~lock_guard-Destruktor

Entsperrt das `mutex`-Objekt, das an den Konstruktor übergeben wurde.

```cpp
~lock_guard() noexcept;
```

### <a name="remarks"></a>Hinweise

Wenn das `mutex`-Objekt nicht vorhanden ist, wenn der Destruktor ausgeführt wird, ist das Verhalten nicht definiert.

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<mutex>](../standard-library/mutex.md)<br/>
