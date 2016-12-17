---
title: "cache_chunklist-Klasse"
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
  - "allocators/stdext::cache_chunklist"
  - "stdext.cache_chunklist"
  - "stdext::cache_chunklist"
  - "cache_chunklist"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cache_chunklist-Klasse"
ms.assetid: af19eccc-4ae7-4a34-bbb2-81e397424cb9
caps.latest.revision: 17
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# cache_chunklist-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Definiert das [Blocks\-Zuweisung](../standard-library/allocators-header.md), Speicherblöcken einer einzelnen Größe zuordnet und freigibt.  
  
## Syntax  
  
```  
template <std::size_t Sz, std::size_t Nelts = 20> class cache_chunklist  
```  
  
#### Parameter  
  
|Parameter|**Beschreibung**|  
|---------------|----------------------|  
|`Sz`|Die Anzahl der Elemente im Array zugeordnet werden.|  
  
## Hinweise  
 Diese Klasse verwendet `operator new`, um den Dump unformatierter Arbeitsspeicher reserviert und suballocating Blöcke, um Speicher für einen Speicherblock nach Bedarf zuordnen; Sie speichert freigegebene Speicherblöcke in einer eigenen Liste der freien Blöcke für jeden Block und verwendet `operator delete`, um einen Block frei, wenn keine der Speicherblöcke verwendet wird.  
  
 Jeder Speicherblock enthält `Sz` Bytes des verwendbaren Arbeitsspeicher und des Zeigers auf den Block an, dass es gehört.  Jeder Block enthält `Nelts` Speicherblöcke, drei Zeiger, int und die Daten an, die `operator new` und `operator delete` benötigen.  
  
### Konstruktoren  
  
|||  
|-|-|  
|[cache\_chunklist](../Topic/cache_chunklist::cache_chunklist.md)|Konstruiert ein Objekt vom Typ `cache_chunklist`.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[Zuordnen zu](../Topic/cache_chunklist::allocate.md)|Ordnet einen Speicherblock zu.|  
|[geben Sie frei](../Topic/cache_chunklist::deallocate.md)|Gibt eine angegebene Anzahl Objekten vom Speicheranfang in einer angegebenen Position frei.|  
  
## Anforderungen  
 Zuweisungen **Header:** \<\>  
  
 **Namespace:** stdext  
  
## Siehe auch  
 [\<allocators\>](../standard-library/allocators-header.md)