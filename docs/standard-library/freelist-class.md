---
title: "freelist-Klasse"
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
  - "stdext::freelist"
  - "freelist"
  - "stdext.freelist"
  - "allocators/stdext::freelist"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "freelist-Klasse"
ms.assetid: 8ad7e35c-4c80-4479-8ede-1a2497b06d71
caps.latest.revision: 17
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# freelist-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Verwaltet eine Liste von Speicherblöcken.  
  
## Syntax  
  
```  
template <std::size_t Sz, class Max> class freelist  
    : public Max  
```  
  
#### Parameter  
  
|Parameter|**Beschreibung**|  
|---------------|----------------------|  
|`Sz`|Die Anzahl der Elemente im Array zugeordnet werden.|  
|`Max`|Die maximale Klasse, die die maximale Anzahl der in der Liste der freien Blöcke zu speichernden Elemente, darstellt.  Die maximale Klasse kann [max\_none](../standard-library/max-none-class.md), [max\_unbounded](../standard-library/max-unbounded-class.md), [max\_fixed\_size](../standard-library/max-fixed-size-class.md) oder [max\_variable\_size](../standard-library/max-variable-size-class.md) sein.|  
  
## Hinweise  
 Diese Klasse verwaltet eine Liste von Speicherblöcken Größe `Sz` mit der maximalen Länge der Liste, die die maximale Klasse bestimmt wird, die an `Max` übergeben wird.  
  
### Konstruktoren  
  
|||  
|-|-|  
|[freelist](../Topic/freelist::freelist.md)|Konstruiert ein Objekt vom Typ `freelist`.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[pop](../Topic/freelist::pop.md)|Entfernt den Speicherblock ersten von der Liste der freien Blöcke.|  
|[push](../Topic/freelist::push.md)|Fügt ein Speicherblock der Liste hinzu.|  
  
## Anforderungen  
 Zuweisungen **Header:** \<\>  
  
 **Namespace:** stdext  
  
## Siehe auch  
 [\<allocators\>](../standard-library/allocators-header.md)