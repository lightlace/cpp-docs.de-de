---
title: "is_scalar-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.tr1.is_scalar"
  - "std::tr1::is_scalar"
  - "is_scalar"
  - "std.is_scalar"
  - "std::is_scalar"
  - "type_traits/std::is_scalar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_scalar-Klasse [TR1]"
  - "is_scalar"
ms.assetid: a0cdfc9a-f27e-4808-890f-6ed7942db60c
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# is_scalar-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Testet, ob der Typ skalar ist.  
  
## Syntax  
  
```  
template<class Ty>  
    struct is_scalar;  
```  
  
#### Parameter  
 `Ty`  
 Der abzufragende Typ.  
  
## Hinweise  
 Eine Instanz des Typprädikats ergibt TRUE, wenn der Typ `Ty` ein ganzzahliger Typ, ein Gleitkommawert, ein Enumerationstyp, ein Zeigertyp oder ein Zeiger auf einen Membertyp oder ein `cv-qualified`\-Formular von diesen ist; andernfalls FALSE.  
  
## Beispiel  
  
```  
// std_tr1__type_traits__is_scalar.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_scalar<trivial> == " << std::boolalpha   
        << std::is_scalar<trivial>::value << std::endl;   
    std::cout << "is_scalar<trivial *> == " << std::boolalpha   
        << std::is_scalar<trivial *>::value << std::endl;   
    std::cout << "is_scalar<int> == " << std::boolalpha   
        << std::is_scalar<int>::value << std::endl;   
    std::cout << "is_scalar<float> == " << std::boolalpha   
        << std::is_scalar<float>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **is\_scalar\<trivial\> \=\= false**  
**is\_scalar\<trivial \*\> \=\= true**  
**is\_scalar\<int\> \=\= true**  
**is\_scalar\<float\> \=\= true**   
## Anforderungen  
 **Header:** \<type\_traits\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [is\_compound\-Klasse](../standard-library/is-compound-class.md)