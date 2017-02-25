---
title: "DispatchState-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrtrm/concurrency::DispatchState"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DispatchState-Struktur"
ms.assetid: 8c52546e-1650-48a0-985f-7e4a0fc26a90
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# DispatchState-Struktur
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Die `DispatchState`\-Struktur wird zur Zustandsübertragung auf die `IExecutionContext::Dispatch`\-Methode verwendet.  Sie beschreibt die Umstände, unter denen die `Dispatch`\-Methode für eine `IExecutionContext`\-Schnittstelle aufgerufen wird.  
  
## Syntax  
  
```  
struct DispatchState;  
```  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[DispatchState::DispatchState\-Konstruktor](../Topic/DispatchState::DispatchState%20Constructor.md)|Erstellt ein neues `DispatchState`\-Objekt.|  
  
### Öffentliche Datenmember  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[DispatchState::m\_dispatchStateSize\-Datenmember](../Topic/DispatchState::m_dispatchStateSize%20Data%20Member.md)|Größe dieser Struktur, die zur Versionsverwaltung verwendet wird.|  
|[DispatchState::m\_fIsPreviousContextAsynchronouslyBlocked\-Datenmember](../Topic/DispatchState::m_fIsPreviousContextAsynchronouslyBlocked%20Data%20Member.md)|Gibt an, ob dieser Kontext in die `Dispatch`\-Methode eingetreten ist, weil der vorherige Kontext asynchron blockiert hat.  Dies wird nur im UMS\-Planungskontext verwendet und für alle anderen Ausführungskontexte auf den Wert `0` festgelegt.|  
|[DispatchState::m\_reserved\-Datenmember](../Topic/DispatchState::m_reserved%20Data%20Member.md)|Bits, die für zukünftige Informationen reserviert sind.|  
  
## Vererbungshierarchie  
 `DispatchState`  
  
## Anforderungen  
 **Header:** concrtrm.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [IExecutionContext::Dispatch\-Methode](../Topic/IExecutionContext::Dispatch%20Method.md)