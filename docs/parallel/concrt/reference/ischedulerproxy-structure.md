---
title: "ISchedulerProxy-Struktur"
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
  - "concrtrm/concurrency::ISchedulerProxy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ISchedulerProxy-Struktur"
ms.assetid: af416973-7a1c-4c30-aa3b-4161c2aaea54
caps.latest.revision: 18
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# ISchedulerProxy-Struktur
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Die Schnittstelle, über die Planer mit dem Ressourcen\-Manager der Concurrency Runtime kommunizieren, um die Ressourcenzuordnung auszuhandeln.  
  
## Syntax  
  
```  
struct ISchedulerProxy;  
```  
  
## Member  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[ISchedulerProxy::BindContext\-Methode](../Topic/ISchedulerProxy::BindContext%20Method.md)|Ordnet einen Threadproxy einem Ausführungskontext zu, wenn er nicht bereits zugeordnet ist.|  
|[ISchedulerProxy::CreateOversubscriber\-Methode](../Topic/ISchedulerProxy::CreateOversubscriber%20Method.md)|Erstellt auf dem einer vorhandenen Ausführungsressource zugeordneten Hardwarethread einen neuen virtuellen Prozessorstamm.|  
|[ISchedulerProxy::RequestInitialVirtualProcessors\-Methode](../Topic/ISchedulerProxy::RequestInitialVirtualProcessors%20Method.md)|Fordert eine anfängliche Zuordnung virtueller Prozessorstämme an.  Jeder virtuelle Prozessorstamm stellt die Fähigkeit dar, einen Thread auszuführen, der Arbeiten für den Planer ausführen kann.|  
|[ISchedulerProxy::Shutdown\-Methode](../Topic/ISchedulerProxy::Shutdown%20Method.md)|Benachrichtigt den Ressourcen\-Manager, dass der Planer heruntergefahren wird.  Dies bewirkt, dass der Ressourcen\-Manager sofort alle dem Planer gewährten Ressourcen freigibt.|  
|[ISchedulerProxy::SubscribeCurrentThread\-Methode](../Topic/ISchedulerProxy::SubscribeCurrentThread%20Method.md)|Registriert den aktuellen Thread beim Ressourcen\-Manager und ordnet ihn diesem Planer zu.|  
|[ISchedulerProxy::UnbindContext\-Methode](../Topic/ISchedulerProxy::UnbindContext%20Method.md)|Hebt die Zuordnung eines Threadproxys zum Ausführungskontext auf, der im `pContext`\-Parameter angegeben ist, auf und gibt ihn zurück an den freien Pool der Threadproxy\-Factory.  Diese Methode kann nur für einen Ausführungskontext aufgerufen werden, der über die [ISchedulerProxy::BindContext](../Topic/ISchedulerProxy::BindContext%20Method.md)\-Methode gebunden wurde und noch nicht gestartet wurde, weil er der `pContext`\-Parameter eines [IThreadProxy::SwitchTo](../Topic/IThreadProxy::SwitchTo%20Method.md)\-Methodenaufrufs ist.|  
  
## Hinweise  
 Der Ressourcen\-Manager gibt jedem Planer eine `ISchedulerProxy`\-Schnittstelle, der sich bei dieser mit der [IResourceManager::RegisterScheduler](../Topic/IResourceManager::RegisterScheduler%20Method.md)\-Methode registriert.  
  
## Vererbungshierarchie  
 `ISchedulerProxy`  
  
## Anforderungen  
 **Header:** concrtrm.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [IScheduler\-Struktur](../../../parallel/concrt/reference/ischeduler-structure.md)   
 [IThreadProxy\-Struktur](../../../parallel/concrt/reference/ithreadproxy-structure.md)   
 [IVirtualProcessorRoot\-Struktur](../../../parallel/concrt/reference/ivirtualprocessorroot-structure.md)   
 [IResourceManager\-Struktur](../../../parallel/concrt/reference/iresourcemanager-structure.md)