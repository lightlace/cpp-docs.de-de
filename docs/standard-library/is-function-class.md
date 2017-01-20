---
title: "is_function-Klasse"
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
  - "std::tr1::is_function"
  - "std.tr1.is_function"
  - "is_function"
  - "std.is_function"
  - "std::is_function"
  - "type_traits/std::is_function"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_function-Klasse [TR1]"
  - "is_function"
ms.assetid: e5c0dbcd-829b-415f-853f-8c5be47c5040
caps.latest.revision: 19
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# is_function-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Testet, ob der Typ ein Funktionstyp ist.  
  
## Syntax  
  
```  
template<class Ty>  
    struct is_function;  
```  
  
#### Parameter  
 `Ty`  
 Der abzufragende Typ.  
  
## Hinweise  
 Eine Instanz des Typprädikats ist "true", wenn der `Ty`\-Typ ein Funktionstyp ist; andernfalls "false".  
  
## Beispiel  
  
```  
// std_tr1__type_traits__is_function.cpp   
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
    std::cout << "is_function<trivial> == " << std::boolalpha   
        << std::is_function<trivial>::value << std::endl;   
    std::cout << "is_function<functional> == " << std::boolalpha   
        << std::is_function<functional>::value << std::endl;   
    std::cout << "is_function<float()> == " << std::boolalpha   
        << std::is_function<float()>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **is\_function\<trivial\> \=\= false**  
**is\_function\<functional\> \=\= false**  
**is\_function\<float\(\)\> \=\= true**   
## Anforderungen  
 **Header:** \<type\_traits\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [is\_object\-Klasse](../standard-library/is-object-class.md)