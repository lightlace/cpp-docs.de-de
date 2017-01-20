---
title: "invalid_oversubscribe_operation-Klasse"
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
  - "concrt/concurrency::invalid_oversubscribe_operation"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "invalid_oversubscribe_operation-Klasse"
ms.assetid: 0a9c5f08-d5e6-4ad0-90a9-517472b3ac28
caps.latest.revision: 19
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# invalid_oversubscribe_operation-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn die `Context::Oversubscribe`\-Methode mit dem auf `false` festgelegten `_BeginOversubscription`\-Parameter ohne einen vorherigen Aufruf der `Context::Oversubscribe`\-Methode mit dem auf `true` festgelegten `_BeginOversubscription`\-Parameter aufgerufen wird.  
  
## Syntax  
  
```  
class invalid_oversubscribe_operation : public std::exception;  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[invalid\_oversubscribe\_operation::invalid\_oversubscribe\_operation\-Konstruktor](../Topic/invalid_oversubscribe_operation::invalid_oversubscribe_operation%20Constructor.md)|Überladen.  Erstellt ein `invalid_oversubscribe_operation`\-Objekt.|  
  
## Vererbungshierarchie  
 `exception`  
  
 `invalid_oversubscribe_operation`  
  
## Anforderungen  
 **Header:** concrt.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Context::Oversubscribe\-Methode](../Topic/Context::Oversubscribe%20Method.md)