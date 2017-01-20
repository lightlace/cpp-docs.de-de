---
title: "remove_volatile-Klasse"
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
  - "std::tr1::remove_volatile"
  - "std.tr1.remove_volatile"
  - "remove_volatile"
  - "std.remove_volatile"
  - "std::remove_volatile"
  - "type_traits/std::remove_volatile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "remove_volatile-Klasse [TR1]"
  - "remove_volatile"
ms.assetid: 8b87e2c2-a581-4eb3-8691-c5603910d61d
caps.latest.revision: 20
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# remove_volatile-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wandelt einen Typ in einen permanenten Typ um.  
  
## Syntax  
  
```  
template<class T>  
    struct remove_volatile;  
  
template<class T>  
  using remove_volatile_t = typename remove_volatile<T>::type;  
```  
  
#### Parameter  
 `T`  
 Der zu ändernde Typ.  
  
## Hinweise  
 Eine Instanz von `remove_volatile<T>` enthält einen geänderten Typ, der `T1` ist, wenn `T` das Format `volatile T1` hat; andernfalls `T`.  
  
## Beispiel  
  
```  
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    int *p = (std::remove_volatile_t<volatile int> *)0;   
  
    p = p;  // to quiet "unused" warning   
    std::cout << " remove_volatile_t<volatile int> == "   
        << typeid(*p).name() << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **remove\_volatile\_t\<volatile int\> \=\= int**   
## Anforderungen  
 **Header:** \<type\_traits\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [add\_volatile\-Klasse](../standard-library/add-volatile-class.md)