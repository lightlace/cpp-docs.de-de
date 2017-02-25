---
title: "is_compound-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::tr1::is_compound"
  - "is_compound"
  - "std.tr1.is_compound"
  - "std.is_compound"
  - "std::is_compound"
  - "type_traits/std::is_compound"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_compound-Klasse [TR1]"
  - "is_compound"
ms.assetid: bdad1167-cf3f-4f37-8321-62a5df159ead
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# is_compound-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Testet, ob der angegebene Typ nicht grundlegend ist.  
  
## Syntax  
  
```  
template<class Ty>  
    struct is_compound;  
```  
  
#### Parameter  
 `Ty`  
 Der abzufragende Typ.  
  
## Hinweise  
 Eine Instanz des Typs Prädikat enthält `false`, wenn der Typ von `Ty` ein grundlegender Typ ist \(d. h., wenn [is\_fundamental](../standard-library/is-fundamental-class.md)`<``Ty``>` `true` enthält\), andernfalls enthält sie `true`.  Daher enthält das Prädikat `true`, wenn `Ty` ein Arraytyp ist, ein Funktionstyp, ein Zeiger auf `void` oder ein Objekt oder eine Funktion, ein Verweis, eine Klasse, eine Union, eine Enumeration oder ein Zeiger auf ein nicht\-statisches Klassenmember oder eine *cv\-qualified*\-Form eines dieser Elemente.  
  
## Beispiel  
  
```  
// std_tr1__type_traits__is_compound.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_compound<trivial> == " << std::boolalpha   
        << std::is_compound<trivial>::value << std::endl;   
    std::cout << "is_compound<int[]> == " << std::boolalpha   
        << std::is_compound<int[]>::value << std::endl;   
    std::cout << "is_compound<int()> == " << std::boolalpha   
        << std::is_compound<int()>::value << std::endl;   
    std::cout << "is_compound<int&> == " << std::boolalpha   
        << std::is_compound<int&>::value << std::endl;   
    std::cout << "is_compound<void *> == " << std::boolalpha   
        << std::is_compound<void *>::value << std::endl;   
    std::cout << "is_compound<int> == " << std::boolalpha   
        << std::is_compound<int>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **is\_compound\<trivial\> \=\= true**  
**is\_compound\<int\[\]\> \=\= true**  
**is\_compound\<int\(\)\> \=\= true**  
**is\_compound\<int&\> \=\= true**  
**is\_compound\<void \*\> \=\= true**  
**is\_compound\<int\> \=\= false**   
## Anforderungen  
 **Header:** \<type\_traits\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [is\_class\-Klasse](../standard-library/is-class-class.md)