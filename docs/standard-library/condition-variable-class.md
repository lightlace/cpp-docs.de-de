---
title: condition_variable-Klass | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- condition_variable/std::condition
- condition_variable/std::condition_variable::condition_variable
- condition_variable/std::condition_variable::native_handle
- condition_variable/std::condition_variable::notify_all
- condition_variable/std::condition_variable::notify_one
- condition_variable/std::condition_variable::wait
- condition_variable/std::condition_variable::wait_for
- condition_variable/std::condition_variable::wait_until
dev_langs:
- C++
ms.assetid: 80b1295c-b73d-4d46-b664-6e183f2eec1b
author: corob-msft
ms.author: corob
helpviewer_keywords:
- std::condition
- std::condition_variable::condition_variable
- std::condition_variable::native_handle
- std::condition_variable::notify_all
- std::condition_variable::notify_one
- std::condition_variable::wait
- std::condition_variable::wait_for
- std::condition_variable::wait_until
ms.workload:
- cplusplus
ms.openlocfilehash: 55598e4d4aad92e9f4557886bbcb3bd442917624
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33847545"
---
# <a name="conditionvariable-class"></a>condition_variable-Klasse

Verwenden Sie die `condition_variable`-Klasse, um ein Ereignis zu erwarten, wenn Sie über ein `mutex` des Typs `unique_lock<mutex>` verfügen. Objekte dieses Typs bieten möglicherweise mehr Leistung als Objekte des Typs [condition_variable_any<unique_lock\<<mutex>>](../standard-library/condition-variable-any-class.md).

## <a name="syntax"></a>Syntax

```cpp
class condition_variable;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[condition_variable](#condition_variable)|Erstellt ein `condition_variable`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[native_handle](#native_handle)|Gibt den implementierungsspezifischen Typ zurück, der das Handle "condition_variable" darstellt.|
|[notify_all](#notify_all)|Hebt die Blockierung aller Threads auf, die das `condition_variable`-Objekt erwarten.|
|[notify_one](#notify_one)|Hebt die Blockierung von einem der Threads, die auf das `condition_variable`-Objekt warten, auf.|
|[wait](#wait)|Blockiert einen Thread.|
|[wait_for](#wait_for)|Blockiert einen Thread und legt ein Zeitintervall fest, nachdem die Blockierung des Threads aufgehoben wird.|
|[wait_until](#wait_until)|Blockiert einen Thread und legt einen maximalen Zeitpunkt fest, an dem die Blockierung des Threads aufgehoben wird.|

## <a name="requirements"></a>Anforderungen

**Header:** \<condition_variable>

**Namespace:** std

## <a name="condition_variable"></a>condition_variable::condition_variable-Konstruktor

Erstellt ein `condition_variable`-Objekt.

```cpp
condition_variable();
```

### <a name="remarks"></a>Hinweise

Wenn nicht genügend Arbeitsspeicher verfügbar ist, gibt der Konstruktor ein [system_error](../standard-library/system-error-class.md)-Objekt mit einem `not_enough_memory`-Fehlercode aus. Wenn das Objekt nicht erstellt werden kann, da eine andere Ressource nicht verfügbar ist, wird vom Konstruktor ein `system_error`-Objekt mit einem `resource_unavailable_try_again`-Fehlercode ausgelöst.

## <a name="native_handle"></a> condition_variable::native_handle

Gibt den implementierungsspezifischen Typ zurück, der das „condition_variable“-Handle darstellt.

```cpp
native_handle_type native_handle();
```

### <a name="return-value"></a>Rückgabewert

`native_handle_type` wird als Zeiger auf interne Datenstrukturen Concurrency Runtime von Concurrency Runtime definiert.

## <a name="notify_all"></a> condition_variable::notify_all

Hebt die Blockierung aller Threads auf, die das `condition_variable`-Objekt erwarten.

```cpp
void notify_all() noexcept;
```

## <a name="notify_one"></a> condition_variable::notify_one

Hebt die Blockierung von einem der Threads, die auf das `condition_variable`-Objekt warten auf.

```cpp
void notify_one() noexcept;
```

## <a name="wait"></a> condition_variable::wait

Blockiert einen Thread.

```cpp
void wait(unique_lock<mutex>& Lck);

template <class Predicate>
void wait(unique_lock<mutex>& Lck, Predicate Pred);
```

### <a name="parameters"></a>Parameter

`Lck` Ein [Unique_lock\<Mutex >](../standard-library/unique-lock-class.md) Objekt.

`Pred` Ein Ausdruck, der gibt `true` oder `false`.

### <a name="remarks"></a>Hinweise

Die erste Methode sperrt, bis das `condition_variable`-Objekt durch einen Aufruf von [notify_one](#notify_one) oder [notify_all](#notify_all) signalisiert wurde. Sie kann auch falsch aktiviert werden.

Tatsächlich führt die zweite Methode den folgenden Code aus.

```cpp
while(!Pred())
    wait(Lck);
```

## <a name="wait_for"></a> condition_variable::wait_for

Blockiert einen Thread und legt ein Zeitintervall fest, nachdem die Blockierung des Threads aufgehoben wird.

```cpp
template <class Rep, class Period>
cv_status wait_for(
    unique_lock<mutex>& Lck,
    const chrono::duration<Rep, Period>& Rel_time);

template <class Rep, class Period, class Predicate>
bool wait_for(
    unique_lock<mutex>& Lck,
    const chrono::duration<Rep, Period>& Rel_time,
    Predicate Pred);
```

### <a name="parameters"></a>Parameter

`Lck` Ein [Unique_lock\<Mutex >](../standard-library/unique-lock-class.md) Objekt.

`Rel_time` Ein `chrono::duration` reaktiviert Objekt, das die Zeitspanne, bevor der Thread angibt.

`Pred` Ein Ausdruck, der gibt `true` oder `false`.

### <a name="return-value"></a>Rückgabewert

Die erste Methode gibt `cv_status::timeout` zurück, wenn der Wartevorgang beendet wird, sobald `Rel_time` verstrichen ist. Andernfalls gibt diese Methode `cv_status::no_timeout` zurück.

Die zweite Methode gibt den Wert von `Pred` zurück.

### <a name="remarks"></a>Hinweise

Die erste Methode sperrt, bis das `condition_variable`-Objekt durch einen Aufruf von [notify_one](#notify_one) oder [notify_all](#notify_all) signalisiert wird oder bis das Zeitintervall `Rel_time` abgelaufen ist. Sie kann auch falsch aktiviert werden.

Tatsächlich führt die zweite Methode den folgenden Code aus.

```cpp
while(!Pred())
    if(wait_for(Lck, Rel_time) == cv_status::timeout)
    return Pred();

return true;
```

## <a name="wait_until"></a> condition_variable::wait_until

Blockiert einen Thread und legt einen maximalen Zeitpunkt fest, an dem die Blockierung des Threads aufgehoben wird.

```cpp
template <class Clock, class Duration>
cv_status wait_until(
    unique_lock<mutex>& Lck,
    const chrono::time_point<Clock, Duration>& Abs_time);

template <class Clock, class Duration, class Predicate>
bool wait_until(
    unique_lock<mutex>& Lck,
    const chrono::time_point<Clock, Duration>& Abs_time,
    Predicate Pred);

cv_status wait_until(
    unique_lock<mutex>& Lck,
    const xtime* Abs_time);

template <class Predicate>
bool wait_until(
    unique_lock<mutex>& Lck,
    const xtime* Abs_time,
    Predicate Pred);
```

### <a name="parameters"></a>Parameter

`Lck` Ein [Unique_lock\<Mutex >](../standard-library/unique-lock-class.md) Objekt.

`Abs_time` Ein [chrono:: time_point](../standard-library/time-point-class.md) Objekt.

`Pred` Ein Ausdruck, der gibt `true` oder `false`.

### <a name="return-value"></a>Rückgabewert

Methoden, die eine `cv_status`-Typ zurückgeben, geben `cv_status::timeout` zurück, wenn der Wartevorgang beendet wird, sobald `Abs_time` verstrichen ist. Andernfalls geben diese Methoden `cv_status::no_timeout` zurück.

Methoden, die `bool` zurückgeben, geben den Wert von `Pred` zurück.

### <a name="remarks"></a>Hinweise

Die erste Methode blockiert, bis das `condition_variable`-Objekt durch einen Aufruf von [notify_one](#notify_one) oder [notify_all](#notify_all) signalisiert wurde, oder bis `Abs_time`. Sie kann auch falsch aktiviert werden.

Tatsächlich führt die zweite Methode den folgenden Code aus.

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
