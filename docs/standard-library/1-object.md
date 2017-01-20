---
title: "_1-Objekt"
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
  - "std.tr1._1"
  - "_1"
  - "std::tr1::_1"
  - "functional/std::tr1::_1"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_1-Objekt [TR1]"
ms.assetid: 30c3c480-ff31-4708-94be-7d0d65f243c9
caps.latest.revision: 24
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# _1-Objekt
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Platzhalter für austauschbare Argumente.  
  
## Syntax  
  
```  
namespace placeholders {  
  extern unspecified _1, _2, ... _M  
  } // namespace placeholders (within std)  
```  
  
## Hinweise  
 Bei den Objekte `_1, _2, ... _M` handelt es sich um Platzhalter, die jeweils das erste, zweite, ..., n\-te Argument in einem Funktionsaufruf eines Objekts festlegen, das von [bind\-Funktion](../Topic/bind%20Function.md) zurückgegeben wird.  Sie verwenden `_N`, um anzugeben, wo das n\-te Argument bei Auswertung des Bindungsausdrucks eingefügt werden soll.  
  
 In dieser Implementierung lautet der Wert von `M` 20.  
  
## Beispiel  
  
```cpp  
// std__functional_placeholder.cpp   
// compile with: /EHsc   
#include <functional>   
#include <algorithm>   
#include <iostream>   
  
using namespace std::placeholders;   
  
void square(double x)   
    {   
    std::cout << x << "^2 == " << x * x << std::endl;   
    }   
  
void product(double x, double y)   
    {   
    std::cout << x << "*" << y << " == " << x * y << std::endl;   
    }   
  
int main()   
    {   
    double arg[] = {1, 2, 3};   
  
    std::for_each(&arg[0], &arg[3], square);   
    std::cout << std::endl;   
  
    std::for_each(&arg[0], &arg[3], std::bind(product, _1, 2));   
    std::cout << std::endl;   
  
    std::for_each(&arg[0], &arg[3], std::bind(square, _1));   
  
    return (0);   
    }  
  
```  
  
  **1^2 \=\= 1**  
**2^2 \=\= 4**  
**3^2 \=\= 9**  
**1\*2 \=\= 2**  
**2\*2 \=\= 4**  
**3\*2 \=\= 6**  
**1^2 \=\= 1**  
**2^2 \=\= 4**  
**3^2 \=\= 9**   
## Anforderungen  
 **Header:** \<functional\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [bind\-Funktion](../Topic/bind%20Function.md)   
 [is\_placeholder\-Klasse](../standard-library/is-placeholder-class.md)