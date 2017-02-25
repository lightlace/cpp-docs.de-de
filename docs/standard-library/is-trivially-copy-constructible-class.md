---
title: "is_trivially_copy_constructible-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
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
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
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