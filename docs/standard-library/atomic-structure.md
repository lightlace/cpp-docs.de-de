---
title: atomic-Struktur
ms.date: 04/20/2018
f1_keywords:
- atomic/std::atomic
ms.assetid: 261628ed-7049-41ac-99b9-cfe49f696b44
ms.openlocfilehash: 1b3b60d71fcdf68fdf215820535c3bfb3d4dfb2b
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456731"
---
# <a name="atomic-structure"></a>atomic-Struktur

Beschreibt ein Objekt, das atomarische Vorgänge für einen gespeicherten Wert vom Typ " *Ty*" ausführt.

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
|[Atomic:: Operator Ty](#op_ty)|Liest und den gespeicherten Wert und gibt ihn zurück. ([Atomic:: Load](#load))|
|[atomic::operator=](#op_eq)|Verwendet zum Ersetzen des gespeicherten Werts einen angegebenen Wert. ([Atomic:: Store](#store))|
|[atomic::operator++](#op_inc)|Erhöht den gespeicherten Wert. Wird nur von integrale und Zeigerspezialisierungen verwendet.|
|[atomic::operator+=](#op_add_eq)|Fügt dem gespeicherten Wert einen angegebenen Wert hinzu. Wird nur von integrale und Zeigerspezialisierungen verwendet.|
|[atomic::operator--](#op_dec)|Verringert den gespeicherten Wert. Wird nur von integrale und Zeigerspezialisierungen verwendet.|
|[atomic::operator-=](#op_sub_eq)|Subtrahiert einen angegebenen Wert vom gespeicherten Wert. Wird nur von integrale und Zeigerspezialisierungen verwendet.|
|[atomic::operator&=](#op_and_eq)|Führt ein bitweises and für einen angegebenen-Wert und den gespeicherten-Wert aus. Wird nur bei Integralspezialisierungen verwendet.|
|[Atomic:: Operator&#124;=](#op_or_eq)|Führt ein bitweises OR für einen angegebenen-Wert und den gespeicherten Wert aus. Wird nur bei Integralspezialisierungen verwendet.|
|[atomic::operator^=](#op_xor_eq)|Führt ein bitweises exklusives OR für einen angegebenen-Wert und den gespeicherten-Wert aus. Wird nur bei Integralspezialisierungen verwendet.|
|**Funktionen**||
|[compare_exchange_strong](#compare_exchange_strong)|Führt einen *atomic_compare_and_exchange* -Vorgang für **diesen** aus und gibt das Ergebnis zurück.|
|[compare_exchange_weak](#compare_exchange_weak)|Führt einen *weak_atomic_compare_and_exchange* -Vorgang für **dieses** aus und gibt das Ergebnis zurück.|
|[fetch_add](#fetch_add)|Fügt dem gespeicherten Wert einen angegebenen Wert hinzu.|
|[fetch_and](#fetch_and)|Führt ein bitweises and für einen angegebenen-Wert und den gespeicherten-Wert aus.|
|[fetch_or](#fetch_or)|Führt ein bitweises OR für einen angegebenen-Wert und den gespeicherten Wert aus.|
|[fetch_sub](#fetch_sub)|Subtrahiert einen angegebenen Wert vom gespeicherten Wert.|
|[fetch_xor](#fetch_xor)|Führt ein bitweises exklusives OR für einen angegebenen-Wert und den gespeicherten-Wert aus.|
|[is_lock_free](#is_lock_free)|Gibt an, ob atomarische Vorgänge für **diesen** *sperrfrei*sind. Ein atomischer Typ ist *sperrfrei*, wenn für keine der atomischen Vorgänge auf diesem Typ Sperren verwendet werden.|
|[load](#load)|Liest und den gespeicherten Wert und gibt ihn zurück.|
|[store](#store)|Verwendet zum Ersetzen des gespeicherten Werts einen angegebenen Wert.|

## <a name="remarks"></a>Hinweise

Die *typty* muss *trivial kopiert*sein. Das heißt, das Kopieren der Bytes mithilfe von [memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md) muss ein gültiges *Ty* -Objekt liefern, das mit dem ursprünglichen Objekt übereinstimmt. Die Member-Funktionen [compare_exchange_weak](#compare_exchange_weak) und [compare_exchange_strong](#compare_exchange_strong) verwenden [memcmp](../c-runtime-library/reference/memcmp-wmemcmp.md) , um zu bestimmen, ob zwei *Ty* -Werte gleich sind. Diese Funktionen verwenden keine *Ty*-defined `operator==`. Die Element Funktionen von `atomic` `memcpy` , mit denen Werte vom Typ " *Ty*" kopiert werden.

Eine partielle Spezialisierung **(\<Atomic \*Ty >** ) ist für alle Zeiger Typen vorhanden. Mit der Spezialisierung wird das Hinzufügen eines Offsets zum verwalteten Zeigerwert oder die Wegnahme eines Offsets von dort ermöglicht. Bei arithmetischen Operationen wird ein Argument des `ptrdiff_t` Typs akzeptiert und dieses Argument entsprechend der Größe angepasst *, damit* es mit normaler Adress Arithmetik konsistent ist.

Eine Spezialisierung ist für jeden ganzzahligen Typ mit Ausnahme von **bool**vorhanden. Mit jeder Spezialisierung wird ein umfangreicher Satz an Methoden für atomisch arithmetische und logische Vorgänge bereitgestellt.

||||
|-|-|-|
|**atomic\<char>**|**atomarisch\<signierter Char->**|**atomarische\<nicht signierte Char->**|
|**atomarische\<char16_t->**|**atomarische\<char32_t->**|**atomic\<wchar_t>**|
|**atomic\<short>**|**\<Ganzzahl ohne Vorzeichen Short-> mit Vorzeichen**|**atomic\<int>**|
|**Atomic\<-> ohne Vorzeichen**|**atomic\<long>**|**Atomic\<Ganzzahl ohne Vorzeichen long->**|
|**atomarische\<Long Long->**|**Atomic\<Ganzzahl ohne Vorzeichen long long->**|

Integralspezialisierungen werden von den entsprechenden `atomic_integral`-Typen abgeleitet. Beispielsweise ist **Atomic\<-> vom Typ Ganzzahl ohne Vorzeichen int** von `atomic_uint`abgeleitet.

## <a name="requirements"></a>Anforderungen

**Header:** \<atomic>

**Namespace:** std

## <a name="atomic"></a>Atomic:: Atomic

Erstellt ein atomisches Objekt.

```cpp
atomic();
atomic( const atomic& );
atomic( Ty Value ) noexcept;
```

### <a name="parameters"></a>Parameter

*Wert*\
Initialisierungswert

### <a name="remarks"></a>Hinweise

Atomische Objekte können nicht kopiert oder verschoben werden.

Objekte, bei denen es sich um Instanziierungen von atomaren\<*Ty*-> handelt, können nur vom Konstruktor initialisiert werden, der ein Argument vom Typ " *Ty* " annimmt, nicht mithilfe der Aggregat Initialisierung. Atomic_integral-Objekte können jedoch nur mithilfe der Aggregat Initialisierung initialisiert werden.

```cpp
atomic<int> ai0 = ATOMIC_VAR_INIT(0);
atomic<int> ai1(0);
```

## <a name="op_ty"></a>Atomic:: Operator *Ty*

Der Operator für den Typ, der für die Vorlage angegeben\<ist, Atomic*Ty*>. Ruft den gespeicherten Wert in  **\*dieser**ab.

```cpp
atomic<Ty>::operator Ty() const volatile noexcept;
atomic<Ty>::operator Ty() const noexcept;
```

### <a name="remarks"></a>Hinweise

Dieser Operator wendet das `memory_order_seq_cst` [memory_order](atomic-enums.md)an.

## <a name="op_eq"></a>Atomic:: Operator =

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

*Wert*\
Ein *Ty* -Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt den *Wert*zurück.

## <a name="op_inc"></a>Atomic:: Operator + +

Erhöht den gespeicherten Wert. Wird nur von integrale und Zeigerspezialisierungen verwendet.

```cpp
Ty atomic<Ty>::operator++(int) volatile noexcept;
Ty atomic<Ty>::operator++(int) noexcept;
Ty atomic<Ty>::operator++() volatile noexcept;
Ty atomic<Ty>::operator++() noexcept;
```

### <a name="return-value"></a>Rückgabewert

Die ersten beiden Operatoren geben den inkrementierten Wert zurück. die letzten zwei Operatoren geben den Wert vor dem Inkrement zurück. Die Operatoren verwenden `memory_order_seq_cst` den [memory_order](atomic-enums.md).

## <a name="op_add_eq"></a>Atomic:: Operator + =

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

*Wert*\
Ein ganzzahliger Wert oder Zeiger Wert.

### <a name="return-value"></a>Rückgabewert

Ein *Ty* -Objekt, das das Ergebnis der Addition enthält.

### <a name="remarks"></a>Hinweise

Dieser Operator verwendet das `memory_order_seq_cst` [memory_order](atomic-enums.md).

## <a name="op_dec"></a>Atomic:: Operator--

Verringert den gespeicherten Wert. Wird nur von integrale und Zeigerspezialisierungen verwendet.

```cpp
Ty atomic<Ty>::operator--(int) volatile noexcept;
Ty atomic<Ty>::operator--(int) noexcept;
Ty atomic<Ty>::operator--() volatile noexcept;
Ty atomic<Ty>::operator--() noexcept;
```

### <a name="return-value"></a>Rückgabewert

Die ersten beiden Operatoren geben den dekrementierten Wert zurück. die letzten zwei Operatoren geben den Wert vor dem Dekrement zurück. Die Operatoren verwenden `memory_order_seq_cst` den [memory_order](atomic-enums.md).

## <a name="op_sub_eq"></a>Atomic:: Operator-=

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

*Wert*\
Ein ganzzahliger Wert oder Zeiger Wert.

### <a name="return-value"></a>Rückgabewert

Ein *Ty* -Objekt, das das Ergebnis der Subtraktion enthält.

### <a name="remarks"></a>Hinweise

Dieser Operator verwendet das `memory_order_seq_cst` [memory_order](atomic-enums.md).

## <a name="op_and_eq"></a>Atomic:: Operator & =

Führt ein bitweises and für einen angegebenen-Wert und den gespeicherten Wert  **\*dieses**aus. Wird nur bei Integralspezialisierungen verwendet.

```cpp
atomic<Ty>::operator&= (
   Ty Value
) volatile noexcept;
atomic<Ty>::operator&= (
   Ty Value
) noexcept;
```

### <a name="parameters"></a>Parameter

*Wert*\
Ein Wert vom Typ " *Ty*".

### <a name="return-value"></a>Rückgabewert

Das Ergebnis des bitweisen and-Elements.

### <a name="remarks"></a>Hinweise

Dieser Operator führt einen Lese-/Änderungs-Schreibvorgang aus  **\*** , um den gespeicherten Wert dieses durch einen bitweisen and-of- *Wert* und den aktuellen Wert, der in  **\*diesem**gespeichert ist, innerhalb der Einschränkungen des `memory_order_seq_cst`zuersetzen. [memory_order](atomic-enums.md).

## <a name="op_or_eq"></a>Atomic:: Operator&#124;=

Führt ein bitweises OR für einen angegebenen-Wert und den gespeicherten Wert  **\*dieses**aus. Wird nur bei Integralspezialisierungen verwendet.

```cpp
atomic<Ty>::operator|= (
   Ty Value
) volatile noexcept;
atomic<Ty>::operator|= (
   Ty Value
) noexcept;
```

### <a name="parameters"></a>Parameter

*Wert*\
Ein Wert vom Typ " *Ty*".

### <a name="return-value"></a>Rückgabewert

Das Ergebnis des bitweisen or-Elements.

### <a name="remarks"></a>Hinweise

Dieser Operator führt einen Lese-/Änderungs-Schreibvorgang aus  **\*** , um den gespeicherten Wert dieses durch einen bitweisen or- *Wert* und den aktuellen Wert, der in  **\*diesem**gespeichert ist, innerhalb der Einschränkungen des `memory_order_seq_cst`zuersetzen. [memory_order](atomic-enums.md) -Einschränkungen.

## <a name="op_xor_eq"></a>Atomic:: Operator ^ =

Führt ein bitweises exklusives OR für einen angegebenen-Wert und den gespeicherten Wert  **\*dieses**aus. Wird nur bei Integralspezialisierungen verwendet.

```cpp
atomic<Ty>::operator^= (
   Ty Value
) volatile noexcept;
atomic<Ty>::operator^= (
   Ty Value
) noexcept;
```

### <a name="parameters"></a>Parameter

*Wert*\
Ein Wert vom Typ " *Ty*".

### <a name="return-value"></a>Rückgabewert

Das Ergebnis des bitweisen exklusiven or-Elements.

### <a name="remarks"></a>Hinweise

Dieser Operator führt einen Lese-/Änderungs-Schreibvorgang aus, um den gespeicherten Wert  **\*dieses** durch einen bitweisen exklusiven or- *Wert* und den aktuellen Wert, der in  **\*diesem**gespeichert ist, innerhalb der Einschränkungen von zu ersetzen. memory_order-Einschränkungen. [](atomic-enums.md) `memory_order_seq_cst`

## <a name="compare_exchange_strong"></a>Atomic:: compare_exchange_strong

Führt einen atomischen Vergleichs-und Austausch Vorgang für  **\*diese**aus.

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

*Exp*\
Ein Wert vom Typ " *Ty*".

*Wert*\
Ein Wert vom Typ " *Ty*".

*Order1*\
Erstes `memory_order` Argument.

*Order2*\
Zweites `memory_order`-Argument.

### <a name="return-value"></a>Rückgabewert

Ein  boolescher Wert, der das Ergebnis des Wert Vergleichs angibt.

### <a name="remarks"></a>Hinweise

Dieser atomarische Vergleichs-und Austausch Vorgang vergleicht den in  **\*diesem** gespeicherten Wert mit *Exp*. Wenn die Werte gleich sind, ersetzt der Vorgang den in  **\*diesem** gespeicherten *Wert durch einen* Lese-/Änderungs-Schreibvorgang und das Anwenden der durch *order1*angegebenen Einschränkungen für die Speicher Reihenfolge. Wenn die Werte nicht identisch sind, verwendet der Vorgang den in  **\*diesem** gespeicherten Wert, um *Exp* zu ersetzen, und wendet die von *Order2*angegebenen Einschränkungen für die Speicher Reihenfolge an.

Bei über Ladungen, die keine Sekunde `memory_order` aufweisen, wird ein implizites *Order2* verwendet, das auf dem Wert von *order1*basiert. Wenn *order1* `memory_order_acq_rel`den Wert hat, `memory_order_acquire`ist *Order2* . Wenn *order1* `memory_order_release`den Wert hat, `memory_order_relaxed`ist *Order2* . In allen anderen Fällen ist *Order2* gleich *order1*.

Bei über Ladungen, die zwei `memory_order` Parameter annehmen, darf der Wert von *Order2* nicht `memory_order_release` oder `memory_order_acq_rel`sein, und er darf nicht stärker als der Wert von *order1*sein.

## <a name="compare_exchange_weak"></a>Atomic:: compare_exchange_weak

Führt einen schwachen atomischen Vergleichs-und Austausch Vorgang für  **\*diese**aus.

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

*Exp*\
Ein Wert vom Typ " *Ty*".

*Wert*\
Ein Wert vom Typ " *Ty*".

*Order1*\
Erstes `memory_order` Argument.

*Order2*\
Zweites `memory_order`-Argument.

### <a name="return-value"></a>Rückgabewert

Ein  boolescher Wert, der das Ergebnis des Wert Vergleichs angibt.

### <a name="remarks"></a>Hinweise

Dieser atomarische Vergleichs-und Austausch Vorgang vergleicht den in  **\*diesem** gespeicherten Wert mit *Exp*. Wenn die Werte gleich sind, ersetzt der Vorgang den in  **\*diesem** gespeicherten*Wert durch einen* Lese-/Änderungs-Schreibvorgang und das Anwenden der durch *order1*angegebenen Einschränkungen für die Speicher Reihenfolge. Wenn die Werte nicht identisch sind, verwendet der Vorgang den in  **\*diesem** gespeicherten Wert, um *Exp* zu ersetzen, und wendet die von *Order2*angegebenen Einschränkungen für die Speicher Reihenfolge an.

Ein schwacher Atomischer Vergleichs-und Austausch Vorgang führt einen Austausch aus, wenn die verglichenen Werte gleich sind. Wenn die Werte nicht gleich sind, ist nicht sichergestellt, dass Austausch mit dem Vorgang ausgeführt wird.

Bei über Ladungen, die keine Sekunde `memory_order` aufweisen, wird ein implizites *Order2* verwendet, das auf dem Wert von *order1*basiert. Wenn *order1* `memory_order_acq_rel`den Wert hat, `memory_order_acquire`ist *Order2* . Wenn *order1* `memory_order_release`den Wert hat, `memory_order_relaxed`ist *Order2* . In allen anderen Fällen ist *Order2* gleich *order1*.

Bei über Ladungen, die zwei `memory_order` Parameter annehmen, darf der Wert von *Order2* nicht `memory_order_release` oder `memory_order_acq_rel`sein, und er darf nicht stärker als der Wert von *order1*sein.

## <a name="exchange"></a>atomisch:: Exchange

Verwendet einen angegebenen-Wert, um den gespeicherten Wert  **\*dieses**zu ersetzen.

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

*Wert*\
Ein Wert vom Typ " *Ty*".

*Reihenfolge*\
Ein `memory_order`.

### <a name="return-value"></a>Rückgabewert

Der gespeicherte Wert  **\*dieses** vor dem Austausch.

### <a name="remarks"></a>Hinweise

Mit diesem Vorgang wird ein Lese-und Schreibvorgang durchführt  , um den Wert, der in  **\*diesem**gespeichert ist, innerhalb der durch die *Reihenfolge*angegebenen Speicher Einschränkungen zu ersetzen.

## <a name="fetch_add"></a>Atomic:: fetch_add

Ruft den in  **\*diesem**gespeicherten Wert ab und fügt dann dem gespeicherten Wert einen angegebenen Wert hinzu.

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

*Wert*\
Ein Wert vom Typ " *Ty*".

*Reihenfolge*\
Ein `memory_order`.

### <a name="return-value"></a>Rückgabewert

Ein *Ty* -Objekt, das den Wert enthält, der vor dem Hinzufügen in  **\*diesem** gespeichert wird.

### <a name="remarks"></a>Hinweise

Die `fetch_add` -Methode führt einen Lese-/Schreib-Schreibvorgang aus, um dem gespeicherten Wert in  **\*diesem**atomisch einen *Wert* hinzuzufügen, und wendet die Speicher Einschränkungen an, die nach *Reihenfolge*angegeben werden.

## <a name="fetch_and"></a>Atomic:: fetch_and

Führt ein bitweises and für einen-Wert und einen vorhandenen Wert aus, der in  **\*diesem**gespeichert wird.

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

*Wert*\
Ein Wert vom Typ " *Ty*".

*Reihenfolge*\
Ein `memory_order`.

### <a name="return-value"></a>Rückgabewert

Ein *Ty* -Objekt, das das Ergebnis des bitweisen and-Objekts enthält.

### <a name="remarks"></a>Hinweise

Die `fetch_and` -Methode führt einen Lese-/Änderungs-Schreibvorgang aus  **\*** , um den gespeicherten Wert dieses durch einen bitweisen and-of- *Wert* und den aktuellen Wert, der in  **\*diesem**gespeichert ist, im Arbeitsspeicher zu ersetzen. Einschränkungen, die nach *Reihenfolge*angegeben werden.

## <a name="fetch_or"></a>Atomic:: fetch_or

Führt ein bitweises OR für einen-Wert und einen vorhandenen Wert aus, der in  **\*diesem**gespeichert wird.

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

*Wert*\
Ein Wert vom Typ " *Ty*".

*Reihenfolge*\
Ein `memory_order`.

### <a name="return-value"></a>Rückgabewert

Ein *Ty* -Objekt, das das Ergebnis des bitweisen or enthält.

### <a name="remarks"></a>Hinweise

Die `fetch_or` -Methode führt einen Lese-/Änderungs-Schreibvorgang aus  **\*** , um den gespeicherten Wert dieses durch einen bitweisen or- *Wert* und den aktuellen Wert, der in  **\*diesem**gespeichert ist, im Arbeitsspeicher zu ersetzen. Einschränkungen, die nach *Reihenfolge*angegeben werden.

## <a name="fetch_sub"></a>Atomic:: fetch_sub

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

*Wert*\
Ein Wert vom Typ " *Ty*".

*Reihenfolge*\
Ein `memory_order`.

### <a name="return-value"></a>Rückgabewert

Ein *Ty* -Objekt, das das Ergebnis der Subtraktion enthält.

### <a name="remarks"></a>Hinweise

Die `fetch_sub` -Methode führt einen Lese-/Änderungs-Schreibvorgang aus, um den *Wert* aus dem gespeicherten Wert in  **\*diesem**innerhalb der durch die *Reihenfolge*angegebenen Speicher Einschränkungen atomisch zu subtrahieren.

## <a name="fetch_xor"></a>Atomic:: fetch_xor

Führt ein bitweises exklusives OR für einen-Wert und einen vorhandenen Wert aus, der in  **\*diesem**gespeichert wird.

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

*Wert*\
Ein Wert vom Typ " *Ty*".

*Reihenfolge*\
Ein `memory_order`.

### <a name="return-value"></a>Rückgabewert

Ein *Ty* -Objekt, das das Ergebnis der bitweisen exklusiven or-Spalte enthält.

### <a name="remarks"></a>Hinweise

Die `fetch_xor` -Methode führt einen Lese-/Änderungs-Schreibvorgang aus,  **\*** um den gespeicherten Wert dieses durch einen bitweisen exklusiven or- *Wert* und den aktuellen Wert zu ersetzen, der in  **\*diesem**gespeichert ist, und wendet das Speicher Einschränkungen, die nach *Reihenfolge*angegeben werden.

## <a name="is_lock_free"></a>Atomic:: is_lock_free

Gibt an, ob atomarische Vorgänge für  **\*diesen** sperrfrei sind.

```cpp
bool is_lock_free() const volatile noexcept;
```

### <a name="return-value"></a>Rückgabewert

true, wenn atomarische Vorgänge für  **\*dieses** Sperr frei sind, andernfalls false.

### <a name="remarks"></a>Hinweise

Ein Atomischer Typ ist sperrfrei, wenn für keine atomarischen Vorgänge in diesem Typ Sperren verwendet werden.

## <a name="load"></a>Atomic:: Load

Ruft den gespeicherten Wert in  **\*dieser**innerhalb der angegebenen Speicher Einschränkungen ab.

```cpp
Ty atomic::load(
   memory_order Order = memory_order_seq_cst
) const volatile noexcept;
Ty atomic::load(
   memory_order Order = memory_order_seq_cst
) const noexcept;
```

### <a name="parameters"></a>Parameter

*Reihenfolge*\
Ein `memory_order`. Die *Reihenfolge* darf `memory_order_release` nicht `memory_order_acq_rel`oder sein.

### <a name="return-value"></a>Rückgabewert

Der abgerufene Wert, der in  **\*diesem**gespeichert wird.

## <a name="store"></a>Atomic:: Store

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

*Wert*\
Ein *Ty* -Objekt.

*Reihenfolge*\
Eine `memory_order` -Einschränkung.

### <a name="remarks"></a>Hinweise

Diese Member-Funktion speichert den *Wert* in `*this`atomisch in, innerhalb der durch die *Reihenfolge*angegebenen Speicher Einschränkungen.

## <a name="see-also"></a>Siehe auch

[\<atomic>](../standard-library/atomic.md)\
[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)
