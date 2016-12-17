---
title: "Is_nothrow_constructible-Klasse"
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
  - "is_nothrow_constructible"
  - "std.is_nothrow_constructible"
  - "std::is_nothrow_constructible"
  - "type_traits/std::is_nothrow_constructible"
dev_langs: 
  - "C++"
  - "c++"
helpviewer_keywords: 
  - "is_nothrow_constructible"
ms.assetid: 8be3f927-283e-4d67-95a5-8bf5dc4e7a3d
caps.latest.revision: 12
caps.handback.revision: "2"
ms.author: "corob"
manager: "ghogen"
---
# Is_nothrow_constructible-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Testet, ob ein Typ erstellt und ist bekannt, auslösen, wenn Sie die angegebenen Argumenttypen verwendet werden.  
  
## Syntax  
  
```  
template <class T, class... Args>  
    struct is_nothrow_constructible;  
```  
  
#### Parameter  
 `T`  
 Der abzufragende Typ.  
  
 `Args`  
 Die Argumenttypen entsprechend in einem Konstruktor einer `T`.  
  
## Hinweise  
 Eine Instanz des Typs Prädikat enthält true, wenn der Typ `T` ist mit den Argumenttypen in erstellbaren `Args`, und der Konstruktor wird vom Compiler aus bezeichnet; andernfalls enthält er false. Typ `T` ist erstellbaren Wenn die Definition der Variablen `T t(std::declval<Args>()...);` wohlgeformt ist. Beide `T` und alle Typen in `Args` vollständige Typen sein `void`, oder Arrays von unbekannten gebunden.  
  
## Anforderungen  
 **Header:** \<type\_traits\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<type\_traits\>](../standard-library/type-traits.md)