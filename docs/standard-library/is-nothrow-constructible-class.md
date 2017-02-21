---
title: "Is_nothrow_constructible-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "is_nothrow_constructible"
  - "std.is_nothrow_constructible"
  - "std::is_nothrow_constructible"
  - "type_traits/std::is_nothrow_constructible"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_nothrow_constructible"
ms.assetid: 8be3f927-283e-4d67-95a5-8bf5dc4e7a3d
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
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