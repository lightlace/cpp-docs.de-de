---
title: "cache_freelist-Klasse"
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
  - "stdext.cache_freelist"
  - "allocators/stdext::cache_freelist"
  - "stdext::cache_freelist"
  - "cache_freelist"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cache_freelist-Klasse"
ms.assetid: 840694de-36ba-470f-8dae-2b723d5a8cd9
caps.latest.revision: 19
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# cache_freelist-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Definiert eine [Blockieren Zuweisung](../standard-library/allocators-header.md) die zuweist und freigibt Speicherblöcke mit einer einzelnen Größe.  
  
## Syntax  
  
```  
template <std::size_t Sz, class Max> class cache_freelist  
```  
  
#### Parameter  
  
|Parameter|Beschreibung|  
|---------------|------------------|  
|`Sz`|Die Anzahl der Elemente im Array zugewiesen werden.|  
|`Max`|Die max\-Klasse, die die maximale Größe der Freiliste darstellt. Dies kann [Max\_fixed\_size](../standard-library/max-fixed-size-class.md), [Max\_none](../standard-library/max-none-class.md), [Max\_unbounded](../standard-library/max-unbounded-class.md), oder [Max\_variable\_size](../standard-library/max-variable-size-class.md).|  
  
## Hinweise  
 Die Vorlagenklasse Cache\_freelist verwaltet eine Freiliste Speicherblöcke Größe `Sz`. Wenn Sie die kostenlose Liste voll ist verwendet `operator delete` blockiert, um Arbeitsspeicher freizugeben. Wenn die freie Liste leer ist verwendet `operator new` in neue Speicherblöcke zuweisen. Die maximale Größe der Freiliste richtet sich nach der Klasse max\-Klasse übergeben wird, in der `Max` Parameter.  
  
 Jeder Speicherblock enthält `Sz` Bytes Speicherkapazität und die Daten, die `operator new` und `operator delete` erfordern.  
  
### Konstruktoren  
  
|||  
|-|-|  
|[cache\_freelist](../Topic/cache_freelist::cache_freelist.md)|Konstruiert ein Objekt vom Typ `cache_freelist`.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[allocate](../Topic/cache_freelist::allocate.md)|Belegt einen Speicherblock.|  
|[Aufheben der Zuordnung](../Topic/cache_freelist::deallocate.md)|Gibt eine angegebene Anzahl von Objekten im Speicher frei, beginnend an einer angegebenen Position.|  
  
## Anforderungen  
 **Header:** \<allocators\>  
  
 **Namespace:** stdext  
  
## Siehe auch  
 [\<allocators\>](../standard-library/allocators-header.md)