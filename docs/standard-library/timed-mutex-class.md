---
title: timed_mutex-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- mutex/std::timed_mutex
- mutex/std::timed_mutex::timed_mutex
- mutex/std::timed_mutex::lock
- mutex/std::timed_mutex::try_lock
- mutex/std::timed_mutex::try_lock_for
- mutex/std::timed_mutex::try_lock_until
- mutex/std::timed_mutex::unlock
dev_langs:
- C++
ms.assetid: cd198081-6f38-447a-9dba-e06dfbfafe59
author: corob-msft
ms.author: corob
helpviewer_keywords:
- std::timed_mutex [C++]
- std::timed_mutex [C++], timed_mutex
- std::timed_mutex [C++], lock
- std::timed_mutex [C++], try_lock
- std::timed_mutex [C++], try_lock_for
- std::timed_mutex [C++], try_lock_until
- std::timed_mutex [C++], unlock
ms.workload:
- cplusplus
ms.openlocfilehash: a4dc22ed8676c720dd8bde5c8f424915dfa8fe40
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="timedmutex-class"></a>timed_mutex-Klasse

Stellt einen *timed mutex type* dar. Objekte dieses Typs werden verwendet, um den gegenseitigen Ausschluss durch zeitlich begrenzte Blockierung innerhalb eines Programms zu erzwingen.

## <a name="syntax"></a>Syntax

```cpp
class timed_mutex;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[timed_mutex](#timed_mutex)|Erstellt ein `timed_mutex`-Objekt, das nicht gesperrt ist.|
|[timed_mutex::~timed_mutex-Destruktor](#dtortimed_mutex_destructor)|Gibt alle Ressourcen frei, die vom `timed_mutex`-Objekt verwendet werden.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[lock](#lock)|Blockiert den aufrufenden Thread, bis der Thread in den Besitz von `mutex` gelangt.|
|[try_lock](#try_lock)|Versucht, ohne Blockierung in den Besitz von `mutex` zu gelangen.|
|[try_lock_for](#try_lock_for)|Versucht, den Besitz von `mutex` für ein angegebenes Zeitintervall zu erlangen.|
|[try_lock_until](#try_lock_until)|Versucht, den Besitz von `mutex` bis zu einem angegebenen Zeitpunkt zu erlangen.|
|[unlock](#unlock)|Gibt den Besitz von `mutex` frei.|

## <a name="requirements"></a>Anforderungen

**Header:** \<mutex>

**Namespace:** std

## <a name="lock"></a>  timed_mutex:: lock

Blockiert den aufrufenden Thread, bis der Thread in den Besitz von `mutex` gelangt.

```cpp
void lock();
```

### <a name="remarks"></a>Hinweise

Wenn der aufrufende Thread bereits im Besitz von `mutex` ist, so ist das Verhalten nicht definiert.

## <a name="timed_mutex"></a> timed_mutex::timed_mutex-Konstruktor

Erstellt ein `timed_mutex`-Objekt, das nicht gesperrt ist.

```cpp
timed_mutex();
```

## <a name="dtortimed_mutex_destructor"></a> timed_mutex::~timed_mutex-Destruktor

Gibt alle Ressourcen frei, die vom `mutex`-Objekt verwendet werden.

```cpp
~timed_mutex();
```

### <a name="remarks"></a>Hinweise

Wenn das Objekt gesperrt ist, wenn der Destruktor ausgeführt wird, ist das Verhalten nicht definiert.

## <a name="try_lock"></a>  timed_mutex:: try_lock

Versucht, ohne Blockierung in den Besitz von `mutex` zu gelangen.

```cpp
bool try_lock();
```

### <a name="return-value"></a>Rückgabewert

`true`, wenn die Methode erfolgreich in den Besitz von `mutex` gelangt; andernfalls `false`.

### <a name="remarks"></a>Hinweise

Wenn der aufrufende Thread bereits im Besitz von `mutex` ist, so ist das Verhalten nicht definiert.

## <a name="try_lock_for"></a>  timed_mutex:: try_lock_for

Versucht, ohne Blockierung in den Besitz von `mutex` zu gelangen.

```cpp
template <class Rep, class Period>
bool try_lock_for(const chrono::duration<Rep, Period>& Rel_time);
```

### <a name="parameters"></a>Parameter

`Rel_time` Ein [chrono](../standard-library/duration-class.md) Objekt, das die maximale Zeitdauer, die die Methode versucht angibt, den Besitz von gelangen die `mutex`.

### <a name="return-value"></a>Rückgabewert

`true`, wenn die Methode erfolgreich in den Besitz von `mutex` gelangt; andernfalls `false`.

### <a name="remarks"></a>Hinweise

Wenn der aufrufende Thread bereits im Besitz von `mutex` ist, so ist das Verhalten nicht definiert.

## <a name="try_lock_until"></a>  timed_mutex:: try_lock_until

Versucht, ohne Blockierung in den Besitz von `mutex` zu gelangen.

```cpp
template <class Clock, class Duration>
bool try_lock_for(const chrono::time_point<Clock, Duration>& Abs_time);

bool try_lock_until(const xtime* Abs_time);
```

### <a name="parameters"></a>Parameter

`Abs_time` Zeitpunkt, die den Schwellenwert angibt, nach dem die Methode nicht mehr versucht, den Besitz von gelangen, die `mutex`.

### <a name="return-value"></a>Rückgabewert

`true`, wenn die Methode erfolgreich in den Besitz von `mutex` gelangt; andernfalls `false`.

### <a name="remarks"></a>Hinweise

Wenn der aufrufende Thread bereits im Besitz von `mutex` ist, so ist das Verhalten nicht definiert.

## <a name="unlock"></a>  timed_mutex:: Unlock

Gibt den Besitz von `mutex` frei.

```cpp
void unlock();
```

### <a name="remarks"></a>Hinweise

Wenn der aufrufende Thread nicht im Besitz von `mutex` ist, so ist das Verhalten nicht definiert.

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<mutex>](../standard-library/mutex.md)<br/>
