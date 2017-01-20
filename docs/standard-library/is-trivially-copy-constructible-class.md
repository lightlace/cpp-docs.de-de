---
title: "is_trivially_copy_constructible-Klasse"
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
  - "is_trivially_copy_constructible"
  - "std.is_trivially_copy_constructible"
  - "std::is_trivially_copy_constructible"
  - "type_traits/std::is_trivially_copy_constructible"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_trivially_copy_constructible"
ms.assetid: 4274cef5-afdd-4f2d-bc83-7562e7944ddf
caps.latest.revision: 24
caps.handback.revision: "14"
ms.author: "corob"
manager: "ghogen"
---
# is_trivially_copy_constructible-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Testet, ob der Typ einen trivialen kopienkonstruktor aufweist.  
  
## Syntax  
  
```  
template<class T>  
    struct is_trivially_copy_constructible;  
```  
  
#### Parameter  
 `T`  
 Der abzufragende Typ.  
  
## Hinweise  
 Eine Instanz des Typprädikats ist „true“, wenn der `T` Typ eine Klasse ist, die einen trivialen Kopierkonstruktor aufweist; andernfalls „false“.  
  
 Für eine Klasse einen Kopierkonstruktor `T` ist trivial, wenn er implizit deklariert ist, die Klasse `T` verfügt über keine virtuellen Funktionen oder virtuellen Basen, die direkte Grundlagen der Klasse `T` trivial Kopierkonstruktoren verfügen, die Klassen alle nicht statischen Datenmember des Klassentyps trivial Kopierkonstruktoren und Klassen alle nicht statischen Datenmember vom Typarray der Klasse trivial Kopierkonstruktoren.  
  
## Anforderungen  
 **Header:** \<type\_traits\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<type\_traits\>](../standard-library/type-traits.md)