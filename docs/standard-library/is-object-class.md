---
title: "is_object-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "is_object"
  - "std.tr1.is_object"
  - "std::tr1::is_object"
  - "std.is_object"
  - "std::is_object"
  - "type_traits/std::is_object"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_object-Klasse [TR1]"
  - "is_object"
ms.assetid: b452ceea-5676-488f-925b-ab881126c387
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# is_object-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prüft, ob der Typ ein Objekttyp ist.  
  
## Syntax  
  
```  
template<class Ty>  
    struct is_object;  
```  
  
#### Parameter  
 `Ty`  
 Der abzufragende Typ.  
  
## Hinweise  
 Eine Instanz des Typs Prädikats ist „false“, wenn der Typ `Ty` ein Verweistyp, ein Funktionstyp, ungültig oder eine `cv-qualified`\-Form davon ist, andernfalls „true“.  
  
## Beispiel  
  
```  
// std_tr1__type_traits__is_object.cpp   
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
    std::cout << "is_object<trivial> == " << std::boolalpha   
        << std::is_object<trivial>::value << std::endl;   
    std::cout << "is_object<functional> == " << std::boolalpha   
        << std::is_object<functional>::value << std::endl;   
    std::cout << "is_object<trivial&> == " << std::boolalpha   
        << std::is_object<trivial&>::value << std::endl;   
    std::cout << "is_object<float()> == " << std::boolalpha   
        << std::is_object<float()>::value << std::endl;   
    std::cout << "is_object<void> == " << std::boolalpha   
        << std::is_object<void>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **is\_object\<trivial\> \=\= true**  
**is\_object\<functional\> \=\= true**  
**is\_object\<trivial&\> \=\= false**  
**is\_object\<float\(\)\> \=\= false**  
**is\_object\<void\> \=\= false**   
## Anforderungen  
 **Header:** \<type\_traits\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [is\_function\-Klasse](../standard-library/is-function-class.md)