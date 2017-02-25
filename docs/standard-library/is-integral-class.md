---
title: "is_integral-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::tr1::is_integral"
  - "std.tr1.is_integral"
  - "is_integral"
  - "std.is_integral"
  - "std::is_integral"
  - "type_traits/std::is_integral"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_integral-Klasse [TR1]"
  - "is_integral"
ms.assetid: fe9279d0-4495-4e88-bf23-153cc6602397
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# is_integral-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Testet, ob der Typ eine Ganzzahl ist.  
  
## Syntax  
  
```  
template<class Ty>  
    struct is_integral;  
```  
  
#### Parameter  
 `Ty`  
 Der abzufragende Typ.  
  
## Hinweise  
 Eine Instanz des Typprädikats ist „true“, wenn der Typ `Ty` ein ganzzahliger Typ oder ein `cv-qualified`\-Formular eines der ganzzahligen Typen ist, andernfalls ist sie „false“.  
  
 Ein ganzzahliger Typ ist entweder `bool`, `char`, `unsigned char`, `signed char`, `wchar_t`, `short`, `unsigned short`, `int`, `unsigned int`, `long` oder `unsigned long`.  Mit Compilern kann der ganzzahlige Typ darüber hinaus `long long`, `unsigned long long`, `__int64` und `unsigned __int64` sein.  
  
## Beispiel  
  
```  
// std_tr1__type_traits__is_integral.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_integral<trivial> == " << std::boolalpha   
        << std::is_integral<trivial>::value << std::endl;   
    std::cout << "is_integral<int> == " << std::boolalpha   
        << std::is_integral<int>::value << std::endl;   
    std::cout << "is_integral<float> == " << std::boolalpha   
        << std::is_integral<float>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **is\_integral\<trivial\> \=\= false**  
**is\_integral\<int\> \=\= true**  
**is\_integral\<float\> \=\= false**   
## Anforderungen  
 **Header:** \<type\_traits\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [is\_enum\-Klasse](../standard-library/is-enum-class.md)   
 [is\_floating\_point\-Klasse](../standard-library/is-floating-point-class.md)