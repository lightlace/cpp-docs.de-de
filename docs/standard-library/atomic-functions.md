---
title: '&lt;atomic&gt;-Funktionen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 07/11/2018
ms.topic: reference
f1_keywords:
- atomic/std::atomic_compare_exchange_strong
- atomic/std::atomic_compare_exchange_strong_explicit
- atomic/std::atomic_compare_exchange_weak
- atomic/std::atomic_compare_exchange_weak_explicit
- atomic/std::atomic_exchange
- atomic/std::atomic_exchange_explicit
- atomic/std::atomic_fetch_add
- atomic/std::atomic_fetch_add_explicit
- atomic/std::atomic_fetch_and
- atomic/std::atomic_fetch_and_explicit
- atomic/std::atomic_fetch_or
- atomic/std::atomic_fetch_or_explicit
- atomic/std::atomic_fetch_sub
- atomic/std::atomic_fetch_sub_explicit
- atomic/std::atomic_fetch_xor
- atomic/std::atomic_fetch_xor_explicit
- atomic/std::atomic_flag_clear
- atomic/std::atomic_flag_clear_explicit
- atomic/std::atomic_flag_test_and_set
- atomic/std::atomic_flag_test_and_set_explicit
- atomic/std::atomic_init
- atomic/std::atomic_is_lock_free
- atomic/std::atomic_load
- atomic/std::atomic_load_explicit
- atomic/std::atomic_signal_fence
- atomic/std::atomic_store
- atomic/std::atomic_store_explicit
- atomic/std::atomic_thread_fence
- atomic/std::kill_dependency
ms.assetid: 5c53b4f8-6ff5-47d7-beb2-2d6ee3c6ea89
author: mikeblome
ms.author: mblome
helpviewer_keywords:
- std::atomic_compare_exchange_strong [C++]
- std::atomic_compare_exchange_strong_explicit [C++]
- std::atomic_compare_exchange_weak [C++]
- std::atomic_compare_exchange_weak_explicit [C++]
- std::atomic_exchange [C++]
- std::atomic_exchange_explicit [C++]
- std::atomic_fetch_add [C++]
- std::atomic_fetch_add_explicit [C++]
- std::atomic_fetch_and [C++]
- std::atomic_fetch_and_explicit [C++]
- std::atomic_fetch_or [C++]
- std::atomic_fetch_or_explicit [C++]
- std::atomic_fetch_sub [C++]
- std::atomic_fetch_sub_explicit [C++]
- std::atomic_fetch_xor [C++]
- std::atomic_fetch_xor_explicit [C++]
- std::atomic_flag_clear [C++]
- std::atomic_flag_clear_explicit [C++]
- std::atomic_flag_test_and_set [C++]
- std::atomic_flag_test_and_set_explicit [C++]
- std::atomic_init [C++]
- std::atomic_is_lock_free [C++]
- std::atomic_load [C++]
- std::atomic_load_explicit [C++]
- std::atomic_signal_fence [C++]
- std::atomic_store [C++]
- std::atomic_store_explicit [C++]
- std::atomic_thread_fence [C++]
- std::kill_dependency [C++]
ms.workload:
- cplusplus
ms.openlocfilehash: b70f4df63b5a885403b91c1470c3066c33f5f123
ms.sourcegitcommit: e9ce38decc9f986edab5543de3464b11ebccb123
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2018
ms.locfileid: "42540440"
---
# <a name="ltatomicgt-functions"></a>&lt;atomic&gt;-Funktionen

||||
|-|-|-|
|[atomic_compare_exchange_strong](#atomic_compare_exchange_strong)|[atomic_compare_exchange_strong_explicit](#atomic_compare_exchange_strong_explicit)|[atomic_compare_exchange_weak](#atomic_compare_exchange_weak)|
|[atomic_compare_exchange_weak_explicit](#atomic_compare_exchange_weak_explicit)|[atomic_exchange](#atomic_exchange)|[atomic_exchange_explicit](#atomic_exchange_explicit)|
|[atomic_fetch_add](#atomic_fetch_add)|[atomic_fetch_add_explicit](#atomic_fetch_add_explicit)|[atomic_fetch_and](#atomic_fetch_and)|
|[atomic_fetch_and_explicit](#atomic_fetch_and_explicit)|[atomic_fetch_or](#atomic_fetch_or)|[atomic_fetch_or_explicit](#atomic_fetch_or_explicit)|
|[atomic_fetch_sub](#atomic_fetch_sub)|[atomic_fetch_sub_explicit](#atomic_fetch_sub_explicit)|[atomic_fetch_xor](#atomic_fetch_xor)|
|[atomic_fetch_xor_explicit](#atomic_fetch_xor_explicit)|[atomic_flag_clear](#atomic_flag_clear)|[atomic_flag_clear_explicit](#atomic_flag_clear_explicit)|
|[atomic_flag_test_and_set](#atomic_flag_test_and_set)|[atomic_flag_test_and_set_explicit](#atomic_flag_test_and_set_explicit)|[atomic_init](#atomic_init)|
|[atomic_is_lock_free](#atomic_is_lock_free)|[atomic_load](#atomic_load)|[atomic_load_explicit](#atomic_load_explicit)|
|[atomic_signal_fence](#atomic_signal_fence)|[atomic_store](#atomic_store)|[atomic_store_explicit](#atomic_store_explicit)|
|[atomic_thread_fence](#atomic_thread_fence)|[kill_dependency](#kill_dependency)|

## <a name="atomic_compare_exchange_strong"></a> atomic_compare_exchange_strong

Führt einen atomischen Vergleichs- und Austausch-Vorgang aus.

```cpp
template <class Ty>
inline bool atomic_compare_exchange_strong(
    volatile atomic<Ty>* Atom,
    Ty* Exp,
    Value) noexcept;

template <class Ty>
inline bool atomic_compare_exchange_strong(
    atomic<Ty>* Atom,
    Ty* Exp,
    Ty Value) noexcept;
```

### <a name="parameters"></a>Parameter

*Atom* ein Zeiger auf ein *atomic* Objekt, das einen Wert vom Typ speichert `Ty`.

*"Exp"* ein Zeiger auf einen Wert vom Typ `Ty`.

*Wert* ein Wert vom Typ `Ty`.

### <a name="return-value"></a>Rückgabewert

**"true"** , wenn die Werte gleich, andernfalls sind **"false"**.

### <a name="remarks"></a>Hinweise

Mit dieser Methode wird ein atomischer Vergleichs- und Austauschvorgang ausgeführt, indem implizite `memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum)-Argumente verwendet werden. Weitere Informationen finden Sie unter [atomic_compare_exchange_strong_explicit](../standard-library/atomic-functions.md#atomic_compare_exchange_strong_explicit).

## <a name="atomic_compare_exchange_strong_explicit"></a> atomic_compare_exchange_strong_explicit

Führt einen *atomischen Vergleichs- und Austauschvorgang* aus.

```cpp
template <class T>
inline bool atomic_compare_exchange_strong_explicit(
    volatile atomic<Ty>* Atom,
    Ty* Exp,
    Ty Value,
    memory_order Order1,
    memory_order Order2) noexcept;

template <class Ty>
inline bool atomic_compare_exchange_strong_explicit(
    atomic<Ty>* Atom,
    Ty* Exp,
    Ty Value,
    memory_order Order1,
    memory_order Order2) noexcept;
```

### <a name="parameters"></a>Parameter

*Atom* ein Zeiger auf ein `atomic` Objekt, das einen Wert vom Typ speichert `Ty`.

*"Exp"* ein Zeiger auf einen Wert vom Typ `Ty`.

*Wert* ein Wert vom Typ `Ty`.

*Order1* erste [Memory_order](../standard-library/atomic-enums.md#memory_order_enum) Argument.

*Order2* zweite `memory_order` Argument. Der Wert des *Order2* nicht `memory_order_release` oder `memory_order_acq_rel`, er kann nicht stärker als der Wert des *Order1*.

### <a name="return-value"></a>Rückgabewert

**"true"** , wenn die Werte gleich, andernfalls sind **"false"**.

### <a name="remarks"></a>Hinweise

Ein *atomischen Vergleichs- und Austausch-Vorgang* vergleicht den Wert, der in dem Objekt gespeichert wird, auf das von *Atom* anhand des Werts, auf das von *"exp"*. Wenn die Werte gleich sind, den Wert, der in dem Objekt gespeichert wird, auf das von *Atom* durch ersetzt *Wert* mithilfe einer `read-modify-write` Vorgang und Anwenden von Einschränkungen der arbeitsspeicherreihenfolge, die gemäß *Order1*. Wenn die Werte nicht gleich sind, ersetzt den Wert, auf das von *"exp"* mit dem Wert, der in dem Objekt gespeichert wird, auf das von *Atom* und, die Einschränkungen für die Speicherreihenfolge angewendet gemäß *Order2*.

## <a name="atomic_compare_exchange_weak"></a> atomic_compare_exchange_weak

Führt einen *schwachen atomischen Vergleichs- und Austauschvorgang* aus.

```cpp
template <class Ty>
inline bool atomic_compare_exchange_strong(
    volatile atomic<Ty>* Atom,
    Ty* Exp,
    Ty Value) noexcept;

template <class Ty>
inline bool atomic_compare_exchange_strong(
    atomic<Ty>* Atom,
    Ty* Exp,
    Ty Value) noexcept;
```

### <a name="parameters"></a>Parameter

*Atom* ein Zeiger auf ein `atomic` Objekt, das einen Wert vom Typ speichert `Ty`.

*"Exp"* ein Zeiger auf einen Wert vom Typ `Ty`.

*Wert* ein Wert vom Typ `Ty`.

### <a name="return-value"></a>Rückgabewert

**"true"** , wenn die Werte gleich, andernfalls sind **"false"**.

### <a name="remarks"></a>Hinweise

Mit dieser Methode wird ein *schwacher atomischer Vergleichs- und Austauschvorgang* ausgeführt, der über implizite `memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum)-Argumente verfügt. Weitere Informationen finden Sie unter [atomic_compare_exchange_weak_explicit](../standard-library/atomic-functions.md#atomic_compare_exchange_weak_explicit).

## <a name="atomic_compare_exchange_weak_explicit"></a> atomic_compare_exchange_weak_explicit

Führt einen *schwachen atomischen Vergleichs- und Austauschvorgang* aus.

```cpp
template <class Ty>
inline bool atomic_compare_exchange_weak_explicit(
    volatile atomic<Ty>* Atom,
    Ty* Exp,
    Ty Value,
    memory_order Order1,
    memory_order Order2) noexcept;

template <class Ty>
inline bool atomic_compare_exchange_weak_explicit(
    atomic<Ty>* Atom,
    Ty* Exp,
    Ty Value,
    memory_order Order1,
    memory_order Order2) noexcept;
```

### <a name="parameters"></a>Parameter

*Atom* ein Zeiger auf ein `atomic` Objekt, das einen Wert vom Typ speichert `Ty`.

*"Exp"* ein Zeiger auf einen Wert vom Typ `Ty`.

*Wert* ein Wert vom Typ `Ty`.

*Order1* erste [Memory_order](../standard-library/atomic-enums.md#memory_order_enum) Argument.

*Order2* zweite `memory_order` Argument. Der Wert des *Order2* nicht `memory_order_release` oder `memory_order_acq_rel`, noch kann er stärker als der Wert des *Order1*.

### <a name="return-value"></a>Rückgabewert

**"true"** , wenn die Werte gleich, andernfalls sind **"false"**.

### <a name="remarks"></a>Hinweise

Die starken und schwachen Arten von einem *atomischen Vergleichs- und Austausch-Vorgang* Garantie, dass sie den neuen Wert nicht speichern, wenn die erwartete und aktuellen Werte nicht gleich sind. Der starke Typ wird sichergestellt, dass sie den neuen Wert gespeichert werden, wenn die erwartete und aktuellen Werte gleich sind. Der unsichere Typ kann in einigen Fällen zurückgeben **"false"** und den neuen Wert nicht speichern, selbst wenn der aktuelle und die erwarteten Werte gleich sind. Das heißt, die Funktion zurück **"false"**, aber möglicherweise eine spätere Untersuchung des erwarteten Werts anzuzeigen, wurde nicht geändert und sollte daher als gleich verglichen haben.

## <a name="atomic_exchange"></a> atomic_exchange

Verwendet *Wert* ersetzt den gespeicherten Wert von *Atom*.

```cpp
template <class T>
inline Ty atomic_exchange(volatile atomic<Ty>* _Atom, Ty Value) noexcept;

template <class Ty>
inline T atomic_exchange(atomic<Ty>* Atom, Ty Value) noexcept;
```

### <a name="parameters"></a>Parameter

*Atom* ein Zeiger auf ein `atomic` Objekt, das einen Wert vom Typ speichert `Ty`.

*Wert* ein Wert vom Typ `Ty`.

### <a name="return-value"></a>Rückgabewert

Der gespeicherte Wert von *Atom* vor dem Austausch.

### <a name="remarks"></a>Hinweise

Die `atomic_exchange` Funktion führt eine `read-modify-write` Vorgang, der den Wert austauschen, die in gespeichert ist *Atom* mit *Wert*unter Verwendung der `memory_order_seq_cst` [Memory_order](../standard-library/atomic-enums.md#memory_order_enum).

## <a name="atomic_exchange_explicit"></a> atomic_exchange_explicit

Ersetzt den gespeicherten Wert von *Atom* mit *Wert*.

```cpp
template <class Ty>
inline Ty atomic_exchange_explicit(
    volatile atomic<Ty>* Atom,
    Ty Value,
    memory_order Order) noexcept;

template <class Ty>
inline Ty atomic_exchange_explicit(
    atomic<Ty>* Atom,
    Ty Value,
    memory_order Order) noexcept;
```

### <a name="parameters"></a>Parameter

*Atom* ein Zeiger auf ein `atomic` Objekt, das einen Wert vom Typ speichert `Ty`.

*Wert* ein Wert vom Typ `Ty`.

*Reihenfolge* ein [Memory_order](../standard-library/atomic-enums.md#memory_order_enum).

### <a name="return-value"></a>Rückgabewert

Der gespeicherte Wert von *Atom* vor dem Austausch.

### <a name="remarks"></a>Hinweise

Die `atomic_exchange_explicit` Funktion führt eine `read-modify-write` Vorgang, der den Wert austauschen, die in gespeicherten *Atom* mit *Wert*, innerhalb der mit den vom angegebenen  *Reihenfolge*.

## <a name="atomic_fetch_add"></a> atomic_fetch_add

Fügt einem vorhandenen Wert einen in einem `atomic`-Objekt gespeicherten Wert hinzu.

```cpp
template <class T>
T* atomic_fetch_add(volatile atomic<T*>* Atom, ptrdiff_t Value) noexcept;
template <class T>
T* atomic_fetch_add(atomic<T*>* Atom, ptrdiff_t Value) noexcept;
```

### <a name="parameters"></a>Parameter

*Atom* ein Zeiger auf ein `atomic` Objekt, das einen Zeiger auf den Typ speichert `T`.

*Wert* ein Wert vom Typ `ptrdiff_t`.

### <a name="return-value"></a>Rückgabewert

Der Wert des unmittelbar vor dem Ausführen des Vorgangs im atomischen Objekt enthaltenen Zeigers.

### <a name="remarks"></a>Hinweise

Die `atomic_fetch_add` Funktion führt eine `read-modify-write` Vorgang atomar hinzufügen *Wert* gespeicherten Wert in *Atom*unter Verwendung der `memory_order_seq_cst` [Memory_order](../standard-library/atomic-enums.md#memory_order_enum)Einschränkung.

Wenn der atomare Typ ist `atomic_address`, *Wert* weist den Typ `ptrdiff_t` und der Vorgang behandelt den gespeicherten Zeiger als einen `char *`.

Dieser Vorgang wird auch bei Integraltypen überladen:

```cpp
integral atomic_fetch_add(volatile atomic-integral* Atom, integral Value) noexcept;

integral atomic_fetch_add(atomic-integral* Atom, integral Value) noexcept;
```

## <a name="atomic_fetch_add_explicit"></a> atomic_fetch_add_explicit

Fügt einem vorhandenen Wert einen in einem `atomic`-Objekt gespeicherten Wert hinzu.

```cpp
template <class T>
T* atomic_fetch_add_explicit(
    volatile atomic<T*>* Atom,
    ptrdiff_t Value,
    memory_order Order) noexcept;

template <class T>
T* atomic_fetch_add_explicit(
    atomic<T*>* Atom,
    ptrdiff_t Value,
    memory_order Order) noexcept;
```

### <a name="parameters"></a>Parameter

*Atom* ein Zeiger auf ein `atomic` Objekt, das einen Zeiger auf den Typ speichert `T`.

*Wert* ein Wert vom Typ `ptrdiff_t`.

### <a name="return-value"></a>Rückgabewert

Der Wert des unmittelbar vor dem Ausführen des Vorgangs im atomischen Objekt enthaltenen Zeigers.

### <a name="remarks"></a>Hinweise

Die `atomic_fetch_add_explicit` Funktion führt eine `read-modify-write` Vorgang atomar hinzufügen *Wert* gespeicherten Wert in *Atom*innerhalb der [Memory_order](../standard-library/atomic-enums.md#memory_order_enum) Einschränkungen dem angegebenen `Order`.

Wenn der atomische Typ `atomic_address` ist, dann ist `Value` vom Typ `ptrdiff_t`, und der Vorgang behandelt den gespeicherten Zeiger als `char *`.

Dieser Vorgang wird auch bei Integraltypen überladen:

```cpp
integral atomic_fetch_add_explicit(
    volatile atomic-integral* Atom,
    integral Value,
    memory_order Order) noexcept;

integral atomic_fetch_add_explicit(
    atomic-integral* Atom,
    integral Value,
    memory_order Order) noexcept;
```

## <a name="atomic_fetch_and"></a> atomic_fetch_and

Führt ein bitweises `and` auf einem Wert und einem vorhandenen in einem `atomic`-Objekt gespeicherten Wert aus.

```cpp
template <class T>
inline T atomic_fetch_and(volatile atomic<T>* Atom, T Value) noexcept;
template <class T>
inline T atomic_fetch_and(volatile atomic<T>* Atom, T Value) noexcept;
```

### <a name="parameters"></a>Parameter

*Atom* ein Zeiger auf ein `atomic` Objekt, das einen Wert vom Typ speichert `T`.

*Wert* ein Wert vom Typ `T`.

### <a name="return-value"></a>Rückgabewert

Der Wert, der unmittelbar vor dem Ausführen des Vorgangs im atomischen Objekt enthalten war.

### <a name="remarks"></a>Hinweise

Die `atomic_fetch_and` Funktion führt eine `read-modify-write` Vorgang zum Ersetzen des gespeicherten Werts von *Atom* mit einer bitweisen `and` von *Wert* und den aktuellen Wert an, die in gespeichertist*Atom*unter Verwendung der `memory_order_seq_cst` [Memory_order](../standard-library/atomic-enums.md#memory_order_enum) Einschränkung.

## <a name="atomic_fetch_and_explicit"></a> atomic_fetch_and_explicit

Führt ein bitweises `and` eines Werts und einen vorhandenen in einem `atomic`-Objekt gespeicherten Wert aus.

```cpp
template <class T>
inline T atomic_fetch_and_explicit(
    volatile atomic<T>* Atom,
    T Value,
    memory_order Order) noexcept;

template <class T>
inline T atomic_fetch_and_explicit(
    volatile atomic<T>* Atom,
    T Value,
    memory_order Order) noexcept;
```

### <a name="parameters"></a>Parameter

*Atom* ein Zeiger auf ein `atomic` Objekt, das einen Wert vom Typ speichert `T`.

*Wert* ein Wert vom Typ `T`.

*Reihenfolge* ein [Memory_order](../standard-library/atomic-enums.md#memory_order_enum).

### <a name="return-value"></a>Rückgabewert

Der Wert, der unmittelbar vor dem Ausführen des Vorgangs im atomischen Objekt enthalten war.

### <a name="remarks"></a>Hinweise

Die `atomic_fetch_and_explicit` Funktion führt eine `read-modify-write` Vorgang zum Ersetzen des gespeicherten Werts von *Atom* mit einer bitweisen `and` von *Wert* und den aktuellen Wert an, die in gespeichertist*Atom*, innerhalb der mit den vom angegebenen *Reihenfolge*.

## <a name="atomic_fetch_or"></a> atomic_fetch_or

Führt ein bitweises `or` auf einem Wert und einem vorhandenen in einem `atomic`-Objekt gespeicherten Wert aus.

```cpp
template <class T>
inline T atomic_fetch_or (volatile atomic<T>* Atom, T Value) noexcept;
template <class T>
inline T atomic_fetch_or (volatile atomic<T>* Atom, T Value) noexcept;
```

### <a name="parameters"></a>Parameter

*Atom* ein Zeiger auf ein `atomic` Objekt, das einen Wert vom Typ speichert `T`.

*Wert* ein Wert vom Typ `T`.

### <a name="return-value"></a>Rückgabewert

Der Wert, der unmittelbar vor dem Ausführen des Vorgangs im atomischen Objekt enthalten war.

### <a name="remarks"></a>Hinweise

Die `atomic_fetch_or` Funktion führt eine `read-modify-write` Vorgang zum Ersetzen des gespeicherten Werts von *Atom* mit einer bitweisen `or` von *Wert* und den aktuellen Wert an, die in gespeichertist*Atom*unter Verwendung der `memory_order_seq_cst` [Memory_order](../standard-library/atomic-enums.md#memory_order_enum).

## <a name="atomic_fetch_or_explicit"></a> atomic_fetch_or_explicit

Führt ein bitweises `or` auf einem Wert und einem vorhandenen in einem `atomic`-Objekt gespeicherten Wert aus.

```cpp
template <class T>
inline T atomic_fetch_or_explicit(
    volatile atomic<T>* Atom,
    T Value,
    memory_order Order) noexcept;

template <class T>
inline T atomic_fetch_or_explicit(
    volatile atomic<T>* Atom,
    T Value,
    memory_order Order) noexcept;
```

### <a name="parameters"></a>Parameter

*Atom* ein Zeiger auf ein `atomic` Objekt, das einen Wert vom Typ speichert `T`.

*Wert* ein Wert vom Typ `T`.

*Reihenfolge* ein [Memory_order](../standard-library/atomic-enums.md#memory_order_enum).

### <a name="return-value"></a>Rückgabewert

Der Wert, der unmittelbar vor dem Ausführen des Vorgangs im atomischen Objekt enthalten war.

### <a name="remarks"></a>Hinweise

Die `atomic_fetch_or_explicit` Funktion führt eine `read-modify-write` Vorgang zum Ersetzen des gespeicherten Werts von *Atom* mit einer bitweisen `or` von *Wert* und den aktuellen Wert an, die in gespeichertist*Atom*innerhalb der [Memory_order](../standard-library/atomic-enums.md#memory_order_enum) angegebenen *Reihenfolge*.

## <a name="atomic_fetch_sub"></a> atomic_fetch_sub

Subtrahiert einen Wert von einem in einem `atomic`-Objekt vorhandenen Wert.

```cpp
template <class T>
T* atomic_fetch_sub(
    volatile atomic<T*>* Atom,
    ptrdiff_t Value) noexcept;

template <class T>
T* atomic_fetch_sub(
    atomic<T*>* Atom,
    ptrdiff_t Value) noexcept;
```

### <a name="parameters"></a>Parameter

*Atom* ein Zeiger auf ein `atomic` Objekt, das einen Zeiger auf den Typ speichert `T`.

*Wert* ein Wert vom Typ `ptrdiff_t`.

### <a name="return-value"></a>Rückgabewert

Der Wert des unmittelbar vor dem Ausführen des Vorgangs im atomischen Objekt enthaltenen Zeigers.

### <a name="remarks"></a>Hinweise

Die `atomic_fetch_sub` Funktion führt eine `read-modify-write` Vorgang atomar subtrahiert werden soll *Wert* aus den gespeicherten Wert in *Atom*unter Verwendung der `memory_order_seq_cst` [Memory_order](../standard-library/atomic-enums.md#memory_order_enum) Einschränkung.

Wenn der atomare Typ ist `atomic_address`, *Wert* weist den Typ `ptrdiff_t` und der Vorgang behandelt den gespeicherten Zeiger als einen `char *`.

Dieser Vorgang wird auch bei Integraltypen überladen:

```cpp
integral atomic_fetch_sub(volatile atomic-integral* Atom, integral Value) noexcept;
integral atomic_fetch_sub(atomic-integral* Atom, integral Value) noexcept;
```

## <a name="atomic_fetch_sub_explicit"></a> atomic_fetch_sub_explicit

Subtrahiert einen Wert von einem in einem `atomic`-Objekt vorhandenen Wert.

```cpp
template <class T>
T* atomic_fetch_sub_explicit(
    volatile atomic<T*>* Atom,
    ptrdiff_t Value,
    memory_order Order) noexcept;

template <class T>
T* atomic_fetch_sub_explicit(
    atomic<T*>* Atom,
    ptrdiff_t Value, memory_order Order) noexcept;
```

### <a name="parameters"></a>Parameter

*Atom* ein Zeiger auf ein `atomic` Objekt, das einen Zeiger auf den Typ speichert `T`.

*Wert* ein Wert vom Typ `ptrdiff_t`.

### <a name="return-value"></a>Rückgabewert

Der Wert des unmittelbar vor dem Ausführen des Vorgangs im atomischen Objekt enthaltenen Zeigers.

### <a name="remarks"></a>Hinweise

Die `atomic_fetch_sub_explicit` Funktion führt eine `read-modify-write` Vorgang atomar subtrahiert *Wert* aus den gespeicherten Wert in *Atom*in die [Memory_order](../standard-library/atomic-enums.md#memory_order_enum) Einschränkungen, die vom angegebenen `Order`.

Wenn der atomare Typ ist `atomic_address`, *Wert* weist den Typ `ptrdiff_t` und der Vorgang behandelt den gespeicherten Zeiger als einen `char *`.

Dieser Vorgang wird auch bei Integraltypen überladen:

```cpp
integral atomic_fetch_sub_explicit(
    volatile atomic-integral* Atom,
    integral Value,
    memory_order Order) noexcept;

integral atomic_fetch_sub_explicit(
    atomic-integral* Atom,
    integral Value,
    memory_order Order) noexcept;
```

## <a name="atomic_fetch_xor"></a> atomic_fetch_xor

Führt ein bitweises `exclusive or` auf einem Wert und einem vorhandenen in einem `atomic`-Objekt gespeicherten Wert aus.

```cpp
template <class T>
inline T atomic_fetch_xor(volatile atomic<T>* Atom, T Value) noexcept;

template <class T>
inline T atomic_fetch_xor(volatile atomic<T>* Atom, T Value) noexcept;
```

### <a name="parameters"></a>Parameter

*Atom* ein Zeiger auf ein `atomic` Objekt, das einen Wert vom Typ speichert `T`.

*Wert* ein Wert vom Typ `T`.

### <a name="return-value"></a>Rückgabewert

Der Wert, der unmittelbar vor dem Ausführen des Vorgangs im atomischen Objekt enthalten war.

### <a name="remarks"></a>Hinweise

Die `atomic_fetch_xor` Funktion führt eine `read-modify-write` Vorgang zum Ersetzen des gespeicherten Werts von *Atom* mit einer bitweisen `exclusive or` von *Wert* und den aktuellen Wert an, die in gespeichertist*Atom*unter Verwendung der `memory_order_seq_cst` [Memory_order](../standard-library/atomic-enums.md#memory_order_enum).

## <a name="atomic_fetch_xor_explicit"></a> atomic_fetch_xor_explicit

Führt ein bitweises `exclusive or` auf einem Wert und einem vorhandenen in einem `atomic`-Objekt gespeicherten Wert aus.

```cpp
template <class T>
inline T atomic_fetch_xor_explicit(
    volatile atomic<T>* Atom,
    T Value,
    memory_order Order) noexcept;

template <class T>
inline T atomic_fetch_xor_explicit(
    volatile atomic<T>* Atom,
    T Value,
    memory_order Order) noexcept;
```

### <a name="parameters"></a>Parameter

*Atom* ein Zeiger auf ein `atomic` Objekt, das einen Wert vom Typ speichert `T`.

*Wert* ein Wert vom Typ `T`.

*Reihenfolge* ein [Memory_order](../standard-library/atomic-enums.md#memory_order_enum).

### <a name="return-value"></a>Rückgabewert

Der Wert, der unmittelbar vor dem Ausführen des Vorgangs im atomischen Objekt enthalten war.

### <a name="remarks"></a>Hinweise

Die `atomic_fetch_xor_explicit` Funktion führt eine `read-modify-write` Vorgang zum Ersetzen des gespeicherten Werts von *Atom* mit einer bitweisen `exclusive or` von *Wert* und den aktuellen Wert an, die in gespeichertist*Atom*innerhalb der [Memory_order](../standard-library/atomic-enums.md#memory_order_enum) Einschränkungen, die vom angegebenen *Reihenfolge*.

## <a name="atomic_flag_clear"></a> atomic_flag_clear

Legt die **"bool"** -flag in einer [Atomic_flag](../standard-library/atomic-flag-structure.md) -Objekt **"false"** innerhalb der `memory_order_seq_cst` [Memory_order](../standard-library/atomic-enums.md#memory_order_enum).

```cpp
inline void atomic_flag_clear(volatile atomic_flag* Flag) noexcept;
inline void atomic_flag_clear(atomic_flag* Flag) noexcept;
```

### <a name="parameters"></a>Parameter

*Flag* ein Zeiger auf ein `atomic_flag` Objekt.

## <a name="atomic_flag_clear_explicit"></a> atomic_flag_clear_explicit

Legt die **"bool"** -flag in einem [Atomic_flag](../standard-library/atomic-flag-structure.md) -Objekt **"false"**, innerhalb des angegebenen [Memory_order](../standard-library/atomic-enums.md#memory_order_enum) Einschränkungen.

```cpp
inline void atomic_flag_clear_explicit(volatile atomic_flag* Flag, memory_order Order) noexcept;
inline void atomic_flag_clear_explicit(atomic_flag* Flag, memory_order Order) noexcept;
```

### <a name="parameters"></a>Parameter

*Flag* ein Zeiger auf ein `atomic_flag` Objekt.

*Reihenfolge* ein [Memory_order](../standard-library/atomic-enums.md#memory_order_enum).

## <a name="atomic_flag_test_and_set"></a> atomic_flag_test_and_set

Legt die **"bool"** -flag in einer [Atomic_flag](../standard-library/atomic-flag-structure.md) -Objekt **"true"**, innerhalb der Einschränkungen der der `memory_order_seq_cst` [Memory_order](../standard-library/atomic-enums.md#memory_order_enum).

```cpp
inline bool atomic_flag_test_and_set(volatile atomic_flag* Flag,) noexcept;
inline bool atomic_flag_test_and_set(atomic_flag* Flag,) noexcept;
```

### <a name="parameters"></a>Parameter

*Flag* ein Zeiger auf ein `atomic_flag` Objekt.

### <a name="return-value"></a>Rückgabewert

Der Anfangswert des *Flag*.

## <a name="atomic_flag_test_and_set_explicit"></a> atomic_flag_test_and_set_explicit

Legt die **"bool"** -flag in einem [Atomic_flag](../standard-library/atomic-flag-structure.md) -Objekt **"true"**, innerhalb des angegebenen [Memory_order](../standard-library/atomic-enums.md#memory_order_enum) Einschränkungen.

```cpp
inline bool atomic_flag_test_and_set_explicit(volatile atomic_flag* Flag, memory_order Order) noexcept;
inline bool atomic_flag_test_and_set_explicit(atomic_flag* Flag, memory_order Order) noexcept;
```

### <a name="parameters"></a>Parameter

*Flag* ein Zeiger auf ein `atomic_flag` Objekt.

*Reihenfolge* ein [Memory_order](../standard-library/atomic-enums.md#memory_order_enum).

### <a name="return-value"></a>Rückgabewert

Der Anfangswert des *Flag*.

## <a name="atomic_init"></a> atomic_init

Legt den gespeicherten Wert in einem `atomic`-Objekt fest.

```cpp
template <class Ty>
inline void atomic_init(volatile atomic<Ty>* Atom, Ty Value) noexcept;
template <class Ty>
inline void atomic_init(atomic<Ty>* Atom, Ty Value) noexcept;
```

### <a name="parameters"></a>Parameter

*Atom* ein Zeiger auf ein `atomic` Objekt, das einen Wert vom Typ speichert `Ty`.

*Wert* ein Wert vom Typ `Ty`.

### <a name="remarks"></a>Hinweise

`atomic_init` ist kein atomischer Vorgang. Ist nicht threadsicher.

## <a name="atomic_is_lock_free"></a> atomic_is_lock_free

Gibt an, ob die atomischen Vorgänge auf ein `atomic`-Objekt *sperrfrei* sind.

```cpp
template <class T>
inline bool atomic_is_lock_free(const volatile atomic<T>* Atom) noexcept;
template <class T>
inline bool atomic_is_lock_free(const atomic<T>* Atom) noexcept;
```

### <a name="parameters"></a>Parameter

*Atom* ein Zeiger auf ein `atomic` Objekt, das einen Wert vom Typ speichert `T`.

### <a name="return-value"></a>Rückgabewert

**"true"** Wenn atomischen Vorgänge auf *Atom* sind sperrfrei sind; andernfalls **"false"**.

### <a name="remarks"></a>Hinweise

Ein atomischer Typ ist sperrfrei, wenn für keine der atomischen Vorgänge auf diesem Typ Sperren verwendet werden. Wenn diese Funktion TRUE zurückgibt, ist der Typ sicher und kann in Signalhandlern verwendet werden.

## <a name="atomic_load"></a> atomic_load

Ruft den gespeicherten Wert in einem `atomic`-Objekt ab.

```cpp
template <class Ty>
inline Ty atomic_load(const volatile atomic<Ty>* Atom) noexcept;
template <class Ty>
inline Ty atomic_load(const atomic<Ty>* Atom) noexcept;
```

### <a name="parameters"></a>Parameter

*Atom* ein Zeiger auf ein `atomic` Objekt, das einen Wert vom Typ enthält `Ty`.

### <a name="return-value"></a>Rückgabewert

Der abgerufene Wert, der in gespeichert ist *Atom*.

### <a name="remarks"></a>Hinweise

`atomic_load` verwendet implizit `memory_order_seq_cst`[memory_order](../standard-library/atomic-enums.md#memory_order_enum).

## <a name="atomic_load_explicit"></a> atomic_load_explicit

Ruft den gespeicherten Wert in einem `atomic`-Objekt in einer angegebenen [memory_order](../standard-library/atomic-enums.md#memory_order_enum) ab.

```cpp
template <class Ty>
inline Ty atomic_load_explicit(const volatile atomic<Ty>* Atom, memory_order Order) noexcept;
template <class Ty>
inline Ty atomic_load_explicit(const atomic<Ty>* Atom, memory_order Order) noexcept;
```

### <a name="parameters"></a>Parameter

*Atom* ein Zeiger auf ein `atomic` Objekt, das einen Wert vom Typ enthält `Ty`.

*Reihenfolge* ein [Memory_order](../standard-library/atomic-enums.md#memory_order_enum). Verwenden Sie nicht `memory_order_release` oder `memory_order_acq_rel`.

### <a name="return-value"></a>Rückgabewert

Der abgerufene Wert, der in gespeichert ist *Atom*.

## <a name="atomic_signal_fence"></a> atomic_signal_fence

Fungiert als *Umgrenzung* (das ist eine Arbeitsspeicher-Synchronisierungsprimitive, mit der die Reihenfolge zwischen Lade- bzw. Speichervorgängen erzwungen wird) zwischen anderen Umgrenzungen in einem aufrufenden Thread, die über im gleichen Thread ausgeführte Signalhandler verfügen.

```cpp
inline void atomic_signal_fence(memory_order Order) noexcept;
```

### <a name="parameters"></a>Parameter

*Reihenfolge* eine Einschränkung, die umgrenzungstyp bestimmt die speichersortierung.

### <a name="remarks"></a>Hinweise

Die *Reihenfolge* Argument bestimmt den umgrenzungstyp.

|||
|-|-|
|`memory_order_relaxed`|Die Umgrenzung hat keine Auswirkung.|
|`memory_order_consume`|Die Umgrenzung ist eine Abrufumgrenzung.|
|`memory_order_acquire`|Die Umgrenzung ist eine Abrufumgrenzung.|
|`memory_order_release`|Die Umgrenzung ist eine Releaseumgrenzung.|
|`memory_order_acq_rel`|Die Umgrenzung ist eine Abrufumgrenzung und eine Releaseumgrenzung.|
|`memory_order_seq_cst`|Die Umgrenzung ist eine Abrufumgrenzung und eine Releaseumgrenzung, und sie ist sequenziell konsistent.|

## <a name="atomic_store"></a> atomic_store

Speichert einen Wert atomisch in einem atomischen Objekt.

```cpp
template <class Ty>
inline Ty atomic_store_explicit(const volatile atomic<Ty>* Atom, Ty Value) noexcept;
template <class Ty>
inline Ty atomic_store_explicit(const atomic<Ty>* Atom, T Value) noexcept;
```

### <a name="parameters"></a>Parameter

*Atom* ein Zeiger auf ein atomisches Objekt, das einen Wert vom Typ enthält `Ty`.

*Wert* ein Wert vom Typ `Ty`.

### <a name="remarks"></a>Hinweise

`atomic_store` speichert *Wert* im-Objekt, auf das von *Atom*innerhalb der `memory_order_seq_cst` [Memory_order](../standard-library/atomic-enums.md#memory_order_enum) Einschränkung.

## <a name="atomic_store_explicit"></a> atomic_store_explicit

Speichert einen Wert atomisch in einem atomischen Objekt.

```cpp
template <class Ty>
inline Ty atomic_store_explicit(
    const volatile atomic<Ty>* Atom,
    Ty Value,
    memory_order Order) noexcept;

template <class Ty>
inline Ty atomic_store_explicit(
    const atomic<Ty>* Atom,
    T Value,
    memory_order Order) noexcept;
```

### <a name="parameters"></a>Parameter

*Atom* ein Zeiger auf ein `atomic` Objekt, das einen Wert vom Typ enthält `Ty`.

*Wert* ein Wert vom Typ `Ty`.

*Reihenfolge* ein [Memory_order](../standard-library/atomic-enums.md#memory_order_enum). Verwenden Sie nicht `memory_order_consume`, `memory_order_acquire`, oder `memory_order_acq_rel`.

### <a name="remarks"></a>Hinweise

`atomic_store` speichert *Wert* im-Objekt, auf das von *Atom*innerhalb der `memory_order` angegebenen *Reihenfolge*.

## <a name="atomic_thread_fence"></a> atomic_thread_fence

Fungiert als *Umgrenzung*. Dabei handelt es sich um eine Arbeitsspeichersynchronisierungs-Primitive, mit der die Reihenfolge zwischen Lade- bzw. Speichervorgängen ohne einen zugeordneten atomischen Vorgang erzwungen wird.

```cpp
inline void atomic_thread_fence(memory_order Order) noexcept;
```

### <a name="parameters"></a>Parameter

*Reihenfolge* eine Einschränkung, die umgrenzungstyp bestimmt die speichersortierung.

### <a name="remarks"></a>Hinweise

Die *Reihenfolge* Argument bestimmt den umgrenzungstyp.

|||
|-|-|
|`memory_order_relaxed`|Die Umgrenzung hat keine Auswirkung.|
|`memory_order_consume`|Die Umgrenzung ist eine Abrufumgrenzung.|
|`memory_order_acquire`|Die Umgrenzung ist eine Abrufumgrenzung.|
|`memory_order_release`|Die Umgrenzung ist eine Releaseumgrenzung.|
|`memory_order_acq_rel`|Die Umgrenzung ist eine Abrufumgrenzung und eine Releaseumgrenzung.|
|`memory_order_seq_cst`|Die Umgrenzung ist eine Abrufumgrenzung und eine Releaseumgrenzung, und sie ist sequenziell konsistent.|

## <a name="kill_dependency"></a> kill_dependency

Entfernt eine Abhängigkeit.

```cpp
template <class Ty>
Ty kill_dependency(Ty Arg) noexcept;
```

### <a name="parameters"></a>Parameter

*Arg* ein Wert vom Typ `Ty`.

### <a name="return-value"></a>Rückgabewert

Der Rückgabewert ist *Arg*. Die Auswertung von *Arg* ist keine Abhängigkeit auf den Funktionsaufruf. Durch Unterbrechen einer möglichen Abhängigkeitskette könnte die Funktion zulassen, dass der Compiler effizienteren Code generiert.

## <a name="see-also"></a>Siehe auch

[\<atomic>](../standard-library/atomic.md)<br/>
