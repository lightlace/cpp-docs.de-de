---
title: "add_volatile-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::tr1::add_volatile"
  - "add_volatile"
  - "std.tr1.add_volatile"
  - "std.add_volatile"
  - "std::add_volatile"
  - "type_traits/std::add_volatile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "add_volatile-Klasse [TR1]"
  - "add_volatile"
ms.assetid: cde57277-d764-402d-841e-97611ebaab14
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# add_volatile-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wandelt den angegebenen Typ in einen volatile\-Typ um.  
  
## Syntax  
  
```  
template<class Ty>  
    struct add_volatile;  
  
template<class T>  
using add_volatile_t = typename add_volatile<T>::type;  
```  
  
#### Parameter  
 `Ty`  
 Der zu ändernde Typ.  
  
## Hinweise  
 Eine Instanz des Typmodifizierers enthält einen geänderten Typ, der `Ty` ist, wenn `Ty` ein Verweis, eine Funktion oder ein volatile\-qualified\-Typ ist; andernfalls `volatile Ty`.  
  
## Beispiel  
  
```  
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    std::add_volatile_t<int> *p = (volatile int *)0;   
  
    p = p;  // to quiet "unused" warning   
    std::cout << "add_volatile<int> == "   
        << typeid(*p).name() << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **add\_volatile\<int\> \=\= int**   
## Anforderungen  
 **Header:** \<type\_traits\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [remove\_volatile\-Klasse](../standard-library/remove-volatile-class.md)