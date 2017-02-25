---
title: "is_bind_expression-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.tr1.is_bind_expression"
  - "is_bind_expression"
  - "std::tr1::is_bind_expression"
  - "functional/std::tr1::is_bind_expression"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_bind_expression-Klasse [TR1]"
ms.assetid: 0715f9e9-2239-4778-a1cf-2c21f49dfd47
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# is_bind_expression-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Tests wenn Typ generiert durch Aufrufen von `bind`.  
  
## Syntax  
  
```  
template<class Ty>  
    struct is_bind_expression {  
    static const bool value;  
    };  
```  
  
## Hinweise  
 Der konstante Wert `value` ist true, wenn der Typ `Ty` ist ein Typ, der durch einen Aufruf von `bind` zurückgegeben wird; andernfalls false.  
  
## Beispiel  
  
```  
// std_tr1__functional__is_bind_expression.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
  
void square(double x)   
    {   
    std::cout << x << "^2 == " << x * x << std::endl;   
    }   
  
template<class Expr>   
    void test_for_bind(const Expr&)   
    {   
    std::cout << std::is_bind_expression<Expr>::value << std::endl;   
    }   
  
int main()   
    {   
    test_for_bind(3.0 * 3.0);   
    test_for_bind(std::bind(square, 3));   
  
    return (0);   
    }  
  
```  
  
  **0**  
**1**   
## Anforderungen  
 **Header:** \<functional\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [bind\-Funktion](../Topic/bind%20Function.md)