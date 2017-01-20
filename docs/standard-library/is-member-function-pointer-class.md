---
title: "is_member_function_pointer-Klasse"
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
  - "std.tr1.is_member_function_pointer"
  - "std::tr1::is_member_function_pointer"
  - "is_member_function_pointer"
  - "std.is_member_function_pointer"
  - "std::is_member_function_pointer"
  - "type_traits/std::is_member_function_pointer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_member_function_pointer-Klasse [TR1]"
  - "is_member_function_pointer"
ms.assetid: 02e372c4-2714-40f2-b376-2e10ca91c8ed
caps.latest.revision: 19
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# is_member_function_pointer-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Testet, ob der Typ ein Zeiger zu einer Memberfunktion ist.  
  
## Syntax  
  
```  
template<class Ty>  
    struct is_member_function_pointer;  
```  
  
#### Parameter  
 `Ty`  
 Der abzufragende Typ.  
  
## Hinweise  
 Eine Instanz des Typprädikats enthält „true“, wenn der Typ `Ty` ein Zeiger auf eine Memberfunktion oder ein `cv-qualified`\-Zeiger auf eine Memberfunktion ist, andernfalls enthält es „false“.  
  
## Beispiel  
  
```  
// std_tr1__type_traits__is_member_function_pointer.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
struct functional   
    {   
    int f();   
    };   
  
int main()   
    {   
    std::cout << "is_member_function_pointer<trivial *> == "   
        << std::boolalpha   
        << std::is_member_function_pointer<trivial *>::value   
        << std::endl;   
    std::cout << "is_member_function_pointer<int trivial::*> == "   
        << std::boolalpha   
        << std::is_member_function_pointer<int trivial::*>::value   
        << std::endl;   
    std::cout << "is_member_function_pointer<int (functional::*)()> == "   
        << std::boolalpha   
        << std::is_member_function_pointer<int (functional::*)()>::value   
        << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **is\_member\_function\_pointer\<trivial \*\> \=\= false**  
**is\_member\_function\_pointer\<int trivial::\*\> \=\= false**  
**is\_member\_function\_pointer\<int \(functional::\*\)\(\)\> \=\= true**   
## Anforderungen  
 **Header:** \<type\_traits\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [is\_member\_pointer\-Klasse](../standard-library/is-member-pointer-class.md)