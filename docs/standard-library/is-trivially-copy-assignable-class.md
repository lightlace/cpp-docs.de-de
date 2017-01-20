---
title: "is_trivially_copy_assignable"
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
  - "is_trivially_copy_assignable"
  - "std.is_trivially_copy_assignable"
  - "std::is_trivially_copy_assignable"
  - "type_traits/std::is_trivially_copy_assignable"
dev_langs: 
  - "C++"
ms.assetid: 7410133e-f367-493f-92a7-e34e3ec5e879
caps.latest.revision: 12
caps.handback.revision: "1"
ms.author: "corob"
manager: "ghogen"
---
# is_trivially_copy_assignable
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Testet, ob der Typ einen trivialen Kopierzuweisungsoperator aufweist.  
  
## Syntax  
  
```  
template<class Ty>  
    struct is_trivially_copy_constructible;  
```  
  
#### Parameter  
 `Ty`  
 Der abzufragende Typ.  
  
## Hinweise  
 Eine Instanz des Typprädikats ist TRUE, wenn der `Ty`\-Typ eine Klasse ist, die einen Kopierzuweisungsoperator aufweist; andernfalls FALSE.  
  
 Ein Zuweisungskonstruktor für eine `Ty`\-Klasse ist trivial, wenn Folgendes erfüllt wird:  
  
 er wird impliziert bereitgestellt  
  
 die `Ty`\-Klasse hat keine virtuellen Funktionen  
  
 die `Ty`\-Klasse hat keine virtuellen Basen  
  
 die Klassen aller nicht statischen Datenmember des Klassentyps haben triviale Zuweisungsoperatoren  
  
 die Klassen aller nicht statischen Datenmember des Typarrays der Klasse haben triviale Zuweisungsoperatoren  
  
## Anforderungen  
 **Header:** \<type\_traits\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<type\_traits\>](../standard-library/type-traits.md)