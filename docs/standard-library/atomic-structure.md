---
title: atomic-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/20/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- atomic/std::atomic
dev_langs:
- C++
ms.assetid: 261628ed-7049-41ac-99b9-cfe49f696b44
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ae025dd124e8091994bea1d6a19a7b55d3984fed
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="atomic-structure"></a>atomic-Struktur

Beschreibt ein Objekt, das atomarische Vorgänge für einen gespeicherten Wert vom Typ ausführt *"ty"*.

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
|[Atomic::Operator "ty"](#op_ty)|Liest und den gespeicherten Wert und gibt ihn zurück. ([Atomic:: Load](#load))|
|[Atomic::Operator =](#op_eq)|Verwendet zum Ersetzen des gespeicherten Werts einen angegebenen Wert. ([Atomic:: Store](#store))|
|[Atomic::Operator ++](#op_inc)|Erhöht den gespeicherten Wert. Wird nur von integrale und Zeigerspezialisierungen verwendet.|
|[Atomic::Operator +=](#op_add_eq)|Fügt dem gespeicherten Wert einen angegebenen Wert hinzu. Wird nur von integrale und Zeigerspezialisierungen verwendet.|
|[Atomic::Operator--](#op_dec)|Verringert den gespeicherten Wert. Wird nur von integrale und Zeigerspezialisierungen verwendet.|
|[Atomic::Operator =](#op_sub_eq)|Subtrahiert einen angegebenen Wert vom gespeicherten Wert. Wird nur von integrale und Zeigerspezialisierungen verwendet.|
|[Atomic::Operator & =](#op_and_eq)|Führt ein bitweises und auf einen angegebenen Wert und dem gespeicherten Wert. Wird nur bei Integralspezialisierungen verwendet.|
|[Atomic::Operator&#124;=](#op_or_eq)|Führt ein bitweises oder auf einen angegebenen Wert und dem gespeicherten Wert. Wird nur bei Integralspezialisierungen verwendet.|
|[Atomic::Operator ^ =](#op_xor_eq)|Führt eine bitweise exklusive oder auf einen angegebenen Wert und dem gespeicherten Wert. Wird nur bei Integralspezialisierungen verwendet.|
|**Funktionen**||
|[compare_exchange_strong](#compare_exchange_strong)|Führt eine *Atomic_compare_and_exchange* Vorgang auf **dies** und gibt das Ergebnis zurück.|
|[compare_exchange_weak](#compare_exchange_weak)|Führt eine *Weak_atomic_compare_and_exchange* Vorgang auf **dies** und gibt das Ergebnis zurück.|
|[fetch_add](#fetch_add)|Fügt dem gespeicherten Wert einen angegebenen Wert hinzu.|
|[fetch_and](#fetch_and)|Führt ein bitweises und auf einen angegebenen Wert und dem gespeicherten Wert.|
|[fetch_or](#fetch_or)|Führt ein bitweises oder auf einen angegebenen Wert und dem gespeicherten Wert.|
|[fetch_sub](#fetch_sub)|Subtrahiert einen angegebenen Wert vom gespeicherten Wert.|
|[fetch_xor](#fetch_xor)|Führt eine bitweise exklusive oder auf einen angegebenen Wert und dem gespeicherten Wert.|
|[is_lock_free](#is_lock_free)|Gibt an, ob der atomischen Vorgänge auf **dies** sind *sperrfrei*. Ein atomischer Typ ist *sperrfrei*, wenn für keine der atomischen Vorgänge auf diesem Typ Sperren verwendet werden.|
|[Auslastungstest](#load)|Liest und den gespeicherten Wert und gibt ihn zurück.|
|[store](#store)|Verwendet zum Ersetzen des gespeicherten Werts einen angegebenen Wert.|

## <a name="remarks"></a>Hinweise

Der Typ *"ty"* muss *belanglos kopierbare*. D. h. [Memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md) Kopieren der Bytes muss erzeugen eine gültige *"ty"* -Objekt, das auf das ursprüngliche Objekt übereinstimmt. Die [Compare_exchange_weak](#compare_exchange_weak) und [Compare_exchange_strong](#compare_exchange_strong) Memberfunktionen verwenden [Memcmp](../c-runtime-library/reference/memcmp-wmemcmp.md) zu bestimmen, ob zwei *"ty"* Werte gleich sind. Diese Funktionen nicht verwenden eine *"ty"*-definierten **Operator ==**. Die Memberfunktionen von **atomic** verwenden **Memcpy** zum Kopieren von Werten des Typs *"ty"*.

Eine teilweise Spezialisierung ** atomic\<"ty" * > **, für alle Zeigertypen vorhanden ist. Mit der Spezialisierung wird das Hinzufügen eines Offsets zum verwalteten Zeigerwert oder die Wegnahme eines Offsets von dort ermöglicht. Arithmetischen Operationen nehmen ein Argument des Typs **Ptrdiff_t** und angepasst, entsprechend der Größe von *"ty"* mit normaler Adressenarithmetik konsistent.

Eine Spezialisierung ist für jeden Integraltypen außer vorhanden **Bool**. Mit jeder Spezialisierung wird ein umfangreicher Satz an Methoden für atomisch arithmetische und logische Vorgänge bereitgestellt.

||||
|-|-|-|
|**Atomic\<Char >**|**Atomic\<signiert Char >**|**Atomic\<unsigned Char >**|
|**Atomic\<char16_t >**|**Atomic\<char32_t >**|**Atomic\<Wchar_t >**|
|**Atomic\<kurze >**|**Atomic\<kurz ohne Vorzeichen >**|**Atomic\<Int >**|
|**Atomic\<unsigned Int >**|**Atomic\<lange >**|**Atomic\<unsigned long >**|
|**Atomic\<long long >**|**Atomic\<unsigned long long >**|

Integralspezialisierungen werden von der entsprechenden abgeleitet **Atomic_integral** Typen. Beispielsweise **atomic\<unsigned Int >** stammt aus **Atomic_uint**.

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

Objekte, die Instanziierungen von atomaren\<*"ty"*> kann nur vom Konstruktor, der ein des Typs Argument initialisiert werden *"ty"* und nicht mithilfe aggregierten Initialisierung. Allerdings können Atomic_integral Objekte nur mithilfe von aggregierter Initialisierung initialisiert werden.

```cpp
atomic<int> ai0 = ATOMIC_VAR_INIT(0);
atomic<int> ai1(0);
```

## <a name="op_ty"></a> Atomic::Operator *"ty"*

Der Operator für den Typ der Vorlage, das atomarische angegeben\<*"ty"*>. Ruft den gespeicherten Wert in  **\*dies**.

```cpp
atomic<Ty>::operator Ty() const volatile noexcept;
atomic<Ty>::operator Ty() const noexcept;
```

### <a name="remarks"></a>Hinweise

Dieser Operator gilt die **Memory_order_seq_cst** [Memory_order](atomic-enums.md).

## <a name="op_eq"></a> Atomic::Operator =

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
Ein *"ty"* Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt *Wert*.

## <a name="op_inc"></a> Atomic::Operator ++

Erhöht den gespeicherten Wert. Wird nur von integrale und Zeigerspezialisierungen verwendet.

```cpp
Ty atomic<Ty>::operator++(int) volatile noexcept;
Ty atomic<Ty>::operator++(int) noexcept;
Ty atomic<Ty>::operator++() volatile noexcept;
Ty atomic<Ty>::operator++() noexcept;
```

### <a name="return-value"></a>Rückgabewert

Die ersten beiden Operatoren zurückgegeben, den inkrementierten Wert. die letzten beiden Operatoren geben den Wert vor dem Inkrementieren zurück. Verwenden Sie die Operatoren der **Memory_order_seq_cst** [Memory_order](atomic-enums.md).

## <a name="op_add_eq"></a> Atomic::Operator +=

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

Ein *"ty"* -Objekt, das das Ergebnis der Addition enthält.

### <a name="remarks"></a>Hinweise

Dieser Operator wird verwendet, die **Memory_order_seq_cst** [Memory_order](atomic-enums.md).

## <a name="op_dec"></a> Atomic::Operator--

Verringert den gespeicherten Wert. Wird nur von integrale und Zeigerspezialisierungen verwendet.

```cpp
Ty atomic<Ty>::operator--(int) volatile noexcept;
Ty atomic<Ty>::operator--(int) noexcept;
Ty atomic<Ty>::operator--() volatile noexcept;
Ty atomic<Ty>::operator--() noexcept;
```

### <a name="return-value"></a>Rückgabewert

Die ersten beiden Operatoren zurückgegeben, den dekrementierte Wert. die letzten beiden Operatoren geben den Wert vor dem dekrementieren. Verwenden Sie die Operatoren der **Memory_order_seq_cst** [Memory_order](atomic-enums.md).

## <a name="op_sub_eq"></a> Atomic::Operator =

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

Ein *"ty"* -Objekt, das das Ergebnis der Subtraktion enthält.

### <a name="remarks"></a>Hinweise

Dieser Operator wird verwendet, die **Memory_order_seq_cst** [Memory_order](atomic-enums.md).

## <a name="op_and_eq"></a> Atomic::Operator & =

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
Ein Wert vom Typ *"ty"*.

### <a name="return-value"></a>Rückgabewert

Das Ergebnis des bitweisen und.

### <a name="remarks"></a>Hinweise

Dieser Operator führt einen Read-modify-Write-Vorgang zum Ersetzen des gespeicherten Werts von  **\*dies** mit einem bitweisen und der *Wert* und den aktuellen Wert an, die in gespeichert ist  **\*dies**, in die Einschränkungen der **Memory_order_seq_cst** [Memory_order](atomic-enums.md).

## <a name="op_or_eq"></a> Atomic::Operator&#124;=

Führt ein bitweises oder auf einem angegebenen Wert und den gespeicherten Wert von  **\*dies**. Wird nur bei Integralspezialisierungen verwendet.

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
Ein Wert vom Typ *"ty"*.

### <a name="return-value"></a>Rückgabewert

Das Ergebnis des bitweisen oder.

### <a name="remarks"></a>Hinweise

Dieser Operator führt einen Read-modify-Write-Vorgang zum Ersetzen des gespeicherten Werts von  **\*dies** mit einem bitweisen oder der *Wert* und den aktuellen Wert an, die in gespeichert ist  **\*dies**, in die Einschränkungen der **Memory_order_seq_cst** [Memory_order](atomic-enums.md) Einschränkungen.

## <a name="op_xor_eq"></a> Atomic::Operator ^ =

Führt eine bitweise exklusive oder auf einem angegebenen Wert und den gespeicherten Wert von  **\*dies**. Wird nur bei Integralspezialisierungen verwendet.

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
Ein Wert vom Typ *"ty"*.

### <a name="return-value"></a>Rückgabewert

Das Ergebnis der bitweise exklusive oder.

### <a name="remarks"></a>Hinweise

Dieser Operator führt einen Read-modify-Write-Vorgang zum Ersetzen des gespeicherten Werts von  **\*dies** bei eine bitweise exklusive oder *Wert* und den aktuellen Wert an, die in gespeichert ist  **\*dies**, in die Einschränkungen der **Memory_order_seq_cst** [Memory_order](atomic-enums.md) Einschränkungen.

## <a name="compare_exchange_strong"></a> Atomic:: compare_exchange_strong

Führt einen atomarischen Vergleichs- und Austausch-Vorgang auf  **\*dies**.

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
Ein Wert vom Typ *"ty"*.

*Wert*<br/>
Ein Wert vom Typ *"ty"*.

*Order1*<br/>
Erstes **memory_order**-Argument.

*Order2*<br/>
Zweite **Memory_order** Argument.

### <a name="return-value"></a>Rückgabewert

Ein **Bool** , der das Ergebnis des Vergleichs Wert angibt.

### <a name="remarks"></a>Hinweise

Dieser unteilbare Vergleichs- und Austausch-Vorgang vergleicht den Wert an, die in gespeichert ist  **\*dies** mit *Exp*. Wenn die Werte gleich sind, wird der Vorgang ersetzt den Wert, der in gespeichert ist  **\*dies** mit *Wert* mithilfe von ein Read-modify-Write-Vorgang und anwenden, die Einschränkungen der arbeitsspeicherreihenfolge vom angegebenen *Order1*. Wenn die Werte nicht gleich sind, wird vom Vorgang verwendet den Wert, der in gespeichert ist  **\*dies** ersetzen *Exp* und mit den vom angegebenen Einschränkungen der arbeitsspeicherreihenfolge werden angewendet *Order2* .

Überladungen ohne ein zweites **Memory_order** eine implizite *Order2* , basiert auf den Wert der *Order1*. Wenn *Order1* ist **Memory_order_acq_rel**, *Order2* ist **Memory_order_acquire**. Wenn *Order1* ist **Memory_order_release**, *Order2* ist **Memory_order_relaxed**. In allen anderen Fällen *Order2* gleich *Order1*.

Für Überladungen, die zwei **Memory_order** Parameter, den Wert der *Order2* muss **Memory_order_release** oder **Memory_order_acq_rel**, und darf nicht stärker als der Wert der *Order1*.

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
Ein Wert vom Typ *"ty"*.

*Wert*<br/>
Ein Wert vom Typ *"ty"*.

*Order1*<br/>
Erstes **memory_order**-Argument.

*Order2*<br/>
Zweite **Memory_order** Argument.

### <a name="return-value"></a>Rückgabewert

Ein **Bool** , der das Ergebnis des Vergleichs Wert angibt.

### <a name="remarks"></a>Hinweise

Dieser unteilbare Vergleichs- und Austausch-Vorgang vergleicht den Wert an, die in gespeichert ist  **\*dies** mit *Exp*. Wenn die Werte gleich sind, wird der Vorgang ersetzt den Wert, der in gespeichert ist  **\*dies** mit*Wert* mithilfe von ein Read-modify-Write-Vorgang und anwenden, die Einschränkungen der arbeitsspeicherreihenfolge vom angegebenen *Order1*. Wenn die Werte nicht gleich sind, wird vom Vorgang verwendet den Wert, der in gespeichert ist  **\*dies** ersetzen *Exp* und mit den vom angegebenen Einschränkungen der arbeitsspeicherreihenfolge werden angewendet *Order2* .

Eine atomic schwache vergleichen, und Exchange-Vorgang wird einen Austausch ausgeführt, wenn die verglichenen Werte gleich sind. Wenn die Werte nicht gleich sind, ist nicht sichergestellt, dass Austausch mit dem Vorgang ausgeführt wird.

Überladungen ohne ein zweites **Memory_order** eine implizite *Order2* , basiert auf den Wert der *Order1*. Wenn *Order1* ist **Memory_order_acq_rel**, *Order2* ist **Memory_order_acquire**. Wenn *Order1* ist **Memory_order_release**, *Order2* ist **Memory_order_relaxed**. In allen anderen Fällen *Order2* gleich *Order1*.

Für Überladungen, die zwei **Memory_order** Parameter, den Wert der *Order2* muss **Memory_order_release** oder **Memory_order_acq_rel**, und darf nicht stärker als der Wert der *Order1*.

## <a name="exchange"></a> Atomic:: Exchange

Verwendet einen angegebenen Wert zum Ersetzen des gespeicherten Werts von  **\*dies**.

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
Ein Wert vom Typ *"ty"*.

*Reihenfolge*<br/>
Ein **memory_order**.

### <a name="return-value"></a>Rückgabewert

Der gespeicherte Wert von  **\*dies** vor dem Austausch.

### <a name="remarks"></a>Hinweise

Dieser Vorgang wird eine Read-modify-Write-Operation mit *Wert* zum Ersetzen des Werts, die in gespeichert ist  **\*dies**, in den Arbeitsspeicher-Einschränkungen, die vom angegebenen  *Reihenfolge*.

## <a name="fetch_add"></a> Atomic:: fetch_add

Ruft den Wert in gespeicherten  **\*dies**, und fügt dann mit dem gespeicherten Wert einen angegebenen Wert.

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
Ein Wert vom Typ *"ty"*.

*Reihenfolge*<br/>
Ein **memory_order**.

### <a name="return-value"></a>Rückgabewert

Ein *"ty"* Objekt mit dem Wert in gespeicherten  **\*dies** vor dem hinzufügen.

### <a name="remarks"></a>Hinweise

Die **Fetch_add** Methode führt einen Read-modify-Write-Vorgang atomar hinzufügen *Wert* mit dem gespeicherten Wert in  **\*dies**, und wendet den Arbeitsspeicher Einschränkungen, die vom angegebenen *Reihenfolge*.

## <a name="fetch_and"></a> Atomic:: fetch_and

Führt ein bitweises und auf einen Wert und einen vorhandenen Wert aus, die in gespeichert ist  **\*dies**.

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
Ein Wert vom Typ *"ty"*.

*Reihenfolge*<br/>
Ein **memory_order**.

### <a name="return-value"></a>Rückgabewert

Ein *"ty"* -Objekt, das das Ergebnis des bitweisen enthält und.

### <a name="remarks"></a>Hinweise

Die **Fetch_and** -Methode führt einen Read-modify-Write-Vorgang zum Ersetzen des gespeicherten Werts von  **\*dies** mit einem bitweisen und der *Wert* und der aktuelle in gespeicherten Wert  **\*dies**, in den Arbeitsspeicher-Einschränkungen, die vom angegebenen *Reihenfolge*.

## <a name="fetch_or"></a> Atomic:: fetch_or

Führt ein bitweises oder auf einen Wert und einen vorhandenen Wert aus, die in gespeichert ist  **\*dies**.

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
Ein Wert vom Typ *"ty"*.

*Reihenfolge*<br/>
Ein **memory_order**.

### <a name="return-value"></a>Rückgabewert

Ein *"ty"* -Objekt, das das Ergebnis des bitweisen enthält oder.

### <a name="remarks"></a>Hinweise

Die **Fetch_or** -Methode führt einen Read-modify-Write-Vorgang zum Ersetzen des gespeicherten Werts von  **\*dies** mit einem bitweisen oder der *Wert* und den aktuellen Wert im gespeichert wird  **\*dies**, in den Arbeitsspeicher-Einschränkungen, die vom angegebenen *Reihenfolge*.

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
Ein Wert vom Typ *"ty"*.

*Reihenfolge*<br/>
Ein **memory_order**.

### <a name="return-value"></a>Rückgabewert

Ein *"ty"* -Objekt, das das Ergebnis der Subtraktion enthält.

### <a name="remarks"></a>Hinweise

Die **Fetch_sub** Methode führt einen Read-modify-Write-Vorgang atomar subtrahieren *Wert* aus den gespeicherten Wert in  **\*dies**, innerhalb des Arbeitsspeichers Einschränkungen, die vom angegebenen *Reihenfolge*.

## <a name="fetch_xor"></a> Atomic:: fetch_xor

Führt eine bitweise exklusive oder auf einen Wert und einen vorhandenen Wert aus, die in gespeichert ist  **\*dies**.

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
Ein Wert vom Typ *"ty"*.

*Reihenfolge*<br/>
Ein **memory_order**.

### <a name="return-value"></a>Rückgabewert

Ein *"ty"* -Objekt, das das Ergebnis des bitweisen exklusiven enthält oder.

### <a name="remarks"></a>Hinweise

Die **Fetch_xor** -Methode führt einen Read-modify-Write-Vorgang zum Ersetzen des gespeicherten Werts von  **\*dies** bei eine bitweise exklusive oder *Wert* und aktuelle in gespeicherten Wert  **\*dies**, und wendet die Arbeitsspeicher-Einschränkungen, die vom angegebenen *Reihenfolge*.

## <a name="is_lock_free"></a> Atomic:: is_lock_free

Gibt an, ob der atomischen Vorgänge auf  **\*dies** sperrfrei sind.

```cpp
bool is_lock_free() const volatile noexcept;
```

### <a name="return-value"></a>Rückgabewert

True, wenn atomare Vorgänge für  **\*dies** Sperre frei, andernfalls "false" sind.

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
Ein **memory_order**. *Reihenfolge* muss **Memory_order_release** oder **Memory_order_acq_rel**.

### <a name="return-value"></a>Rückgabewert

Der abgerufene Wert, die in gespeichert ist  **\*dies**.

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
Ein *"ty"* Objekt.

*Reihenfolge*<br/>
Ein **Memory_order** Einschränkung.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion speichert atomisch *Wert* in `*this`, in den Arbeitsspeicher-Einschränkungen, die vom angegebenen *Reihenfolge*.

## <a name="see-also"></a>Siehe auch

[\<atomic>](../standard-library/atomic.md)<br/>
[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
