---
title: duration-Klasse
ms.date: 03/27/2016
f1_keywords:
- chrono/std::chrono::duration
- chrono/std::chrono::duration::duration
- chrono/std::chrono::duration::count
- chrono/std::chrono::duration::max
- chrono/std::chrono::duration::min
- chrono/std::chrono::duration::zero
ms.assetid: 06b863b3-65be-4ded-a72e-6e1eb1531077
helpviewer_keywords:
- std::chrono [C++], duration
ms.openlocfilehash: 4c537b7dfdd23ba641438e0caf6306cf5549b2d7
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68454304"
---
# <a name="duration-class"></a>duration-Klasse

Beschreibt einen Typ, der ein *Zeitintervall* enthält, bei dem es sich um die verstrichene Zeit zwischen zwei Situationen handelt.

## <a name="syntax"></a>Syntax

```cpp
template <class Rep, class Period = ratio<1>>
class duration;
template <class Rep, class Period>
class duration;
template <class Rep, class Period1, class Period2>
class duration <duration<Rep, Period1>, Period2>;
```

## <a name="remarks"></a>Hinweise

Mit dem Vorlagenargument `Rep` wird der Typ beschrieben, der zum Aufnehmen der Anzahl von Zeiteinheiten im Intervall verwendet wird. Das template-Argument `Period` ist eine Instanziierung von [ratio](../standard-library/ratio.md), mit dem die Größe des von jeder Zeiteinheit dargestellten Intervalls beschrieben wird.

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|Beschreibung|
|----------|-----------------|
|duration::period Typedef|Stellt ein Synonym für den Vorlagenparameter `Period` dar.|
|duration::rep Typedef|Stellt ein Synonym für den Vorlagenparameter `Rep` dar.|

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[auf](#duration)|Erstellt ein `duration`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[count](#count)|Gibt die Anzahl von Zeiteinheiten im Zeitintervall zurück.|
|[max](#max)|Statisch Gibt den maximal zulässigen Wert des Vorlagenparameters `Ref` zurück.|
|[Min.](#min)|Statisch Gibt den niedrigsten zulässigen Wert des Vorlagenparameters `Ref` zurück.|
|[zero](#zero)|Statisch Tatsächlich wird `Rep`(0) zurückgegeben.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[duration::operator-](#operator-)|Gibt eine Kopie des `duration`-Objekts zusammen mit einer negierten Taktanzahl zurück.|
|[duration::operator--](#operator--)|Verringert die gespeicherte Taktanzahl.|
|[duration::operator=](#op_eq)|Reduziert die gespeicherte Taktanzahl-Modulo um einen angegebenen Wert.|
|[duration::operator*=](#op_star_eq)|Multipliziert die gespeicherte Taktanzahl mit einem angegebenen Wert.|
|[duration::operator/=](#op_div_eq)|Dividiert die gespeicherte Taktanzahl durch die Taktanzahl eines angegebenen `duration`-Objekts.|
|[duration::operator+](#op_add)|Gibt `*this`zurück.|
|[duration::operator++](#op_add_add)|Erhöht die gespeicherte Taktanzahl.|
|[duration::operator+=](#op_add_eq)|Fügt der gespeicherten Taktanzahl die Taktanzahl eines angegebenen `duration`-Objekts hinzu.|
|[duration::operator-=](#operator-_eq)|Subtrahiert die Taktanzahl eines angegebenen `duration`-Objekts von der gespeicherten Taktanzahl.|

## <a name="requirements"></a>Anforderungen

**Header:** \<chrono>

**Namespace:** std::chrono

## <a name="count"></a> duration::count

Ruft die Anzahl von Zeiteinheiten im Zeitintervall ab.

```cpp
constexpr Rep count() const;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl von Zeiteinheiten im Zeitintervall.

## <a name="duration"></a> duration::duration-Konstruktor

Erstellt ein `duration`-Objekt.

```cpp
constexpr duration() = default;

template <class Rep2>
constexpr explicit duration(const Rep2& R);

template <class Rep2, class Period2>
constexpr duration(const duration<Rep2, Period2>& Dur);
```

### <a name="parameters"></a>Parameter

*Rep2*\
Ein arithmetischer Typ, der die Anzahl von Zeiteinheiten darstellt.

*Period2*\
Eine `std::ratio`-Vorlagenspezialisierung zur Darstellung des Zeitraums von Zeiteinheiten in Sekunden.

*R*\
Die Anzahl der Zeiteinheiten der Standardperiode.

*Local*\
Die Anzahl der Ticks des durch *Period2*angegebenen Zeitraums.

### <a name="remarks"></a>Hinweise

Vom Standardkonstruktor wird ein nicht initialisiertes Objekt erstellt. Durch die Wertinitialisierung mithilfe von leeren Klammern wird ein Objekt initialisiert, das ein Zeitintervall mit null Zeiteinheiten darstellt.

Mit dem zweiten, einem Vorlagen Argument-Konstruktor wird ein-Objekt erstellt, das ein Zeitintervall von *R* -Takt Ticks `std::ratio<1>`mit einem Standard Zeitraum von darstellt. Um das Abrunden der Takt Anzahl zu vermeiden, ist es ein Fehler, ein Duration-Objekt aus einem Darstellungstyp zu erstellen *Rep2* , das als Gleit kommatyp `duration::rep` behandelt werden kann, wenn nicht als Gleit kommatyp behandelt werden kann.

Der dritte, zwei Vorlagen Argument-Konstruktor erstellt ein-Objekt, das ein Zeitintervall darstellt, dessen Länge das von *Dur*angegebene Zeitintervall ist. Um die Verkürzung von Taktanzahlen zu vermeiden, ist das Erstellen eines Dauerobjekts aus einem anderen Dauerobjekt, dessen Typ mit dem Zieltyp *unvereinbar* ist, ein Fehler.

Ein `D1`-Dauertyp ist mit einem anderen Dauertyp `D2` *unvereinbar*, wenn `D2` nicht als Gleitkommatyp behandelt werden kann und [ratio_divide\<D1::period, D2::period>::type::den](../standard-library/ratio.md) nicht 1 ist.

Wenn *Rep2* nicht implizit in `rep` konvertierbar ist `treat_as_floating_point<rep>`und entweder " `treat_as_floating_point<Rep2>` *true* " oder " *false" enthält*, wird der zweite Konstruktor nicht an der Überladungs Auflösung beteiligt. Weitere Informationen finden Sie unter [<type_traits>](../standard-library/type-traits.md).

Sofern kein Überlauf in die Konvertierung induziert wurde und `treat_as_floating_point<rep>` nicht *TRUE* ist bzw. beide `ratio_divide<Period2, period>::den` nicht 1 entsprechen und `treat_as_floating_point<Rep2>` nicht *FALSE* ist, wird der dritte Konstruktor nicht an der Überladungsauflösung beteiligt. Weitere Informationen finden Sie unter [<type_traits>](../standard-library/type-traits.md).

## <a name="max"></a> duration::max

Statische Methode, von der die Obergrenze für Werte vom Vorlagenparametertyp `Ref` zurückgegeben wird.

```cpp
static constexpr duration max();
```

### <a name="return-value"></a>Rückgabewert

Tatsächlich wird `duration(duration_values<rep>::max())` zurückgegeben.

## <a name="min"></a> duration::min

Statische Methode, von der die Untergrenze für Werte vom Vorlagenparametertyp `Ref` zurückgegeben wird.

```cpp
static constexpr duration min();
```

### <a name="return-value"></a>Rückgabewert

Tatsächlich wird `duration(duration_values<rep>::min())` zurückgegeben.

## <a name="operator-"></a> duration::operator-

Gibt eine Kopie des `duration`-Objekts zusammen mit einer negierten Taktanzahl zurück.

```cpp
constexpr duration operator-() const;
```

## <a name="operator--"></a> duration::operator--

Verringert die gespeicherte Taktanzahl.

```cpp
duration& operator--();

duration operator--(int);
```

### <a name="return-value"></a>Rückgabewert

Die erste Methode gibt `*this` zurück.

Die zweite Methode gibt eine Kopie von `*this` zurück, die vor dem Verringern erstellt wird.

## <a name="op_eq"></a> duration::operator=

Reduziert die gespeicherte Taktanzahl-Modulo um einen angegebenen Wert.

```cpp
duration& operator%=(const rep& Div);

duration& operator%=(const duration& Div);
```

### <a name="parameters"></a>Parameter

*Div*\
Für die erste Methode stellt *div* eine Takt Anzahl dar. Bei der zweiten Methode ist *div* ein `duration` -Objekt, das eine Takt Anzahl enthält.

### <a name="return-value"></a>Rückgabewert

Das `duration`-Objekt nach dem Modulo-Vorgang wird ausgeführt.

## <a name="op_star_eq"></a> duration::operator*=

Multipliziert die gespeicherte Taktanzahl mit einem angegebenen Wert.

```cpp
duration& operator*=(const rep& Mult);
```

### <a name="parameters"></a>Parameter

*Mult*\
Ein Wert des von `duration::rep` angegebenen Typs.

### <a name="return-value"></a>Rückgabewert

Das `duration`-Objekt nach Ausführung der Multiplikation.

## <a name="op_div_eq"></a> duration::operator/=

Dividiert die gespeicherte Taktanzahl mit einem angegebenen Wert.

```cpp
duration& operator/=(const rep& Div);
```

### <a name="parameters"></a>Parameter

*Div*\
Ein Wert des von `duration::rep` angegebenen Typs.

### <a name="return-value"></a>Rückgabewert

Das `duration`-Objekt nach Ausführung der Division.

## <a name="op_add"></a> duration::operator+

Gibt `*this`zurück.

```cpp
constexpr duration operator+() const;
```

## <a name="op_add_add"></a> duration::operator++

Erhöht die gespeicherte Taktanzahl.

```cpp
duration& operator++();

duration operator++(int);
```

### <a name="return-value"></a>Rückgabewert

Die erste Methode gibt `*this` zurück.

Die zweite Methode gibt eine Kopie von `*this` zurück, die vor dem Inkrementieren erstellt wird.

## <a name="op_add_eq"></a> duration::operator+=

Fügt der gespeicherten Taktanzahl die Taktanzahl eines angegebenen `duration`-Objekts hinzu.

```cpp
duration& operator+=(const duration& Dur);
```

### <a name="parameters"></a>Parameter

*Local*\
Ein `duration`-Objekt.

### <a name="return-value"></a>Rückgabewert

Das `duration`-Objekt nach Ausführung der Addition.

## <a name="operator-_eq"></a> duration::operator-=

Subtrahiert die Taktanzahl eines angegebenen `duration`-Objekts von der gespeicherten Taktanzahl.

```cpp
duration& operator-=(const duration& Dur);
```

### <a name="parameters"></a>Parameter

*Local*\
Ein `duration`-Objekt.

### <a name="return-value"></a>Rückgabewert

Das `duration`-Objekt nach Ausführung der Subtraktion.

## <a name="zero"></a> duration::zero

Gibt `duration(duration_values<rep>::zero())`zurück.

```cpp
static constexpr duration zero();
```

## <a name="op_mod_eq"></a> duration::operator mod=

Reduziert die gespeicherte Taktanzahl-Modulo Div oder Div.count().

```cpp
duration& operator%=(const rep& Div);duration& operator%=(const duration& Div);
```

### <a name="parameters"></a>Parameter

*Div*\
Der Divisor, der ein Duration-Objekt oder ein Wert ist, der Taktzähler darstellt.

### <a name="remarks"></a>Hinweise

Die erste Memberfunktion reduziert die gespeicherte Taktanzahl-Modulo Div und gibt *dies zurück. Die zweite Memberfunktion reduziert die gespeicherte Taktanzahl-Modulo Div.count() und gibt \*dies zurück.

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)\
[\<chrono>](../standard-library/chrono.md)\
[duration_values-Struktur](../standard-library/duration-values-structure.md)
