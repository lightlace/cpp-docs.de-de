---
title: Concurrency-Namespace-Operatoren (AMP) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- C++
ms.assetid: 77f1ae17-1eb2-480d-8fe5-66d4c24bb91e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d6e8d2a198105e9cd63581dd8ed8445b681da2e0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46026932"
---
# <a name="concurrency-namespace-operators-amp"></a>Concurrency-Namespace-Operatoren (AMP)
||||  
|-|-|-|  
|[operator!=](#operator_neq)|[operator%](#operator_mod)|[operator*](#operator_star)|  
|[operator+](#operator_add)|[operator-](#operator-)|[operator/](#operator_div)|  
|[operator==](#operator_eq_eq)|  
  
##  <a name="operator_eq_eq"></a> operator==   
 Bestimmt, ob die angegebenen Argumente gleich sind.  
  
```  
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
bool operator== (
    const _Tuple_type<_Rank>& _Lhs,  
    const _Tuple_type<_Rank>& _Rhs) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
*_Rank*<br/>
Der Rang der Tupel-Argumente.  
  
*_Lhs*<br/>
Eines der zu vergleichenden Tupel.  
  
*_Rhs*<br/>
Eines der zu vergleichenden Tupel.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn die Tupel gleich sind, andernfalls `false`.  
  
##  <a name="operator_neq"></a> operator!=   
 Bestimmt, ob die angegebenen Argumente ungleich sind.  
  
```  
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
bool operator!= (
    const _Tuple_type<_Rank>& _Lhs,  
    const _Tuple_type<_Rank>& _Rhs) restrict(amp);
```  
  
### <a name="parameters"></a>Parameter  
*_Rank*<br/>
Der Rang der Tupel-Argumente.  
  
*_Lhs*<br/>
Eines der zu vergleichenden Tupel.  
  
*_Rhs*<br/>
Eines der zu vergleichenden Tupel.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn die Tupel nicht gleich sind, andernfalls `false`.  
  
##  <a name="operator_add"></a> operator+   

 Berechnet die komponentenbezogene Summe der angegebenen Argumente.  
  
```  
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
class _Tuple_type> _Tuple_type<_Rank>   operator+(
    const _Tuple_type<_Rank>& _Lhs,  
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);

 
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
class _Tuple_type> _Tuple_type<_Rank>   operator+(
    const _Tuple_type<_Rank>& _Lhs,  
    typename _Tuple_type<_Rank>::value_type _Rhs) restrict(amp,cpu);

 
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
class _Tuple_type> _Tuple_type<_Rank>   operator+(
    typename _Tuple_type<_Rank>::value_type _Lhs,  
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);
```  
  
### <a name="parameters"></a>Parameter  
*_Rank*<br/>
Der Rang der Tupel-Argumente.  
  
*_Lhs*<br/>
Eines der hinzuzufügenden Argumente.  
  
*_Rhs*<br/>
Eines der hinzuzufügenden Argumente.  
  
### <a name="return-value"></a>Rückgabewert  
 Die komponentenbezogene Summe der angegebenen Argumente.  
  
##  <a name="operator-"></a> operator-   

 Berechnet die Differenz zwischen den angegebenen Argumenten pro Komponente.  
  
```  
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
_Tuple_type<_Rank>   operator-(
    const _Tuple_type<_Rank>& _Lhs,  
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);

 
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
_Tuple_type<_Rank>   operator-(
    const _Tuple_type<_Rank>& _Lhs,  
    typename _Tuple_type<_Rank>::value_type _Rhs) restrict(amp,cpu);

 
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
_Tuple_type<_Rank>   operator-(
    typename _Tuple_type<_Rank>::value_type _Lhs,  
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);
```  
  
### <a name="parameters"></a>Parameter  
*_Rank*<br/>
Der Rang der Tupel-Argumente.  
  
*_Lhs*<br/>
Das Argument, von dem subtrahiert werden soll.  
  
*_Rhs*<br/>
Das zu subtrahierende Argument.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Differenz zwischen den angegebenen Argumenten pro Komponente.  
  
##  <a name="operator_star"></a> operator*   

 Berechnet das komponentenbezogene Produkt der angegebenen Argumente.  
  
```  
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
_Tuple_type<_Rank>   operator*(
    const _Tuple_type<_Rank>& _Lhs,  
    typename _Tuple_type<_Rank>::value_type _Rhs) restrict(amp,cpu);

 
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
_Tuple_type<_Rank>   operator*(
    typename _Tuple_type<_Rank>::value_type _Lhs,  
    const _Tuple_type<_Rank>& _Rhs) restrict(amp, cpu);
```  
  
### <a name="parameters"></a>Parameter  
*_Rank*<br/>
Der Rang der Tupel-Argumente.  
  
*_Lhs*<br/>
Eines der zu multiplizierenden Tupel.  
  
*_Rhs*<br/>
Eines der zu multiplizierenden Tupel.  
  
### <a name="return-value"></a>Rückgabewert  
 Das komponentenbezogene Produkt der angegebenen Argumente.  
  

##  <a name="operator_div"></a> operator/   
 Berechnet den komponentenbezogenen Quotienten der angegebenen Argumente.  
  
```  
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
_Tuple_type<_Rank>   operator/(
    const _Tuple_type<_Rank>& _Lhs,  
    typename _Tuple_type<_Rank>::value_type _Rhs) restrict(amp,cpu);

 
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
_Tuple_type<_Rank>   operator/(
    typename _Tuple_type<_Rank>::value_type _Lhs,  
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);
```  
  
### <a name="parameters"></a>Parameter  
*_Rank*<br/>
Der Rang der Tupel-Argumente.  
  
*_Lhs*<br/>
Das zu dividierende Tupel.  
  
*_Rhs*<br/>
Das Tupel für die Division.  
  
### <a name="return-value"></a>Rückgabewert  
 Der komponentenbezogene Quotient der angegebenen Argumente.  
  
##  <a name="operator_mod"></a> operator%   

 Berechnet den Modul des angegebenen ersten Arguments dividiert durch das zweite angegebene Argument.  
  
```  
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
_Tuple_type<_Rank>   operator%(
    const _Tuple_type<_Rank>& _Lhs,  
    typename _Tuple_type<_Rank>::value_type _Rhs) restrict(amp,cpu);

 
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
_Tuple_type<_Rank>   operator%(
    typename _Tuple_type<_Rank>::value_type _Lhs,  
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);
```  
  
### <a name="parameters"></a>Parameter  
*_Rank*<br/>
Der Rang der Tupel-Argumente.  
  
*_Lhs*<br/>
Das Tupel, auf dessen Basis das Modulo berechnet wird.  
  
*_Rhs*<br/>
Das Tupel für die Modulo-Berechnung.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Ergebnis des ersten angegebenen Arguments ergibt das zweite angegebene Argument.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace ](concurrency-namespace-cpp-amp.md)
