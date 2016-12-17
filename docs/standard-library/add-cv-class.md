---
title: "add_cv-Klasse"
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
  - "std.tr1.add_cv"
  - "add_cv"
  - "std::tr1::add_cv"
  - "std.add_cv"
  - "std::add_cv"
  - "type_traits/std::add_cv"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "add_cv-Klasse [TR1]"
  - "add_cv"
ms.assetid: a5572c78-a097-45d7-b476-ed4876889dea
caps.latest.revision: 20
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# add_cv-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wandelt einen Typ in einen konstanten\/permanenten Typ um.  
  
## Syntax  
  
```  
template<class Ty>  
    struct add_cv;  
  
template<class T>  
using add_cv_t = typename add_cv<T>::type;  
```  
  
#### Parameter  
 `Ty`  
 Der zu ändernde Typ.  
  
## Hinweise  
 Eine Instanz des Typmodifizierers enthält den geänderten Typ [add\_volatile\-Klasse](../standard-library/add-volatile-class.md)`<` [add\_const\-Klasse](../standard-library/add-const-class.md)`<Ty> >`.  
  
## Beispiel  
  
```  
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    std::add_cv_t<int> *p = (const volatile int *)0;   
  
    p = p;  // to quiet "unused" warning   
    std::cout << "add_cv<int> == "   
        << typeid(*p).name() << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **add\_cv\_t\<int\> \=\= int**   
## Anforderungen  
 **Header:** \<type\_traits\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [remove\_const\-Klasse](../standard-library/remove-const-class.md)   
 [remove\_volatile\-Klasse](../standard-library/remove-volatile-class.md)