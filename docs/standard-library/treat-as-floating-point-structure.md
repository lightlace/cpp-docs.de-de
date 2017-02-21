---
title: "treat_as_floating_point-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "chrono/std::chrono::treat_as_floating_point"
dev_langs: 
  - "C++"
ms.assetid: d0a2161c-bbb2-4924-8961-7568d5ad5434
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# treat_as_floating_point-Struktur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt an, ob `Rep` als Gleitkommatyp behandelt werden kann.  
  
## Syntax  
  
```  
template<class Rep>  
struct treat_as_floating_point : is_floating_point<Rep>;  
```  
  
## Hinweise  
 `Rep` kann als Gleitkommatyp behandelt werden, wenn die Spezialisierung `treat_as_floating_point<Rep>` von [true\_type](../Topic/true_type%20Typedef.md) abgeleitet wird.  Die Vorlagenklasse kann für einen benutzerdefinierten Typ abgeleitet werden.  
  
## Anforderungen  
 **Header:** chrono  
  
 **Namespace:** std::chrono  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono\>](../standard-library/chrono.md)