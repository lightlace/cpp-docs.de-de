---
title: "sync_per_thread-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "stdext::sync_per_thread"
  - "sync_per_thread"
  - "allocators/stdext::sync_per_thread"
  - "stdext.sync_per_thread"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "sync_per_thread-Klasse"
ms.assetid: 47bf75f8-5b02-4760-b1d3-3099d08fe14c
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# sync_per_thread-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beschreibt [Synchronisierungsfilter](../standard-library/allocators-header.md), ein separates Cacheobjekt für jeden Thread enthält.  
  
## Syntax  
  
```  
template <class Cache> class sync_per_thread  
```  
  
#### Parameter  
  
|Parameter|**Beschreibung**|  
|---------------|----------------------|  
|`Cache`|Der Typ des dem Cache Synchronisierungsfilter.  Dies kann unter [cache\_chunklist](../standard-library/cache-chunklist-class.md), [cache\_freelist](../standard-library/cache-freelist-class.md) oder [cache\_suballoc](../standard-library/cache-suballoc-class.md) sein.|  
  
## Hinweise  
 Zuweisungen, die `sync_per_thread` verwenden, können gleich vergleichen, obwohl die Blöcke, die in einem Thread zugeordnet sind, nicht von einem anderen Thread freigegeben werden können.  Wenn sollte die Verwendung einer dieser Zuweisungsspeicherblöcke, die in einem Thread zugeordnet sind, nicht eingeblendet werden an andere Threads.  In der Praxis bedeutet dies, dass auf einen Container, der einer dieser Zuweisungen verwendet, durch einen einzelnen Thread nur zugegriffen werden soll.  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[Zuordnen zu](../Topic/sync_per_thread::allocate.md)|Ordnet einen Speicherblock zu.|  
|[geben Sie frei](../Topic/sync_per_thread::deallocate.md)|Gibt eine angegebene Anzahl Objekten vom Speicheranfang in einer angegebenen Position frei.|  
|[equals](../Topic/sync_per_thread::equals.md)|Vergleicht zwei Cache für Gleichheit.|  
  
## Anforderungen  
 Zuweisungen **Header:** \<\>  
  
 **Namespace:** stdext  
  
## Siehe auch  
 [\<allocators\>](../standard-library/allocators-header.md)