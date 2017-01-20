---
title: "is_abstract-Klasse"
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
  - "std.tr1.is_abstract"
  - "std::tr1::is_abstract"
  - "is_abstract"
  - "std.is_abstract"
  - "std::is_abstract"
  - "type_traits/std::is_abstract"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_abstract-Klasse [TR1]"
  - "is_abstract"
ms.assetid: 8867f660-3434-404c-ba90-c26607a5e0d2
caps.latest.revision: 19
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# is_abstract-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Testet, ob „type“ eine abstrakte Klasse ist.  
  
## Syntax  
  
```  
template<class Ty>  
    struct is_abstract;  
```  
  
#### Parameter  
 `Ty`  
 Der abzufragende Typ.  
  
## Hinweise  
 Eine Instanz des Typprädikats ist TRUE, wenn der `Ty`\-Typ eine Klasse ist, die mindestens eine reine virtuelle Funktion aufweist; andernfalls FALSE.  
  
## Beispiel  
  
```  
// std_tr1__type_traits__is_abstract.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
struct abstract   
    {   
    virtual int val() = 0;   
    };   
  
int main()   
    {   
    std::cout << "is_abstract<trivial> == " << std::boolalpha   
        << std::is_abstract<trivial>::value << std::endl;   
    std::cout << "is_abstract<abstract> == " << std::boolalpha   
        << std::is_abstract<abstract>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
Is_abstract < trivial > == false Is_abstract < Abstract > == True  
```  
  
## Anforderungen  
 **Header:** \<type\_traits\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [is\_polymorphic\-Klasse](../standard-library/is-polymorphic-class.md)