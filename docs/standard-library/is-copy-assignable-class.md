---
title: "Is_copy_assignable-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "is_copy_assignable"
  - "std.is_copy_assignable"
  - "std::is_copy_assignable"
  - "type_traits/std::is_copy_assignable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_copy_assignable"
ms.assetid: 3ae6bca1-85fb-4829-9ee9-0183b081ff50
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Is_copy_assignable-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Testet, ob der Typ durch Zuweisung kopiert werden kann.  
  
## Syntax  
  
```  
template<class Ty>  
    struct is_copy_assignable;  
```  
  
#### Parameter  
 `Ty`  
 Der abzufragende Typ.  
  
## Hinweise  
 Eine Instanz des Typprädikats ist „true“, wenn der `Ty`\-Typ eine Klasse ist, die einen Kopierzuweisungsoperator aufweist; andernfalls „false“.  Gleichbedeutend mit is\_assignable\<Ty&, const Ty&\>.  
  
## Anforderungen  
 **Header:** \<type\_traits\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<type\_traits\>](../standard-library/type-traits.md)