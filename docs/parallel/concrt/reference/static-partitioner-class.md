---
title: "static_partitioner-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ppl/concurrency::static_partitioner"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "static_partitioner-Klasse"
ms.assetid: 2b3dbdf0-6eb9-49f6-8639-03df1d974143
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# static_partitioner-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Die `static_partitioner`\-Klasse stellt eine statische Partitionierung des Bereichs dar, der von `parallel_for` durchlaufen wird.  Mit dem Partitionierer wird der Bereich in so viele Blöcke unterteilt, wie Worker für den zugrunde liegenden Planer verfügbar sind.  
  
## Syntax  
  
```  
class static_partitioner;  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[static\_partitioner::static\_partitioner\-Konstruktor](../Topic/static_partitioner::static_partitioner%20Constructor.md)|Erstellt ein `static_partitioner`\-Objekt.|  
|[static\_partitioner::~static\_partitioner\-Destruktor](../Topic/static_partitioner::~static_partitioner%20Destructor.md)|Zerstört ein `static_partitioner`\-Objekt.|  
  
## Vererbungshierarchie  
 `static_partitioner`  
  
## Anforderungen  
 **Header:** ppl.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)