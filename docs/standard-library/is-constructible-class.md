---
title: "Is_constructible-Klasse"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "is_constructible"
  - "std.is_constructible"
  - "std::is_constructible"
  - "type_traits/std::is_constructible"
dev_langs: 
  - "C++"
  - "c++"
helpviewer_keywords: 
  - "is_constructible"
ms.assetid: 7cdec5ff-73cf-4f78-a9db-ced2e9c0fd7f
caps.latest.revision: 14
caps.handback.revision: "4"
ms.author: "corob"
manager: "ghogen"
---
# Is_constructible-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Testet, ob ein Typ erstellt ist, wenn die angegebenen Argumenttypen verwendet werden.  
  
## Syntax  
  
```  
template <class T, class... Args>  
    struct is_constructible;  
```  
  
#### Parameter  
 `T`  
 Der abzufragende Typ.  
  
 `Args`  
 Die Argumenttypen entsprechend in einem Konstruktor einer `T`.  
  
## Hinweise  
 Eine Instanz des Typs Prädikat enthält true, wenn der Typ `T` ist mit den Argumenttypen in erstellbaren `Args`, andernfalls enthält er false. Typ `T` ist erstellbaren Wenn die Definition der Variablen `T t(std::declval<Args>()...);` wohlgeformt ist. Beide `T` und alle Typen in `Args` vollständige Typen sein `void`, oder Arrays von unbekannten gebunden.  
  
## Anforderungen  
 **Header:** \<type\_traits\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<type\_traits\>](../standard-library/type-traits.md)