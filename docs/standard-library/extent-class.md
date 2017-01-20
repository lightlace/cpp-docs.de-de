---
title: "extent-Klasse"
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
  - "std.tr1.extent"
  - "extent"
  - "std::tr1::extent"
  - "std.extent"
  - "std::extent"
  - "type_traits/std::extent"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "extent-Klasse [TR1]"
  - "extent"
ms.assetid: 6d16263d-90b2-4330-9ec7-b59ed898792d
caps.latest.revision: 20
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# extent-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ruft eine Arraydimension ab.  
  
## Syntax  
  
```  
template<class Ty, unsigned I = 0>  
    struct extent;  
```  
  
#### Parameter  
 `Ty`  
 Der abzufragende Typ.  
  
 `I`  
 Das an die Abfrage gebundene Array.  
  
## Hinweise  
 Wenn `Ty` ein Arraytyp mit mindestens `I` Dimensionen ist, enthält die Abfrage die Anzahl der Elemente in der durch `I` angegebener Dimension.  Wenn `Ty` nicht ein Arraytyp oder sein Rang kleiner als `I` ist, oder wenn `I` 0 und `Ty` vom Datentyp „Array mit unbekannter Grenze `U`“ ist, enthält die Abfrage den Wert 0.  
  
## Beispiel  
  
```  
// std_tr1__type_traits__extent.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    std::cout << "extent 0 == "   
        << std::extent<int[5][10]>::value << std::endl;   
    std::cout << "extent 1 == "   
        << std::extent<int[5][10], 1>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
  **extent 0 \=\= 5**  
**extent 1 \=\= 10**   
## Anforderungen  
 **Header:** \<type\_traits\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [remove\_all\_extents\-Klasse](../standard-library/remove-all-extents-class.md)   
 [remove\_extent\-Klasse](../standard-library/remove-extent-class.md)