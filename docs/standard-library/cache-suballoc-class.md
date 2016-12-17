---
title: "cache_suballoc-Klasse"
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
  - "stdext.cache_suballoc"
  - "allocators/stdext::cache_suballoc"
  - "stdext::cache_suballoc"
  - "cache_suballoc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cache_suballoc-Klasse"
ms.assetid: 9ea9c5e9-1dcc-45d0-b3a7-a56a93d88898
caps.latest.revision: 17
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# cache_suballoc-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Definiert eine [Blockieren Zuweisung](../standard-library/allocators-header.md) die zuweist und freigibt Speicherblöcke mit einer einzelnen Größe.  
  
## Syntax  
  
```  
template <std::size_t Sz, size_t Nelts = 20> class cache_suballoc  
```  
  
#### Parameter  
  
|Parameter|Beschreibung|  
|---------------|------------------|  
|`Sz`|Die Anzahl der Elemente im Array zugewiesen werden.|  
  
## Hinweise  
 Die Vorlagenklasse Cache\_suballoc speichert aufgehoben, wenn die Speicherblöcke in der Liste mit unbegrenzte Länge mit `freelist<sizeof(Type), max_unbounded>`, und suballocates Speicherblöcke aus einem größeren Segment zugeordnet `operator new` Wenn die freie Liste leer ist.  
  
 Jeder Block enthält `Sz * Nelts` Bytes Speicherkapazität und die Daten, die `operator new` und `operator delete` erfordern. Zugeordnete Blöcke werden nicht freigegeben.  
  
### Konstruktoren  
  
|||  
|-|-|  
|[cache\_suballoc](../Topic/cache_suballoc::cache_suballoc.md)|Konstruiert ein Objekt vom Typ `cache_suballoc`.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[allocate](../Topic/cache_suballoc::allocate.md)|Belegt einen Speicherblock.|  
|[Aufheben der Zuordnung](../Topic/cache_suballoc::deallocate.md)|Gibt eine angegebene Anzahl von Objekten im Speicher frei, beginnend an einer angegebenen Position.|  
  
## Anforderungen  
 **Header:** \<allocators\>  
  
 **Namespace:** stdext  
  
## Siehe auch  
 [\<allocators\>](../standard-library/allocators-header.md)