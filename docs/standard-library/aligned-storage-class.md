---
title: "aligned_storage-Klasse"
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
  - "aligned_storage"
  - "std::tr1::aligned_storage"
  - "std.tr1.aligned_storage"
  - "std.aligned_storage"
  - "std::aligned_storage"
  - "type_traits/std::aligned_storage"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "aligned_storage-Klasse [TR1]"
  - "aligned_storage"
ms.assetid: f255e345-1f05-4d07-81e4-017f420839fb
caps.latest.revision: 23
caps.handback.revision: "15"
ms.author: "corob"
manager: "ghogen"
---
# aligned_storage-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Erstellt einen entsprechend ausgerichteten Typ.  
  
## Syntax  
  
```  
template<std::size_t Len, std::size_t Align>  
    struct aligned_storage;  
  
template <std::size_t Len, std::size_t Align = alignment_of<max_align_t>::value>  
    using aligned_storage_t = typename aligned_storage<Len, Align>::type;  
```  
  
#### Parameter  
 `Len`  
 Die Objektgröße.  
  
 `Align`  
 Die Objektausrichtung.  
  
## Hinweise  
 Die Vorlage Member Typedef `type` ist ein Synonym für ein POD\-Typ mit Ausrichtung `Align` und Größe `Len`.`Align` muss gleich sein `alignment_of<T>::value` für einen Typ `T`, oder die standardmäßige Ausrichtung.  
  
## Beispiel  
  
```  
#include <type_traits>   
#include <iostream>   
  
typedef std::aligned_storage<sizeof (int),   
    std::alignment_of<double>::value>::type New_type;   
int main()   
    {   
    std::cout << "alignment_of<int> == "   
        << std::alignment_of<int>::value << std::endl;   
    std::cout << "aligned to double == "   
        << std::alignment_of<New_type>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
Alignment_of < Int > == 4 ausgerichtet, doppelte == 8  
```  
  
## Anforderungen  
 **Header:** \<type\_traits\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [\<type\_traits\>](../standard-library/type-traits.md)   
 [alignment\_of\-Klasse](../standard-library/alignment-of-class.md)