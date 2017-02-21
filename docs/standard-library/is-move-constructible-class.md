---
title: "Is_move_constructible-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "is_move_constructible"
  - "std.is_move_constructible"
  - "std::is_move_constructible"
  - "type_traits/std::is_move_constructible"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_move_constructible"
ms.assetid: becdf076-7419-488d-a335-78adf2478b9b
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Is_move_constructible-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Testet, ob der Typ einen Verschiebungskonstruktor aufweist.  
  
## Syntax  
  
```  
template <class T>  
    struct is_move_constructible;  
```  
  
#### Parameter  
 T  
 Der auszuwertende Typ.  
  
## Hinweise  
 Ein typprädikat, das ergibt true, wenn den Typ `T` mithilfe eines Verschiebevorgangs konstruiert werden kann. Dieses Prädikat entspricht `is_constructible<T, T&&>`.  
  
## Anforderungen  
 **Header:** \<type\_traits\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<type\_traits\>](../standard-library/type-traits.md)