---
title: '&lt;chrono&gt;-Operatoren | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c5a19267-4684-40c1-b7a9-cc1012b058f3
caps.latest.revision: 8
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: c2ea4241ef1db4989caf8cdc6a16044d9c9381f6
ms.lasthandoff: 02/24/2017

---
# <a name="ltchronogt-operators"></a>&lt;chrono&gt;-Operatoren
||||  
|-|-|-|  
|[operator modulo](#operator_modulo)|[operator!=](#operator_neq)|[operator&gt;](#operator_gt_)|  
|[operator&gt;=](#operator_gt__eq)|[operator&lt;](#operator_lt_)|[operator&lt;=](#operator_lt__eq)|  
|[operator*](#operator_star)|[operator+](#operator_add)|[operator-](#operator-)|  
|[operator/](#operator_)|[operator==](#operator_eq_eq)|  
  
##  <a name="a-nameoperator-a--operator-"></a><a name="operator-"></a> operator-  
 Operator für die Subtraktion oder Negation von [duration](../standard-library/duration-class.md)- und [time_point](../standard-library/time-point-class.md)-Objekten.  
  
```  
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
 `Left`  
 Das linke `duration` oder `time_point`-Objekt.  
  
 `Right`  
 Das rechte `duration` oder `time_point`-Objekt.  
  
 `Time`  
 Ein `time_point`-Objekt.  
  
 `Dur`  
 Ein `duration`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Von der ersten Funktion wird ein `duration`-Objekt zurückgegeben, dessen Intervalllänge der Unterschied zwischen den Zeitintervallen zweier Argumente ist.  
  
 Von der zweiten Funktion wird ein `time_point`-Objekt zurückgegeben, das einen Zeitpunkt darstellt, der mithilfe der Negation des Zeitintervalls, das von `Dur` dargestellt wird, von dem Zeitpunkt, der von `Time` angegeben wird, ersetzt wird.  
  
 Von der dritten Funktion wird ein `duration`-Objekt zurückgegeben, von dem das Zeitintervall zwischen `Left` und `Right` dargestellt wird.  
  
##  <a name="a-nameoperatorneqa--operator"></a><a name="operator_neq"></a> operator!=  
 Ungleichheitsoperator für [duration](../standard-library/duration-class.md)- oder [time_point](../standard-library/time-point-class.md)-Objekte.  
  
```  
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
 `Left`  
 Das linke `duration` oder `time_point`-Objekt.  
  
 `Right`  
 Das rechte `duration` oder `time_point`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Jede Funktion gibt `!(Left == Right)` zurück.  
  
##  <a name="a-nameoperatorstara--operator"></a><a name="operator_star"></a> operator*  
 Multiplikationsoperator für [duration](../standard-library/chrono-operators.md#operator_star)-Objekte.  
  
```  
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
 `Dur`  
 Ein `duration`-Objekt.  
  
 `Mult`  
 Ein Integralwert.  
  
### <a name="return-value"></a>Rückgabewert  
 Jede Funktion gibt ein `duration`-Objekt zurück, dessen Intervalllänge `Mult` mit der Länge von `Dur` multipliziert wird.  
  
 Sofern `is_convertible<Rep2, common_type<Rep1, Rep2>>`* nicht wahr ist*, wird die erste Funktion nicht an der Überladungsauflösung beteiligt. Weitere Informationen finden Sie unter [<type_traits>](../standard-library/type-traits.md).  
  
 Sofern `is_convertible<Rep1, common_type<Rep1, Rep2>>`* nicht wahr ist*, wird die zweite Funktion nicht an der Überladungsauflösung beteiligt. Weitere Informationen finden Sie unter [<type_traits>](../standard-library/type-traits.md).  
  
##  <a name="a-nameoperatora--operator"></a><a name="operator_"></a> operator/  
 Divisionsoperator für [duration](../standard-library/chrono-operators.md#operator_star)-Objekte.  
  
```  
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
 `Dur`  
 Ein `duration`-Objekt.  
  
 `Div`  
 Ein Integralwert.  
  
 `Left`  
 Das linke `duration`-Objekt.  
  
 `Right`  
 Das rechte `duration`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Der erste Operator gibt ein duration-Objekt zurück, dessen Intervalllänge die Länge von `Dur` dividiert durch den `Div`-Wert ist.  
  
 Der zweite Operator gibt das Verhältnis der Intervalllängen von `Left` und `Right` zurück.  
  
 Sofern `is_convertible<Rep2, common_type<Rep1, Rep2>>`* nicht wahr ist* und `Rep2` keine Instanziierung von `duration` ist, wird der erste Operator nicht an der Überladungsauflösung beteiligt. Weitere Informationen finden Sie unter [<type_traits>](../standard-library/type-traits.md).  
  
##  <a name="a-nameoperatoradda--operator"></a><a name="operator_add"></a> operator+  
 Fügt [duration](../standard-library/duration-class.md)- und [time_point](../standard-library/time-point-class.md)-Objekte hinzu.  
  
```  
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
 `Left`  
 Das linke `duration` oder `time_point`-Objekt.  
  
 `Right`  
 Das rechte `duration` oder `time_point`-Objekt.  
  
 `Time`  
 Ein `time_point`-Objekt.  
  
 `Dur`  
 Ein `duration`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Von der ersten Funktion wird ein `duration`-Objekt zurückgegeben, das über ein Zeitintervall verfügt, dessen Summe den Zeitintervallen von `Left` und `Right` entspricht.  
  
 Von der zweiten und dritten Funktionen wird ein `time_point`-Objekt zurückgegeben, das einen vom `Dur`-Intervall aus dem Zeitpunkt `Time` ersetzten Zeitpunkt darstellt.  
  
##  <a name="a-nameoperatorlta--operatorlt"></a><a name="operator_lt_"></a> operator&lt;  
 Bestimmt, ob ein [duration](../standard-library/duration-class.md)- oder [time_point](../standard-library/time-point-class.md)-Objekt kleiner als ein anderes `duration`- oder `time_point`-Objekt ist.  
  
```  
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
 `Left`  
 Das linke `duration` oder `time_point`-Objekt.  
  
 `Right`  
 Das rechte `duration` oder `time_point`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Die erste Funktion gibt `true` zurück, wenn die Intervalllänge von `Left` kleiner als die Intervalllänge von `Right` ist. Andernfalls wird von der Funktion `false` zurückgegeben.  
  
 Von der zweiten Funktion wird `true` zurückgegeben, wenn `Left``Right` vorangeht. Andernfalls wird von der Funktion `false` zurückgegeben.  
  
##  <a name="a-nameoperatorlteqa--operatorlt"></a><a name="operator_lt__eq"></a> operator&lt;=  
 Bestimmt, ob ein [duration](../standard-library/duration-class.md)- oder [time_point](../standard-library/time-point-class.md)-Objekt kleiner oder gleich einem anderen `duration`- oder `time_point`-Objekt ist.  
  
```  
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
 `Left`  
 Das linke `duration` oder `time_point`-Objekt.  
  
 `Right`  
 Das rechte `duration` oder `time_point`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Jede Funktion gibt `!(Right < Left)` zurück.  
  
##  <a name="a-nameoperatoreqeqa--operator"></a><a name="operator_eq_eq"></a> operator==  
 Bestimmt, ob zwei `duration`-Objekte Zeitintervalle mit derselben Länge darstellen, oder ob zwei `time_point`-Objekte den gleichen Zeitpunkt darstellen.  
  
```  
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
 `Left`  
 Das linke `duration` oder `time_point`-Objekt.  
  
 `Right`  
 Das rechte `duration` oder `time_point`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Die erste Funktion gibt `true` zurück, wenn `Left` und `Right` Zeitintervalle mit derselben Länge darstellen. Andernfalls wird von der Funktion `false` zurückgegeben.  
  
 Die zweite Funktion gibt `true` zurück, wenn `Left` und `Right` den gleichen Zeitpunkt darstellen. Andernfalls wird von der Funktion `false` zurückgegeben.  
  
##  <a name="a-nameoperatorgta--operatorgt"></a><a name="operator_gt_"></a> operator&gt;  
 Bestimmt, ob ein [duration](../standard-library/duration-class.md)- oder [time_point](../standard-library/time-point-class.md)-Objekt größer als ein anderes `duration`- oder `time_point`-Objekt ist.  
  
```  
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
 `Left`  
 Das linke `duration` oder `time_point`-Objekt.  
  
 `Right`  
 Das rechte `duration` oder `time_point`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Jede Funktion gibt `Right < Left` zurück.  
  
##  <a name="a-nameoperatorgteqa--operatorgt"></a><a name="operator_gt__eq"></a> operator&gt;=  
 Bestimmt, ob ein [duration](../standard-library/duration-class.md)- oder [time_point](../standard-library/time-point-class.md)-Objekt größer oder gleich einem anderen `duration`- oder `time_point`-Objekt ist.  
  
```  
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
 `Left`  
 Das linke `duration` oder `time_point`-Objekt.  
  
 `Right`  
 Das rechte `duration` oder `time_point`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Jede Funktion gibt `!(Left < Right)` zurück.  
  
##  <a name="a-nameoperatormoduloa--operator-modulo"></a><a name="operator_modulo"></a> operator modulo  
 Operator für Modulo-Vorgänge für [duration](../standard-library/duration-class.md)-Objekte.  
  
```  
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
 `Dur`  
 Ein `duration`-Objekt.  
  
 `Div`  
 Ein Integralwert.  
  
 `Left`  
 Das linke `duration`-Objekt.  
  
 `Right`  
 Das rechte `duration`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Die erste Funktion gibt ein `duration`-Objekt zurück, dessen Intervalllänge `Dur` Modulo `Div` ist.  
  
 Die zweite Funktion gibt einen Wert zurück, der `Left` Modulo `Right` darstellt.  
  
## <a name="see-also"></a>Siehe auch  
 [\<chrono>](../standard-library/chrono.md)


