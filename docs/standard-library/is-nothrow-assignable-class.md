---
title: "Is_nothrow_assignable-Klasse | Microsoft Docs"
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
  - "is_nothrow_assignable"
  - "std.is_nothrow_assignable"
  - "std::is_nothrow_assignable"
  - "type_traits/std::is_nothrow_assignable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_nothrow_assignable"
ms.assetid: aa3aca92-308b-4b1d-b3f3-c54216c48fe7
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# Is_nothrow_assignable-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Testet, ob der Wert `From` Typ zugewiesen werden kann `To` Typ und die Zuweisung aus bezeichnet wird.  
  
## Syntax  
  
```  
template <class To, class From>   
    struct is_nothrow_assignable;  
```  
  
#### Parameter  
 Beschreibung  
 Der Typ des Objekts, das die Zuweisung empfängt.  
  
 Von  
 Der Typ des Objekts, das den Wert bereitstellt.  
  
## Hinweise  
 Der Ausdruck `declval<To>() = declval<From>()` muss wohlgeformt sein und muss aus dem Compiler bekannt sein. Beide `From` und `To` muss vollständige Typen `void`, oder Arrays von unbekannten gebunden.  
  
## Anforderungen  
 **Header:** \<type\_traits\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<type\_traits\>](../standard-library/type-traits.md)