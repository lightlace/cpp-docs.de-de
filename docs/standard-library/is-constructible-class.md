---
title: "Is_constructible-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "is_constructible"
  - "std.is_constructible"
  - "std::is_constructible"
  - "type_traits/std::is_constructible"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_constructible"
ms.assetid: 7cdec5ff-73cf-4f78-a9db-ced2e9c0fd7f
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
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