---
title: "is_convertible-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "is_convertible"
  - "std.tr1.is_convertible"
  - "std::tr1::is_convertible"
  - "std.is_convertible"
  - "std::is_convertible"
  - "type_traits/std::is_convertible"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_convertible-Klasse [TR1]"
  - "is_convertible"
ms.assetid: 75614008-1894-42ea-bd57-974399628536
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# is_convertible-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Testet, ob ein Typ in einen anderen konvertiert werden kann.  
  
## Syntax  
  
```  
template<class From, class To>  
    struct is_convertible;  
```  
  
#### Parameter  
 `From`  
 Der Typ, aus dem konvertiert wird.  
  
 `Ty`  
 Der Typ, in den konvertiert werden soll.  
  
## Hinweise  
 Eine Instanz des Typprädikats ist TRUE, wenn der Ausdruck `To to = from;`, wobei `from` ein Objekt vom Typ `From` ist, wohlgeformt ist.  
  
## Beispiel  
  
```  
// std_tr1__type_traits__is_convertible.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_convertible<trivial, int> == " << std::boolalpha   
        << std::is_convertible<trivial, int>::value << std::endl;   
    std::cout << "is_convertible<trivial, trivial> == " << std::boolalpha   
        << std::is_convertible<trivial, trivial>::value << std::endl;   
    std::cout << "is_convertible<char, int> == " << std::boolalpha   
        << std::is_convertible<char, int>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **is\_convertible\<trivial, int\> \=\= false**  
**is\_convertible\<trivial, trivial\> \=\= true**  
**is\_convertible\<char, int\> \=\= true**   
## Anforderungen  
 **Header:** \<type\_traits\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [is\_base\_of\-Klasse](../standard-library/is-base-of-class.md)