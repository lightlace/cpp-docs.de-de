---
title: Concurrency-Namespace-Operatoren (AMP) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: 77f1ae17-1eb2-480d-8fe5-66d4c24bb91e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 308c09af9989aa998a7e1f7d748f52a2d8dca391
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
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
 `_Rank`  
 Der Rang der Tupel-Argumente.  
  
 `_Lhs`  
 Eines der zu vergleichenden Tupel.  
  
 `_Rhs`  
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
 `_Rank`  
 Der Rang der Tupel-Argumente.  
  
 `_Lhs`  
 Eines der zu vergleichenden Tupel.  
  
 `_Rhs`  
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
 `_Rank`  
 Der Rang der Tupel-Argumente.  
  
 `_Lhs`  
 Eines der hinzuzufügenden Argumente.  
  
 `_Rhs`  
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
 `_Rank`  
 Der Rang der Tupel-Argumente.  
  
 `_Lhs`  
 Das Argument, von dem subtrahiert werden soll.  
  
 `_Rhs`  
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
 `_Rank`  
 Der Rang der Tupel-Argumente.  
  
 `_Lhs`  
 Eines der zu multiplizierenden Tupel.  
  
 `_Rhs`  
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
 `_Rank`  
 Der Rang der Tupel-Argumente.  
  
 `_Lhs`  
 Das zu dividierende Tupel.  
  
 `_Rhs`  
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
 `_Rank`  
 Der Rang der Tupel-Argumente.  
  
 `_Lhs`  
 Das Tupel, auf dessen Basis das Modulo berechnet wird.  
  
 `_Rhs`  
 Das Tupel für die Modulo-Berechnung.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Ergebnis des ersten angegebenen Arguments ergibt das zweite angegebene Argument.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace ](concurrency-namespace-cpp-amp.md)
