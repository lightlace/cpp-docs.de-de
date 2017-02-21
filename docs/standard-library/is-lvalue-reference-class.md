---
title: "is_lvalue_reference-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.tr1.is_lvalue_reference"
  - "std::tr1::is_lvalue_reference"
  - "is_lvalue_reference"
  - "std.is_lvalue_reference"
  - "std::is_lvalue_reference"
  - "type_traits/std::is_lvalue_reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_lvalue_reference-Klasse[TR1]"
  - "is_lvalue_reference"
ms.assetid: 7f11896b-935c-4de1-9c87-9d0127f904e2
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# is_lvalue_reference-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Testet, ob es sich beim Typ um einen lvalue\-Verweis handelt.  
  
## Syntax  
  
```  
template<class Ty>  
    struct is_lvalue_reference;  
```  
  
#### Parameter  
 `Ty`  
 Der abzufragende Typ.  
  
## Hinweise  
 Eine Instanz dieses Typprädikats ist TRUE, wenn der `Ty`\-Typ ein Verweis auf ein Objekt oder eine Funktion ist; andernfalls FALSE.  Beachten Sie, dass es sich beim `Ty`\-Typ möglicherweise nicht um einen rvalue\-Verweis handelt.  Weitere Informationen zu rvalues finden Sie unter [Rvalue\-Verweisdeklarator: &&](../cpp/rvalue-reference-declarator-amp-amp.md).  
  
## Anforderungen  
 **Header:** \<type\_traits\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [Lvalues und Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md)