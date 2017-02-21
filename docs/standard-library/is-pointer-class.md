---
title: "is_pointer-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.tr1.is_pointer"
  - "is_pointer"
  - "std::tr1::is_pointer"
  - "std.is_pointer"
  - "std::is_pointer"
  - "type_traits/std::is_pointer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_pointer-Klasse [TR1]"
  - "is_pointer"
ms.assetid: 44e0a403-7241-4e0a-8922-32877bcb9a4c
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# is_pointer-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Testet, ob der Typ ein Zeiger ist.  
  
## Syntax  
  
```  
template<class Ty>  
    struct is_pointer;  
```  
  
#### Parameter  
 `Ty`  
 Der abzufragende Typ.  
  
## Hinweise  
 Eine Instanz des Typprädikats ist „true“, wenn der Typ `Ty` ein Zeiger auf `void`, ein Zeiger auf ein Objekt oder ein Zeiger auf eine Funktion oder ein `cv-qualified`\-Formular von einem davon ist, andernfalls „false“.  Beachten Sie, dass `is_pointer` „false“ ist, wenn `Ty` ein Zeiger auf ein Member oder ein Zeiger auf eine Memberfunktion ist.  
  
## Beispiel  
  
```  
// std_tr1__type_traits__is_pointer.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_pointer<trivial> == " << std::boolalpha   
        << std::is_pointer<trivial>::value << std::endl;   
    std::cout << "is_pointer<int trivial::*> == " << std::boolalpha   
        << std::is_pointer<int trivial::*>::value << std::endl;   
    std::cout << "is_pointer<trivial *> == " << std::boolalpha   
        << std::is_pointer<trivial *>::value << std::endl;   
    std::cout << "is_pointer<int> == " << std::boolalpha   
        << std::is_pointer<int>::value << std::endl;   
    std::cout << "is_pointer<int *> == " << std::boolalpha   
        << std::is_pointer<int *>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **is\_pointer\<trivial\> \=\= false**  
**is\_pointer\<int trivial::\*\> \=\= false**  
**is\_pointer\<trivial \*\> \=\= true**  
**is\_pointer\<int\> \=\= false**  
**is\_pointer\<int \*\> \=\= true**   
## Anforderungen  
 **Header:** \<type\_traits\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [is\_member\_pointer\-Klasse](../standard-library/is-member-pointer-class.md)   
 [is\_reference\-Klasse](../standard-library/is-reference-class.md)