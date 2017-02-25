---
title: "sync_per_container-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "stdext.sync_per_container"
  - "sync_per_container"
  - "stdext::sync_per_container"
  - "allocators/stdext::sync_per_container"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "sync_per_container-Klasse"
ms.assetid: 0b4b2904-b668-4d94-a422-d4f919cbffab
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# sync_per_container-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beschreibt [Synchronisierungsfilter](../standard-library/allocators-header.md), ein separates Cacheobjekt für jedes Zuweisungsobjekt bereitstellt.  
  
## Syntax  
  
```  
template <class Cache> class sync_per_container  
    : public Cache  
```  
  
#### Parameter  
  
|Parameter|**Beschreibung**|  
|---------------|----------------------|  
|`Cache`|Der Typ des dem Cache Synchronisierungsfilter.  Dies kann unter [cache\_chunklist](../standard-library/cache-chunklist-class.md), [cache\_freelist](../standard-library/cache-freelist-class.md) oder [cache\_suballoc](../standard-library/cache-suballoc-class.md) sein.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[equals](../Topic/sync_per_container::equals.md)|Vergleicht zwei Cache für Gleichheit.|  
  
## Anforderungen  
 Zuweisungen **Header:** \<\>  
  
 **Namespace:** stdext  
  
## Siehe auch  
 [\<allocators\>](../standard-library/allocators-header.md)