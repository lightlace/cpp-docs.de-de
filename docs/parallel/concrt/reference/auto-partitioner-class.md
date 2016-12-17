---
title: "auto_partitioner-Klasse"
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
  - "ppl/concurrency::auto_partitioner"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "auto_partitioner-Klasse"
ms.assetid: 7cc08e5d-20b4-47a4-b4b5-c214a78f5a9e
caps.latest.revision: 8
caps.handback.revision: "2"
ms.author: "mblome"
manager: "ghogen"
---
# auto_partitioner-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Die `auto_partitioner`\-Klasse stellt die Standardmethoden `parallel_for`, `parallel_for_each` und `parallel_transform` dar, die verwendet werden, um den Bereich zu partitionieren, den sie durchlaufen.  Diese Partitionierungsmethode verwendet Bereichsstealing zum Lastenausgleich sowie Abbruch pro Durchlauf.  
  
## Syntax  
  
```  
class auto_partitioner;  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[auto\_partitioner::auto\_partitioner\-Konstruktor](../Topic/auto_partitioner::auto_partitioner%20Constructor.md)|Erstellt ein `auto_partitioner`\-Objekt.|  
|[auto\_partitioner::~auto\_partitioner\-Destruktor](../Topic/auto_partitioner::~auto_partitioner%20Destructor.md)|Zerstört ein `auto_partitioner`\-Objekt.|  
  
## Vererbungshierarchie  
 `auto_partitioner`  
  
## Anforderungen  
 **Header:** ppl.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)