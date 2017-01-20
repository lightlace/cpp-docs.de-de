---
title: "IUMSUnblockNotification-Struktur"
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
  - "concrtrm/concurrency::IUMSUnblockNotification"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IUMSUnblockNotification-Struktur"
ms.assetid: eaca9529-c1cc-472b-8ec6-722a1ff0fa2a
caps.latest.revision: 19
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# IUMSUnblockNotification-Struktur
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Stellt eine Benachrichtigung vom Ressourcen\-Manager darüber dar, dass ein Threadproxy, der blockiert und eine Rückkehr zum festgelegten Planungskontext des Planers ausgelöst hatte, die Blockierung aufgehoben hat und zum Planen bereit ist.  Diese Schnittstelle ist ungültig, sobald der zugeordnete Ausführungskontext des Threadproxys, der von der `GetContext`\-Methode zurückgegeben wurde, neu geplant wird.  
  
## Syntax  
  
```  
struct IUMSUnblockNotification;  
```  
  
## Member  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[IUMSUnblockNotification::GetContext\-Methode](../Topic/IUMSUnblockNotification::GetContext%20Method.md)|Gibt die `IExecutionContext`\-Schnittstelle für den Ausführungskontext zurück, der dem Threadproxy zugeordnet ist, der nicht mehr blockiert.  Sobald diese Methode zurückkehrt und der zugrunde liegende Ausführungskontext mit einen Aufruf der `IThreadProxy::SwitchTo`\-Methode neu geplant wurde, ist diese Schnittstelle nicht mehr gültig.|  
|[IUMSUnblockNotification::GetNextUnblockNotification\-Methode](../Topic/IUMSUnblockNotification::GetNextUnblockNotification%20Method.md)|Gibt die nächste `IUMSUnblockNotification`\-Schnittstelle in der von der `IUMSCompletionList::GetUnblockNotifications`\-Methode zurückgegebenen Kette zurück.|  
  
## Vererbungshierarchie  
 `IUMSUnblockNotification`  
  
## Anforderungen  
 **Header:** concrtrm.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [IUMSScheduler\-Struktur](../../../parallel/concrt/reference/iumsscheduler-structure.md)   
 [IUMSCompletionList\-Struktur](../../../parallel/concrt/reference/iumscompletionlist-structure.md)