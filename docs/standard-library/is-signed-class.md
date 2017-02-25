---
title: "is_signed-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "is_signed"
  - "std.tr1.is_signed"
  - "std::tr1::is_signed"
  - "std.is_signed"
  - "std::is_signed"
  - "type_traits/std::is_signed"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_signed-Klasse [TR1]"
  - "is_signed"
ms.assetid: 20ae44d9-22ad-4fbd-b26a-f18c62689451
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# is_signed-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Testen Sie, ob es sich beim Typ um eine ganze Zahl mit Vorzeichen handelt.  
  
## Syntax  
  
```  
template<class Ty>  
    struct is_signed;  
```  
  
#### Parameter  
 `Ty`  
 Der abzufragende Typ.  
  
## Hinweise  
 Eine Instanz des Typprädikats ist „true“, wenn es sich beim Typ `Ty` um einen Typ für eine ganze Zahl mit Vorzeichen oder um einen `cv-qualified`\-Typ für eine ganze Zahl mit Vorzeichen handelt, andernfalls „false“.  
  
## Beispiel  
  
```  
// std_tr1__type_traits__is_signed.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_signed<trivial> == " << std::boolalpha   
        << std::is_signed<trivial>::value << std::endl;   
    std::cout << "is_signed<int> == " << std::boolalpha   
        << std::is_signed<int>::value << std::endl;   
    std::cout << "is_signed<unsigned int> == " << std::boolalpha   
        << std::is_signed<unsigned int>::value << std::endl;   
    std::cout << "is_signed<float> == " << std::boolalpha   
        << std::is_signed<float>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **is\_signed\<trivial\> \=\= false**  
**is\_signed\<int\> \=\= true**  
**is\_signed\<unsigned int\> \=\= false**  
**is\_signed\<float\> \=\= false**   
## Anforderungen  
 **Header:** \<type\_traits\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [is\_unsigned\-Klasse](../standard-library/is-unsigned-class.md)