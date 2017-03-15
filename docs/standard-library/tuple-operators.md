---
title: '&lt;tuple&gt;-Operatoren | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- tuple/std::operator!=
- tuple/std::operator>
- tuple/std::operator>=
- tuple/std::operator<
- tuple/std::operator<=
- tuple/std::operator==
ms.assetid: f25752dc-d3e2-4e12-b5ac-9a8682ca60ed
caps.latest.revision: 13
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 41b445ceeeb1f37ee9873cb55f62d30d480d8718
ms.openlocfilehash: 9d8418ee3cd3d2ff0295b7cfa8beb063000ebc2f
ms.lasthandoff: 02/24/2017

---
# <a name="lttuplegt-operators"></a>&lt;tuple&gt;-Operatoren
||||  
|-|-|-|  
|[operator!=](#operator_neq)|[operator&gt;](#operator_gt_)|[operator&gt;=](#operator_gt__eq)|  
|[operator&lt;](#operator_lt_)|[operator&lt;=](#operator_lt__eq)|[operator==](#operator_eq_eq)|  
  
##  <a name="a-nameoperatorneqa--operator"></a><a name="operator_neq"></a> operator!=  
 Vergleicht `tuple`-Objekte, ob diese ungleich sind.  
  
```  
template <class T1, class T2, ..., class TN,  
    class U1, class U2, ..., class UN>  
bool operator!=(const tuple<T1, T2, ..., TN>& tpl1,  
    const tuple<U1, U2, ..., UN>& tpl2);
```  
  
### <a name="parameters"></a>Parameter  
 `TN`  
 Der Typ des N-ten Tupelelements.  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion gibt FALSE zurück, wenn `N` 0 ist, andernfalls `get<0>(tpl1) != get<0>(tpl2) || get<1>(tpl1) != get<1>(tpl2) || ... || get<N - 1>(tpl1) == get<N - 1>(tpl2)`.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__tuple__operator_ne.cpp   
// compile with: /EHsc   
#include <tuple>   
#include <iostream>   
  
typedef std::tuple<int, double, int, double> Mytuple;   
int main() {   
    Mytuple c0(0, 1, 2, 3);   
  
// display contents " 0 1 2 3"   
    std::cout << " " << std::get<0>(c0);   
    std::cout << " " << std::get<1>(c0);   
    std::cout << " " << std::get<2>(c0);   
    std::cout << " " << std::get<3>(c0);   
    std::cout << std::endl;   
  
    Mytuple c1 = std::make_tuple(4, 5, 6, 7);   
  
// display contents " 4 5 6 7"   
    std::cout << " " << std::get<0>(c0);   
    std::cout << " " << std::get<1>(c0);   
    std::cout << " " << std::get<2>(c0);   
    std::cout << " " << std::get<3>(c0);   
    std::cout << std::endl;   
  
// display results of comparisons   
    std::cout << std::boolalpha << " " << (c0 != c0);   
    std::cout << std::endl;   
    std::cout << std::boolalpha << " " << (c0 != c1);   
    std::cout << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
0 1 2 3  
0 1 2 3  
false  
true  
```  
  
##  <a name="a-nameoperatorlta--operatorlt"></a><a name="operator_lt_"></a> operator&lt;  
 Vergleicht `tuple`-Objekte, ob diese kleiner sind.  
  
```  
template <class T1, class T2, ..., class TN,  
    class U1, class U2, ..., class UN>  
bool operator<(const tuple<T1, T2, ..., TN>& tpl1,  
    const tuple<U1, U2, ..., UN>& tpl2);
```  
  
### <a name="parameters"></a>Parameter  
 `TN`  
 Der Typ des N-ten Tupelelements.  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion gibt TRUE zurück, wenn `N` größer als 0 ist und der erste unterschiedliche Wert in `tpl1` kleiner als der entsprechende Wert in `tpl2` ist, andernfalls wird FALSE zurückgegeben.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__tuple__operator_lt.cpp   
// compile with: /EHsc   
#include <tuple>   
#include <iostream>   
  
typedef std::tuple<int, double, int, double> Mytuple;   
int main() {   
    Mytuple c0(0, 1, 2, 3);   
  
// display contents " 0 1 2 3"   
    std::cout << " " << std::get<0>(c0);   
    std::cout << " " << std::get<1>(c0);   
    std::cout << " " << std::get<2>(c0);   
    std::cout << " " << std::get<3>(c0);   
    std::cout << std::endl;   
  
    Mytuple c1 = std::make_tuple(4, 5, 6, 7);   
  
// display contents " 4 5 6 7"   
    std::cout << " " << std::get<0>(c0);   
    std::cout << " " << std::get<1>(c0);   
    std::cout << " " << std::get<2>(c0);   
    std::cout << " " << std::get<3>(c0);   
    std::cout << std::endl;   
  
// display results of comparisons   
    std::cout << std::boolalpha << " " << (c0 < c0);   
    std::cout << std::endl;   
    std::cout << std::boolalpha << " " << (c0 < c1);   
    std::cout << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
0 1 2 3  
0 1 2 3  
false  
true  
```  
  
##  <a name="a-nameoperatorlteqa--operatorlt"></a><a name="operator_lt__eq"></a> operator&lt;=  
 Vergleicht `tuple` -Objekte, ob diese kleiner oder gleich sind.  
  
```  
template <class T1, class T2, ..., class TN,  
    class U1, class U2, ..., class UN>  
bool operator<=(const tuple<T1, T2, ..., TN>& tpl1,  
    const tuple<U1, U2, ..., UN>& tpl2);
```  
  
### <a name="parameters"></a>Parameter  
 `TN`  
 Der Typ des N-ten Tupelelements.  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion gibt `!(tpl2 < tpl1)` zurück.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__tuple__operator_le.cpp   
// compile with: /EHsc   
#include <tuple>   
#include <iostream>   
  
typedef std::tuple<int, double, int, double> Mytuple;   
int main() {   
    Mytuple c0(0, 1, 2, 3);   
  
// display contents " 0 1 2 3"   
    std::cout << " " << std::get<0>(c0);   
    std::cout << " " << std::get<1>(c0);   
    std::cout << " " << std::get<2>(c0);   
    std::cout << " " << std::get<3>(c0);   
    std::cout << std::endl;   
  
    Mytuple c1 = std::make_tuple(4, 5, 6, 7);   
  
// display contents " 4 5 6 7"   
    std::cout << " " << std::get<0>(c0);   
    std::cout << " " << std::get<1>(c0);   
    std::cout << " " << std::get<2>(c0);   
    std::cout << " " << std::get<3>(c0);   
    std::cout << std::endl;   
  
// display results of comparisons   
    std::cout << std::boolalpha << " " << (c0 <= c0);   
    std::cout << std::endl;   
    std::cout << std::boolalpha << " " << (c1 <= c0);   
    std::cout << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
0 1 2 3  
0 1 2 3  
true  
false  
```  
  
##  <a name="a-nameoperatoreqeqa--operator"></a><a name="operator_eq_eq"></a> operator==  
 Vergleicht `tuple`-Objekte, ob diese gleich sind.  
  
```  
template <class T1, class T2, ..., class TN,  
    class U1, class U2, ..., class UN>  
bool operator==(const tuple<T1, T2, ..., TN>& tpl1,  
    const tuple<U1, U2, ..., UN>& tpl2);
```  
  
### <a name="parameters"></a>Parameter  
 `TN`  
 Der Typ des N-ten Tupelelements.  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion gibt TRUE zurück, wenn `N` 0 ist, andernfalls `get<0>(tpl1) == get<0>(tpl2) && get<1>(tpl1) == get<1>(tpl2) && ... && get<N - 1>(tpl1) == get<N - 1>(tpl2)`.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__tuple__operator_eq.cpp   
// compile with: /EHsc   
#include <tuple>   
#include <iostream>   
  
typedef std::tuple<int, double, int, double> Mytuple;   
int main() {   
    Mytuple c0(0, 1, 2, 3);   
  
// display contents " 0 1 2 3"   
    std::cout << " " << std::get<0>(c0);   
    std::cout << " " << std::get<1>(c0);   
    std::cout << " " << std::get<2>(c0);   
    std::cout << " " << std::get<3>(c0);   
    std::cout << std::endl;   
  
    Mytuple c1 = std::make_tuple(4, 5, 6, 7);   
  
// display contents " 4 5 6 7"   
    std::cout << " " << std::get<0>(c0);   
    std::cout << " " << std::get<1>(c0);   
    std::cout << " " << std::get<2>(c0);   
    std::cout << " " << std::get<3>(c0);   
    std::cout << std::endl;   
  
// display results of comparisons   
    std::cout << std::boolalpha << " " << (c0 == c0);   
    std::cout << std::endl;   
    std::cout << std::boolalpha << " " << (c0 == c1);   
    std::cout << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
0 1 2 3  
0 1 2 3  
true  
false  
```  
  
##  <a name="a-nameoperatorgta--operatorgt"></a><a name="operator_gt_"></a> operator&gt;  
 Vergleicht `tuple`-Objekte, ob diese größer sind.  
  
```  
template <class T1, class T2, ..., class TN,  
    class U1, class U2, ..., class UN>  
bool operator>(const tuple<T1, T2, ..., TN>& tpl1,  
    const tuple<U1, U2, ..., UN>& tpl2);
```  
  
### <a name="parameters"></a>Parameter  
 `TN`  
 Der Typ des N-ten Tupelelements.  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion gibt `tpl2 < tpl1` zurück.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__tuple__operator_gt.cpp   
// compile with: /EHsc   
#include <tuple>   
#include <iostream>   
  
typedef std::tuple<int, double, int, double> Mytuple;   
int main() {   
    Mytuple c0(0, 1, 2, 3);   
  
// display contents " 0 1 2 3"   
    std::cout << " " << std::get<0>(c0);   
    std::cout << " " << std::get<1>(c0);   
    std::cout << " " << std::get<2>(c0);   
    std::cout << " " << std::get<3>(c0);   
    std::cout << std::endl;   
  
    Mytuple c1 = std::make_tuple(4, 5, 6, 7);   
  
// display contents " 4 5 6 7"   
    std::cout << " " << std::get<0>(c0);   
    std::cout << " " << std::get<1>(c0);   
    std::cout << " " << std::get<2>(c0);   
    std::cout << " " << std::get<3>(c0);   
    std::cout << std::endl;   
  
// display results of comparisons   
    std::cout << std::boolalpha << " " << (c0 > c0);   
    std::cout << std::endl;   
    std::cout << std::boolalpha << " " << (c1 > c0);   
    std::cout << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
0 1 2 3  
0 1 2 3  
false  
true  
```  
  
##  <a name="a-nameoperatorgteqa--operatorgt"></a><a name="operator_gt__eq"></a> operator&gt;=  
 Vergleicht `tuple`-Objekte, ob diese größer oder gleich sind.  
  
```  
template <class T1, class T2, ..., class TN,  
    class U1, class U2, ..., class UN>  
bool operator>=(const tuple<T1, T2, ..., TN>& tpl1,  
    const tuple<U1, U2, ..., UN>& tpl2);
```  
  
### <a name="parameters"></a>Parameter  
 `TN`  
 Der Typ des N-ten Tupelelements.  
  
### <a name="remarks"></a>Hinweise  
 Die Funktion gibt `!(tpl1 < tpl2)` zurück.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__tuple__operator_ge.cpp   
// compile with: /EHsc   
#include <tuple>   
#include <iostream>   
  
typedef std::tuple<int, double, int, double> Mytuple;   
int main() {   
    Mytuple c0(0, 1, 2, 3);   
  
// display contents " 0 1 2 3"   
    std::cout << " " << std::get<0>(c0);   
    std::cout << " " << std::get<1>(c0);   
    std::cout << " " << std::get<2>(c0);   
    std::cout << " " << std::get<3>(c0);   
    std::cout << std::endl;   
  
    Mytuple c1 = std::make_tuple(4, 5, 6, 7);   
  
// display contents " 4 5 6 7"   
    std::cout << " " << std::get<0>(c0);   
    std::cout << " " << std::get<1>(c0);   
    std::cout << " " << std::get<2>(c0);   
    std::cout << " " << std::get<3>(c0);   
    std::cout << std::endl;   
  
// display results of comparisons   
    std::cout << std::boolalpha << " " << (c0 >= c0);   
    std::cout << std::endl;   
    std::cout << std::boolalpha << " " << (c0 >= c1);   
    std::cout << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
0 1 2 3  
0 1 2 3  
true  
false  
```  
  
## <a name="see-also"></a>Siehe auch  
 [\<tuple>](../standard-library/tuple.md)


