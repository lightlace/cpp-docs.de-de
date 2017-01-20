---
title: "is_standard_layout-Klasse"
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
  - "std.tr1.is_standard_layout"
  - "std::tr1::is_standard_layout"
  - "is_standard_layout"
  - "std.is_standard_layout"
  - "std::is_standard_layout"
  - "type_traits/std::is_standard_layout"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "is_standard_layout-Klasse[TR1]"
  - "is_standard_layout"
ms.assetid: 15ccf111-f537-45ef-b552-59152a7ba312
caps.latest.revision: 16
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# is_standard_layout-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Testet, ob der Typ ein Standardlayout ist.  
  
## Syntax  
  
```  
template<class Ty>  
    struct is_standard_layout;  
```  
  
#### Parameter  
  
|Parameter|Beschreibung|  
|---------------|------------------|  
|`Ty`|Der abzufragende Typ.|  
  
## Hinweise  
 Eine Instanz dieses Typenprädikats gibt „true“ aus, wenn der Typ `Ty` eine Klasse ist, die über ein Standardlayout der Memberobjekte im Arbeitsspeicher verfügt; ansonsten wird „false“ ausgegeben.  
  
## Anforderungen  
 **Header:** \<type\_traits\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<type\_traits\>](../standard-library/type-traits.md)