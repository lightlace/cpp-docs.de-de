---
title: "allocator_chunklist-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "stdext::allocators::allocator_chunklist"
  - "allocators::allocator_chunklist"
  - "allocators/stdext::allocator_chunklist"
  - "allocators.allocator_chunklist"
  - "allocators/stdext::allocators::allocator_chunklist"
  - "allocator_chunklist"
  - "stdext.allocators.allocator_chunklist"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "allocator_chunklist-Klasse"
ms.assetid: ea72ed0a-dfdb-4c8b-8096-e4baf567b80f
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# allocator_chunklist-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beschreibt ein Objekt, das Speicherzuweisung und Freigeben für Objekte mithilfe eines Cache Typs [cache\_chunklist](../standard-library/cache-chunklist-class.md).  
  
## Syntax  
  
```  
template <class Type>  
    class allocator_chunklist;  
```  
  
#### Parameter  
  
|Parameter|**Beschreibung**|  
|---------------|----------------------|  
|`Type`|Der Typ von den Elementen zugeordnet von der Zuweisung.|  
  
## Hinweise  
 [ALLOCATOR\_DECL](../Topic/ALLOCATOR_DECL%20\(%3Callocators%3E\).md) Das Makro listet diese Klasse als Parameter der `name` in der folgenden Anweisung: `ALLOCATOR_DECL(CACHE_CHUNKLIST, SYNC_DEFAULT, allocator_chunklist``);`  
  
## Anforderungen  
 Zuweisungen **Header:** \<\>  
  
 **Namespace:** stdext  
  
## Siehe auch  
 [\<allocators\>](../standard-library/allocators-header.md)