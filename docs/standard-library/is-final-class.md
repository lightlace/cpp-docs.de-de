---
title: "Is_final-Klasse"
ms.custom: na
ms.date: "12/03/2016"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "is_final"
  - "std.is_final"
  - "std::is_final"
  - "type_traits/std::is_final"
dev_langs: 
  - "C++"
  - "c++"
helpviewer_keywords: 
  - "is_final"
ms.assetid: 9dbad82f-6685-4909-94e8-98e4a93994b9
caps.latest.revision: 12
caps.handback.revision: "2"
ms.author: "corob"
manager: "ghogen"
---
# Is_final-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Testet, ob der Typ ein Klassentyp gekennzeichnet ist `final`.  
  
## Syntax  
  
```  
template<class T>  
    struct is_final;  
```  
  
#### Parameter  
 `T`  
 Der abzufragende Typ.  
  
## Hinweise  
 Eine Instanz des Typs Prädikat enthält true, wenn der Typ `T` ist ein Klassentyp markiert `final`, andernfalls enthält er false. Wenn `T` ist ein Klassentyp, es muss ein vollständiger Typ sein.  
  
## Anforderungen  
 **Header:** \<type\_traits\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [final\-Bezeichner](../cpp/final-specifier.md)