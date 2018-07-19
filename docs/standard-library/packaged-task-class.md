---
title: packaged_task-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- future/std::packaged_task
- future/std::packaged_task::packaged_task
- future/std::packaged_task::get_future
- future/std::packaged_task::make_ready_at_thread_exit
- future/std::packaged_task::reset
- future/std::packaged_task::swap
- future/std::packaged_task::valid
- future/std::packaged_task::operator()
- future/std::packaged_task::operator bool
dev_langs:
- C++
ms.assetid: 0a72cbe3-f22a-4bfe-8e50-dcb268c98780
author: corob-msft
ms.author: corob
helpviewer_keywords:
- std::packaged_task [C++]
- std::packaged_task [C++], packaged_task
- std::packaged_task [C++], get_future
- std::packaged_task [C++], make_ready_at_thread_exit
- std::packaged_task [C++], reset
- std::packaged_task [C++], swap
- std::packaged_task [C++], valid
ms.workload:
- cplusplus
ms.openlocfilehash: 7eb5b8d003682f5b941dd805f424afbe4a36cc85
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38964794"
---
# <a name="packagedtask-class"></a>packaged_task-Klasse

Beschreibt einen *asynchronen Anbieter*, der ein Aufrufwrapper und dessen Aufrufsignatur `Ty(ArgTypes...)` ist. Der *zugehörige asynchrone Zustand*  enthält zusätzlich zum potentiellen Ergebnis eine Kopie des aufrufbaren Objekts.

## <a name="syntax"></a>Syntax

```cpp
template <class>
class packaged_task;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[packaged_task](#packaged_task)|Erstellt ein `packaged_task`-Objekt.|
|[packaged_task::~packaged_task-Destruktor](#dtorpackaged_task_destructor)|Zerstört ein `packaged_task`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[get_future](#get_future)|Gibt ein [future](../standard-library/future-class.md)-Objekt zurück, das über den gleichen zugeordneten asynchronen Zustand verfügt.|
|[make_ready_at_thread_exit](#make_ready_at_thread_exit)|Ruft das aufrufbare Objekt auf, das im zugeordneten asynchronen Zustand gespeichert ist und speichert automatisch den zurückgegebenen Wert.|
|[reset](#reset)|Ersetzt den zugeordneten asynchronen Zustand.|
|[swap](#swap)|Tauscht den zugeordneten asynchronen Zustand dieses Zusageobjekts mit dem eines angegebenen Objekts aus.|
|[valid](#valid)|Legt fest, ob das Objekt einen zugeordneten asynchronen Zustand hat.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[packaged_task::operator=](#op_eq)|Überträgt einen zugeordneten asynchronen Zustand aus einem angegebenen Objekt.|
|[packaged_task::operator()](#op_call)|Ruft das aufrufbare Objekt auf, das im zugeordneten asynchronen Zustand gespeichert ist, speichert den zurückgegebenen Wert atomar und legt den Zustand auf *bereit* fest.|
|[packaged_task::operator bool](#op_bool)|Legt fest, ob das Objekt einen zugeordneten asynchronen Zustand hat.|

## <a name="requirements"></a>Anforderungen

**Header:** \<zukünftige >

**Namespace:** std

## <a name="get_future"></a> packaged_task::get_future

Gibt ein `future<Ty>`-Objekt zurück, das über den gleichen *zugeordneten asynchronen Zustand* verfügt.

```cpp
future<Ty> get_future();
```

### <a name="remarks"></a>Hinweise

Wenn das `packaged_task`-Objekt über keinen zugeordneten asynchronen Zustand verfügt, löst diese Methode [future_error](../standard-library/future-error-class.md) mit einem Fehlercode von `no_state` aus.

Wenn diese Methode bereits für ein `packaged_task`-Objekt mit dem gleichen zugeordneten asynchronen Zustand aufgerufen wurde, löst die Methode ein `future_error` mit einem Fehlercode von `future_already_retrieved` aus.

## <a name="make_ready_at_thread_exit"></a> packaged_task::make_ready_at_thread_exit

Ruft das aufrufbare Objekt auf, das im *zugeordneten asynchronen Zustand* gespeichert ist und den Rückgabewert atomar speichert.

```cpp
void make_ready_at_thread_exit(ArgTypes... args);
```

### <a name="remarks"></a>Hinweise

Wenn das `packaged_task`-Objekt über keinen zugeordneten asynchronen Zustand verfügt, löst diese Methode [future_error](../standard-library/future-error-class.md) mit einem Fehlercode von `no_state` aus.

Wenn diese Methode oder [make_ready_at_thread_exit](#make_ready_at_thread_exit) bereits für ein `packaged_task`-Objekt mit dem gleichen zugeordneten asynchronen Zustand aufgerufen wurde, löst die Methode ein `future_error` mit einem Fehlercode von `promise_already_satisfied` aus.

Andernfalls ruft dieser Operator `INVOKE(fn, args..., Ty)` auf, in dem *fn* das aufrufbare Objekt ist, das im zugeordneten asynchronen Zustand gespeichert ist. Jeder Rückgabewert wird atomar als das zurückgegebene Ergebnis des assoziierten asynchronen Zustands gespeichert.

Im Gegensatz zu [packaged_task::operator()](#op_call), wird der zugeordnete asynchrone Zustand erst auf `ready` festgelegt, nachdem alle Objekte eines lokalen Threads im aktuellen Thread zerstört wurden. Normalerweise kann die Blockierung von Threads, die auf dem zugeordneten asynchronen Zustand blockiert werden, nicht aufgehoben werden, bis der aktuelle Thread beendet wird.

## <a name="op_eq"></a> packaged_task::operator=

Überträgt den *zugeordneten asynchronen Zustand* aus einem angegebenen Objekt.

```cpp
packaged_task& operator=(packaged_task&& Right);
```

### <a name="parameters"></a>Parameter

*Rechts* ein `packaged_task` Objekt.

### <a name="return-value"></a>Rückgabewert

`*this`

### <a name="remarks"></a>Hinweise

Nach dem Vorgang *rechts* mehr verfügt über keinen zugeordneten asynchronen Zustand.

## <a name="op_call"></a> packaged_task::operator()

Ruft das aufrufbare Objekt auf, das im *zugeordneten asynchronen Zustand* gespeichert ist, den Rückgabewert atomar speichert und den Zustand auf *bereit* festlegt.

```cpp
void operator()(ArgTypes... args);
```

### <a name="remarks"></a>Hinweise

Wenn das `packaged_task`-Objekt über keinen zugeordneten asynchronen Zustand verfügt, löst diese Methode [future_error](../standard-library/future-error-class.md) mit einem Fehlercode von `no_state` aus.

Wenn diese Methode oder [make_ready_at_thread_exit](#make_ready_at_thread_exit) bereits für ein `packaged_task`-Objekt mit dem gleichen zugeordneten asynchronen Zustand aufgerufen wurde, löst die Methode ein `future_error` mit einem Fehlercode von `promise_already_satisfied` aus.

Andernfalls ruft dieser Operator `INVOKE(fn, args..., Ty)` auf, in dem *fn* das aufrufbare Objekt ist, das im zugeordneten asynchronen Zustand gespeichert ist. Alle Rückgabewerte werden als das zurückgegebene Ergebnis des assoziierten asynchronen Zustands atomar gespeichert wird, und der Status wird auf bereit festgelegt. Deshalb wird die Blockierung aller Threads, die auf dem zugeordneten asynchronen Zustand blockiert werden, aufgehoben.

## <a name="op_bool"></a> packaged_task::operator bool

Gibt an, ob das Objekt über `associated asynchronous state` verfügt.

```cpp
operator bool() const noexcept;
```

### <a name="return-value"></a>Rückgabewert

**"true"** verfügt das Objekt einen zugeordneten asynchronen Zustand ist; andernfalls **"false"**.

## <a name="packaged_task"></a> packaged_task::packaged_task-Konstruktor

Erstellt ein `packaged_task`-Objekt.

```cpp
packaged_task() noexcept;
packaged_task(packaged_task&& Right) noexcept;
template <class Fn>
   explicit packaged_task(Fn&& fn);

template <class Fn, class Alloc>
   explicit packaged_task(
      allocator_arg_t, const Alloc& alloc, Fn&& fn);
```

### <a name="parameters"></a>Parameter

*Rechts* ein `packaged_task` Objekt.

*Alloc* eine speicherbelegung. Siehe [\<allocators>](../standard-library/allocators-header.md) für weitere Informationen.

*fn* ein Function-Objekt.

### <a name="remarks"></a>Hinweise

Der erste Konstruktor erstellt ein `packaged_task`-Objekt, das über keinen *zugeordneten asynchronen Zustand* verfügt.

Der zweite Konstruktor erstellt ein `packaged_task` Objekt aus, und überträgt den zugeordneten asynchronen Zustand aus *rechts*. Nach dem Vorgang *rechts* mehr verfügt über keinen zugeordneten asynchronen Zustand.

Der dritte Konstruktor erstellt ein `packaged_task` -Objekt, das eine Kopie des ist *fn* in dessen zugeordnetem asynchronen Zustand gespeichert.

Der vierte Konstruktor erstellt ein `packaged_task` -Objekt, das eine Kopie des ist *fn* in dessen zugeordnetem asynchronen Zustand gespeichert, und verwendet `alloc` für speicherbelegung.

## <a name="dtorpackaged_task_destructor"></a> packaged_task::~packaged_task-Destruktor

Zerstört ein `packaged_task`-Objekt.

```cpp
~packaged_task();
```

### <a name="remarks"></a>Hinweise

Wenn der *zugeordnete asynchrone Zustand* nicht *bereit* ist, speichert der Destruktor eine [future_error](../standard-library/future-error-class.md)-Ausnahme, die über den Fehlercode `broken_promise` als Ergebnis im zugeordneten asynchronen Zustand verfügt, und alle Threads, die auf dem zugeordneten asynchronen Zustand blockiert sind, werden aufgehoben.

## <a name="reset"></a> packaged_task::reset

Verwendet einen neuen *zugeordneten asynchronen Zustand* zum Ersetzen des vorhandenen zugeordneten asynchronen Zustands.

```cpp
void reset();
```

### <a name="remarks"></a>Hinweise

Diese Methode führt tatsächlich `*this = packaged_task(move(fn))` aus, wobei *fn* das Funktionsobjekt ist, das im zugeordneten asynchronen Zustand dieses Objekts gespeichert ist. Daher wird der Zustand des Objekts deaktiviert, und [get_future](#get_future), [operator()](#op_call) und [make_ready_at_thread_exit](#make_ready_at_thread_exit) können aufgerufen werden, als ob sie sich auf einem neu erstellten Objekt befinden würden.

## <a name="swap"></a> packaged_task::swap

Tauscht den zugeordneten asynchronen Zustand dieses Zusageobjekts mit dem eines angegebenen Objekts aus.

```cpp
void swap(packaged_task& Right) noexcept;
```

### <a name="parameters"></a>Parameter

*Rechts* ein `packaged_task` Objekt.

## <a name="valid"></a> packaged_task::valid

Gibt an, ob das Objekt über `associated asynchronous state` verfügt.

```cpp
bool valid() const;
```

### <a name="return-value"></a>Rückgabewert

**"true"** verfügt das Objekt einen zugeordneten asynchronen Zustand ist; andernfalls **"false"**.

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<future>](../standard-library/future.md)<br/>
