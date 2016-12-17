---
title: "uninitialized_object-Klasse"
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
  - "amprt/Concurrency::uninitialized_object"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "uninitialized_object-Klasse"
ms.assetid: 6ae3c4e8-64a6-4511-a158-03be197b63af
caps.latest.revision: 10
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# uninitialized_object-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Die Ausnahme, die ausgelöst wird, wenn ein nicht initialisiertes Objekt verwendet wird.  
  
## Syntax  
  
```  
class uninitialized_object : public runtime_exception;  
  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[uninitialized\_object::uninitialized\_object\-Konstruktor](../Topic/uninitialized_object::uninitialized_object%20Constructor.md)|Initialisiert eine neue Instanz der `uninitialized_object`\-Klasse.|  
  
## Vererbungshierarchie  
 `exception`  
  
 `runtime_exception`  
  
 `uninitialized_object`  
  
## Anforderungen  
 **Header:** amprt.h  
  
 **Namespace:** Nebenläufigkeit  
  
## Siehe auch  
 [Concurrency\-Namespace \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)