---
title: '&lt;tuple&gt;-Funktionen | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- tuple/std::get
- tuple/std::make_tuple
- tuple/std::tie
dev_langs: C++
ms.assetid: bc6be38f-5258-4c14-b81b-63caa335fd44
caps.latest.revision: "13"
manager: ghogen
helpviewer_keywords:
- std::get [C++]
- std::make_tuple [C++]
- std::tie [C++]
- std::get [C++]
- std::make_tuple [C++]
- std::tie [C++]
ms.openlocfilehash: a81820c920339bb3e006af6df11bda855d4d33ca
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="lttuplegt-functions"></a>&lt;tuple&gt;-Funktionen
||||  
|-|-|-|  
|[get](#get)|[make_tuple](#make_tuple)|[tie](#tie)|  
  
##  <a name="get"></a> get
 Ruft ein Element aus einem `tuple` -Objekt nach dem Index oder (in C++14) nach dem Typ ab.  
  
```  
// by index:
// get reference to Index element of tuple
template <size_t Index, class... Types>  
   constexpr tuple_element_t<Index, tuple<Types...>>& get(tuple<Types...>& Tuple) noexcept;

// get const reference to Index element of tuple
template <size_t Index, class... Types>  
   constexpr const tuple_element_t<Index, tuple<Types...>>& get(const tuple<Types...>& Tuple) noexcept;

// get rvalue reference to Index element of tuple
template <size_t Index, class... Types>  
   constexpr tuple_element_t<Index, tuple<Types...>>&& get(tuple<Types...>&& Tuple) noexcept;

// (C++14) by type:
// get reference to T element of tuple
template <class T, class... Types>  
   constexpr T& get(tuple<Types...>& Tuple) noexcept;

// get const reference to T element of tuple
template <class T, class... Types>  
   constexpr const T& get(const tuple<Types...>& Tuple) noexcept;

// get rvalue reference to T element of tuple
template <class T, class... Types>  
   constexpr T&& get(tuple<Types...>&& Tuple) noexcept;  
```  
  
### <a name="parameters"></a>Parameter  
 `Index`  
 Der Index des abzurufenden Elements.  
  
 `Types`  
 Die Sequenz der im Tupel deklarierten Typen in der Deklarationsreihenfolge.  
  
 `T`  
 Der Typ des abzurufenden Elements.  
  
 `Tuple`  
 std::tuple mit einer beliebigen Anzahl von Elementen.  
  
### <a name="remarks"></a>Hinweise  
 Die Vorlagenfunktionen geben einen Verweis auf den Wert am Index `Index`oder vom Typ `T` im `tuple` -Objekt zurück.  
  
 Das Aufrufen von `get<T>(Tuple)` führt zu einem Compilerfehler, wenn das Tupel mehr oder weniger als ein Element vom Typ T enthält.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
#include <tuple>   
#include <iostream>   
#include <string>  
  
using namespace std;  
  
int main() {  
    tuple<int, double, string> tup(0, 1.42, "Call me Tuple");  
  
    // get elements by index  
    cout << " " << get<0>(tup);  
    cout << " " << get<1>(tup);  
    cout << " " << get<2>(tup) << endl;  
  
    // get elements by type  
    cout << " " << get<int>(tup);  
    cout << " " << get<double>(tup);  
    cout << " " << get<string>(tup) << endl;    
}  
```  
  
```Output  
0 1.42 Call me Tuple  
0 1.42 Call me Tuple  
```  
  
##  <a name="make_tuple"></a>make_tuple
 Erstellt eine `tuple` aus Elementwerten.  
  
```  
template <class T1, class T2, ..., class TN>  
   tuple<V1, V2, ..., VN> make_tuple(const T1& t1, const T2& t2, ..., const TN& tN);
```  
  
### <a name="parameters"></a>Parameter  
 `TN`  
 Der Typ des Parameters der Nth-Funktion.  
  
 `tN`  
 Der Wert des Parameters der Nth-Funktion.  
  
### <a name="remarks"></a>Hinweise  
 Die Vorlagenfunktion gibt `tuple<V1, V2, ..., VN>(t1, t2, ..., tN)` zurück, wobei jeder `Vi`-Typ `X&` ist, wenn der entsprechende `Ti`-Typ `cv` `reference_wrapper<X>` ist, andernfalls ist er `Ti`.  
  
 Ein Vorteil von `make_tuple` ist, dass die Typen von Objekten, die gespeichert werden, automatisch vom Compiler bestimmt werden und nicht explizit angegeben werden müssen. Verwenden Sie keine expliziten Vorlagenargumente wie `make_tuple<int, int>(1, 2)`, wenn Sie `make_tuple` verwenden, da dies unnötig detailliert ist und zu komplexen rvalue-Verweisproblemen führt, die möglicherweise Kompilierungsfehler verursachen.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__tuple__make_tuple.cpp   
// compile by using: /EHsc   
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
  
    c0 = std::make_tuple(4, 5, 6, 7);   
  
// display contents " 4 5 6 7"   
    std::cout << " " << std::get<0>(c0);   
    std::cout << " " << std::get<1>(c0);   
    std::cout << " " << std::get<2>(c0);   
    std::cout << " " << std::get<3>(c0);   
    std::cout << std::endl;   
  
    return (0);   
}  
```  
  
```  
 0 1 2 3
 4 5 6 7  
```  
  
##  <a name="tie"></a>Tie
 Erstellt eine `tuple` aus Elementverweisen.  
  
```  
template <class T1, class T2, ..., class TN>  
tuple<T1&, T2&, ..., TN&> tie(T1& t1, T2& t2, ..., TN& tN);
```  
  
### <a name="parameters"></a>Parameter  
 `TN`  
 Der Basistyp des N-ten Tupelelements.  
  
### <a name="remarks"></a>Hinweise  
 Die Vorlagenfunktion gibt `tuple<T1&, T2&, ..., TN&>(t1, t2, ..., tN)` zurück.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__tuple__tie.cpp   
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
  
    int v4 = 4;   
    double v5 = 5;   
    int v6 = 6;   
    double v7 = 7;   
    std::tie(v4, v5, v6, v7) = c0;   
  
// display contents " 0 1 2 3"   
    std::cout << " " << v4;   
    std::cout << " " << v5;   
    std::cout << " " << v6;   
    std::cout << " " << v7;   
    std::cout << std::endl;   
  
    return (0);   
}    
```  
  
```Output  
0 1 2 3  
0 1 2 3  
```  
  
## <a name="see-also"></a>Siehe auch  
 [\<tuple>](../standard-library/tuple.md)

