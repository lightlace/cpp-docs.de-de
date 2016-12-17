---
title: "is_base_of-Klasse"
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
  - "std.tr1.is_base_of"
  - "is_base_of"
  - "std::tr1::is_base_of"
  - "std.is_base_of"
  - "std::is_base_of"
  - "type_traits/std::is_base_of"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_base_of-Klasse [TR1]"
  - "is_base_of"
ms.assetid: 436f6213-1d4c-4ffc-a588-fc7c4887dd86
caps.latest.revision: 19
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# is_base_of-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Testet, ob ein Typ die Basis eines anderen ist.  
  
## Syntax  
  
```  
template<class Base, class Derived>  
    struct is_base_of;  
```  
  
#### Parameter  
 `Base`  
 Die Basisklasse zum Testen.  
  
 `Derived`  
 Der abgeleitete Typ zum Testen.  
  
## Hinweise  
 Eine Instanz des Typprädikats ist „true“, wenn der `Base`\-Typ eine Basisklasse des Typs `Derived` ist, andernfalls „false“.  
  
## Beispiel  
  
```  
  
#include <type_traits>   
#include <iostream>   
  
struct base   
    {   
    int val;   
    };   
  
struct derived   
    : public base   
    {   
    };   
  
int main()   
    {   
    std::cout << "is_base_of<base, base> == " << std::boolalpha   
        << std::is_base_of<base, base>::value << std::endl;   
    std::cout << "is_base_of<base, derived> == " << std::boolalpha   
        << std::is_base_of<base, derived>::value << std::endl;   
    std::cout << "is_base_of<derived, base> == " << std::boolalpha   
        << std::is_base_of<derived, base>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **is\_base\_of\<base, base\> \=\= true**  
**is\_base\_of\<base, derived\> \=\= true**  
**is\_base\_of\<derived, base\> \=\= false**   
## Anforderungen  
 **Header:** \<type\_traits\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [is\_convertible\-Klasse](../standard-library/is-convertible-class.md)