---
title: "invalid_compute_domain-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amprt/Concurrency::invalid_compute_domain"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "invalid_compute_domain-Klasse"
ms.assetid: ac7a7166-8bdb-4db1-8caf-ea129ab5117e
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# invalid_compute_domain-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Die Ausnahme, die ausgelöst wird, wenn die Laufzeit eines Kernel starten kann, indem die Berechnungsdomäne verwendet, die an der Aufrufsite [parallel\_for\_each](../Topic/parallel_for_each%20Function%20\(C++%20AMP\).md) angegeben wird.  
  
## Syntax  
  
```  
class invalid_compute_domain : public runtime_exception;  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[invalid\_compute\_domain::invalid\_compute\_domain\-Konstruktor](../Topic/invalid_compute_domain::invalid_compute_domain%20Constructor.md)|Initialisiert eine neue Instanz der `invalid_compute_domain`\-Klasse.|  
  
## Vererbungshierarchie  
 `exception`  
  
 `runtime_exception`  
  
 `invalid_compute_domain`  
  
## Anforderungen  
 **Header:** amprt.h  
  
 **Namespace:** Nebenläufigkeit  
  
## Siehe auch  
 [Concurrency\-Namespace \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)