---
title: "IUMSScheduler-Struktur"
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
  - "concrtrm/concurrency::IUMSScheduler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IUMSScheduler-Struktur"
ms.assetid: 3a500225-4e02-4849-bb56-d744865f5870
caps.latest.revision: 18
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# IUMSScheduler-Struktur
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Eine Schnittstelle zu der Abstraktion eines Arbeitsplaners, der planbare Threads vom Ressourcen\-Manager der Concurrency Runtime im Benutzermodus erwartet.  Der Ressourcen\-Manager verwendet diese Schnittstelle für die Kommunikation mit UMS\-Threadplanern.  Die `IUMSScheduler`\-Schnittstelle erbt von der `IScheduler`\-Schnittstelle.  
  
## Syntax  
  
```  
struct IUMSScheduler : public IScheduler;  
```  
  
## Member  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[IUMSScheduler::SetCompletionList\-Methode](../Topic/IUMSScheduler::SetCompletionList%20Method.md)|Weist einem UMS\-Threadplaner eine `IUMSCompletionList`\-Schnittstelle zu.|  
  
## Hinweise  
 Wenn Sie einen benutzerdefinierten Planer implementieren, der mit dem Ressourcen\-Manager kommuniziert, und Sie möchten, dass UMS\-Threads an Ihren Planer übergeben werden, anstelle gewöhnlicher Win32\-Threads, dann müssen Sie eine Implementierung der `IUMSScheduler`\-Schnittstelle bereitstellen.  Außerdem sollten Sie den Richtlinienwert für den Planerrichtlinienschlüssel `SchedulerKind` auf `UmsThreadDefault` festlegen.  Wenn die Richtlinie einen UMS\-Thread angibt, muss die `IScheduler`\-Schnittstelle, die als Parameter an die [IResourceManager::RegisterScheduler](../Topic/IResourceManager::RegisterScheduler%20Method.md)\-Methode übergeben wird, eine `IUMSScheduler`\-Schnittstelle sein.  
  
 Der Ressourcen\-Manager ist in der Lage, Ihnen UMS\-Threads nur unter Betriebssystemen zuzuweisen, die über die UMS\-Funktion verfügen. 64\-Bit\-Betriebssysteme mit Version Windows 7 und höher unterstützen UMS\-Threads.  Wenn Sie eine Planerrichtlinie mit dem `SchedulerKind`\-Schlüsselwert `UmsThreadDefault` erstellen und die zugrunde liegende Plattform UMS nicht unterstützt, dann wird der Wert des `SchedulerKind`\-Schlüssels dieser Richtlinie in den Wert `ThreadScheduler` geändert.  Sie sollten diesen Richtlinienwert immer zurücklesen, bevor Sie den Empfang von UMS\-Threads erwarten.  
  
 Die `IUMSScheduler`\-Schnittstelle ist ein Ende eines bidirektionalen Kommunikationskanals zwischen einem Planer und dem Ressourcen\-Manager.  Das andere Ende wird durch die `IResourceManager`\-Schnittstelle und `ISchedulerProxy`\-Schnittstelle dargestellt, die welche vom Ressourcen\-Manager implementiert werden.  
  
## Vererbungshierarchie  
 [IScheduler](../../../parallel/concrt/reference/ischeduler-structure.md)  
  
 `IUMSScheduler`  
  
## Anforderungen  
 **Header:** concrtrm.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [PolicyElementKey\-Enumeration](../Topic/PolicyElementKey%20Enumeration.md)   
 [IScheduler\-Struktur](../../../parallel/concrt/reference/ischeduler-structure.md)   
 [IUMSCompletionList\-Struktur](../../../parallel/concrt/reference/iumscompletionlist-structure.md)   
 [IResourceManager\-Struktur](../../../parallel/concrt/reference/iresourcemanager-structure.md)