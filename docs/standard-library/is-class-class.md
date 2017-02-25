---
title: "is_class-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "is_class"
  - "std::tr1::is_class"
  - "std.tr1.is_class"
  - "std.is_class"
  - "std::is_class"
  - "type_traits/std::is_class"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_class-Klasse [TR1]"
  - "is_class"
ms.assetid: 96fc34a3-a81b-4ec6-b7fb-baafde1a0f4e
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# is_class-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Testet, ob der Typ eine Klasse ist.  
  
## Syntax  
  
```  
template<class Ty>  
    struct is_class;  
```  
  
#### Parameter  
 `Ty`  
 Der abzufragende Typ.  
  
## Hinweise  
 Eine Instanz des Typs Prädikats ist „true“, wenn der Typ `Ty` ein Typ ist, der als `class` oder `struct` oder `cv-qualified`\-Formular eines der Typen definiert ist; andernfalls ist sie „false“.  
  
## Beispiel  
  
```  
// std_tr1__type_traits__is_class.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_class<trivial> == " << std::boolalpha   
        << std::is_class<trivial>::value << std::endl;   
    std::cout << "is_class<int> == " << std::boolalpha   
        << std::is_class<int>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **is\_class\<trivial\> \=\= true**  
**is\_class\<int\> \=\= false**   
## Anforderungen  
 **Header:** \<type\_traits\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [is\_compound\-Klasse](../standard-library/is-compound-class.md)   
 [is\_union\-Klasse](../standard-library/is-union-class.md)