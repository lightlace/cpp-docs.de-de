---
title: "Is_trivially_copyable-Klasse | Microsoft Docs"
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
  - "is_trivially_copyable"
  - "std.is_trivially_copyable"
  - "std::is_trivially_copyable"
  - "type_traits/std::is_trivially_copyable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_trivially_copyable"
ms.assetid: 89a53bf8-036c-4108-91e1-fe34adbde8b3
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Is_trivially_copyable-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Testet, ob der Typ ein belanglos kopierbar ist.  
  
## Syntax  
  
```  
template<class T>  
    struct is_trivially_copyable;  
```  
  
#### Parameter  
 `T`  
 Der abzufragende Typ.  
  
## Hinweise  
 Eine Instanz des Typs Prädikat enthält true, wenn der Typ `T` ist ein belanglos kopierbar, andernfalls er false enthält. Belanglos kopierbare Typen haben keine nicht trivialen Kopiervorgänge, verschieben oder Destruktoren. Im Allgemeinen wird ein Kopiervorgang betrachtet trivial, wenn sie eine bitweise Kopie implementiert werden kann. Integrierte Typen und Arrays belanglos kopierbar Typen im Grunde können kopiert werden.  
  
## Anforderungen  
 **Header:** \<type\_traits\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<type\_traits\>](../standard-library/type-traits.md)