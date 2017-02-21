---
title: "aligned_union-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "aligned_union"
  - "std.aligned_union"
  - "std::aligned_union"
  - "type_traits/std::aligned_union"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "aligned_union"
ms.assetid: 9931a44d-3a67-4f29-a0f6-d47a7cf560ac
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# aligned_union-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Bietet groß genug ist und einen entsprechend ausgerichteten einen POD\-Typ um einen union\-Typ und die erforderliche Größe zu speichern.  
  
## Syntax  
  
```  
template <std::size_t Len, class... Types>  
    struct aligned_union;  
  
template <std::size_t Len, class... Types>  
    using aligned_union_t = typename aligned_union<Len, Types...>::type;  
```  
  
#### Parameter  
 `Len`  
 Der Ausrichtungswert für den größten Typ in der Union.  
  
 `Types`  
 Die unterschiedlichen Typen in der zugrunde liegenden Union.  
  
## Hinweise  
 Verwenden Sie die Vorlagenklasse, um die Ausrichtung und Größe, die zum Speichern einer Union im nicht initialisierten Speicher abzurufen. Der Member Typedef `type` ein POD Typnamen für die Speicherung eines beliebigen Typs in aufgeführten geeignet `Types`; die minimale Größe beträgt `Len`. Das statische Element `alignment_value` vom Typ `std::size_t` enthält die strengste Ausrichtung erforderlich, alle Dateitypen in `Types`.  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie Sie `aligned_union` einen ausgerichteter Stapel\-Puffer zum Platzieren einer Union zuweisen.  
  
```  
// std__type_traits__aligned_union.cpp  
#include <iostream>  
#include <type_traits>  
  
union U_type  
{  
    int i;  
    float f;  
    double d;  
    U_type(float e) : f(e) {}  
};  
  
typedef std::aligned_union<16, int, float, double>::type aligned_U_type;  
  
int main()  
{  
    // allocate memory for a U_type aligned on a 16-byte boundary  
    aligned_U_type au;  
    // do placement new in the aligned memory on the stack  
    U_type* u = new (&au) U_type(1.0f);  
    if (nullptr != u)  
    {  
        std::cout << "value of u->i is " << u->i << std::endl;  
        // must clean up placement objects manually!  
        u->~U_type();  
    }  
}  
```  
  
```Output  
-> Wert von i ist 1065353216  
```  
  
## Anforderungen  
 **Header:** \<type\_traits\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [alignment\_of\-Klasse](../standard-library/alignment-of-class.md)