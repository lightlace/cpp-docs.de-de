---
title: add_cv-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- add_cv
- std::add_cv
- type_traits/std::add_cv
dev_langs:
- C++
helpviewer_keywords:
- add_cv class
- add_cv
ms.assetid: a5572c78-a097-45d7-b476-ed4876889dea
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.sourcegitcommit: 8630a5c0b97b85e0dc75e8b470974bb7d223a511
ms.openlocfilehash: efa1d246eb793cb2d0a64347aa062e7ab908e7c4
ms.lasthandoff: 02/24/2017

---
# <a name="addcv-class"></a>add_cv-Klasse
Wandelt einen Typ in einen konstanten volatil-Typ um.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class T>  
struct add_cv;  
 
template <class T>
using add_cv_t = typename add_cv<T>::type;  
```  
  
#### <a name="parameters"></a>Parameter  
*T*  
Der zu ändernde Typ.  
  
## <a name="remarks"></a>Hinweise  
Ein modifizierter `add_cv<T>`-Typ hat einen typedef-Member`type`, der *T*entspricht, das sowohl von [add_volatile](../standard-library/add-volatile-class.md) als auch von [add_const](../standard-library/add-const-class.md) modifiziert wird, es sei denn, *T* hat schon CV-Qualifizierer, ist ein Verweis oder eine Funktion.  
  
Das `add_cv_t<T>`-Hilfsprogramm ist eine Verknüpfung für den Zugriff auf den `add_cv<T>`typedef-Member`type`.
  
## <a name="example"></a>Beispiel  
  
```cpp  
// add_cv.cpp
// compile by using: cl /EHsc /W4 add_cv.cpp
#include <type_traits>   
#include <iostream>   

struct S {
    void f() { 
        std::cout << "invoked non-cv-qualified S.f()" << std::endl; 
    }
    void f() const { 
        std::cout << "invoked const S.f()" << std::endl; 
    }
    void f() volatile { 
        std::cout << "invoked volatile S.f()" << std::endl; 
    }
    void f() const volatile { 
        std::cout << "invoked const volatile S.f()" << std::endl; 
    }
};

template <class T>
void invoke() {
    T t;
    ((T *)&t)->f(); 
}

int main()
{
    invoke<S>();
    invoke<std::add_const<S>::type>();
    invoke<std::add_volatile<S>::type>();
    invoke<std::add_cv<S>::type>();
}  
```  
  
```Output  
invoked non-cv-qualified S.f()
invoked const S.f()
invoked volatile S.f()
invoked const volatile S.f()  
```  
  
## <a name="requirements"></a>Anforderungen  
**Header:** \<type_traits>  
**Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
[<type_traits>](../standard-library/type-traits.md)   
[remove_const-Klasse](../standard-library/remove-const-class.md)   
[remove_volatile-Klasse](../standard-library/remove-volatile-class.md)

