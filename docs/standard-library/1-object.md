---
title: _1-Objekt | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _1
- std::_1
- functional/std::_1
dev_langs:
- C++
helpviewer_keywords:
- _1 object
ms.assetid: 30c3c480-ff31-4708-94be-7d0d65f243c9
caps.latest.revision: 24
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: f293f074f2b8e2334dc70fbebba8e6f4c17efecc
ms.openlocfilehash: e90ee470e3cf990240f3c586c23fe8fd3d487f3d
ms.lasthandoff: 02/24/2017

---
# <a name="1-object"></a>_1-Objekt
Platzhalter für austauschbare Argumente.  
  
## <a name="syntax"></a>Syntax  
  
```  
namespace placeholders {  
    extern unspecified _1,
    _2, ... _M  
 } // namespace placeholders (within std)  
```  
  
## <a name="remarks"></a>Hinweise  
 Bei den Objekten `_1, _2, ... _M` handelt es sich um Platzhalter, die jeweils das erste, zweite, ..., n-te Argument in einem Funktionsaufruf eines Objekts festlegen, das von [bind-Funktion](../standard-library/functional-functions.md#bind_function) zurückgegeben wird. Sie verwenden `_N`, um anzugeben, wo das n-te Argument bei Auswertung des Bindungsausdrucks eingefügt werden soll.  
  
 In dieser Implementierung lautet der Wert von `M` 20.  
  
## <a name="example"></a>Beispiel  
  
```cpp  
// std__functional_placeholder.cpp   
// compile with: /EHsc   
#include <functional>   
#include <algorithm>   
#include <iostream>   
  
using namespace std::placeholders;   
  
void square(double x)   
    {   
    std::cout << x << "^2 == " << x * x << std::endl;   
    }   
  
void product(double x, double y)   
    {   
    std::cout << x << "*" << y << " == " << x * y << std::endl;   
    }   
  
int main()   
    {   
    double arg[] = {1, 2, 3};   
  
    std::for_each(&arg[0], &arg[3], square);   
    std::cout << std::endl;   
  
    std::for_each(&arg[0], &arg[3], std::bind(product, _1, 2));   
    std::cout << std::endl;   
  
    std::for_each(&arg[0], &arg[3], std::bind(square, _1));   
  
    return (0);   
    }  
  
```  
  
```Output  
1^2 == 1  
2^2 == 4  
3^2 == 9  
  
1*2 == 2  
2*2 == 4  
3*2 == 6  
  
1^2 == 1  
2^2 == 4  
3^2 == 9  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<functional>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [bind-Funktion](../standard-library/functional-functions.md#bind_function)   
 [is_placeholder-Klasse](../standard-library/is-placeholder-class.md)

