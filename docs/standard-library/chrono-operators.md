---
title: '&lt;chrono&gt;-Operatoren'
ms.date: 11/04/2016
f1_keywords:
- chrono/std::operator modulo
ms.assetid: c5a19267-4684-40c1-b7a9-cc1012b058f3
ms.openlocfilehash: 398e2429c38cffb454c7b510aa5ab44fbe4cfef6
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68244892"
---
# <a name="ltchronogt-operators"></a>&lt;chrono&gt;-Operatoren

## <a name="operator-"></a> Operator-

Operator für die Subtraktion oder Negation von [duration](../standard-library/duration-class.md)- und [time_point](../standard-library/time-point-class.md)-Objekten.

```cpp
template <class Rep1, class Period1, class Rep2, class Period2>
constexpr typename common_type<duration<Rep1, Period1>, duration<Rep2, Period2>>::type
   operator-(
       const duration<Rep1, Period1>& Left,
       cconst duration<Rep2, Period2>& Right);

template <class Clock, class Duration1, class Rep2, class Period2>
constexpr time_point<Clock, typename common_type<Duration1, duration<Rep2, Period2>>::type
   operator-(
       const time_point<Clock, Duration1>& Time,
       const duration<Rep2, Period2>& Dur);

template <class Clock, class Duration1, class Duration2>
constexpr typename common_type<Duration1, Duration2>::type
   operator-(
       const time_point<Clock, Duration1>& Left,
       const time_point<Clock, Duration2>& Right);
```

### <a name="parameters"></a>Parameter

*Links*\
Das linke `duration` oder `time_point`-Objekt.

*Richting*\
Das rechte `duration` oder `time_point`-Objekt.

*Zeit*\
Ein `time_point`-Objekt.

*Abfragedauer*\
Ein `duration`-Objekt.

### <a name="return-value"></a>Rückgabewert

Von der ersten Funktion wird ein `duration`-Objekt zurückgegeben, dessen Intervalllänge der Unterschied zwischen den Zeitintervallen zweier Argumente ist.

Die zweite Funktion gibt eine `time_point` -Objekt, das einem bestimmten Zeitpunkt darstellt, die ersetzt wird durch die Negation des Zeitintervalls, der durch dargestellt wird *Dur*, aus dem Zeitpunkt, der angegebenen *Zeit*.

Die dritte Funktion gibt eine `duration` -Objekt, das Zeitintervall zwischen darstellt *Links* und *rechts*.

## <a name="op_neq"></a> Operator! =

Ungleichheitsoperator für [duration](../standard-library/duration-class.md)- oder [time_point](../standard-library/time-point-class.md)-Objekte.

```cpp
template <class Rep1, class Period1, class Rep2, class Period2>
constexpr bool operator!=(
    const duration<Rep1, Period1>& Left,
    const duration<Rep2, Period2>& Right);

template <class Clock, class Duration1, class Duration2>
constexpr bool operator!=(
    const time_point<Clock, Duration1>& Left,
    const time_point<Clock, Duration2>& Right);
```

### <a name="parameters"></a>Parameter

*Links*\
Das linke `duration` oder `time_point`-Objekt.

*Richting*\
Das rechte `duration` oder `time_point`-Objekt.

### <a name="return-value"></a>Rückgabewert

Jede Funktion gibt `!(Left == Right)` zurück.

## <a name="op_star"></a> Operator *

Multiplikationsoperator für [duration](../standard-library/chrono-operators.md#op_star)-Objekte.

```cpp
template <class Rep1, class Period1, class Rep2>
constexpr duration<typename common_type<Rep1, Rep2>::type, Period1>
   operator*(
      const duration<Rep1, Period1>& Dur,
      const Rep2& Mult);

template <class Rep1, class Rep2, class Period2>
constexpr duration<typename common_type<Rep1, Rep2>::type, Period2>
   operator*(
       const Rep1& Mult,
       const duration<Rep2,
       Period2>& Dur);
```

### <a name="parameters"></a>Parameter

*Abfragedauer*\
Ein `duration`-Objekt.

*Mult*\
Ein Integralwert.

### <a name="return-value"></a>Rückgabewert

Jede Funktion gibt eine `duration` Objekt, dessen Intervalllänge *Mult* multipliziert mit der Länge der *Dur*.

Sofern `is_convertible<Rep2, common_type<Rep1, Rep2>>` *nicht wahr ist*, wird die erste Funktion nicht an der Überladungsauflösung beteiligt. Weitere Informationen finden Sie unter [<type_traits>](../standard-library/type-traits.md).

Sofern `is_convertible<Rep1, common_type<Rep1, Rep2>>` *nicht wahr ist*, wird die zweite Funktion nicht an der Überladungsauflösung beteiligt. Weitere Informationen finden Sie unter [<type_traits>](../standard-library/type-traits.md).

## <a name="op_div"></a> Operator /

Divisionsoperator für [duration](../standard-library/chrono-operators.md#op_star)-Objekte.

```cpp
template <class Rep1, class Period1, class Rep2>
constexpr duration<typename common_type<Rep1, Rep2>::type, Period1>
   operator/(
     const duration<Rep1, Period1>& Dur,
     const Rep2& Div);

template <class Rep1, class Period1, class Rep2, class Period2>
constexpr typename common_type<Rep1, Rep2>::type
   operator/(
     const duration<Rep1, Period1>& Left,
     const duration<Rep2, Period2>& Right);
```

### <a name="parameters"></a>Parameter

*Abfragedauer*\
Ein `duration`-Objekt.

*div*\
Ein Integralwert.

*Links*\
Das linke `duration`-Objekt.

*Richting*\
Das rechte `duration`-Objekt.

### <a name="return-value"></a>Rückgabewert

Der erste Operator gibt ein Duration-Objekt, dessen Intervall beträgt die Länge des *Dur* geteilt durch den Wert *Div*.

Der zweite Operator gibt das Verhältnis der Intervalllängen von *Links* und *rechts*.

Sofern `is_convertible<Rep2, common_type<Rep1, Rep2>>` *nicht wahr ist* und `Rep2` keine Instanziierung von `duration` ist, wird der erste Operator nicht an der Überladungsauflösung beteiligt. Weitere Informationen finden Sie unter [<type_traits>](../standard-library/type-traits.md).

## <a name="op_add"></a> Operator +-

Fügt [duration](../standard-library/duration-class.md)- und [time_point](../standard-library/time-point-class.md)-Objekte hinzu.

```cpp
template <class Rep1, class Period1, class Rep2, class Period2>
constexpr typename common_type<duration<Rep1, Period1>, duration<Rep2, Period2>>::type
   operator+(
      const duration<Rep1, Period1>& Left,
      const duration<Rep2, Period2>& Right);

template <class Clock, class Duration1, class Rep2, class Period2>
constexpr time_point<Clock, typename common_type<Duration1, duration<Rep2, Period2>>::type>
   operator+(
      const time_point<Clock, Duration1>& Time,
      const duration<Rep2, Period2>& Dur);

template <class Rep1, class Period1, class Clock, class Duration2>
time_point<Clock, constexpr typename common_type<duration<Rep1, Period1>, Duration2>::type>
   operator+(
      const duration<Rep1, Period1>& Dur,
      const time_point<Clock, Duration2>& Time);
```

### <a name="parameters"></a>Parameter

*Links*\
Das linke `duration` oder `time_point`-Objekt.

*Richting*\
Das rechte `duration` oder `time_point`-Objekt.

*Zeit*\
Ein `time_point`-Objekt.

*Abfragedauer*\
Ein `duration`-Objekt.

### <a name="return-value"></a>Rückgabewert

Die erste Funktion gibt eine `duration` -Objekt, das ein Zeitintervall verfügt, der gleich der Summe den Zeitintervallen von *Links* und *rechts*.

Die zweiten und dritten Funktionen geben eine `time_point` -Objekt, das einem bestimmten Zeitpunkt, die ersetzt wird darstellt, indem Sie das Intervall *Dur*, von dem Zeitpunkt *Zeit*.

## <a name="op_lt"></a>-Operator&lt;

Bestimmt, ob ein [duration](../standard-library/duration-class.md)- oder [time_point](../standard-library/time-point-class.md)-Objekt kleiner als ein anderes `duration`- oder `time_point`-Objekt ist.

```cpp
template <class Rep1, class Period1, class Rep2, class Period2>
constexpr bool operator<(
    const duration<Rep1, Period1>& Left,
    const duration<Rep2, Period2>& Right);

template <class Clock, class Duration1, class Duration2>
constexpr bool operator<(
    const time_point<Clock, Duration1>& Left,
    const time_point<Clock, Duration2>& Right);
```

### <a name="parameters"></a>Parameter

*Links*\
Das linke `duration` oder `time_point`-Objekt.

*Richting*\
Das rechte `duration` oder `time_point`-Objekt.

### <a name="return-value"></a>Rückgabewert

Die erste Funktion gibt **"true"** Wenn die Intervalllänge von *Links* ist kleiner als die Intervalllänge von *rechts*. Die Funktion hingegen gibt **"false"** .

Die zweite Funktion gibt **"true"** Wenn *Links* vorausgeht *rechts*. Die Funktion hingegen gibt **"false"** .

## <a name="op_lt_eq"></a> Operator&lt;=

Bestimmt, ob ein [duration](../standard-library/duration-class.md)- oder [time_point](../standard-library/time-point-class.md)-Objekt kleiner oder gleich einem anderen `duration`- oder `time_point`-Objekt ist.

```cpp
template <class Rep1, class Period1, class Rep2, class Period2>
constexpr bool operator<=(
    const duration<Rep1, Period1>& Left,
    const duration<Rep2, Period2>& Right);

template <class Clock, class Duration1, class Duration2>
constexpr bool operator<=(
    const time_point<Clock, Duration1>& Left,
    const time_point<Clock, Duration2>& Right);
```

### <a name="parameters"></a>Parameter

*Links*\
Das linke `duration` oder `time_point`-Objekt.

*Richting*\
Das rechte `duration` oder `time_point`-Objekt.

### <a name="return-value"></a>Rückgabewert

Jede Funktion gibt `!(Right < Left)` zurück.

## <a name="op_eq_eq"></a> Operator ==

Bestimmt, ob zwei `duration`-Objekte Zeitintervalle mit derselben Länge darstellen, oder ob zwei `time_point`-Objekte den gleichen Zeitpunkt darstellen.

```cpp
template <class Rep1, class Period1, class Rep2, class Period2>
constexpr bool operator==(
    const duration<Rep1, Period1>& Left,
    const duration<Rep2, Period2>& Right);

template <class Clock, class Duration1, class Duration2>
constexpr bool operator==(
    const time_point<Clock, Duration1>& Left,
    const time_point<Clock, Duration2>& Right);
```

### <a name="parameters"></a>Parameter

*Links*\
Das linke `duration` oder `time_point`-Objekt.

*Richting*\
Das rechte `duration` oder `time_point`-Objekt.

### <a name="return-value"></a>Rückgabewert

Die erste Funktion gibt **"true"** Wenn *Links* und *rechts* Zeitintervalle mit derselben Länge darstellen. Die Funktion hingegen gibt **"false"** .

Die zweite Funktion gibt **"true"** Wenn *Links* und *rechts* den gleichen Zeitpunkt darstellen. Die Funktion hingegen gibt **"false"** .

## <a name="op_gt"></a>-Operator&gt;

Bestimmt, ob ein [duration](../standard-library/duration-class.md)- oder [time_point](../standard-library/time-point-class.md)-Objekt größer als ein anderes `duration`- oder `time_point`-Objekt ist.

```cpp
template <class Rep1, class Period1, class Rep2, class Period2>
constexpr bool operator>(
    const duration<Rep1, Period1>& Left,
    const duration<Rep2, Period2>& Right);

template <class Clock, class Duration1, class Duration2>
constexpr bool operator>(
    const time_point<Clock, Duration1>& Left,
    const time_point<Clock, Duration2>& Right);
```

### <a name="parameters"></a>Parameter

*Links*\
Das linke `duration` oder `time_point`-Objekt.

*Richting*\
Das rechte `duration` oder `time_point`-Objekt.

### <a name="return-value"></a>Rückgabewert

Jede Funktion gibt `Right < Left` zurück.

## <a name="op_gt_eq"></a> Operator&gt;=

Bestimmt, ob ein [duration](../standard-library/duration-class.md)- oder [time_point](../standard-library/time-point-class.md)-Objekt größer oder gleich einem anderen `duration`- oder `time_point`-Objekt ist.

```cpp
template <class Rep1, class Period1, class Rep2, class Period2>
constexpr bool operator>=(
    const duration<Rep1, Period1>& Left,
    const duration<Rep2, Period2>& Right);

template <class Clock, class Duration1, class Duration2>
constexpr bool operator>=(
    const time_point<Clock, Duration1>& Left,
    const time_point<Clock, Duration2>& Right);
```

### <a name="parameters"></a>Parameter

*Links*\
Das linke `duration` oder `time_point`-Objekt.

*Richting*\
Das rechte `duration` oder `time_point`-Objekt.

### <a name="return-value"></a>Rückgabewert

Jede Funktion gibt `!(Left < Right)` zurück.

## <a name="op_modulo"></a> Operator modulo

Operator für Modulo-Vorgänge für [duration](../standard-library/duration-class.md)-Objekte.

```cpp
template <class Rep1, class Period1, class Rep2>
constexpr duration<Rep1, Period1, Rep2>::type
   operator%(
      const duration<Rep1, Period1>& Dur,
      const Rep2& Div);

template <class Rep1, class Period1, class Rep2, class Period2>
constexpr typename common_type<duration<Rep1, _Period1>, duration<Rep2, Period2>>::type
   operator%(
     const duration<Rep1, Period1>& Left,
     const duration<Rep2, Period2>& Right);
```

### <a name="parameters"></a>Parameter

*Abfragedauer*\
Ein `duration`-Objekt.

*div*\
Ein Integralwert.

*Links*\
Das linke `duration`-Objekt.

*Richting*\
Das rechte `duration`-Objekt.

### <a name="return-value"></a>Rückgabewert

Die erste Funktion gibt eine `duration` Objekt, dessen Intervalllänge *Dur* modulo *Div*.

Die zweite Funktion gibt einen Wert, der darstellt *Links* modulo *rechts*.
