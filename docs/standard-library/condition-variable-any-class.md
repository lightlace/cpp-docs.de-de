---
title: Condition_variable_any-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- condition_variable/std::condition_variable_any
- condition_variable/std::condition_variable_any::condition_variable_any
- condition_variable/std::condition_variable_any::notify_all
- condition_variable/std::condition_variable_any::notify_one
- condition_variable/std::condition_variable_any::wait
- condition_variable/std::condition_variable_any::wait_for
- condition_variable/std::condition_variable_any::wait_until
dev_langs:
- C++
ms.assetid: d8afe5db-1561-4ec2-8e85-21ea03ee4321
author: corob-msft
ms.author: corob
helpviewer_keywords:
- std::condition_variable_any
- std::condition_variable_any::condition_variable_any
- std::condition_variable_any::notify_all
- std::condition_variable_any::notify_one
- std::condition_variable_any::wait
- std::condition_variable_any::wait_for
- std::condition_variable_any::wait_until
ms.workload:
- cplusplus
ms.openlocfilehash: f0fe38031dc215f537d82fe6e06f68acf6db8e0f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33847129"
---
# <a name="conditionvariableany-class"></a>condition_variable_any-Klasse

Verwenden Sie die `condition_variable_any`-Klasse, um ein Ereignis mit jeglichem `mutex`-Typ zu erwarten.

## <a name="syntax"></a>Syntax

```cpp
class condition_variable_any;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[condition_variable_any](#condition_variable_any)|Erstellt ein `condition_variable_any`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[notify_all](#notify_all)|Hebt die Blockierung aller Threads auf, die das `condition_variable_any`-Objekt erwarten.|
|[notify_one](#notify_one)|Hebt die Blockierung von einem der Threads, die auf das `condition_variable_any`-Objekt warten, auf.|
|[wait](#wait)|Blockiert einen Thread.|
|[wait_for](#wait_for)|Blockiert einen Thread und legt ein Zeitintervall fest, nachdem die Blockierung des Threads aufgehoben wird.|
|[wait_until](#wait_until)|Blockiert einen Thread und legt einen maximalen Zeitpunkt fest, an dem die Blockierung des Threads aufgehoben wird.|

## <a name="requirements"></a>Anforderungen

**Header:** \<condition_variable>

**Namespace:** std

## <a name="condition_variable_any"></a> condition_variable_any::condition_variable_any-Konstruktur

Erstellt ein `condition_variable_any`-Objekt.

```cpp
condition_variable_any();
```

### <a name="remarks"></a>Hinweise

Wenn nicht genügend Arbeitsspeicher verfügbar ist, gibt der Konstruktor ein [system_error](../standard-library/system-error-class.md)-Objekt mit einem `not_enough_memory`-Fehlercode aus. Wenn das Objekt nicht erstellt werden kann, da eine andere Ressource nicht verfügbar ist, wird vom Konstruktor ein `system_error`-Objekt mit einem `resource_unavailable_try_again`-Fehlercode ausgelöst.

## <a name="notify_all"></a> condition_variable_any::notify_all

Hebt die Blockierung aller Threads auf, die das `condition_variable_any`-Objekt erwarten.

```cpp
void notify_all() noexcept;
```

## <a name="notify_one"></a> condition_variable_any::notify_one

Hebt die Blockierung von einem der Threads, die auf das `condition_variable_any`-Objekt warten auf.

```cpp
void notify_one() noexcept;
```

## <a name="wait"></a> condition_variable_any::wait

Blockiert einen Thread.

```cpp
template <class Lock>
void wait(Lock& Lck);

template <class Lock, class Predicate>
void wait(Lock& Lck, Predicate Pred);
```

### <a name="parameters"></a>Parameter

`Lck` Ein `mutex` Objekt eines beliebigen Typs.

`Pred` Ein Ausdruck, der gibt `true` oder `false`.

### <a name="remarks"></a>Hinweise

Die erste Methode sperrt, bis das `condition_variable_any`-Objekt durch einen Aufruf von [notify_one](../standard-library/condition-variable-class.md#notify_one) oder [notify_all](../standard-library/condition-variable-class.md#notify_all) signalisiert wurde. Sie kann auch falsch aktiviert werden.

Die zweite Methode führt tatsächlich den folgenden Code aus.

```cpp
while (!Pred())
    wait(Lck);
```

## <a name="wait_for"></a> condition_variable_any::wait_for

Blockiert einen Thread und legt ein Zeitintervall fest, nachdem die Blockierung des Threads aufgehoben wird.

```cpp
template <class Lock, class Rep, class Period>
bool wait_for(Lock& Lck, const chrono::duration<Rep, Period>& Rel_time);

template <class Lock, class Rep, class Period, class Predicate>
bool wait_for(Lock& Lck, const chrono::duration<Rep, Period>& Rel_time, Predicate Pred);
```

### <a name="parameters"></a>Parameter

`Lck` Ein `mutex` Objekt eines beliebigen Typs.

`Rel_time` Ein `chrono::duration` reaktiviert Objekt, das die Zeitspanne, bevor der Thread angibt.

`Pred` Ein Ausdruck, der gibt `true` oder `false`.

### <a name="return-value"></a>Rückgabewert

Die erste Methode gibt `cv_status::timeout` zurück, wenn der Wartevorgang beendet wird, sobald `Rel_time` verstrichen ist. Andernfalls gibt diese Methode `cv_status::no_timeout` zurück.

Die zweite Methode gibt den Wert von `Pred` zurück.

### <a name="remarks"></a>Hinweise

Die erste Methode sperrt, bis das `condition_variable_any`-Objekt durch einen Aufruf von [notify_one](../standard-library/condition-variable-class.md#notify_one) oder [notify_all](../standard-library/condition-variable-class.md#notify_all) signalisiert wird, oder bis das Zeitintervall `Rel_time` abgelaufen ist. Sie kann auch falsch aktiviert werden.

Die zweite Methode führt tatsächlich den folgenden Code aus.

```cpp
while(!Pred())
    if(wait_for(Lck, Rel_time) == cv_status::timeout)
    return Pred();

return true;
```

## <a name="wait_until"></a> condition_variable_any::wait_until

Blockiert einen Thread und legt einen maximalen Zeitpunkt fest, an dem die Blockierung des Threads aufgehoben wird.

```cpp
template <class Lock, class Clock, class Duration>
void wait_until(Lock& Lck, const chrono::time_point<Clock, Duration>& Abs_time);

template <class Lock, class Clock, class Duration, class Predicate>
void wait_until(
    Lock& Lck,
    const chrono::time_point<Clock, Duration>& Abs_time,
    Predicate Pred);

template <class Lock>
void wait_until(Lock Lck, const xtime* Abs_time);

template <class Lock, class Predicate>
void wait_until(
    Lock Lck,
    const xtime* Abs_time,
    Predicate Pred);
```

### <a name="parameters"></a>Parameter

`Lck` Ein Mutex-Objekt.

`Abs_time` Ein [chrono:: time_point](../standard-library/time-point-class.md) Objekt.

`Pred` Ein Ausdruck, der gibt `true` oder `false`.

### <a name="return-value"></a>Rückgabewert

Methoden, die eine `cv_status`-Typ zurückgeben, geben `cv_status::timeout` zurück, wenn der Wartevorgang beendet wird, sobald `Abs_time` verstrichen ist. Andernfalls geben diese Methoden `cv_status::no_timeout` zurück.

Methoden, die `bool` zurückgeben, geben den Wert von `Pred` zurück.

### <a name="remarks"></a>Hinweise

Die erste Methode sperrt, bis das `condition_variable`-Objekt durch einen Aufruf von [notify_one](../standard-library/condition-variable-class.md#notify_one) oder [notify_al](../standard-library/condition-variable-class.md#notify_all) signalisiert wurde, oder bis `Abs_time`. Sie kann auch falsch aktiviert werden.

Die zweite Methode führt tatsächlich den folgenden Code aus.

```cpp
while(!Pred())
    if(wait_until(Lck, Abs_time) == cv_status::timeout)
    return Pred();

return true;
```

Bei der dritten und vierten Methode wird einen Zeiger auf ein Objekt des Typs `xtime`, verwendet, um das `chrono::time_point`-Objekt zu ersetzen. Mit dem `xtime`-Objekt wird die maximale Zeit angegeben, die auf ein Signal gewartet wird.

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[<condition_variable>](../standard-library/condition-variable.md)<br/>
