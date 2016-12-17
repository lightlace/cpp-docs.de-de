---
title: "sync_shared-Klasse"
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
  - "sync_shared"
  - "allocators/stdext::sync_shared"
  - "stdext.sync_shared"
  - "stdext::sync_shared"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "sync_shared-Klasse"
ms.assetid: cab3af9e-3d1a-4f2c-8580-0f89e5687d8e
caps.latest.revision: 19
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# sync_shared-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beschreibt einen [Synchronisierungsfilter](../standard-library/allocators-header.md), in dem ein Mutex verwendet wird, um den Zugriff auf ein Cacheobjekt zu steuern, das von allen Zuweisungen \(allocator\-Objekten\) gemeinsam verwendet wird.  
  
## Syntax  
  
```  
template <class Cache> class sync_shared  
```  
  
#### Parameter  
  
|Parameter|Beschreibung|  
|---------------|------------------|  
|`Cache`|Der Cachetyp, der diesem Synchronisierungsfilter zugeordnet werden soll. Dieser kann [cache\_chunklist](../standard-library/cache-chunklist-class.md), [cache\_freelist](../standard-library/cache-freelist-class.md) oder [cache\_suballoc](../standard-library/cache-suballoc-class.md) sein.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[allocate](../Topic/sync_shared::allocate.md)|Belegt einen Speicherblock.|  
|[Aufheben der Zuordnung](../Topic/sync_shared::deallocate.md)|Gibt eine angegebene Anzahl von Objekten im Speicher frei, beginnend an einer angegebenen Position.|  
|[ist gleich](../Topic/sync_shared::equals.md)|Vergleicht zwei Caches auf Gleichheit.|  
  
## Anforderungen  
 **Header:** \<allocators\>  
  
 **Namespace:** stdext  
  
## Siehe auch  
 [\<allocators\>](../standard-library/allocators-header.md)