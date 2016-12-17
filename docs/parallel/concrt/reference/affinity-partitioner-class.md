---
title: "affinity_partitioner-Klasse"
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
  - "ppl/concurrency::affinity_partitioner"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "affinity_partitioner-Klasse"
ms.assetid: 31bf7bb1-bd01-491c-9760-d9d60edfccad
caps.latest.revision: 9
caps.handback.revision: "3"
ms.author: "mblome"
manager: "ghogen"
---
# affinity_partitioner-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Die `affinity_partitioner`\-Klasse ist der `static_partitioner`\-Klasse ähnlich, allerdings wird die Cacheaffinität dank der Auswahl, den Arbeitsthreads Unterbereiche zuzuordnen, verbessert.  Sie kann die Leistung, bei erneutem Ausführen einer Schleife über dem gleichen Dataset, und wenn die Daten im Cache gespeichert werden können, erheblich verbessern.  Beachten Sie, dass das gleiche `affinity_partitioner`\-Objekt mit nachfolgenden Iterationen einer parallelen Schleife verwendet werden muss, die für ein bestimmtes Dataset ausgeführt wird, um vom Datenort zu profitieren.  
  
## Syntax  
  
```  
class affinity_partitioner;  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[affinity\_partitioner::affinity\_partitioner\-Konstruktor](../Topic/affinity_partitioner::affinity_partitioner%20Constructor.md)|Erstellt ein `affinity_partitioner`\-Objekt.|  
|[affinity\_partitioner::~affinity\_partitioner\-Destruktor](../Topic/affinity_partitioner::~affinity_partitioner%20Destructor.md)|Zerstört ein `affinity_partitioner`\-Objekt.|  
  
## Vererbungshierarchie  
 `affinity_partitioner`  
  
## Anforderungen  
 **Header:** ppl.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)