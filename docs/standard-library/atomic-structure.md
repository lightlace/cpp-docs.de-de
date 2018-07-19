---
title: atomic-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/20/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- atomic/std::atomic
dev_langs:
- C++
ms.assetid: 261628ed-7049-41ac-99b9-cfe49f696b44
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0e5982fc303362a9636c4bf1b0e2d89c6aa05031
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38962357"
---
# <a name="atomic-structure"></a>atomic-Struktur

Beschreibt ein Objekt, das vom Typ der atomischen Vorgänge auf einem gespeicherten Wert führt *Ty*.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
struct atomic;
```

## <a name="members"></a>Member

|Member|Beschreibung|
|----------|-----------------|
|**Konstruktor**||
|[atomic](#atomic)|Erstellt ein atomisches Objekt.|
|**Operatoren**||
|[Atomic:: Ty](#op_ty)|Liest und den gespeicherten Wert und gibt ihn zurück. ([Atomic:: Load](#load))|
|[Atomic:: =](#op_eq)|Verwendet zum Ersetzen des gespeicherten Werts einen angegebenen Wert. ([Atomic:: Store](#store))|
|[Atomic:: Operator++-](#op_inc)|Erhöht den gespeicherten Wert. Wird nur von integrale und Zeigerspezialisierungen verwendet.|
|[Atomic:: Operator +=](#op_add_eq)|Fügt dem gespeicherten Wert einen angegebenen Wert hinzu. Wird nur von integrale und Zeigerspezialisierungen verwendet.|
|[Atomic:::](#op_dec)|Verringert den gespeicherten Wert. Wird nur von integrale und Zeigerspezialisierungen verwendet.|
|[Atomic:: Operator-=](#op_sub_eq)|Subtrahiert einen angegebenen Wert vom gespeicherten Wert. Wird nur von integrale und Zeigerspezialisierungen verwendet.|
|[Atomic:: & =](#op_and_eq)|Führt ein bitweises und auf einem angegebenen Wert und den gespeicherten Wert. Wird nur bei Integralspezialisierungen verwendet.|
|[Atomic::&#124;=](#op_or_eq)|Führt ein bitweises oder auf einem angegebenen Wert und den gespeicherten Wert. Wird nur bei Integralspezialisierungen verwendet.|
|[Atomic:: ^ =](#op_xor_eq)|Führt eine bitweise exklusive oder auf einem angegebenen Wert und den gespeicherten Wert. Wird nur bei Integralspezialisierungen verwendet.|
|**Funktionen**||
|[compare_exchange_strong](#compare_exchange_strong)|Führt eine *Atomic_compare_and_exchange* -Vorgang für **dies** und gibt das Ergebnis zurück.|
|[compare_exchange_weak](#compare_exchange_weak)|Führt eine *Weak_atomic_compare_and_exchange* -Vorgang für **dies** und gibt das Ergebnis zurück.|
|[fetch_add](#fetch_add)|Fügt dem gespeicherten Wert einen angegebenen Wert hinzu.|
|[fetch_and](#fetch_and)|Führt ein bitweises und auf einem angegebenen Wert und den gespeicherten Wert.|
|[fetch_or](#fetch_or)|Führt ein bitweises oder auf einem angegebenen Wert und den gespeicherten Wert.|
|[fetch_sub](#fetch_sub)|Subtrahiert einen angegebenen Wert vom gespeicherten Wert.|
|[fetch_xor](#fetch_xor)|Führt eine bitweise exklusive oder auf einem angegebenen Wert und den gespeicherten Wert.|
|[is_lock_free](#is_lock_free)|Gibt an, ob der atomischen Vorgänge auf **dies** sind *sperrfrei*. Ein atomischer Typ ist *sperrfrei*, wenn für keine der atomischen Vorgänge auf diesem Typ Sperren verwendet werden.|
|[Auslastungstest](#load)|Liest und den gespeicherten Wert und gibt ihn zurück.|
|[store](#store)|Verwendet zum Ersetzen des gespeicherten Werts einen angegebenen Wert.|

## <a name="remarks"></a>Hinweise

Der Typ *Ty* muss *Trivial kopierbares*. D. h. [Memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md) Kopieren der Bytes muss erzeugen eine gültige *Ty* -Objekt, das im Vergleich dem ursprünglichen Objekt entspricht. Die [Compare_exchange_weak](#compare_exchange_weak) und [Compare_exchange_strong](#compare_exchange_strong) Memberfunktionen [Memcmp](../c-runtime-library/reference/memcmp-wmemcmp.md) zu bestimmen, ob zwei *Ty* Werte gleich sind. Diese Funktionen werden nicht dazu verwendet eine *Ty*-definierten `operator==`. Die Memberfunktionen der `atomic` verwenden `memcpy` zum Kopieren von Werten des Typs *Ty*.

Eine teilweise Spezialisierung, **atomic\<Ty \* >** , für alle Zeigertypen vorhanden ist. Mit der Spezialisierung wird das Hinzufügen eines Offsets zum verwalteten Zeigerwert oder die Wegnahme eines Offsets von dort ermöglicht. Die arithmetischen Operationen akzeptieren ein Argument vom Typ `ptrdiff_t` , und passen Sie dieses Argument entsprechend der Größe der *Ty* mit normaler Adressenarithmetik konsistent ist.

Eine Spezialisierung ist für jeden Integraltypen außer vorhanden **"bool"**. Mit jeder Spezialisierung wird ein umfangreicher Satz an Methoden für atomisch arithmetische und logische Vorgänge bereitgestellt.

||||
|-|-|-|
|**Atomic\<Char >**|**Atomic\<signiert Char >**|**Atomic\<unsigned Char >**|
|**Atomic\<char16_t >**|**Atomic\<char32_t >**|**Atomic\<"wchar_t" >**|
|**Atomic\<kurze >**|**Atomic\<unsigned short >**|**Atomic\<Int >**|
|**Atomic\<unsigned Int >**|**Atomic\<lange >**|**Atomic\<unsigned long >**|
|**Atomic\<long long >**|**Atomic\<long long ohne Vorzeichen >**|

Integralspezialisierungen werden von den entsprechenden `atomic_integral`-Typen abgeleitet. Z. B. **atomic\<unsigned Int >** ergibt sich aus `atomic_uint`.

## <a name="requirements"></a>Anforderungen

**Header:** \<atomic >

**Namespace:** std

## <a name="atomic"></a> Atomic:: Atomic

Erstellt ein atomisches Objekt.

```cpp
atomic();
atomic( const atomic& );
atomic( Ty Value ) noexcept;
```

### <a name="parameters"></a>Parameter

*Wert*<br/>
Initialisierungswert

### <a name="remarks"></a>Hinweise

Atomische Objekte können nicht kopiert oder verschoben werden.

Objekte, die Instanziierungen von atomaren sind\<*Ty*> kann nur durch den Konstruktor, der ein des Typs Argument initialisiert werden *Ty* und nicht mithilfe aggregierten Initialisierung. Allerdings können Atomic_integral-Objekte initialisiert werden, nur mithilfe von aggregierter Initialisierung.

```cpp
atomic<int> ai0 = ATOMIC_VAR_INIT(0);
atomic<int> ai1(0);
```

## <a name="op_ty"></a> Atomic:: *Ty*

Der Operator für dem angegebenen Typ in der Vorlage, die atomare\<*Ty*>. Ruft den gespeicherten Wert in  **\*dies**.

```cpp
atomic<Ty>::operator Ty() const volatile noexcept;
atomic<Ty>::operator Ty() const noexcept;
```

### <a name="remarks"></a>Hinweise

Dieser Operator gilt die `memory_order_seq_cst` [Memory_order](atomic-enums.md).

## <a name="op_eq"></a> Atomic:: =

Speichert einen angegebenen Wert.

```cpp
Ty operator=(
   Ty Value
) volatile noexcept;
Ty operator=(
   Ty Value
) noexcept;
```

### <a name="parameters"></a>Parameter

*Wert*<br/>
Ein *Ty* Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt *Wert*.

## <a name="op_inc"></a> Atomic:: Operator++-

Erhöht den gespeicherten Wert. Wird nur von integrale und Zeigerspezialisierungen verwendet.

```cpp
Ty atomic<Ty>::operator++(int) volatile noexcept;
Ty atomic<Ty>::operator++(int) noexcept;
Ty atomic<Ty>::operator++() volatile noexcept;
Ty atomic<Ty>::operator++() noexcept;
```

### <a name="return-value"></a>Rückgabewert

Die ersten beiden Operatoren zurückgegeben wird den inkrementierten Wert. die letzten beiden Operatoren geben den Wert vor dem Inkrementieren zurück. Verwenden Sie die Operatoren der `memory_order_seq_cst` [Memory_order](atomic-enums.md).

## <a name="op_add_eq"></a> Atomic:: Operator +=

Fügt dem gespeicherten Wert einen angegebenen Wert hinzu. Wird nur von integrale und Zeigerspezialisierungen verwendet.

```cpp
Ty atomic<Ty>::operator+=(
   Ty Value
) volatile noexcept;
Ty atomic<Ty>::operator+=(
   Ty Value
) noexcept;
```

### <a name="parameters"></a>Parameter

*Wert*<br/>
Ein Wert Ganzzahltypen oder Zeigertypen.

### <a name="return-value"></a>Rückgabewert

Ein *Ty* -Objekt, das das Ergebnis der Addition enthält.

### <a name="remarks"></a>Hinweise

Dieser Operator wird verwendet, die `memory_order_seq_cst` [Memory_order](atomic-enums.md).

## <a name="op_dec"></a> Atomic:::

Verringert den gespeicherten Wert. Wird nur von integrale und Zeigerspezialisierungen verwendet.

```cpp
Ty atomic<Ty>::operator--(int) volatile noexcept;
Ty atomic<Ty>::operator--(int) noexcept;
Ty atomic<Ty>::operator--() volatile noexcept;
Ty atomic<Ty>::operator--() noexcept;
```

### <a name="return-value"></a>Rückgabewert

Die ersten beiden Operatoren den dekrementierte Wert zurückgegeben wird. die letzten beiden Operatoren geben den Wert vor dem verringern zurück. Verwenden Sie die Operatoren der `memory_order_seq_cst` [Memory_order](atomic-enums.md).

## <a name="op_sub_eq"></a> Atomic:: Operator-=

Subtrahiert einen angegebenen Wert vom gespeicherten Wert. Wird nur von integrale und Zeigerspezialisierungen verwendet.

```cpp
Ty atomic<Ty>::operator-=(
   Ty Value
) volatile noexcept;
Ty atomic<Ty>::operator-=(
   Ty Value
) noexcept;
```

### <a name="parameters"></a>Parameter

*Wert*<br/>
Ein Wert Ganzzahltypen oder Zeigertypen.

### <a name="return-value"></a>Rückgabewert

Ein *Ty* -Objekt, das das Ergebnis der Subtraktion enthält.

### <a name="remarks"></a>Hinweise

Dieser Operator wird verwendet, die `memory_order_seq_cst` [Memory_order](atomic-enums.md).

## <a name="op_and_eq"></a> Atomic:: & =

Führt ein bitweises und auf einem angegebenen Wert und den gespeicherten Wert von  **\*dies**. Wird nur bei Integralspezialisierungen verwendet.

```cpp
atomic<Ty>::operator&= (
   Ty Value
) volatile noexcept;
atomic<Ty>::operator&= (
   Ty Value
) noexcept;
```

### <a name="parameters"></a>Parameter

*Wert*<br/>
Ein Wert vom Typ *Ty*.

### <a name="return-value"></a>Rückgabewert

Das Ergebnis der bitweisen und.

### <a name="remarks"></a>Hinweise

Dieser Operator führt einen Lese-Änderungs-Schreib-Vorgang zum Ersetzen des gespeicherten Werts von  **\*dies** durch ein bitweises und der *Wert* und den aktuellen Wert auf die in gespeicherten  **\*dies**, innerhalb der Einschränkungen der der `memory_order_seq_cst` [Memory_order](atomic-enums.md).

## <a name="op_or_eq"></a> Atomic::&#124;=

Führt ein bitweises oder in einem angegebenen Wert und den gespeicherten Wert von  **\*dies**. Wird nur bei Integralspezialisierungen verwendet.

```cpp
atomic<Ty>::operator|= (
   Ty Value
) volatile noexcept;
atomic<Ty>::operator|= (
   Ty Value
) noexcept;
```

### <a name="parameters"></a>Parameter

*Wert*<br/>
Ein Wert vom Typ *Ty*.

### <a name="return-value"></a>Rückgabewert

Das Ergebnis der bitweisen oder.

### <a name="remarks"></a>Hinweise

Dieser Operator führt einen Lese-Änderungs-Schreib-Vorgang zum Ersetzen des gespeicherten Werts von  **\*dies** mit einem bitweisen oder von *Wert* und den aktuellen Wert auf die in gespeicherten  **\*dies**, innerhalb der Einschränkungen der der `memory_order_seq_cst` [Memory_order](atomic-enums.md) Einschränkungen.

## <a name="op_xor_eq"></a> Atomic:: ^ =

Führt eine bitweise exklusive oder in einem angegebenen Wert und den gespeicherten Wert von  **\*dies**. Wird nur bei Integralspezialisierungen verwendet.

```cpp
atomic<Ty>::operator^= (
   Ty Value
) volatile noexcept;
atomic<Ty>::operator^= (
   Ty Value
) noexcept;
```

### <a name="parameters"></a>Parameter

*Wert*<br/>
Ein Wert vom Typ *Ty*.

### <a name="return-value"></a>Rückgabewert

Das Ergebnis des bitweisen exklusiven oder.

### <a name="remarks"></a>Hinweise

Dieser Operator führt einen Lese-Änderungs-Schreib-Vorgang zum Ersetzen des gespeicherten Werts von  **\*dies** mit eine bitweise exklusive oder von *Wert* und den aktuellen Wert auf die in gespeicherten  **\*dies**, innerhalb der Einschränkungen der der `memory_order_seq_cst` [Memory_order](atomic-enums.md) Einschränkungen.

## <a name="compare_exchange_strong"></a> Atomic:: compare_exchange_strong

Führt einen atomischen Vergleichs- und Austausch-Vorgang für  **\*dies**.

```cpp
bool compare_exchange_strong(
   Ty& Exp,
   Ty Value,
   memory_order Order1,
   memory_order Order2
) volatile noexcept;
bool compare_exchange_strong(
   Ty& Exp,
   Ty Value,
   memory_order Order1,
   memory_order Order2
) noexcept;
bool compare_exchange_strong(
   Ty& Exp,
   Ty Value,
   memory_order Order1 = memory_order_seq_cst
) volatile noexcept;
bool compare_exchange_strong(
   Ty& Exp,
   Ty Value,
   memory_order Order1 = memory_order_seq_cst
) noexcept;
```

### <a name="parameters"></a>Parameter

*Exp*<br/>
Ein Wert vom Typ *Ty*.

*Wert*<br/>
Ein Wert vom Typ *Ty*.

*Order1*<br/>
Erste `memory_order` Argument.

*Order2*<br/>
Zweites `memory_order`-Argument.

### <a name="return-value"></a>Rückgabewert

Ein **"bool"** , der das Ergebnis des Vergleichs Wert angibt.

### <a name="remarks"></a>Hinweise

Dieser unteilbare Vergleichs- und Austausch-Vorgang wird der Wert verglichen, die in gespeichert ist  **\*dies** mit *"exp"*. Wenn die Werte gleich sind, ersetzt den Wert, der in gespeichert ist  **\*dies** mit *Wert* durch Verwendung einer Lese-Änderungs-Schreib-Operation und anwenden, die Einschränkungen für die Speicherreihenfolge gemäß *Order1*. Wenn die Werte nicht gleich sind, der Vorgang wird verwendet, die in gespeichert ist  **\*dies** ersetzen *"exp"* und mit den vom angegebenen Einschränkungen für die Speicherreihenfolge angewendet *Order2* .

Überladungen, die nicht über eine zweite verfügen `memory_order` eine implizite *Order2* , basiert auf dem Wert des *Order1*. Wenn *Order1* ist `memory_order_acq_rel`, *Order2* ist `memory_order_acquire`. Wenn *Order1* ist `memory_order_release`, *Order2* ist `memory_order_relaxed`. In allen anderen Fällen *Order2* gleich *Order1*.

Für Überladungen, die zwei `memory_order` Parameter wird der Wert des *Order2* darf nicht sein `memory_order_release` oder `memory_order_acq_rel`, und darf nicht stärker als der Wert des *Order1*.

## <a name="compare_exchange_weak"></a> Atomic:: compare_exchange_weak

Führt schwachen atomischen Vergleichs- und Austausch-Vorgang für  **\*dies**.

```cpp
bool compare_exchange_weak(
   Ty& Exp,
   Ty Value,
   memory_order Order1,
   memory_order Order2
) volatile noexcept;
bool compare_exchange_weak(
   Ty& Exp,
   Ty Value,
   memory_order Order1,
   memory_order Order2
) noexcept;
bool compare_exchange_weak(
   Ty& Exp,
   Ty Value,
   memory_order Order1 = memory_order_seq_cst
) volatile noexcept;
bool compare_exchange_weak(
   Ty& Exp,
   Ty Value,
   memory_order Order1 = memory_order_seq_cst
) noexcept;
```

### <a name="parameters"></a>Parameter

*Exp*<br/>
Ein Wert vom Typ *Ty*.

*Wert*<br/>
Ein Wert vom Typ *Ty*.

*Order1*<br/>
Erste `memory_order` Argument.

*Order2*<br/>
Zweites `memory_order`-Argument.

### <a name="return-value"></a>Rückgabewert

Ein **"bool"** , der das Ergebnis des Vergleichs Wert angibt.

### <a name="remarks"></a>Hinweise

Dieser unteilbare Vergleichs- und Austausch-Vorgang wird der Wert verglichen, die in gespeichert ist  **\*dies** mit *"exp"*. Wenn die Werte gleich sind, ersetzt den Wert, der in gespeichert ist  **\*dies** mit*Wert* durch Verwendung einer Lese-Änderungs-Schreib-Operation und anwenden, die Einschränkungen für die Speicherreihenfolge gemäß *Order1*. Wenn die Werte nicht gleich sind, der Vorgang wird verwendet, die in gespeichert ist  **\*dies** ersetzen *"exp"* und mit den vom angegebenen Einschränkungen für die Speicherreihenfolge angewendet *Order2* .

Ein schwacher atomischer verglichen werden soll, und Exchange wird einen Austausch ausgeführt, wenn die verglichenen Werte gleich sind. Wenn die Werte nicht gleich sind, ist nicht sichergestellt, dass Austausch mit dem Vorgang ausgeführt wird.

Überladungen, die nicht über eine zweite verfügen `memory_order` eine implizite *Order2* , basiert auf dem Wert des *Order1*. Wenn *Order1* ist `memory_order_acq_rel`, *Order2* ist `memory_order_acquire`. Wenn *Order1* ist `memory_order_release`, *Order2* ist `memory_order_relaxed`. In allen anderen Fällen *Order2* gleich *Order1*.

Für Überladungen, die zwei `memory_order` Parameter wird der Wert des *Order2* darf nicht sein `memory_order_release` oder `memory_order_acq_rel`, und darf nicht stärker als der Wert des *Order1*.

## <a name="exchange"></a> Atomic:: Exchange

Verwendet einen angegebenen Wert ersetzt den gespeicherten Wert von  **\*dies**.

```cpp
Ty atomic<Ty>::exchange(
   Ty Value,
   memory_order Order = memory_order_seq_cst
) volatile noexcept;
Ty atomic<Ty>::exchange(
   Ty Value,
   memory_order Order = memory_order_seq_cst
) noexcept;
```

### <a name="parameters"></a>Parameter

*Wert*<br/>
Ein Wert vom Typ *Ty*.

*Reihenfolge*<br/>
Ein `memory_order`.

### <a name="return-value"></a>Rückgabewert

Der gespeicherte Wert von  **\*dies** vor dem Austausch.

### <a name="remarks"></a>Hinweise

Dieser Vorgang wird eine Lese-Änderungs-Schreib-Operation mit *Wert* zum Ersetzen des Werts, die in gespeicherten  **\*dies**, innerhalb der mit den vom angegebenen  *Reihenfolge*.

## <a name="fetch_add"></a> Atomic:: fetch_add

Ruft den Wert, der in gespeicherten  **\*dies**, und fügt dann den gespeicherten Wert einen angegebenen Wert hinzu.

```cpp
Ty atomic<Ty>::fetch_add (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) volatile noexcept;
Ty atomic<Ty>::fetch_add (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) noexcept;
```

### <a name="parameters"></a>Parameter

*Wert*<br/>
Ein Wert vom Typ *Ty*.

*Reihenfolge*<br/>
Ein `memory_order`.

### <a name="return-value"></a>Rückgabewert

Ein *Ty* -Objekt, das den Wert, der in gespeicherten enthält  **\*dies** vor dem hinzufügen.

### <a name="remarks"></a>Hinweise

Die `fetch_add` Methode führt einen Lese-Änderungs-Schreib-Vorgang atomar hinzufügen *Wert* gespeicherten Wert in  **\*dies**, und wendet die arbeitsspeichereinschränkungen, die von angegeben werden *Reihenfolge*.

## <a name="fetch_and"></a> Atomic:: fetch_and

Führt ein bitweises und auf einen Wert und einem vorhandenen Wert für die in gespeicherten  **\*dies**.

```cpp
Ty atomic<Ty>::fetch_and (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) volatile noexcept;
Ty atomic<Ty>::fetch_and (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) noexcept;
```

### <a name="parameters"></a>Parameter

*Wert*<br/>
Ein Wert vom Typ *Ty*.

*Reihenfolge*<br/>
Ein `memory_order`.

### <a name="return-value"></a>Rückgabewert

Ein *Ty* -Objekt, das das Ergebnis der bitweisen enthält und.

### <a name="remarks"></a>Hinweise

Die `fetch_and` Methode führt einen Lese-Änderungs-Schreib-Vorgang zum Ersetzen des gespeicherten Werts von  **\*dies** durch ein bitweises und der *Wert* und den aktuellen Wert an, die in gespeichertist **\*dies**, innerhalb der mit den vom angegebenen *Reihenfolge*.

## <a name="fetch_or"></a> Atomic:: fetch_or

Führt ein bitweises oder auf einen Wert und einem vorhandenen Wert für die in gespeicherten  **\*dies**.

```cpp
Ty atomic<Ty>::fetch_or (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) volatile noexcept;
Ty atomic<Ty>::fetch_or (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) noexcept;
```

### <a name="parameters"></a>Parameter

*Wert*<br/>
Ein Wert vom Typ *Ty*.

*Reihenfolge*<br/>
Ein `memory_order`.

### <a name="return-value"></a>Rückgabewert

Ein *Ty* -Objekt, das das Ergebnis der bitweisen enthält oder.

### <a name="remarks"></a>Hinweise

Die `fetch_or` Methode führt einen Lese-Änderungs-Schreib-Vorgang zum Ersetzen des gespeicherten Werts von  **\*dies** mit einem bitweisen oder von *Wert* und den aktuellen Wert an, die in gespeichertist **\*dies**, innerhalb der mit den vom angegebenen *Reihenfolge*.

## <a name="fetch_sub"></a> Atomic:: fetch_sub

Subtrahiert einen angegebenen Wert vom gespeicherten Wert.

```cpp
Ty atomic<Ty>::fetch_sub (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) volatile noexcept;
Ty atomic<Ty>::fetch_sub (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) noexcept;
```

### <a name="parameters"></a>Parameter

*Wert*<br/>
Ein Wert vom Typ *Ty*.

*Reihenfolge*<br/>
Ein `memory_order`.

### <a name="return-value"></a>Rückgabewert

Ein *Ty* -Objekt, das das Ergebnis der Subtraktion enthält.

### <a name="remarks"></a>Hinweise

Die `fetch_sub` Methode führt eine Lese-Änderungs-Schreib-Operation, um atomar zu subtrahieren *Wert* aus den gespeicherten Wert in  **\*dies**, innerhalb der mit den vom angegebenen *Reihenfolge*.

## <a name="fetch_xor"></a> Atomic:: fetch_xor

Führt eine bitweise exklusive oder auf einen Wert und einem vorhandenen Wert für die in gespeicherten  **\*dies**.

```cpp
Ty atomic<Ty>::fetch_xor (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) volatile noexcept;
Ty atomic<Ty>::fetch_xor (
   Ty Value,
   memory_order Order = memory_order_seq_cst
) noexcept;
```

### <a name="parameters"></a>Parameter

*Wert*<br/>
Ein Wert vom Typ *Ty*.

*Reihenfolge*<br/>
Ein `memory_order`.

### <a name="return-value"></a>Rückgabewert

Ein *Ty* -Objekt, das das Ergebnis des bitweisen exklusiven enthält oder.

### <a name="remarks"></a>Hinweise

Die `fetch_xor` Methode führt einen Lese-Änderungs-Schreib-Vorgang zum Ersetzen des gespeicherten Werts von  **\*dies** mit eine bitweise exklusive oder von *Wert* und den aktuellen Wert an, die in gespeichert ist  **\*dies**, und wendet die arbeitsspeichereinschränkungen mit den vom angegebenen *Reihenfolge*.

## <a name="is_lock_free"></a> Atomic:: is_lock_free

Gibt an, ob der atomischen Vorgänge auf  **\*dies** sperrfrei sind.

```cpp
bool is_lock_free() const volatile noexcept;
```

### <a name="return-value"></a>Rückgabewert

True, wenn atomare Operationen auf  **\*dies** Sperre frei; andernfalls "false" werden.

### <a name="remarks"></a>Hinweise

Ein atomischer Typ ist sperrfrei, wenn keine der atomischen Vorgänge auf diesem Typ Sperren verwendet.

## <a name="load"></a> Atomic:: Load

Ruft den gespeicherten Wert in  **\*dies**, innerhalb angegebener speicherplatzeinschränkungen.

```cpp
Ty atomic::load(
   memory_order Order = memory_order_seq_cst
) const volatile noexcept;
Ty atomic::load(
   memory_order Order = memory_order_seq_cst
) const noexcept;
```

### <a name="parameters"></a>Parameter

*Reihenfolge*<br/>
Ein `memory_order`. *Reihenfolge* darf nicht sein `memory_order_release` oder `memory_order_acq_rel`.

### <a name="return-value"></a>Rückgabewert

Der abgerufene Wert, der in gespeichert ist  **\*dies**.

## <a name="store"></a> Atomic:: Store

Speichert einen angegebenen Wert.

```cpp
void atomic<Ty>::store(
   Ty Value,
   memory_order Order = memory_order_seq_cst
) volatile noexcept;
void atomic<Ty>::store(
   Ty Value,
   memory_order Order = memory_order_seq_cst
) noexcept;
```

### <a name="parameters"></a>Parameter

*Wert*<br/>
Ein *Ty* Objekt.

*Reihenfolge*<br/>
Ein `memory_order` Einschränkung.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion speichert atomisch *Wert* in `*this`, innerhalb der mit den vom angegebenen *Reihenfolge*.

## <a name="see-also"></a>Siehe auch

[\<atomic>](../standard-library/atomic.md)<br/>
[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
