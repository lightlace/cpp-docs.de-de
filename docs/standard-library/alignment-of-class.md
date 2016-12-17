---
title: "alignment_of-Klasse"
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
  - "std.tr1.alignment_of"
  - "std::tr1::alignment_of"
  - "alignment_of"
  - "std.alignment_of"
  - "std::alignment_of"
  - "type_traits/std::alignment_of"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "alignment_of-Klasse [TR1]"
  - "alignment_of"
ms.assetid: 4141c59a-f94e-41c4-93fd-9ea578b27387
caps.latest.revision: 22
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# alignment_of-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ruft die Ausrichtung des angegebenen Typs ab.  Diese Struktur wird in Bezug auf [alignof](../cpp/alignof-and-alignas-cpp.md) implementiert.  Verwenden Sie `alignof` direkt, wenn Sie einen Ausrichtungswert einfach abfragen müssen.  Verwenden Sie „alignment\_of“, wenn Sie eine integrale Konstante benötigen, beispielsweise beim Versenden eines Kennzeichens.  
  
## Syntax  
  
```  
template<class Ty>  
    struct alignment_of;  
```  
  
#### Parameter  
 `Ty`  
 Der abzufragende Typ.  
  
## Hinweise  
 Die Typabfrage hält den Wert der Ausrichtung des Typs `Ty`.  
  
## Anforderungen  
 **Header:** \<type\_traits\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [aligned\_storage\-Klasse](../standard-library/aligned-storage-class.md)