---
title: recursive_timed_mutex-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- mutex/std::recursive_timed_mutex
- mutex/std::recursive_timed_mutex::recursive_timed_mutex
- mutex/std::recursive_timed_mutex::lock
- mutex/std::recursive_timed_mutex::try_lock
- mutex/std::recursive_timed_mutex::try_lock_for
- mutex/std::recursive_timed_mutex::try_lock_until
- mutex/std::recursive_timed_mutex::unlock
dev_langs:
- C++
ms.assetid: 59cc2d5c-ed80-45f3-a0a8-05652a8ead7e
author: corob-msft
ms.author: corob
helpviewer_keywords:
- std::recursive_timed_mutex [C++]
- std::recursive_timed_mutex [C++], recursive_timed_mutex
- std::recursive_timed_mutex [C++], lock
- std::recursive_timed_mutex [C++], try_lock
- std::recursive_timed_mutex [C++], try_lock_for
- std::recursive_timed_mutex [C++], try_lock_until
- std::recursive_timed_mutex [C++], unlock
ms.workload:
- cplusplus
ms.openlocfilehash: bfabbd938f2258f7e1a75fd77eaac7b2cd23b2b8
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38957622"
---
# <a name="recursivetimedmutex-class"></a>recursive_timed_mutex-Klasse

Stellt einen *timed_mutex-Typ* dar. Objekte dieses Typs werden verwendet, um den gegenseitigen Ausschluss durch zeitlich begrenzte Blockierung innerhalb eines Programms zu erzwingen. Im Gegensatz zu Objekten des Typs [timed_mutex](../standard-library/timed-mutex-class.md), sind die Auswirkungen von aufrufenden Sperrmethoden für `recursive_timed_mutex`-Objekte klar definiert.

## <a name="syntax"></a>Syntax

```cpp
class recursive_timed_mutex;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[recursive_timed_mutex](#recursive_timed_mutex)|Erstellt ein `recursive_timed_mutex`-Objekt, das nicht gesperrt ist.|
|[recursive_timed_mutex-Destruktor](#dtorrecursive_timed_mutex_destructor)|Gibt alle Ressourcen frei, die vom `recursive_timed_mutex`-Objekt verwendet werden.|

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

## <a name="lock"></a> lock

Blockiert den aufrufenden Thread, bis der Thread in den Besitz von `mutex` gelangt.

```cpp
void lock();
```

### <a name="remarks"></a>Hinweise

Wenn der aufrufende Thread bereits im Besitz von `mutex` ist, wird die Methode sofort zurückgegeben, und die vorherige Sperre bleibt in Kraft.

## <a name="recursive_timed_mutex"></a> recursive_timed_mutex-Konstruktor

Erstellt ein `recursive_timed_mutex`-Objekt, das nicht gesperrt ist.

```cpp
recursive_timed_mutex();
```

## <a name="dtorrecursive_timed_mutex_destructor"></a> ~recursive_timed_mutex-Destruktor

Gibt alle Ressourcen frei, die vom `recursive_timed_mutex`-Objekt verwendet werden.

```cpp
~recursive_timed_mutex();
```

### <a name="remarks"></a>Hinweise

Wenn das Objekt gesperrt ist, wenn der Destruktor ausgeführt wird, ist das Verhalten nicht definiert.

## <a name="try_lock"></a> try_lock

Versucht, ohne Blockierung in den Besitz von `mutex` zu gelangen.

```cpp
bool try_lock() noexcept;
```

### <a name="return-value"></a>Rückgabewert

**"true"** , wenn die Methode erfolgreich Besitzrechte erhalten die `mutex` oder wenn der aufrufende Thread bereits im Besitz der `mutex`ist, andernfalls **"false"**.

### <a name="remarks"></a>Hinweise

Wenn der aufrufende Thread bereits im Besitz der `mutex`, die Funktion sofort zurück **"true"**, und die vorherige Sperre bleibt in Kraft.

## <a name="try_lock_for"></a> try_lock_for

Versucht, ohne Blockierung in den Besitz von `mutex` zu gelangen.

```cpp
template <class Rep, class Period>
bool try_lock_for(const chrono::duration<Rep, Period>& Rel_time);
```

### <a name="parameters"></a>Parameter

*Rel_time* ein [chrono:: Duration](../standard-library/duration-class.md) Objekt, das die maximale Zeitspanne, die die Methode versucht angibt, den Besitz von der `mutex`.

### <a name="return-value"></a>Rückgabewert

**"true"** , wenn die Methode erfolgreich Besitzrechte erhält die `mutex` oder wenn der aufrufende Thread bereits im Besitz der `mutex`ist, andernfalls **"false"**.

### <a name="remarks"></a>Hinweise

Wenn der aufrufende Thread bereits im Besitz der `mutex`, die Methode sofort zurückgegeben **"true"**, und die vorherige Sperre bleibt in Kraft.

## <a name="try_lock_until"></a> try_lock_until

Versucht, ohne Blockierung in den Besitz von `mutex` zu gelangen.

```cpp
template <class Clock, class Duration>
bool try_lock_for(const chrono::time_point<Clock, Duration>& Abs_time);

bool try_lock_until(const xtime* Abs_time);
```

### <a name="parameters"></a>Parameter

*Abs_time* einem bestimmten Zeitpunkt an, die den Schwellenwert angibt, nach dem die Methode nicht mehr versucht, den Besitz von, der `mutex`.

### <a name="return-value"></a>Rückgabewert

**"true"** , wenn die Methode erfolgreich Besitzrechte erhält die `mutex` oder wenn der aufrufende Thread bereits im Besitz der `mutex`ist, andernfalls **"false"**.

### <a name="remarks"></a>Hinweise

Wenn der aufrufende Thread bereits im Besitz der `mutex`, die Methode sofort zurückgegeben **"true"**, und die vorherige Sperre bleibt in Kraft.

## <a name="unlock"></a> unlock

Gibt den Besitz von `mutex` frei.

```cpp
void unlock();
```

### <a name="remarks"></a>Hinweise

Diese Methode gibt den Besitz der `mutex` erst frei, wenn sie so oft aufgerufen wurde, wie [lock](#lock), [try_lock](#try_lock) [try_lock_for](#try_lock_for), und [try_lock_until](#try_lock_until) erfolgreich im `recursive_timed_mutex`-Objekt aufgerufen wurden.

Wenn der aufrufende Thread nicht im Besitz von `mutex` ist, so ist das Verhalten nicht definiert.

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<mutex>](../standard-library/mutex.md)<br/>
