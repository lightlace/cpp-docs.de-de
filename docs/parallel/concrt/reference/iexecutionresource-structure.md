---
title: "IExecutionResource-Struktur"
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
  - "concrtrm/concurrency::IExecutionResource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IExecutionResource-Struktur"
ms.assetid: 6b27042b-b98c-4f7f-b831-566950af84cd
caps.latest.revision: 16
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# IExecutionResource-Struktur
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Eine Abstraktion für einen Hardwarethread.  
  
## Syntax  
  
```  
struct IExecutionResource;  
```  
  
## Member  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[IExecutionResource::CurrentSubscriptionLevel\-Methode](../Topic/IExecutionResource::CurrentSubscriptionLevel%20Method.md)|Gibt die Anzahl der aktivierten virtuellen Prozessorstämme und abonnierten externen Threads zurück, die dem zugrunde liegenden Hardwarethread, den diese Ausführungsressource darstellt, gerade zugeordnet sind.|  
|[IExecutionResource::GetExecutionResourceId\-Methode](../Topic/IExecutionResource::GetExecutionResourceId%20Method.md)|Gibt einen eindeutigen Bezeichner für den Hardwarethread zurück, den diese Ausführungsressource darstellt.|  
|[IExecutionResource::GetNodeId\-Methode](../Topic/IExecutionResource::GetNodeId%20Method.md)|Gibt einen eindeutigen Bezeichner für den Prozessorknoten zurück, zu dem diese Ausführungsressource gehört.|  
|[IExecutionResource::Remove\-Methode](../Topic/IExecutionResource::Remove%20Method.md)|Gibt diese Ausführungsressource an den Ressourcen\-Manager zurück.|  
  
## Hinweise  
 Ausführungsressourcen können eigenständig oder virtuellen Prozessorstämmen zugeordnet sein.  Eine eigenständige Ausführungsressource wird erstellt, wenn ein Thread in der Anwendung ein Threadabonnement erstellt.  Die Methoden [ISchedulerProxy::SubscribeThread](../Topic/ISchedulerProxy::SubscribeCurrentThread%20Method.md) und [ISchedulerProxy::RequestInitialVirtualProcessors](../Topic/ISchedulerProxy::RequestInitialVirtualProcessors%20Method.md) erstellen Threadabonnements und geben eine `IExecutionResource`\-Schnittstelle zurück, die das Abonnement darstellt.  Ein Threadabonnement zu erstellen ist eine Möglichkeit, den Ressourcen\-Manager zu informieren, dass ein bestimmter Thread an der Arbeit teilnimmt, die für einen Planer in die Warteschlange gestellt wurde, zusammen mit den virtuellen Prozessorstämmen, die der Ressourcen\-Manager dem Planer zugewiesen hat.  Der Ressourcen\-Manager vermeidet mithilfe der Informationen, Hardwarethreads zu überzeichnen, wo er kann.  
  
## Vererbungshierarchie  
 `IExecutionResource`  
  
## Anforderungen  
 **Header:** concrtrm.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [IVirtualProcessorRoot\-Struktur](../../../parallel/concrt/reference/ivirtualprocessorroot-structure.md)   
 [ISchedulerProxy::SubscribeCurrentThread\-Methode](../Topic/ISchedulerProxy::SubscribeCurrentThread%20Method.md)   
 [ISchedulerProxy::RequestInitialVirtualProcessors\-Methode](../Topic/ISchedulerProxy::RequestInitialVirtualProcessors%20Method.md)