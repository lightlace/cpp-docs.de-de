---
title: "rank-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::tr1::rank"
  - "std.tr1.rank"
  - "rank"
  - "std.rank"
  - "std::rank"
  - "type_traits/std::rank"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rank-Klasse [TR1]"
  - "rank"
ms.assetid: bc9f1b8f-800f-46ca-b6f4-d8579ed5406a
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# rank-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ruft die Anzahl der Arraydimensionen ab.  
  
## Syntax  
  
```  
template<class Ty>  
    struct rank;  
```  
  
#### Parameter  
 `Ty`  
 Der abzufragende Typ.  
  
## Hinweise  
 Die Typabfrage enthält den Wert der Anzahl der Dimensionen des Arraytyps `Ty` oder 0, wenn `Ty` kein Arraytyp ist.  
  
## Beispiel  
  
```  
// std_tr1__type_traits__rank.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    std::cout << "rank<int> == "   
        << std::rank<int>::value << std::endl;   
    std::cout << "rank<int[5]> == "   
        << std::rank<int[5]>::value << std::endl;   
    std::cout << "rank<int[5][10]> == "   
        << std::rank<int[5][10]>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
Rang < Int > == Rang < Int [5] > 0 == 1 Rank < Int [5] [10] > == 2  
```  
  
## Anforderungen  
 **Header:** \<type\_traits\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [extent\-Klasse](../standard-library/extent-class.md)