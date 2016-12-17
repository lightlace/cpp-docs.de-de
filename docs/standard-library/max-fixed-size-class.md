---
title: "max_fixed_size-Klasse"
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
  - "allocators/stdext::max_fixed_size"
  - "max_fixed_size"
  - "stdext::max_fixed_size"
  - "stdext.max_fixed_size"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "max_fixed_size-Klasse"
ms.assetid: 8c8f4588-37e9-4579-8168-ba3553800914
caps.latest.revision: 18
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# max_fixed_size-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beschreibt ein [maximale Klasse](../standard-library/allocators-header.md)\-Objekt, das ein [freelist](../standard-library/freelist-class.md)\-Objekt einer festen maximale Länge eingeschränkt.  
  
## Syntax  
  
```  
template <std::size_t Max> class max_fixed_size  
```  
  
#### Parameter  
  
|Parameter|**Beschreibung**|  
|---------------|----------------------|  
|`Max`|Die maximale Klasse, die die maximale Anzahl der Elemente, um in `freelist` zu speichern.|  
  
### Konstruktoren  
  
|||  
|-|-|  
|[max\_fixed\_size](../Topic/max_fixed_size::max_fixed_size.md)|Konstruiert ein Objekt vom Typ `max_fixed_size`.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[zugeordnet](../Topic/max_fixed_size::allocated.md)|Inkrementiert die Anzahl von reservierten Speicherblöcken.|  
|[freigegeben](../Topic/max_fixed_size::deallocated.md)|Dekrementiert die Anzahl von reservierten Speicherblöcken.|  
|[full](../Topic/max_fixed_size::full.md)|Gibt einen Wert zurück, der angibt, dass mehr Speicherblöcke zur Liste der freien Blöcke hinzugefügt werden sollen.|  
|[freigegeben](../Topic/max_fixed_size::released.md)|Dekrementiert die Anzahl von Speicherblöcken in der Liste der freien Blöcke.|  
|[gespeichert](../Topic/max_fixed_size::saved.md)|Inkrementiert die Anzahl von Speicherblöcken in der Liste der freien Blöcke.|  
  
## Anforderungen  
 Zuweisungen **Header:** \<\>  
  
 **Namespace:** stdext  
  
## Siehe auch  
 [\<allocators\>](../standard-library/allocators-header.md)