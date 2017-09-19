---
title: '&lt;functional&gt; operators | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- functional/std::operator!=
- functional/std::operator==
dev_langs:
- C++
helpviewer_keywords:
- functional operators
ms.assetid: d4b3c760-f3e2-4b65-bdaa-d42e8dd6f5e1
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: f38d129aab8703b6077b2848d7b71bb0a07e0ea7
ms.contentlocale: de-de
ms.lasthandoff: 04/29/2017

---
# <a name="ltfunctionalgt-operators"></a>&lt;functional&gt;-Operatoren
|||  
|-|-|  
|[operator!=](#op_neq)|[operator==](#op_eq_eq)|  
  
##  <a name="op_eq_eq"></a> operator==  
 Testet, ob das aufrufbare Objekt leer ist.  
  
```  
template <class Fty>  
bool operator==(const function<Fty>& f, null_ptr_type npc);

template <class Fty>  
bool operator==(null_ptr_type npc, const function<Fty>& f);
```  
  
### <a name="parameters"></a>Parameter  
 `Fty`  
 Der zu umschließende Funktionstyp.  
  
 `f`  
 Das Funktionsobjekt  
  
 `npc`  
 Ein Nullzeiger.  
  
### <a name="remarks"></a>Hinweise  
 Beide Operatoren nehmen ein Argument, das einen Verweis auf ein `function`-Objekt darstellt, und ein Argument, das eine Nullzeigerkonstante ist. Beide geben nur dann true zurück, wenn das `function`-Objekt ist leer.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__functional__operator_eq.cpp
// compile with: /EHsc   
#include <functional>   
#include <iostream>   

int neg(int val)
{
    return (-val);
}

int main()
{
    std::function<int(int)> fn0;
    std::cout << std::boolalpha << "empty == "
        << (fn0 == 0) << std::endl;

    std::function<int(int)> fn1(neg);
    std::cout << std::boolalpha << "empty == "
        << (fn1 == 0) << std::endl;

    return (0);
}
  
```  
  
```Output  
empty == true  
empty == false  
```  
  
##  <a name="op_neq"></a> operator!=  
 Testet, ob das aufrufbare Objekt nicht leer ist.  
  
```  
template <class Fty>  
bool operator!=(const function<Fty>& f, null_ptr_type npc);

template <class Fty>  
bool operator!=(null_ptr_type npc, const function<Fty>& f);
```  
  
### <a name="parameters"></a>Parameter  
 `Fty`  
 Der zu umschließende Funktionstyp.  
  
 `f`  
 Das Funktionsobjekt  
  
 `npc`  
 Ein Nullzeiger.  
  
### <a name="remarks"></a>Hinweise  
 Beide Operatoren nehmen ein Argument, das einen Verweis auf ein `function`-Objekt darstellt, und ein Argument, das eine Nullzeigerkonstante ist. Beide geben nur dann TRUE zurück, wenn das `function`-Objekt nicht leer ist.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__functional__operator_ne.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
  
int neg(int val)   
    {   
    return (-val);   
    }   
  
int main()   
    {   
    std::function<int (int)> fn0;   
    std::cout << std::boolalpha << "not empty == "   
        << (fn0 != 0) << std::endl;   
  
    std::function<int (int)> fn1(neg);   
    std::cout << std::boolalpha << "not empty == "   
        << (fn1 != 0) << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
not empty == false  
not empty == true  
```  
  
## <a name="see-also"></a>Siehe auch  
 [\<functional>](../standard-library/functional.md)


