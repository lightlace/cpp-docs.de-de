---
title: "simple_partitioner-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ppl/concurrency::simple_partitioner"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "simple_partitioner-Klasse"
ms.assetid: d7e997af-54d1-43f5-abe0-def72df6edb3
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
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