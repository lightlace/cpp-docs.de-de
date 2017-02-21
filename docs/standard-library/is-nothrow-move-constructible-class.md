---
title: "is_nothrow_move_constructible-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "is_nothrow_move_constructible"
  - "std.is_nothrow_move_constructible"
  - "std::is_nothrow_move_constructible"
  - "type_traits/std::is_nothrow_move_constructible"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_nothrow_move_constructible"
ms.assetid: d186d97b-7b89-470a-8d30-993046a83379
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# is_nothrow_move_constructible-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Testet, ob der Typ einen [nothrow](../cpp/nothrow-cpp.md)\-Bewegungskonstruktor aufweist.  
  
## Syntax  
  
```  
template<class Ty>  
    struct is_nothrow_move_constructible;  
```  
  
#### Parameter  
 `Ty`  
 Der abzufragende Typ.  
  
## Hinweise  
 Eine Instanz des Typprädikats ist „true“, wenn der `Ty`\-Typ einen nothrow\-Bewegungskonstruktor aufweist; andernfalls „false“.  
  
## Anforderungen  
 **Header:** \<type\_traits\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<type\_traits\>](../standard-library/type-traits.md)