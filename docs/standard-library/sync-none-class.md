---
title: "sync_none-Klasse"
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
  - "stdext.sync_none"
  - "sync_none"
  - "allocators/stdext::sync_none"
  - "stdext::sync_none"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "sync_none-Klasse"
ms.assetid: f7473cee-14f3-4fe1-88bc-68cd085e59e1
caps.latest.revision: 21
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# sync_none-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beschreibt [Synchronisierungsfilter](../standard-library/allocators-header.md), das keine Synchronisierung bietet.  
  
## Syntax  
  
```  
template <class Cache> class sync_none  
```  
  
#### Parameter  
  
|Parameter|**Beschreibung**|  
|---------------|----------------------|  
|`Cache`|Der Typ des dem Cache Synchronisierungsfilter.  Dies kann unter [cache\_chunklist](../standard-library/cache-chunklist-class.md), [cache\_freelist](../standard-library/cache-freelist-class.md) oder [cache\_suballoc](../standard-library/cache-suballoc-class.md) sein.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[Zuordnen zu](../Topic/sync_none::allocate.md)|Ordnet einen Speicherblock zu.|  
|[geben Sie frei](../Topic/sync_none::deallocate.md)|Gibt eine angegebene Anzahl Objekten vom Speicheranfang in einer angegebenen Position frei.|  
|[equals](../Topic/sync_none::equals.md)|Vergleicht zwei Cache für Gleichheit.|  
  
## Anforderungen  
 Zuweisungen **Header:** \<\>  
  
 **Namespace:** stdext  
  
## Siehe auch  
 [\<allocators\>](../standard-library/allocators-header.md)