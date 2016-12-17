---
title: "simple_partitioner-Klasse"
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
  - "ppl/concurrency::simple_partitioner"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "simple_partitioner-Klasse"
ms.assetid: d7e997af-54d1-43f5-abe0-def72df6edb3
caps.latest.revision: 8
caps.handback.revision: "2"
ms.author: "mblome"
manager: "ghogen"
---
# simple_partitioner-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Die `simple_partitioner`\-Klasse stellt eine statische Partitionierung des Bereichs dar, der von `parallel_for` durchlaufen wird.  Mit dem Partitionierer wird der Bereich in Blöcke unterteilt, sodass jeder Block mindestens die von der Segmentgröße angegebene Anzahl von Iterationen enthält.  
  
## Syntax  
  
```  
class simple_partitioner;  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[simple\_partitioner::simple\_partitioner\-Konstruktor](../Topic/simple_partitioner::simple_partitioner%20Constructor.md)|Erstellt ein `simple_partitioner`\-Objekt.|  
|[simple\_partitioner::~simple\_partitioner\-Destruktor](../Topic/simple_partitioner::~simple_partitioner%20Destructor.md)|Zerstört ein `simple_partitioner`\-Objekt.|  
  
## Vererbungshierarchie  
 `simple_partitioner`  
  
## Anforderungen  
 **Header:** ppl.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)