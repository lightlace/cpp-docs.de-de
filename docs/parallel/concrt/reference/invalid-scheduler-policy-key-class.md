---
title: "invalid_scheduler_policy_key-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::invalid_scheduler_policy_key"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "invalid_scheduler_policy_key-Klasse"
ms.assetid: 6a7c42fe-9bc4-4a02-bebb-99fe9ef9817d
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# invalid_scheduler_policy_key-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn ein ungültiger oder unbekannter Schlüssel an einen `SchedulerPolicy`\-Objektkonstruktor übergeben wird, oder wenn der `SetPolicyValue`\-Methode eines `SchedulerPolicy`\-Objekts ein Schlüssel übergeben wird, der auf andere Weise geändert werden muss, z. B. die `SetConcurrencyLimits`\-Methode.  
  
## Syntax  
  
```  
class invalid_scheduler_policy_key : public std::exception;  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[invalid\_scheduler\_policy\_key::invalid\_scheduler\_policy\_key\-Konstruktor](../Topic/invalid_scheduler_policy_key::invalid_scheduler_policy_key%20Constructor.md)|Überladen.  Erstellt ein `invalid_scheduler_policy_key`\-Objekt.|  
  
## Vererbungshierarchie  
 `exception`  
  
 `invalid_scheduler_policy_key`  
  
## Anforderungen  
 **Header:** concrt.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [SchedulerPolicy\-Klasse](../../../parallel/concrt/reference/schedulerpolicy-class.md)   
 [PolicyElementKey\-Enumeration](../Topic/PolicyElementKey%20Enumeration.md)   
 [SchedulerPolicy::SetPolicyValue\-Methode](../Topic/SchedulerPolicy::SetPolicyValue%20Method.md)   
 [SchedulerPolicy::SetConcurrencyLimits\-Methode](../Topic/SchedulerPolicy::SetConcurrencyLimits%20Method.md)