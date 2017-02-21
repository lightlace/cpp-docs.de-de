---
title: "Is_trivially_destructible-Klasse | Microsoft Docs"
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
  - "is_trivially_destructible"
  - "std.is_trivially_destructible"
  - "std::is_trivially_destructible"
  - "type_traits/std::is_trivially_destructible"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_trivially_destructible"
ms.assetid: 3f7a787d-2448-40c5-ac51-a228318e02ce
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# Is_trivially_destructible-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Testet, ob der Typ im Grunde zerstörbaren ist.  
  
## Syntax  
  
```  
template <class T>  
    struct is_trivially_destructible;  
```  
  
#### Parameter  
 `T`  
 Der abzufragende Typ.  
  
## Hinweise  
 Eine Instanz des Typs Prädikat enthält true, wenn der Typ `T` ist ein zerstörbaren, und der Destruktor für den Compiler bekannt ist, keine nicht trivialen Vorgänge verwenden. Es enthält, andernfalls false.  
  
## Anforderungen  
 **Header:** \<type\_traits\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<type\_traits\>](../standard-library/type-traits.md)