---
title: "is_rvalue_reference-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.tr1.is_rvalue_reference"
  - "is_rvalue_reference"
  - "std::tr1::is_rvalue_reference"
  - "std.is_rvalue_reference"
  - "std::is_rvalue_reference"
  - "type_traits/std::is_rvalue_reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_rvalue_reference-Klasse[TR1]"
  - "is_rvalue_reference"
ms.assetid: 40a97072-7b5c-4274-9154-298d3dcf064a
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# is_rvalue_reference-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Testet, ob es sich beim Typ um einen „rvalue“\-Verweis handelt.  
  
## Syntax  
  
```  
template<class Ty>  
    struct is_rvalue_reference;  
```  
  
#### Parameter  
 `Ty`  
 Der abzufragende Typ.  
  
## Hinweise  
 Eine Instanz dieses Typenprädikats ist „true“, wenn es sich beim Typ `Ty` um einen [Rvalue\-Verweisdeklarator: &&](../cpp/rvalue-reference-declarator-amp-amp.md)\-Verweis handelt.  
  
## Anforderungen  
 **Header:** \<type\_traits\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [Lvalues und Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md)