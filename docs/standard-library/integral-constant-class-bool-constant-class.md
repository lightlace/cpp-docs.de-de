---
title: integral_constant Class, bool_constant-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- integral_constant
- std::integral_constant
- type_traits/std::integral_constant
- XTR1COMMON/std::integral_constant
- bool_constant
- std::bool_constant
- type_traits/std::bool_constant
- XTR1COMMON/std::bool_constant
dev_langs:
- C++
helpviewer_keywords:
- integral_constant class
- integral_constant
- bool_constant
ms.assetid: 11c002c6-4d31-4042-9341-f2543f43e108
caps.latest.revision: 23
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
ms.openlocfilehash: 6c71c3571e19c57b13c827bbb84e347e3ff26b01
ms.lasthandoff: 02/24/2017

---
# <a name="integralconstant-class-boolconstant-class"></a>integral_constant Class, bool_constant-Klasse
Wandelt einen Typ und einen Wert in eine Ganzzahlkonstante um.  
  
## <a name="syntax"></a>Syntax  
  
```
template<class T, T v>
struct integral_constant {  
   static constexpr T value = v;  
   typedef T value_type;  
   typedef integral_constant<T, v> type;  
   constexpr operator value_type() const noexcept;  
   constexpr value_type operator()() const noexcept;  
   };  
```
  
### <a name="parameters"></a>Parameter  
*T*  
Der Typ der Konstante.  
  
*v*  
Der Wert der Konstante.  
  
## <a name="remarks"></a>Hinweise  
Die `integral_constant`-Vorlagenklasse, sofern mit einem integralen Typ *T* und einem Wert *v* dieses Typs definiert, stellt ein Objekt dar, das eine Konstante dieses integralen Typs mit dem angegebenen Wert hält. Beim Member `type` handelt es sich um ein Alias des erstellten Vorlagenspezialisierungstypen, und der Member `value` hält den Wert *v*, der beim Erstellen der Spezialisierung verwendet wurde.  
  
Die Vorlagenklasse `bool_constant` ist eine explizite Teilspezialisierung von `integral_constant`, die `bool` als *T*-Argument verwendet.  
  
## <a name="example"></a>Beispiel  
  
```cpp  
// std__type_traits__integral_constant.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    std::cout << "integral_constant<int, 5> == "   
        << std::integral_constant<int, 5>::value << std::endl;   
    std::cout << "integral_constant<bool, false> == " << std::boolalpha   
        << std::integral_constant<bool, false>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
integral_constant<int, 5> == 5  
integral_constant<bool, false> == false  
```  
  
## <a name="requirements"></a>Anforderungen  

**Header:** \<type_traits>
  
**Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [<type_traits>](../standard-library/type-traits.md)   
 [false_type-Typdefinition](../standard-library/type-traits-typedefs.md#false_type_typedef)   
 [true_type-Typdefinition](../standard-library/type-traits-typedefs.md#true_type_typedef)


