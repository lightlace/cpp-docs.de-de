---
title: "Is_trivially_constructible-Klasse"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "is_trivially_constructible"
  - "std.is_trivially_constructible"
  - "std::is_trivially_constructible"
  - "type_traits/std::is_trivially_constructible"
dev_langs: 
  - "C++"
  - "c++"
helpviewer_keywords: 
  - "is_trivially_constructible"
ms.assetid: 3fa918c1-e66f-4d0e-a11b-be1fb2c02e7b
caps.latest.revision: 12
caps.handback.revision: "2"
ms.author: "corob"
manager: "ghogen"
---
# Is_trivially_constructible-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Testet, ob ein Typ im Grunde erstellbaren bei die angegebenen Argumenttypen verwendet werden.  
  
## Syntax  
  
```  
template <class T, class... Args>  
    struct is_trivially_constructible;  
```  
  
#### Parameter  
 `T`  
 Der abzufragende Typ.  
  
 `Args`  
 Die Argumenttypen entsprechend in einem Konstruktor einer `T`.  
  
## Hinweise  
 Eine Instanz des Typs Prädikat enthält true, wenn der Typ `T` ist im Grunde erstellbaren mit den Argumenttypen in `Args`, andernfalls enthält er false. Typ `T` ist im Grunde erstellbaren Wenn die Definition der Variablen `T t(std::declval<Args>()...);` wohlgeformt ist, und ist bekannt, dass keine nicht trivialen Vorgänge aufrufen. Beide `T` und alle Typen in `Args` vollständige Typen sein `void`, oder Arrays von unbekannten gebunden.  
  
## Anforderungen  
 **Header:** \<type\_traits\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<type\_traits\>](../standard-library/type-traits.md)