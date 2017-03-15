---
title: '&lt;array&gt;-Funktionen | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std::array::get
- array/std::array::get
ms.assetid: e0700a33-a833-4655-8735-16e71175efc8
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: f293f074f2b8e2334dc70fbebba8e6f4c17efecc
ms.openlocfilehash: 38c1f1a593c43ff0fb8434bfcade4dab9740945d
ms.lasthandoff: 02/24/2017

---
# <a name="ltarraygt-functions"></a>&lt;array&gt;-Funktionen
Der Header \<array> enthält zwei Nicht-Memberfunktionen, `get` und `swap`, die `array`-Objekte verarbeiten.  
  
|||  
|-|-|  
|[get](#get_function)|[swap](#swap_function)|  
  
##  <a name="a-namegetfunctiona--get"></a><a name="get_function"></a> get  
Gibt einen Verweis auf das angegebene Element des Arrays zurück.  
  
```  
template <int Index, class T, size_t N>  
constexpr T& get(array<T, N>& arr) noexcept;  
 
template <int Index, class T, size_t N>  
constexpr const T& get(const array<T, N>& arr) noexcept;  
 
template <int Index, class T, size_t N>  
constexpr T&& get(array<T, N>&& arr) noexcept;  
```  
  
### <a name="parameters"></a>Parameter  
 `Index`  
 Der Offset des Elements.  
  
 `T`  
 Der Typ eines Elements.  
  
 `N`  
 Die Anzahl der Elemente im Array.  
  
 `arr`  
 Das Array, aus dem die Auswahl erfolgt.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
#include <array>   
#include <iostream>   
  
using namespace std;  
  
typedef array<int, 4> MyArray;  
  
int main()  
{  
    MyArray c0 { 0, 1, 2, 3 };  
  
    // display contents " 0 1 2 3"   
    for (const auto& e : c0)  
    {  
        cout << " " << e;  
    }  
    cout << endl;  
  
    // display odd elements " 1 3"   
    cout << " " << get<1>(c0);  
    cout << " " << get<3>(c0) << endl;  
}  
```  
  
```Output  
0 1 2 3  
1 3  
```  
  
##  <a name="a-nameswapfunctiona--swap"></a><a name="swap_function"></a> swap  
Eine Nicht-Member-Vorlagenspezialisierung von `std::swap`, die zwei `array`-Objekte miteinander tauschen kann.  
  
```  
template <class Ty, std::size_t N>  
void swap(array<Ty, N>& left, array<Ty, N>& right);
```  
  
### <a name="parameters"></a>Parameter  
 `Ty`  
 Der Typ eines Elements.  
  
 `N`  
 Die Größe des Arrays.  
  
 `left`  
 Das erste auszutauschende Array.  
  
 `right`  
 Das zweite auszutauschende Array.  
  
### <a name="remarks"></a>Hinweise  
 Die Vorlagenfunktion führt `left.swap(right)` aus.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__array__swap.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;
int main()
{
    Myarray c0 = { 0, 1, 2, 3 };

    // display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

    Myarray c1 = { 4, 5, 6, 7 };
    c0.swap(c1);

    // display swapped contents " 4 5 6 7"   
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

    swap(c0, c1);

    // display swapped contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

    return (0);
}
```  
  
```Output  
0 1 2 3  
4 5 6 7  
0 1 2 3  
```  
  
## <a name="see-also"></a>Siehe auch  
 [\<array>](../standard-library/array.md)


