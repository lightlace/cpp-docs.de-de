---
title: "rts_alloc-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "stdext::rts_alloc"
  - "allocators/stdext::rts_alloc"
  - "rts_alloc"
  - "stdext.rts_alloc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "rts_alloc-Klasse"
ms.assetid: ab41bffa-83d1-4a1c-87b9-5707d516931f
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# rts_alloc-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die rts\_alloc\-Vorlagenklasse beschreibt einen [Filter](../standard-library/allocators-header.md), der ein Array von Cache\-Instanzen enthält, und ermittelt zur Laufzeit, nicht zur Kompilierzeit, welche Instanz für die Belegung und Freigabe von Speicher zu verwenden ist.  
  
## Syntax  
  
```  
template <class Cache> class rts_alloc  
```  
  
#### Parameter  
  
|Parameter|Beschreibung|  
|---------------|------------------|  
|`Cache`|Der Typ der Cache\-Instanzen, die im Array enthalten sind.  Dieser kann [cache\_chunklist\-Klasse](../standard-library/cache-chunklist-class.md), [cache\_freelist](../standard-library/cache-freelist-class.md) oder [cache\_suballoc](../standard-library/cache-suballoc-class.md) sein.|  
  
## Hinweise  
 Diese Vorlagenklasse enthält mehrere Blockbelegungsinstanzen und ermittelt zur Laufzeit, nicht zur Kompilierzeit, welche Instanz für die Belegung oder Freigabe von Speicher zu verwenden ist.  Sie wird mit Compilern verwendet, die keine Neubindungen kompilieren können.  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[allocate](../Topic/rts_alloc::allocate.md)|Belegt einen Speicherblock.|  
|[Aufheben der Zuordnung](../Topic/rts_alloc::deallocate.md)|Gibt eine angegebene Anzahl von Objekten im Speicher frei, beginnend an einer angegebenen Position.|  
|[ist gleich](../Topic/rts_alloc::equals.md)|Vergleicht zwei Caches auf Gleichheit.|  
  
## Anforderungen  
 **Header:** \<allocators\>  
  
 **Namespace:** stdext  
  
## Siehe auch  
 [ALLOCATOR\_DECL](../Topic/ALLOCATOR_DECL%20\(%3Callocators%3E\).md)   
 [\<allocators\>](../standard-library/allocators-header.md)