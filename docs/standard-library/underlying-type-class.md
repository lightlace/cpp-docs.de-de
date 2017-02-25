---
title: "Underlying_type-Klasse | Microsoft Docs"
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
  - "underlying_type"
  - "std.underlying_type"
  - "std::underlying_type"
  - "type_traits/std::underlying_type"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "underlying_type"
ms.assetid: 691ddce3-2677-4480-bd35-d933fab85d3e
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# Underlying_type-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Erstellt den zugrunde liegenden ganzzahligen Typ für einen Enumerationstyp.  
  
## Syntax  
  
```  
template <class T>  
    struct underlying_type;  
```  
  
#### Parameter  
 `T`  
 Der zu ändernde Typ.  
  
## Hinweise  
 Der `type` Member\-Typdefinition der Vorlagenklasse Namen den zugrunde liegende ganzzahligen Typ `T`, bei `T` ein Enumerationstyp ist, es gibt keine Element\-Typdefinition `type`.  
  
## Anforderungen  
 **Header:** \<type\_traits\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<type\_traits\>](../standard-library/type-traits.md)