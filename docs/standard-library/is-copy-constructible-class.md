---
title: "Is_copy_constructible-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "is_copy_constructible"
  - "std.is_copy_constructible"
  - "std::is_copy_constructible"
  - "type_traits/std::is_copy_constructible"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_copy_constructible"
ms.assetid: d8db9d4c-21ed-4884-bead-0b0b562de007
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# Is_copy_constructible-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Testet, ob der Typ einen Kopierkonstruktor aufweist.  
  
## Syntax  
  
```  
template<class Ty>  
    struct is_copy_constructible;  
```  
  
#### Parameter  
 `Ty`  
 Der abzufragende Typ.  
  
## Hinweise  
 Eine Instanz des Typprädikats ist „true“, wenn der `Ty`\-Typ eine Klasse ist, die einen Kopierkonstruktor aufweist; andernfalls „false“.  
  
## Beispiel  
  
```  
#include <type_traits>   
#include <iostream>   
  
struct Copyable  
{  
    int val;  
};  
  
struct NotCopyable  
{  
   NotCopyable(const NotCopyable&) = delete;  
   int val;  
  
};  
  
int main()  
{  
    std::cout << "is_copy_constructible<Copyable> == " << std::boolalpha  
        << std::is_copy_constructible<Copyable>::value << std::endl;  
    std::cout << "is_copy_constructible<NotCopyable> == " << std::boolalpha  
        << std::is_copy_constructible<NotCopyable>::value << std::endl;  
  
    return (0);  
}  
  
```  
  
  **is\_copy\_constructible\<Copyable\> \=\= true**  
**is\_copy\_constructible\<NotCopyable \> \=\= false**   
## Anforderungen  
 **Header:** \<type\_traits\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<type\_traits\>](../standard-library/type-traits.md)