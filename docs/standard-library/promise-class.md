---
title: promise-Klasse
ms.date: 10/18/2018
f1_keywords:
- future/std::promise
- future/std::promise::promise
- future/std::promise::get_future
- future/std::promise::set_exception
- future/std::promise::set_exception_at_thread_exit
- future/std::promise::set_value
- future/std::promise::set_value_at_thread_exit
- future/std::promise::swap
ms.assetid: 2931558c-d94a-4ba1-ac4f-20bf7b6e23f9
helpviewer_keywords:
- std::promise [C++]
- std::promise [C++], promise
- std::promise [C++], get_future
- std::promise [C++], set_exception
- std::promise [C++], set_exception_at_thread_exit
- std::promise [C++], set_value
- std::promise [C++], set_value_at_thread_exit
- std::promise [C++], swap
ms.openlocfilehash: 560339dee5b13ddc13ff2f8af8283ea8615d804a
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68458365"
---
# <a name="promise-class"></a>promise-Klasse

Beschreibt einen *asynchronen Anbieter*.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
class promise;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[promise](#promise)|Erstellt ein `promise`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[get_future](#get_future)|Gibt eine dieser Zusage zugeordnete [Zukunft](../standard-library/future-class.md) zurück.|
|[set_exception](#set_exception)|Legt das Ergebnis dieser Zusage atomisch zum Angeben einer Ausnahme fest.|
|[set_exception_at_thread_exit](#set_exception_at_thread_exit)|Legt das Ergebnis dieser Zusage zum Angeben einer Ausnahme atomisch fest, und stellt die Benachrichtigung nur zu, nachdem alle Objekte eines lokalen Threads im aktuellen Thread zerstört wurden (normalerweise zur Threadbeendigung).|
|[set_value](#set_value)|Legt das Ergebnis dieser Zusage zum Angeben eines Werts atomisch fest.|
|[set_value_at_thread_exit](#set_value_at_thread_exit)|Legt das Ergebnis dieser Zusage zum Angeben eines Werts atomisch fest, und stellt die Benachrichtigung nur zu, nachdem alle Objekte eines lokalen Threads im aktuellen Thread zerstört wurden (normalerweise zur Threadbeendigung).|
|[swap](#swap)|Tauscht den *zugeordneten asynchronen Zustand* dieser Zusage mit dem eines angegebenen Zusageobjekts aus.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[promise::operator=](#op_eq)|Zuweisung des Freigabestatus dieses Zusageobjekts.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

*promise*

## <a name="requirements"></a>Anforderungen

**Header:** \<future>

**Namespace:** std

## <a name="get_future"></a> promise::get_future

Gibt ein [Zukunft](../standard-library/future-class.md)-Objekt zurück, das über den gleichen *zugeordneten asynchronen Zustand* wie die Zusage verfügt.

```cpp
future<Ty> get_future();
```

### <a name="remarks"></a>Hinweise

Wenn das Zusageobjekt leer ist, löst diese Methode [future_error](../standard-library/future-error-class.md) mit einem [error_code](../standard-library/error-code-class.md) von `no_state` aus.

Wenn diese Methode bereits für ein Zusageobjekt mit dem gleichen zugeordneten asynchronen Zustand aufgerufen wurde, löst die Methode `future_error` mit `error_code` von `future_already_retrieved` aus.

## <a name="op_eq"></a> promise::operator=

Überträgt den *zugeordneten asynchronen Zustand* aus einem angegebenen `promise`-Objekt.

```cpp
promise& operator=(promise&& Other) noexcept;
```

### <a name="parameters"></a>Parameter

*Außer*\
Ein `promise`-Objekt.

### <a name="return-value"></a>Rückgabewert

`*this`

### <a name="remarks"></a>Hinweise

Dieser Operator überträgt den zugeordneten asynchronen Zustand von einem *anderen*. Nach der Übertragung  ist andere *leer*.

## <a name="promise"></a> promise::promise-Konstruktor

Erstellt ein `promise`-Objekt.

```cpp
promise();
template <class Alloc>
promise(allocator_arg_t, const Alloc& Al);
promise(promise&& Other) noexcept;
```

### <a name="parameters"></a>Parameter

*Irdische*\
Eine Speicherbelegung. Siehe [\<allocators>](../standard-library/allocators-header.md) für weitere Informationen.

*Außer*\
Ein `promise`-Objekt.

### <a name="remarks"></a>Hinweise

Der erste Konstruktor erstellt ein *leeres* `promise` -Objekt.

Der zweite Konstruktor erstellt ein leeres `promise` -Objekt und verwendet *Al* für die Speicher Belegung.

Der dritte Konstruktor erstellt ein `promise` -Objekt und überträgt den zugeordneten asynchronen Zustand von einem *anderen*und lässt *andere* leer.

## <a name="set_exception"></a> promise::set_exception

Es wird atomisch eine Ausnahme als Ergebnis dieses `promise`-Objekts gespeichert, und der *entsprechende asynchrone Zustand* wird auf *fertig* festgelegt.

```cpp
void set_exception(exception_ptr Exc);
```

### <a name="parameters"></a>Parameter

*Exkl*\
Ein [exception_ptr](../standard-library/exception-typedefs.md#exception_ptr), der von dieser Methode als Ausnahmeergebnis gespeichert ist.

### <a name="remarks"></a>Hinweise

Wenn das `promise`-Objekt über keinen zugeordneten asynchronen Zustand verfügt, löst diese Methode [future_error](../standard-library/future-error-class.md) mit einem Fehlercode von `no_state` aus.

Wenn `set_exception`, [set_exception_at_thread_exit](#set_exception_at_thread_exit), [set_value](#set_value) oder [set_value_at_thread_exit](#set_value_at_thread_exit) bereits für ein `promise`-Objekt mit demselben zugeordneten asynchronen Zustand aufgerufen wurde, löst diese Methode `future_error` mit einem Fehlercode von `promise_already_satisfied` aus.

Aufgrund dieser Methode wird die Blockierung aller Threads, die auf dem zugeordneten asynchronen Zustand blockiert werden, aufgehoben.

## <a name="set_exception_at_thread_exit"></a> promise::set_exception_at_thread_exit

Legt das Ergebnis von `promise` zum Angeben einer Ausnahme atomisch fest, und stellt die Benachrichtigung nur zu, nachdem alle Objekte eines lokalen Threads im aktuellen Thread zerstört wurden (normalerweise zur Threadbeendigung).

```cpp
void set_exception_at_thread_exit(exception_ptr Exc);
```

### <a name="parameters"></a>Parameter

*Exkl*\
Ein [exception_ptr](../standard-library/exception-typedefs.md#exception_ptr), der von dieser Methode als Ausnahmeergebnis gespeichert ist.

### <a name="remarks"></a>Hinweise

Wenn das Zusageobjekt über keinen *zugeordneten asynchronen Zustand* verfügt, löst diese Methode [future_error](../standard-library/future-error-class.md) mit einem Fehlercode von `no_state` aus.

Wenn [, ](#set_exception)set_exception`set_exception_at_thread_exit`, [set_value](#set_value) oder [set_value_at_thread_exit](#set_value_at_thread_exit) bereits für ein `promise`-Objekt mit demselben zugeordneten asynchronen Zustand aufgerufen wurde, löst diese Methode `future_error` mit einem Fehlercode von `promise_already_satisfied` aus.

Im Gegensatz zu [set_exception](#set_exception) wird der asynchrone zugeordnete Zustand von dieser Methode nicht auf „fertig“ festgelegt, bis alle Objekte eines lokalen Threads im aktuellen Thread zerstört wurden. Normalerweise kann die Blockierung von Threads, die auf dem zugeordneten asynchronen Zustand blockiert werden, nicht aufgehoben werden, bis der aktuelle Thread beendet wird.

## <a name="set_value"></a> promise::set_value

Es wird atomisch ein Wert als Ergebnis dieses `promise`-Objekts gespeichert, und der *entsprechende asynchrone Zustand* wird auf *fertig* festgelegt.

```cpp
void promise::set_value(const Ty& Val);
void promise::set_value(Ty&& Val);
void promise<Ty&>::set_value(Ty& Val);
void promise<void>::set_value();
```

### <a name="parameters"></a>Parameter

*Ster*\
Der als Ergebnis zu speichernde Wert.

### <a name="remarks"></a>Hinweise

Wenn das `promise`-Objekt über keinen zugeordneten asynchronen Zustand verfügt, löst diese Methode [future_error](../standard-library/future-error-class.md) mit einem Fehlercode von `no_state` aus.

Wenn [set_exception](#set_exception), [set_exception_at_thread_exit](#set_exception_at_thread_exit), `set_value` oder [set_value_at_thread_exit](#set_value_at_thread_exit) bereits für ein `promise`-Objekt mit demselben zugeordneten asynchronen Zustand aufgerufen wurde, löst diese Methode `future_error` mit einem Fehlercode von `promise_already_satisfied` aus.

Aufgrund dieser Methode wird die Blockierung aller Threads, die auf dem zugeordneten asynchronen Zustand blockiert werden, aufgehoben.

Die erste Methode löst auch jede Ausnahme aus, die ausgelöst wird, wenn *Val* in den zugeordneten asynchronen Zustand kopiert wird. In dieser Situation wird der zugeordnete asynchrone Zustand nicht auf "vorbereitet" festgelegt.

Die zweite Methode löst auch jede Ausnahme aus, die ausgelöst wird, wenn *Val* in den zugeordneten asynchronen Zustand verschoben wird. In dieser Situation wird der zugeordnete asynchrone Zustand nicht auf "vorbereitet" festgelegt.

Bei der partiellen `promise<Ty&>`Spezialisierung ist der gespeicherte Wert ein Verweis auf *Val*.

Für die Spezialisierung `promise<void>` ist kein gespeicherter Wert vorhanden.

## <a name="set_value_at_thread_exit"></a> promise::set_value_at_thread_exit

Speichert einen Wert atomisch als Ergebnis dieses `promise`-Objekts.

```cpp
void promise::set_value_at_thread_exit(const Ty& Val);
void promise::set_value_at_thread_exit(Ty&& Val);
void promise<Ty&>::set_value_at_thread_exit(Ty& Val);
void promise<void>::set_value_at_thread_exit();
```

### <a name="parameters"></a>Parameter

*Ster*\
Der als Ergebnis zu speichernde Wert.

### <a name="remarks"></a>Hinweise

Wenn das Zusageobjekt über keinen *zugeordneten asynchronen Zustand* verfügt, löst diese Methode [future_error](../standard-library/future-error-class.md) mit einem Fehlercode von `no_state` aus.

Wenn [set_exception](#set_exception), [set_exception_at_thread_exit](#set_exception_at_thread_exit), [set_value](#set_value) oder `set_value_at_thread_exit` bereits für ein `promise`-Objekt mit demselben zugeordneten asynchronen Zustand aufgerufen wurde, löst diese Methode `future_error` mit einem Fehlercode von `promise_already_satisfied` aus.

Im Gegensatz zu `set_value`, wird der zugeordnete asynchrone Zustand erst auf "vorbereitet" festgelegt, nachdem alle Objekte eines lokalen Threads im aktuellen Thread zerstört wurden. Normalerweise kann die Blockierung von Threads, die auf dem zugeordneten asynchronen Zustand blockiert werden, nicht aufgehoben werden, bis der aktuelle Thread beendet wird.

Die erste Methode löst auch jede Ausnahme aus, die ausgelöst wird, wenn *Val* in den zugeordneten asynchronen Zustand kopiert wird.

Die zweite Methode löst auch jede Ausnahme aus, die ausgelöst wird, wenn *Val* in den zugeordneten asynchronen Zustand verschoben wird.

Bei der partiellen `promise<Ty&>`Spezialisierung ist der gespeicherte Wert tatsächlich ein Verweis auf *Val*.

Für die Spezialisierung `promise<void>` ist kein gespeicherter Wert vorhanden.

## <a name="swap"></a> promise::swap

Tauscht den *zugeordneten asynchronen Zustand* dieses Zusageobjekts mit dem eines angegebenen Objekts aus.

```cpp
void swap(promise& Other) noexcept;
```

### <a name="parameters"></a>Parameter

*Außer*\
Ein `promise`-Objekt.

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)
