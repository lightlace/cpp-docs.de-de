---
title: "is_placeholder-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "is_placeholder"
  - "std.tr1.is_placeholder"
  - "functional/std::tr1::is_placeholder"
  - "std::tr1::is_placeholder"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_placeholder-Klasse [TR1]"
ms.assetid: 2b21a792-96d1-4bb8-b911-0db796510835
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# is_placeholder-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Testet, ob Typ ein Platzhalter ist.  
  
## Syntax  
  
```  
template<class Ty>  
    struct is_placeholder {  
    static const int value;  
    };  
```  
  
## Hinweise  
 Der konstante Wert `value` ist 0, wenn der Typ `Ty` kein Platzhalter ist; Andernfalls ist der Wert die Position des Funktionsaufrufarguments, dass er gebunden wird.  Sie verwenden ihn, um den Wert `N` für den N\-ten Platzhalter `_N` zu bestimmen.  
  
## Beispiel  
  
```  
// std_tr1__functional__is_placeholder.cpp   
// compile with: /EHsc   
#include <functional>   
#include <iostream>   
  
using namespace std::placeholders;   
  
template<class Expr>   
    void test_for_placeholder(const Expr&)   
    {   
    std::cout << std::is_placeholder<Expr>::value << std::endl;   
    }   
  
int main()   
    {   
    test_for_placeholder(3.0);   
    test_for_placeholder(_3);   
  
    return (0);   
    }  
  
```  
  
  **0**  
**3**   
## Anforderungen  
 **Header:** \<functional\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\_1\-Objekt](../standard-library/1-object.md)