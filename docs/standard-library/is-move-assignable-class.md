---
title: "Is_move_assignable-Klasse"
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
  - "is_move_assignable"
  - "std.is_move_assignable"
  - "std::is_move_assignable"
  - "type_traits/std::is_move_assignable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_move_assignable"
ms.assetid: f33137f2-0639-4912-8745-bc0f9fd18d28
caps.latest.revision: 13
caps.handback.revision: "3"
ms.author: "corob"
manager: "ghogen"
---
# Is_move_assignable-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Testet, ob der Typ werden kann verschieben zugewiesen.  
  
## Syntax  
  
```  
template<class T>  
    struct is_move_assignable;  
```  
  
#### Parameter  
 `T`  
 Der abzufragende Typ.  
  
## Hinweise  
 Ein Typ ist verschieben zugeordnet werden, wenn ein Rvalue\-Verweis auf den Typ in einen Verweis auf den Typ zugewiesen werden kann. Die typprädikat entspricht `is_assignable<T&, T&&>`. Verschieben von zuweisbaren Typen gehören sehen skalare Typen und Klassentypen, die entweder vom Compiler generierte benutzerdefinierte oder move\-Zuweisungsoperatoren.  
  
## Anforderungen  
 **Header:** \<type\_traits\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<type\_traits\>](../standard-library/type-traits.md)