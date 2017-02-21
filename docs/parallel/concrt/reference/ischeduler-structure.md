---
title: "IScheduler-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrtrm/concurrency::IScheduler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IScheduler-Struktur"
ms.assetid: 471de85a-2b1a-4b6d-ab81-2eff2737161e
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# IScheduler-Struktur
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Eine Schnittstelle zu der Abstraktion eines Arbeitsplaners.  Der Ressourcen\-Manager der Concurrency Runtime kommuniziert mithilfe dieser Schnittstelle mit Arbeitsplanern.  
  
## Syntax  
  
```  
struct IScheduler;  
```  
  
## Member  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[IScheduler::AddVirtualProcessors\-Methode](../Topic/IScheduler::AddVirtualProcessors%20Method.md)|Stellt einem Planer einen Satz von virtuellen Prozessorstämmen zur Verwendung bereit.  Jede `IVirtualProcessorRoot`\-Schnittstelle stellt das Recht dar, einen einzelnen Thread auszuführen, der Arbeiten im Auftrag des Planers ausführen kann.|  
|[IScheduler::GetId\-Methode](../Topic/IScheduler::GetId%20Method.md)|Gibt einen eindeutigen Bezeichner für den Planer zurück.|  
|[IScheduler::GetPolicy\-Methode](../Topic/IScheduler::GetPolicy%20Method.md)|Gibt eine Kopie der Richtlinie des Planers zurück.  Weitere Informationen über verfügbare Planerrichtlinien finden Sie unter [SchedulerPolicy](../../../parallel/concrt/reference/schedulerpolicy-class.md).|  
|[IScheduler::NotifyResourcesExternallyBusy\-Methode](../Topic/IScheduler::NotifyResourcesExternallyBusy%20Method.md)|Benachrichtigt diesen Planer, dass die durch den Satz virtueller Prozessorstämme dargestellten Hardwarethreads im Array `ppVirtualProcessorRoots` jetzt von anderen Planern verwendet werden.|  
|[IScheduler::NotifyResourcesExternallyIdle\-Methode](../Topic/IScheduler::NotifyResourcesExternallyIdle%20Method.md)|Benachrichtigt diesen Planer, dass die durch den Satz virtueller Prozessorstämme dargestellten Hardwarethreads im Array `ppVirtualProcessorRoots` nicht von anderen Planern verwendet werden.|  
|[IScheduler::RemoveVirtualProcessors\-Methode](../Topic/IScheduler::RemoveVirtualProcessors%20Method.md)|Initiiert die Löschung von virtuellen Prozessorstämmen, die diesem Planer zuvor zugeordnet wurden.|  
|[IScheduler::Statistics\-Methode](../Topic/IScheduler::Statistics%20Method.md)|Stellt Informationen zur Empfangs\- und Abschlussrate von Aufgaben und zu Änderungen der Warteschlangenlänge eines Planers bereit.|  
  
## Hinweise  
 Wenn Sie einen benutzerdefinierten Planer implementieren, der mit dem Ressourcen\-Manager kommuniziert, müssen Sie eine Implementierung der `IScheduler`\-Schnittstelle bereitstellen.  Diese Schnittstelle ist ein Ende eines bidirektionalen Kommunikationskanals zwischen einem Planer und dem Ressourcen\-Manager.  Das andere Ende wird durch die `IResourceManager`\-Schnittstelle und `ISchedulerProxy`\-Schnittstelle dargestellt, die welche vom Ressourcen\-Manager implementiert werden.  
  
## Vererbungshierarchie  
 `IScheduler`  
  
## Anforderungen  
 **Header:** concrtrm.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [PolicyElementKey\-Enumeration](../Topic/PolicyElementKey%20Enumeration.md)   
 [SchedulerPolicy\-Klasse](../../../parallel/concrt/reference/schedulerpolicy-class.md)   
 [IExecutionContext\-Struktur](../../../parallel/concrt/reference/iexecutioncontext-structure.md)   
 [IThreadProxy\-Struktur](../../../parallel/concrt/reference/ithreadproxy-structure.md)   
 [IVirtualProcessorRoot\-Struktur](../../../parallel/concrt/reference/ivirtualprocessorroot-structure.md)   
 [IResourceManager\-Struktur](../../../parallel/concrt/reference/iresourcemanager-structure.md)