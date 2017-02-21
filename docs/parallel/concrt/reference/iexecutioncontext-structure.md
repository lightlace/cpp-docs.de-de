---
title: "IExecutionContext-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrtrm/concurrency::IExecutionContext"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IExecutionContext-Struktur"
ms.assetid: f3108089-ecda-4b07-86db-3efae60c31e0
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# IExecutionContext-Struktur
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Eine Schnittstelle zu einem Ausführungskontext, der auf einem angegebenen virtuellen Prozessor ausgeführt werden kann und einen gemeinsamen Kontextwechsel zulässt.  
  
## Syntax  
  
```  
struct IExecutionContext;  
```  
  
## Member  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[IExecutionContext::Dispatch\-Methode](../Topic/IExecutionContext::Dispatch%20Method.md)|Die Methode, die aufgerufen wird, wenn ein Threadproxy anfängt, einen bestimmten Ausführungskontext auszuführen.  Dies sollte die Hauptworkerroutine für den Planer sein.|  
|[IExecutionContext::GetId\-Methode](../Topic/IExecutionContext::GetId%20Method.md)|Gibt einen eindeutigen Bezeichner für den Ausführungskontext zurück.|  
|[IExecutionContext::GetProxy\-Methode](../Topic/IExecutionContext::GetProxy%20Method.md)|Gibt eine Schnittstelle zu dem Threadproxy zurück, der diesen Kontext ausführt.|  
|[IExecutionContext::GetScheduler\-Methode](../Topic/IExecutionContext::GetScheduler%20Method.md)|Gibt eine Schnittstelle zu dem Planer zurück, zu dem dieser Ausführungskontext gehört.|  
|[IExecutionContext::SetProxy\-Methode](../Topic/IExecutionContext::SetProxy%20Method.md)|Ordnet diesem Ausführungskontext einen Threadproxy zu.  Der zugeordnete Threadproxy ruft diese Methode auf, unmittelbar bevor die `Dispatch`\-Methode des Kontexts ausgeführt wird.|  
  
## Hinweise  
 Wenn Sie einen benutzerdefinierten Planer implementieren, der eine Schnittstelle zum Ressourcen\-Manager der Concurrency Runtime beinhaltet, müssen Sie die `IExecutionContext`\-Schnittstelle implementieren.  Die vom Ressourcen\-Manager erstellten Threads führen Arbeiten für den Planer aus, indem sie die `IExecutionContext::Dispatch`\-Methode ausführen.  
  
## Vererbungshierarchie  
 `IExecutionContext`  
  
## Anforderungen  
 **Header:** concrtrm.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [IScheduler\-Struktur](../../../parallel/concrt/reference/ischeduler-structure.md)   
 [IThreadProxy\-Struktur](../../../parallel/concrt/reference/ithreadproxy-structure.md)