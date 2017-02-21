---
title: "is_floating_point-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "is_floating_point"
  - "std.tr1.is_floating_point"
  - "std::tr1::is_floating_point"
  - "std.is_floating_point"
  - "std::is_floating_point"
  - "type_traits/std::is_floating_point"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_floating_point-Klasse [TR1]"
  - "is_floating_point"
ms.assetid: 070679c1-115b-4ee4-8ab7-f52e5d9e157f
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# is_floating_point-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Testet, ob es sich beim Typ um ein Gleitkomma handelt.  
  
## Syntax  
  
```  
template<class Ty>  
    struct is_floating_point;  
```  
  
#### Parameter  
 `Ty`  
 Der abzufragende Typ.  
  
## Hinweise  
 Eine Instanz des Typprädikats ist „true“, wenn der `Ty`\-Typ ein Gleitkommatyp oder ein `cv-qualified`\-Formular eines Gleitkommatyps ist; andernfalls „false“.  
  
 Ein Gleitkommatyp ist einer von `float`, `double` oder `long double`.  
  
## Beispiel  
  
```  
// std_tr1__type_traits__is_floating_point.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_floating_point<trivial> == " << std::boolalpha   
        << std::is_floating_point<trivial>::value << std::endl;   
    std::cout << "is_floating_point<int> == " << std::boolalpha   
        << std::is_floating_point<int>::value << std::endl;   
    std::cout << "is_floating_point<float> == " << std::boolalpha   
        << std::is_floating_point<float>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **is\_floating\_point\<trivial\> \=\= false**  
**is\_floating\_point\<int\> \=\= false**  
**is\_floating\_point\<float\> \=\= true**   
## Anforderungen  
 **Header:** \<type\_traits\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [is\_integral\-Klasse](../standard-library/is-integral-class.md)