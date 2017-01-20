---
title: "is_trivially_default_constructible-Klasse"
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
  - "is_trivially_default_constructible"
  - "std.is_trivially_default_constructible"
  - "std::is_trivially_default_constructible"
  - "type_traits/std::is_trivially_default_constructible"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_trivially_default_constructible"
ms.assetid: 653ecd73-909f-4dd8-b95a-d1164d1c2da4
caps.latest.revision: 17
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# is_trivially_default_constructible-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Testet, ob der Typ einen trivialen Standardkonstruktor aufweist.  
  
## Syntax  
  
```  
template<class Ty>  
    struct  is_trivially_default_constructible;  
```  
  
#### Parameter  
 `Ty`  
 Der abzufragende Typ.  
  
## Hinweise  
 Eine Instanz des Typprädikats ist „true“, wenn der `Ty` Typ eine Klasse ist, die einen trivialen Konstruktor aufweist; andernfalls „false“.  
  
 Einen Standardkonstruktor für eine Klasse `Ty` ist trivial, wenn:  
  
-   es ist eine implizit deklarierte Standardkonstruktor  
  
-   die Klasse `Ty` hat keine virtuellen Funktionen  
  
-   die Klasse `Ty` hat keine virtuellen Basen  
  
-   alle direkten Basisklassen der Klasse `Ty` weisen triviale Konstruktoren auf  
  
-   die Klassen aller nicht statischen Datenmember des Klassentyps haben triviale Konstruktoren  
  
-   die Klassen aller nicht statischen Datenmember vom Typarray der Klasse haben triviale Konstruktoren  
  
## Anforderungen  
 **Header:** \<type\_traits\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<type\_traits\>](../standard-library/type-traits.md)