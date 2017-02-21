---
title: "add_const-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::tr1::add_const"
  - "add_const"
  - "std.tr1.add_const"
  - "std.add_const"
  - "std::add_const"
  - "type_traits/std::add_const"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "add_const-Klasse [TR1]"
  - "add_const"
ms.assetid: 1262a1eb-8c9c-4dd6-9f43-88ba280182f1
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# add_const-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Erstellt den „const“\-Typ aus „type“.  
  
## Syntax  
  
```  
template<class Ty>  
    struct add_const;  
```  
  
#### Parameter  
 `Ty`  
 Der zu ändernde Typ.  
  
## Hinweise  
 Eine Instanz des Typmodifizierers enthält einen geänderten Typ, der `Ty` ist, wenn `Ty` ein Verweis, eine Funktion oder ein konstant qualifizierter Typ ist; andernfalls `const Ty`.  
  
## Beispiel  
  
```  
// std_tr1__type_traits__add_const.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    std::add_const<int>::type *p = (const int *)0;   
  
    p = p;  // to quiet "unused" warning   
    std::cout << "add_const<int> == "   
        << typeid(*p).name() << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **add\_const\<int\> \=\= int**   
## Anforderungen  
 **Header:** \<type\_traits\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [remove\_const\-Klasse](../standard-library/remove-const-class.md)