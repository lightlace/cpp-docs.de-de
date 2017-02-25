---
title: "IUMSThreadProxy-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrtrm/concurrency::IUMSThreadProxy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IUMSThreadProxy-Struktur"
ms.assetid: 61c69b7e-5c37-4048-bcb4-e75c536afd86
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# IUMSThreadProxy-Struktur
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Eine Abstraktion für einen Thread der Ausführung.  Wenn dem Planer im Benutzermodus planbare \(UMS\) Threads gewährt werden sollen, legen Sie den Wert für das Planerrichtlinienelement `SchedulerKind` auf `UmsThreadDefault` fest, und implementieren Sie die `IUMSScheduler`\-Schnittstelle.  UMS\-Threads werden nur unter 64\-Bit\-Betriebssystemen mit Version Windows 7 und höher unterstützt.  
  
## Syntax  
  
```  
struct IUMSThreadProxy : public IThreadProxy;  
```  
  
## Member  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[IUMSThreadProxy::EnterCriticalRegion\-Methode](../Topic/IUMSThreadProxy::EnterCriticalRegion%20Method.md)|Wird aufgerufen, um in einen kritischen Bereich einzutreten.  In einem wichtigen Bereich beachtet der Planer keine asynchronen blockierenden Operationen, die während des Bereichs auftreten.  Dies bedeutet, dass der Planer nicht für Seitenfehler, Thread\-Unterbrechungen, Kernelasynchrone prozeduraufrufe \(APCs\) usw. für einen UMS\-Thread erneut eingegeben wird.|  
|[IUMSThreadProxy::EnterHyperCriticalRegion\-Methode](../Topic/IUMSThreadProxy::EnterHyperCriticalRegion%20Method.md)|Wird aufgerufen, um in einen extrem kritischen Bereich einzutreten.  In einem äußerst wichtigen Bereich beachtet der Planer keine blockierenden Operationen, die während des Bereichs auftreten.  Dies bedeutet, dass der Planer nicht für Sperrfunktionsaufrufe, Sperrendatenerfassungsversuche, die blockiert werden, Seitenfehler, Thread\-Unterbrechungen, Kernelasynchrone prozeduraufrufe \(APCs\) usw. für einen UMS\-Thread erneut eingegeben wird.|  
|[IUMSThreadProxy::ExitCriticalRegion\-Methode](../Topic/IUMSThreadProxy::ExitCriticalRegion%20Method.md)|Wird aufgerufen, um einen kritischen Bereich zu verlassen.|  
|[IUMSThreadProxy::ExitHyperCriticalRegion\-Methode](../Topic/IUMSThreadProxy::ExitHyperCriticalRegion%20Method.md)|Wird aufgerufen, um einen extrem kritischen Bereich zu verlassen.|  
|[IUMSThreadProxy::GetCriticalRegionType\-Methode](../Topic/IUMSThreadProxy::GetCriticalRegionType%20Method.md)|Gibt zurück, in was für einem kritischen Bereich sich der Threadproxy befindet.  Da besonders wichtige Bereiche eine Obermenge von kritischen Bereiche sind, wenn Code einem kritischen Bereich und anschließend eines besonders wichtigen Bereich eingegeben hat, wird `InsideHyperCriticalRegion` zurückgegeben.|  
  
## Vererbungshierarchie  
 [IThreadProxy](../../../parallel/concrt/reference/ithreadproxy-structure.md)  
  
 `IUMSThreadProxy`  
  
## Anforderungen  
 **Header:** concrtrm.h  
  
 **Namespace:** Parallelität  
  
## Siehe auch  
 [concurrency\-Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [IUMSScheduler\-Struktur](../../../parallel/concrt/reference/iumsscheduler-structure.md)   
 [SchedulerType\-Enumeration](../Topic/SchedulerType%20Enumeration.md)