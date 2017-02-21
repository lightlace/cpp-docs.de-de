---
title: "Is_literal_type-Klasse | Microsoft Docs"
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
  - "is_literal_type"
  - "std.is_literal_type"
  - "std::is_literal_type"
  - "type_traits/std::is_literal_type"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_literal_type"
ms.assetid: a03a4ebb-ee66-48d6-91bb-41cf72b2401f
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Is_literal_type-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Testet, ob ein Typ kann, als verwendet werden ein `constexpr` Variable oder erstellt werden, verwendet, oder zurückgegeben werden von `constexpr` Funktionen.  
  
## Syntax  
  
```  
template <class T>  
    struct is_literal_type;  
```  
  
#### Parameter  
 `T`  
 Der abzufragende Typ.  
  
## Hinweise  
 Eine Instanz des Typs Prädikat enthält true, wenn der Typ `T` ist ein *Literaltyp*, andernfalls enthält er false. Ein literal ist entweder `void`, einen skalaren Typ, einen Verweistyp, ein Array des Typs Zeichenfolgenliteral oder ein literal\-Klasse. Ein literal\-Klasse ist ein Klassentyp, der einen trivialen Destruktor aufweist, wird entweder ein aggregierter Typ oder verfügt über mindestens ein nicht\-Move, nicht\-Kopie `constexpr` Konstruktor und aller zugehörigen Basisklassen und nicht statische Datenmember sind nicht flüchtigen Literaltypen. Während der Typ eines Literals immer ein literal ist, das Konzept der ein literal enthält alle Elemente, die der Compiler als auswerten kann eine `constexpr` zum Zeitpunkt der Kompilierung.  
  
## Anforderungen  
 **Header:** \<type\_traits\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<type\_traits\>](../standard-library/type-traits.md)