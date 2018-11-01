---
title: completion_future-Klasse
ms.date: 11/04/2016
f1_keywords:
- completion_future
- AMPRT/completion_future
- AMPRT/Concurrency::completion_future::completion_future
- AMPRT/Concurrency::completion_future::get
- AMPRT/Concurrency::completion_future::then
- AMPRT/Concurrency::completion_future::to_task
- AMPRT/Concurrency::completion_future::valid
- AMPRT/Concurrency::completion_future::wait
- AMPRT/Concurrency::completion_future::wait_for
- AMPRT/Concurrency::completion_future::wait_until
ms.assetid: 1303c62e-546d-4b02-a578-251ed3fc0b6b
ms.openlocfilehash: d121477cf63236ee40df826a63dd7c7c9880d142
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50535290"
---
# <a name="completionfuture-class"></a>completion_future-Klasse

Stellt ein "future"-Objekt dar, das einer asynchronen C++ AMP-Operation entspricht.

### <a name="syntax"></a>Syntax

```
class completion_future;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[Completion_future-Konstruktor](#ctor)|Initialisiert eine neue Instanz der `completion_future`-Klasse.|
|[~ Completion_future-Destruktor](#dtor)|Zerstört das `completion_future`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[get](#get)|Wartet, bis der zugeordnete asynchrone Vorgang beendet ist.|
|[then](#then)|Verkettet ein Rückruffunktionsobjekt mit dem `completion_future`-Objekt, das ausgeführt werden soll, wenn der zugeordnete asynchrone Vorgang beendet wird.|
|[to_task](#to_task)|Gibt ein `task`-Objekt zurück, das dem zugeordneten asynchronen Vorgang entspricht.|
|[valid](#valid)|Ruft einen booleschen Wert ab, der angibt, ob das Objekt einem asynchronen Vorgang zugeordnet ist.|
|[wait](#wait)|Blockiert, bis der zugeordnete asynchrone Vorgang beendet ist.|
|[wait_for](#wait_for)|Blockiert, bis der zugeordnete asynchrone Vorgang beendet oder die Zeit, die von `_Rel_time` angegeben wird, abgelaufen ist.|
|[wait_until](#wait_until)|Blockiert, bis der zugeordnete asynchrone Vorgang beendet ist oder die aktuelle Uhrzeit den von `_Abs_time` angegebenen Wert überschreitet.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[operator std::shared_future\<void>](#operator_shared_future)|Konvertiert implizit das `completion_future`-Objekt zu einem `std::shared_future`-Objekt.|
|[operator=](#operator_eq)|Kopiert den Inhalt des angegebenen `completion_future`-Objekts in dieses Objekt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`completion_future`

## <a name="requirements"></a>Anforderungen

**Header:** amprt.h

**Namespace:** Parallelität

## <a name="ctor"></a> completion_future

Initialisiert eine neue Instanz der `completion_future`-Klasse.

### <a name="syntax"></a>Syntax

```
completion_future();

completion_future(
    const completion_future& _Other );

completion_future(
    completion_future&& _Other );
```

### <a name="parameters"></a>Parameter

*_Sonstige*<br/>
Die `completion_future` Objekt kopieren oder verschieben.

### <a name="overloads-list"></a>Überladungsliste

|name|Beschreibung|
|----------|-----------------|
|`completion_future();`|Initialisiert eine neue Instanz der dem `completion_future` Klasse|
|`completion_future(const completion_future& _Other);`|Initialisiert eine neue Instanz der dem `completion_future` -Klasse durch Kopieren eines Konstruktors.|
|`completion_future(completion_future&& _Other);`|Initialisiert eine neue Instanz der dem `completion_future` Klasse, indem Sie einen Konstruktor verschieben.|

## <a name="get"></a> Erhalten

Wartet, bis der zugeordnete asynchrone Vorgang beendet ist. Löst das gespeicherte Ausnahme aus, wenn eine während des asynchronen Vorgangs aufgetreten ist.

### <a name="syntax"></a>Syntax

```
void get() const;
```

## <a name="operator_shared_future"></a> Operator Std:: shared_future<void>

Konvertiert implizit das `completion_future`-Objekt zu einem `std::shared_future`-Objekt.

### <a name="syntax"></a>Syntax

```
operator std::shared_future<void>() const;
```

### <a name="return-value"></a>Rückgabewert

Ein `std::shared_future`-Objekt.

## <a name="operator_eq"></a> Operator =

Kopiert den Inhalt des angegebenen `completion_future`-Objekts in dieses Objekt.

### <a name="syntax"></a>Syntax

```
completion_future&  operator= (const completion_future& _Other );
completion_future&  operator= (completion_future&& _Other );
```

### <a name="parameters"></a>Parameter

*_Sonstige*<br/>
Das Objekt, das kopiert werden soll.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das `completion_future`-Objekt.

## <a name="overloads-list"></a>Überladungsliste

|name|Beschreibung|
|----------|-----------------|
|`completion_future& operator=(const completion_future& _Other);`|Kopiert den Inhalt des angegebenen `completion_future` -Objekts in dieses Objekt, das mithilfe einer tiefen Kopie.|
|`completion_future& operator=(completion_future&& _Other);`|Kopiert den Inhalt des angegebenen `completion_future` -Objekts in dieses Objekt, das mit einer bewegungszuweisung.|

## <a name="then"></a> Klicken Sie dann

Verkettet ein Rückruffunktionsobjekt mit dem `completion_future`-Objekt, das ausgeführt werden soll, wenn der zugeordnete asynchrone Vorgang beendet wird.

### <a name="syntax"></a>Syntax

```
template <typename _Functor>
void then(const _Functor & _Func ) const;
```

### <a name="parameters"></a>Parameter

*_Functor*<br/>
Das Funktionselement Rückruf.

*_Func*<br/>
Das Rückrufobjekt-Funktion.

## <a name="to_task"></a> to_task

Gibt ein `task`-Objekt zurück, das dem zugeordneten asynchronen Vorgang entspricht.

### <a name="syntax"></a>Syntax

```
concurrency::task<void> to_task() const;
```

### <a name="return-value"></a>Rückgabewert

Ein `task` Objekt entsprechend des zugeordneten asynchronen Vorgangs.

## <a name="valid"></a> gültige

Ruft einen booleschen Wert, der angibt, ob das Objekt mit einem asynchronen Vorgang zugeordnet ist.

### <a name="syntax"></a>Syntax

```
bool valid() const;
```

### <a name="return-value"></a>Rückgabewert

**"true"** Wenn das Objekt, einen asynchronen Vorgang zugeordnet ist, andernfalls ist **"false"**.

## <a name="wait"></a> Warte

Blockiert, bis der zugeordnete asynchrone Vorgang beendet ist.

### <a name="syntax"></a>Syntax

```
void wait() const;
```

## <a name="wait_for"></a> wait_for

Blockiert, bis der zugeordnete asynchrone Vorgang beendet oder die Zeit, die von `_Rel_time` angegeben wird, abgelaufen ist.

### <a name="syntax"></a>Syntax

```
template <
    class _Rep,
    class _Period
>
std::future_status::future_status wait_for(
    const std::chrono::duration< _Rep, _Period>& _Rel_time ) const;
```

### <a name="parameters"></a>Parameter

*_Rep*<br/>
Ein arithmetischer Typ, der die Anzahl von Zeiteinheiten darstellt.

*_Period*<br/>
Ein std::ratio, das die Anzahl von Sekunden darstellt, die pro Zeiteinheit verstreichen.

*_Rel_time*<br/>
Die maximale Zeitspanne, die auf den Abschluss der Operation gewartet wird.

### <a name="return-value"></a>Rückgabewert

Rückgabe:

- `std::future_status::deferred`, wenn der zugeordnete asynchrone Vorgang nicht ausgeführt wird.

- `std::future_status::ready`, wenn der zugeordnete asynchrone Vorgang abgeschlossen ist.

- `std::future_status::timeout`, wenn der angegebene Zeitraum verstrichen ist.

## <a name="wait_until"></a> wait_until

Blockiert, bis der zugeordnete asynchrone Vorgang beendet ist oder die aktuelle Uhrzeit den von `_Abs_time` angegebenen Wert überschreitet.

### <a name="syntax"></a>Syntax

```
template <
    class _Clock,
    class _Duration
>
std::future_status::future_status wait_until(
    const std::chrono::time_point< _Clock, _Duration>& _Abs_time ) const;
```

### <a name="parameters"></a>Parameter

*_Clock*<br/>
Die Uhr, auf der der Zeitpunkt gemessen wird.

*_Duration*<br/>
Das Zeitintervall seit dem Beginn der Epoche von `_Clock`, nach der die Funktion durch einen Timeout beendet wird.

*_Abs_time*<br/>
Der Zeitpunkt, nach dem die Funktion durch einen Timeout beendet wird.

### <a name="return-value"></a>Rückgabewert

Rückgabe:

1. `std::future_status::deferred`, wenn der zugeordnete asynchrone Vorgang nicht ausgeführt wird.

1. `std::future_status::ready`, wenn der zugeordnete asynchrone Vorgang abgeschlossen ist.

1. `std::future_status::timeout`, wenn der angegebene Zeitraum verstrichen ist.

## <a name="dtor"></a> ~completion_future

Zerstört das `completion_future`-Objekt.

### <a name="syntax"></a>Syntax

```
~completion_future();
```

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)
