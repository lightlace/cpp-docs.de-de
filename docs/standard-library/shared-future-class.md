---
title: shared_future-Klasse
ms.date: 11/04/2016
f1_keywords:
- future/std::shared_future
- future/std::shared_future::shared_future
- future/std::shared_future::get
- future/std::shared_future::valid
- future/std::shared_future::wait
- future/std::shared_future::wait_for
- future/std::shared_future::wait_until
ms.assetid: 454ebedd-f42b-405f-99a5-a25cc9ad7c90
helpviewer_keywords:
- std::shared_future [C++]
- std::shared_future [C++], shared_future
- std::shared_future [C++], get
- std::shared_future [C++], valid
- std::shared_future [C++], wait
- std::shared_future [C++], wait_for
- std::shared_future [C++], wait_until
ms.openlocfilehash: 2280c17c4ce58fe06365c107ad26d646c7ae2d72
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412604"
---
# <a name="sharedfuture-class"></a>shared_future-Klasse

Beschreibt ein *asynchrones Rückgabeobjekt*. Im Gegensatz zu einem [zukünftigen](../standard-library/future-class.md) Objekt, kann ein *asynchroner Anbieter* beliebig vielen `shared_future`-Objekten zugeordnet werden.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
class shared_future;
```

## <a name="remarks"></a>Hinweise

Rufen Sie keine anderen Methoden als `valid`, `operator=` und den Destruktor eines `shared_future`-Objekts auf, das *leer* ist.

`shared_future`-Objekte werden nicht synchronisiert. Aufrufen von Methoden für das gleiche Objekt von mehreren Threads führt zu einem Datenrace mit unvorhersehbaren Ergebnissen.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[shared_future](#shared_future)|Erstellt ein `shared_future`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[get](#get)|Ruft das Ergebnis ab, das im *zugeordneten asynchronen Zustand* gespeichert ist.|
|[valid](#valid)|Gibt an, dass das Objekt nicht leer ist.|
|[wait](#wait)|Blockiert den aktuellen Thread, bis der zugeordnete asynchrone Zustand bereit ist.|
|[wait_for](#wait_for)|Blockiert, bis der zugeordnete asynchrone Zustand bereit ist, oder bis die angegebene Zeit verstrichen ist.|
|[wait_until](#wait_until)|Blockiert, bis der zugeordnete asynchrone Zustand bereit ist, oder bis ein angegebener Zeitpunkt erreicht ist.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[shared_future::operator=](#op_eq)|Weist einen neuen zugeordneten asynchronen Zustand zu.|

## <a name="requirements"></a>Anforderungen

**Header:** \<future>

**Namespace:** std

## <a name="get"></a>  shared_future:: Get

Ruft das Ergebnis ab, das im *zugeordneten asynchronen Zustand* gespeichert ist.

```cpp
const Ty& get() const;

Ty& get() const;

void get() const;
```

### <a name="remarks"></a>Hinweise

Wenn das Ergebnis eine Ausnahme ist, wird es erneut von der Methode ausgelöst. Andernfalls ist das Ergebnis negativ.

Bevor sie das Ergebnis abruf, blockiert diese Methode den aktuellen Thread, bis der zugeordnete asynchrone Zustand bereit ist.

Für die Teilspezialisierung `shared_future<Ty&>` ist der gespeicherte Wert praktisch ein Verweis auf das Objekt, das dem asynchronen *Anbieter als Rückgabewert* übergeben wurde.

Da kein gespeicherter Wert, für die Spezialisierung vorhanden `shared_future<void>`, gibt die Methode zurück **"void"**.

## <a name="op_eq"></a> shared_future::operator=

Überträgt einen *zugeordneten asynchronen Zustand* aus einem angegebenen Objekt.

```cpp
shared_future& operator=(shared_future&& Right) noexcept;
shared_future& operator=(const shared_future& Right);
```

### <a name="parameters"></a>Parameter

*Rechts*<br/>
Ein `shared_future`-Objekt.

### <a name="return-value"></a>Rückgabewert

`*this`

### <a name="remarks"></a>Hinweise

Für den ersten Operator *rechts* mehr verfügt über keinen zugeordneten asynchronen Zustand nach Abschluss des Vorgangs.

Für die zweite Methode *rechts* den assoziierte asynchronen Zustand verwaltet.

## <a name="shared_future"></a> shared_future::shared_future-Konstruktor

Erstellt ein `shared_future`-Objekt.

```cpp
shared_future() noexcept;
shared_future(future<Ty>&& Right) noexcept;
shared_future(shared_future&& Right) noexcept;
shared_future(const shared_future& Right);
```

### <a name="parameters"></a>Parameter

*Rechts*<br/>
Ein [zukünftiges](../standard-library/future-class.md) oder `shared_future`-Objekt.

### <a name="remarks"></a>Hinweise

Der erste Konstruktor erstellt ein `shared_future`-Objekt, das über keinen *zugeordneten asynchronen Zustand* verfügt.

Die zweiten und dritten Konstruktoren erstellen ein `shared_future` Objekt aus, und übertragen Sie den zugeordneten asynchronen Zustand aus *rechts*. *Rechts* mehr verfügt über keinen zugeordneten asynchronen Zustand.

Der vierte Konstruktor erstellt ein `shared_future` Objekt mit dem gleichen zugeordneten asynchronen Zustand als *rechts*.

## <a name="valid"></a>  shared_future:: Valid

Gibt an, ob das Objekt einen *zugeordneten asynchronen Zustand* hat.

```cpp
bool valid() noexcept;
```

### <a name="return-value"></a>Rückgabewert

**"true"** verfügt das Objekt einen zugeordneten asynchronen Zustand ist; andernfalls **"false"**.

## <a name="wait"></a>  shared_future:: wait

Blockiert den aktuellen Thread, bis der *zugeordnete asynchrone Zustand* *bereit* ist.

```cpp
void wait() const;
```

### <a name="remarks"></a>Hinweise

Ein zugeordneter asynchroner Zustand ist nur dann bereit, wenn sein asynchroner Anbieter einen Rückgabewert oder eine Ausnahme gespeichert hat.

## <a name="wait_for"></a>  shared_future:: wait_for

Blockiert den aktuellen Thread, bis der zugeordnete asynchrone Zustand *bereit* oder eine angegebene Zeit verstrichen ist.

```cpp
template <class Rep, class Period>
future_status wait_for(
    const chrono::duration<Rep, Period>& Rel_time) const;
```

### <a name="parameters"></a>Parameter

*Rel_time*<br/>
Ein [chrono::duration](../standard-library/duration-class.md)-Objekt, das ein maximales Zeitintervall angibt, das der Thread blockiert.

### <a name="return-value"></a>Rückgabewert

Ein [future_status](../standard-library/future-enums.md#future_status), das den Grund für die Rückgabe angibt.

### <a name="remarks"></a>Hinweise

Ein zugeordneter asynchroner Zustand ist nur dann *bereit*, wenn sein asynchroner Anbieter einen Rückgabewert oder eine Ausnahme gespeichert hat.

## <a name="wait_until"></a>  shared_future:: wait_until

Blockiert den aktuelle Thread, bis der zugeordnete asynchrone Zustand *bereit* oder ein angegebener Zeitpunkt verstrichen ist.

```cpp
template <class Clock, class Duration>
future_status wait_until(
    const chrono::time_point<Clock, Duration>& Abs_time) const;
```

### <a name="parameters"></a>Parameter

*Abs_time*<br/>
Ein [chrono::time_point](../standard-library/time-point-class.md)-Objekt, das eine Zeit angibt, nach der der Thread die Blockierung aufheben kann.

### <a name="return-value"></a>Rückgabewert

Ein [future_status](../standard-library/future-enums.md#future_status), das den Grund für die Rückgabe angibt.

### <a name="remarks"></a>Hinweise

Ein zugeordneter asynchroner Zustand ist nur dann bereit, wenn sein asynchroner Anbieter einen Rückgabewert oder eine Ausnahme gespeichert hat.

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<future>](../standard-library/future.md)<br/>
