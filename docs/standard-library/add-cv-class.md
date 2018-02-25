---
title: add_cv-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- type_traits/std::add_cv
dev_langs:
- C++
helpviewer_keywords:
- add_cv class
- add_cv
ms.assetid: a5572c78-a097-45d7-b476-ed4876889dea
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 24709bf7b14d398f55540dd65633785e536280e1
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
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
