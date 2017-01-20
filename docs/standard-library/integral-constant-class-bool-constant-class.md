---
title: "Integral_constant-Klasse, Bool_constant-Klasse"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "std.tr1.integral_constant"
  - "integral_constant"
  - "std::tr1::integral_constant"
  - "std.integral_constant"
  - "std::integral_constant"
  - "type_traits/std::integral_constant"
  - "std.bool_constant"
  - "std::bool_constant"
  - "type_traits/std::bool_constant"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "integral_constant-Klasse [TR1]"
  - "integral_constant"
  - "bool_constant"
ms.assetid: 11c002c6-4d31-4042-9341-f2543f43e108
caps.latest.revision: 23
caps.handback.revision: "15"
ms.author: "corob"
manager: "ghogen"
---
# Integral_constant-Klasse, Bool_constant-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wandelt eine ganzzahlige Konstante einen Typ und Wert.  
  
## Syntax  
  
```  
template <class T, T v>  
    struct integral_constant {  
        static constexpr T value = v;  
        typedef T value_type;  
        typedef integral_constant<T, v> type;  
        constexpr operator value_type() const noexcept { return (value); }  
        constexpr value_type operator()() const noexcept { return (value); }  
    };  
  
template <bool v>  
    using bool_constant = integral_constant<bool, v>;  
  
```  
  
#### Parameter  
 `T`  
 Der Typ der Konstante.  
  
 `v`  
 Der Wert der Konstante.  
  
## Hinweise  
 Die `integral_constant` Vorlagenklasse, wenn mit einem ganzzahligen Typ spezialisiert `T` und den Wert `v` dieses Typs darstellt, ein Objekt, eine Konstante des ganzzahligen Typs mit dem angegebenen Wert enthält. Das Element mit dem Namen `type` ist ein Alias für die Spezialisierung generierte Vorlage, und die `value` enthält den Wert `v` verwendet, um die Spezialisierung erstellen.  
  
 Die `bool_constant` Vorlagenklasse ist ein expliziter partielle Spezialisierung von `integral_constant` verwendet `bool` als die `T` Argument.  
  
## Beispiel  
  
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
Integral_constant < Int, 5 > == 5 Integral_constant < Bool, false > == False  
```  
  
## Anforderungen  
 **Header:** \<type\_traits\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [false\_type\-Typdefinition](../Topic/false_type%20Typedef.md)   
 [true\_type\-Typdefinition](../Topic/true_type%20Typedef.md)