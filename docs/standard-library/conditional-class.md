---
title: "conditional-Klasse"
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
  - "std::tr1::conditional"
  - "std.tr1.conditional"
  - "conditional"
  - "std.conditional"
  - "std::conditional"
  - "type_traits/std::conditional"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "conditional-Klasse[TR1]"
  - "conditional"
ms.assetid: ece9f539-fb28-4e26-a79f-3264bc984493
caps.latest.revision: 22
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# conditional-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wählt einen von zwei Typen, abhängig von der angegebenen Bedingung.  
  
## Syntax  
  
```  
template <bool B, class T1, class T2>  
    struct conditional;  
  
template <bool _Test, class _T1, class _T2>  
    using conditional_t = typename conditional<_Test, _T1, _T2>::type;  
```  
  
#### Parameter  
 `B`  
 Der Wert, der den ausgewählten Typ bestimmt.  
  
 `T1`  
 Das Typergebnis, wenn B „true“ ist.  
  
 `T2`  
 Das Typergebnis, wenn B „false“ ist.  
  
## Hinweise  
 Die Vorlagenmember\-Typdefinition \(typedef\) `conditional<B, T1, T2>::type` wird mit `T1` ausgewertet, wenn `B` mit `true` ausgewertet wird, und wird mit `T2` ausgewertet, wenn `B` mit `false` ausgewertet wird.  
  
## Anforderungen  
 **Header:** \<type\_traits\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<type\_traits\>](../standard-library/type-traits.md)