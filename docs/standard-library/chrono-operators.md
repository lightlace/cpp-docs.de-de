---
title: '&lt;chrono&gt;-Operatoren | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- chrono/std::operator modulo
ms.assetid: c5a19267-4684-40c1-b7a9-cc1012b058f3
caps.latest.revision: 8
manager: ghogen
ms.openlocfilehash: ef535697ab7bda5cf193ef386a7e63542f431f45
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="ltchronogt-operators"></a>&lt;chrono&gt;-Operatoren

||||
|-|-|-|
|[operator modulo](#op_modulo)|[operator!=](#op_neq)|[operator&gt;](#op_gt)|
|[operator&gt;=](#op_gt_eq)|[operator&lt;](#op_lt)|[operator&lt;=](#op_lt_eq)|
|[operator*](#op_star)|[operator+](#op_add)|[operator-](#operator-)|
|[operator/](#op_div)|[operator==](#op_eq_eq)|

## <a name="operator-"></a> operator-

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

`Left` Links `duration` oder `time_point` Objekt.

`Right` Das Recht `duration` oder `time_point` Objekt.

`Time` Ein `time_point` Objekt.

`Dur` Ein `duration` Objekt.

### <a name="return-value"></a>Rückgabewert

Von der ersten Funktion wird ein `duration`-Objekt zurückgegeben, dessen Intervalllänge der Unterschied zwischen den Zeitintervallen zweier Argumente ist.

Von der zweiten Funktion wird ein `time_point`-Objekt zurückgegeben, das einen Zeitpunkt darstellt, der mithilfe der Negation des Zeitintervalls, das von `Dur` dargestellt wird, von dem Zeitpunkt, der von `Time` angegeben wird, ersetzt wird.

Von der dritten Funktion wird ein `duration`-Objekt zurückgegeben, von dem das Zeitintervall zwischen `Left` und `Right` dargestellt wird.

## <a name="op_neq"></a> operator!=

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

`Left` Links `duration` oder `time_point` Objekt.

`Right` Das Recht `duration` oder `time_point` Objekt.

### <a name="return-value"></a>Rückgabewert

Jede Funktion gibt `!(Left == Right)` zurück.

## <a name="op_star"></a> operator*

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

`Dur` Ein `duration` Objekt.

`Mult` Ein Integralwert.

### <a name="return-value"></a>Rückgabewert

Jede Funktion gibt ein `duration`-Objekt zurück, dessen Intervalllänge `Mult` mit der Länge von `Dur` multipliziert wird.

Sofern `is_convertible<Rep2, common_type<Rep1, Rep2>>` *nicht wahr ist*, wird die erste Funktion nicht an der Überladungsauflösung beteiligt. Weitere Informationen finden Sie unter [<type_traits>](../standard-library/type-traits.md).

Sofern `is_convertible<Rep1, common_type<Rep1, Rep2>>` *nicht wahr ist*, wird die zweite Funktion nicht an der Überladungsauflösung beteiligt. Weitere Informationen finden Sie unter [<type_traits>](../standard-library/type-traits.md).

## <a name="op_div"></a> operator/

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

`Dur` Ein `duration` Objekt.

`Div` Ein Integralwert.

`Left` Links `duration` Objekt.

`Right` Das Recht `duration` Objekt.

### <a name="return-value"></a>Rückgabewert

Der erste Operator gibt ein duration-Objekt zurück, dessen Intervalllänge die Länge von `Dur` dividiert durch den `Div`-Wert ist.

Der zweite Operator gibt das Verhältnis der Intervalllängen von `Left` und `Right` zurück.

Sofern `is_convertible<Rep2, common_type<Rep1, Rep2>>` *nicht wahr ist* und `Rep2` keine Instanziierung von `duration` ist, wird der erste Operator nicht an der Überladungsauflösung beteiligt. Weitere Informationen finden Sie unter [<type_traits>](../standard-library/type-traits.md).

## <a name="op_add"></a> operator+

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

`Left` Links `duration` oder `time_point` Objekt.

`Right` Das Recht `duration` oder `time_point` Objekt.

`Time` Ein `time_point` Objekt.

`Dur` Ein `duration` Objekt.

### <a name="return-value"></a>Rückgabewert

Von der ersten Funktion wird ein `duration`-Objekt zurückgegeben, das über ein Zeitintervall verfügt, dessen Summe den Zeitintervallen von `Left` und `Right` entspricht.

Von der zweiten und dritten Funktionen wird ein `time_point`-Objekt zurückgegeben, das einen vom `Dur`-Intervall aus dem Zeitpunkt `Time` ersetzten Zeitpunkt darstellt.

## <a name="op_lt"></a> operator&lt;

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

`Left` Links `duration` oder `time_point` Objekt.

`Right` Das Recht `duration` oder `time_point` Objekt.

### <a name="return-value"></a>Rückgabewert

Die erste Funktion gibt `true` zurück, wenn die Intervalllänge von `Left` kleiner als die Intervalllänge von `Right` ist. Andernfalls wird von der Funktion `false` zurückgegeben.

Von der zweiten Funktion wird `true` zurückgegeben, wenn `Left``Right` vorangeht. Andernfalls wird von der Funktion `false` zurückgegeben.

## <a name="op_lt_eq"></a> operator&lt;=

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

`Left` Links `duration` oder `time_point` Objekt.

`Right` Das Recht `duration` oder `time_point` Objekt.

### <a name="return-value"></a>Rückgabewert

Jede Funktion gibt `!(Right < Left)` zurück.

## <a name="op_eq_eq"></a> operator==

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

`Left` Links `duration` oder `time_point` Objekt.

`Right` Das Recht `duration` oder `time_point` Objekt.

### <a name="return-value"></a>Rückgabewert

Die erste Funktion gibt `true` zurück, wenn `Left` und `Right` Zeitintervalle mit derselben Länge darstellen. Andernfalls wird von der Funktion `false` zurückgegeben.

Die zweite Funktion gibt `true` zurück, wenn `Left` und `Right` den gleichen Zeitpunkt darstellen. Andernfalls wird von der Funktion `false` zurückgegeben.

## <a name="op_gt"></a> operator&gt;

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

`Left` Links `duration` oder `time_point` Objekt.

`Right` Das Recht `duration` oder `time_point` Objekt.

### <a name="return-value"></a>Rückgabewert

Jede Funktion gibt `Right < Left` zurück.

## <a name="op_gt_eq"></a> operator&gt;=

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

`Left` Links `duration` oder `time_point` Objekt.

`Right` Das Recht `duration` oder `time_point` Objekt.

### <a name="return-value"></a>Rückgabewert

Jede Funktion gibt `!(Left < Right)` zurück.

## <a name="op_modulo"></a> operator modulo

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

`Dur` Ein `duration` Objekt.

`Div` Ein Integralwert.

`Left` Links `duration` Objekt.

`Right` Das Recht `duration` Objekt.

### <a name="return-value"></a>Rückgabewert

Die erste Funktion gibt ein `duration`-Objekt zurück, dessen Intervalllänge `Dur` Modulo `Div` ist.

Die zweite Funktion gibt einen Wert zurück, der `Left` Modulo `Right` darstellt.

## <a name="see-also"></a>Siehe auch

[\<chrono>](../standard-library/chrono.md)<br/>
