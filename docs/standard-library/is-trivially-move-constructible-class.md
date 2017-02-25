---
title: "Is_trivially_move_constructible-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "is_trivially_move_constructible"
  - "std.is_trivially_move_constructible"
  - "std::is_trivially_move_constructible"
  - "type_traits/std::is_trivially_move_constructible"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_trivially_move_constructible"
ms.assetid: 740bdec7-65e5-47b3-b94f-a2479ceac3ec
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Is_trivially_move_constructible-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Testet, ob der Typ einen trivialen Bewegungskonstruktor aufweist.  
  
## Syntax  
  
```  
template<class Ty>  
    struct is_trivially_move_constructible;  
```  
  
#### Parameter  
 `Ty`  
 Der abzufragende Typ.  
  
## Hinweise  
 Eine Instanz des Typprädikats ist TRUE, wenn der `Ty` Typ eine Klasse ist, die einen trivialen Bewegungskonstruktor aufweist; andernfalls FALSE.  
  
 Ein Bewegungskonstruktor für eine `Ty`\-Klasse ist trivial, wenn:  
  
 Er wird implizit deklariert.  
  
 die Parametertypen entsprechen den einer impliziten Deklaration  
  
 die `Ty`\-Klasse hat keine virtuellen Funktionen  
  
 die `Ty`\-Klasse hat keine virtuellen Basen  
  
 die Klasse verfügt über keine flüchtigen nicht statischen Datenmember  
  
 alle direkten Basisklassen der `Ty`\-Klasse weisen triviale Bewegungskonstruktoren auf  
  
 die Klassen aller nicht statischen Datenmember des Klassentyps haben triviale Bewegungskonstruktoren  
  
 die Klassen aller nicht statischen Datenmember vom Typarray der Klasse haben triviale Bewegungskonstruktoren  
  
## Anforderungen  
 **Header:** \<type\_traits\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<type\_traits\>](../standard-library/type-traits.md)