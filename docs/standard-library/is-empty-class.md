---
title: "is_empty-Klasse"
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
  - "std::tr1::is_empty"
  - "std.tr1.is_empty"
  - "is_empty"
  - "std.is_empty"
  - "std::is_empty"
  - "type_traits/std::is_empty"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_empty-Klasse [TR1]"
  - "is_empty"
ms.assetid: 44a6fc92-7e55-4fbe-9a24-2a0ce2dccba0
caps.latest.revision: 19
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# is_empty-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Testet, ob „type“ eine leere Klasse ist.  
  
## Syntax  
  
```  
template<class Ty>  
    struct is_empty;  
```  
  
#### Parameter  
 `Ty`  
 Der abzufragende Typ.  
  
## Hinweise  
 Eine Instanz des Typprädikats ist „true“, wenn der `Ty`\-Typ eine leere Klasse ist; andernfalls „false“.  
  
## Beispiel  
  
```  
// std_tr1__type_traits__is_empty.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct empty   
    {   
    };   
  
struct trivial   
    {   
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_empty<trivial> == " << std::boolalpha   
        << std::is_empty<trivial>::value << std::endl;   
    std::cout << "is_empty<empty> == " << std::boolalpha   
        << std::is_empty<empty>::value << std::endl;   
    std::cout << "is_empty<int> == " << std::boolalpha   
        << std::is_empty<int>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
Is_empty < trivial > == false Is_empty < leer > == true Is_empty < Int > == False  
```  
  
## Anforderungen  
 **Header:** \<type\_traits\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<type\_traits\>](../standard-library/type-traits.md)