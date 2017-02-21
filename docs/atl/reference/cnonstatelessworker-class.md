---
title: "CNonStatelessWorker Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CNonStatelessWorker<Worker>"
  - "ATL::CNonStatelessWorker"
  - "ATL.CNonStatelessWorker"
  - "CNonStatelessWorker"
  - "ATL::CNonStatelessWorker<Worker>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CNonStatelessWorker class"
ms.assetid: d00936c6-9e7d-49fb-b87d-417b963367d1
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CNonStatelessWorker Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Empfängt Anforderungen aus einem Threadpool und leitet sie an ein Workerobjekt weiter, die bei jeder Anforderung erstellt und zerstört wird.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
      template <  
class Worker  
>  
class CNonStatelessWorker  
```  
  
#### Parameter  
 *Worker*  
 Eine Arbeitsthreadklasse in Übereinstimmung mit [Workerprototyp](../../atl/reference/worker-archetype.md) geeignet für das Behandeln von den Anforderungen in die Warteschlange gestellt [CThreadPool](../../atl/reference/cthreadpool-class.md) auf.  
  
## Mitglieder  
  
### Öffentliche Typedefs  
  
|Name|Description|  
|----------|-----------------|  
|[CNonStatelessWorker::RequestType](../Topic/CNonStatelessWorker::RequestType.md)|Implementierung von [WorkerArchetype::RequestType](../Topic/WorkerArchetype::RequestType.md).|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CNonStatelessWorker::Execute](../Topic/CNonStatelessWorker::Execute.md)|Implementierung von [WorkerArchetype::Execute](../Topic/WorkerArchetype::Execute.md).|  
|[CNonStatelessWorker::Initialize](../Topic/CNonStatelessWorker::Initialize.md)|Implementierung von [WorkerArchetype::Initialize](../Topic/WorkerArchetype::Initialize.md).|  
|[CNonStatelessWorker::Terminate](../Topic/CNonStatelessWorker::Terminate.md)|Implementierung von [WorkerArchetype::Terminate](../Topic/WorkerArchetype::Terminate.md).|  
  
## Hinweise  
 Diese Klasse ist ein einfacher Arbeitsthread zur Verwendung mit [CThreadPool](../../atl/reference/cthreadpool-class.md).  Diese Klasse stellt keine AnforderungBehandlung Funktionen aus der eigenen.  Stattdessen instanziiert sie eine Instanz *des Workers* pro Anforderung und delegiert die Implementierung der Methoden zu dieser Instanz.  
  
 Der Vorteil dieser Klasse besteht darin, dass eine komfortable Möglichkeit, das Modell für für vorhandene Arbeitsthreadklassen zu ändern.  `CThreadPool` stellt einen einzelnen Worker während der Lebensdauer des Threads, sodass erstellt, wenn der Workerklassen\-Griffzustand, es diesen über mehrere Anforderungen enthält.  Durch Erstellen einfach diese Klasse in der `CNonStatelessWorker` Vorlage, vor der Verwendung mit `CThreadPool` beschränkt ist, die Lebensdauer des Workers und des Zustands, die sie enthält, einer einzelnen Anforderung umschließt.  
  
## Anforderungen  
 **Header:** atlutil.h  
  
## Siehe auch  
 [CThreadPool Class](../../atl/reference/cthreadpool-class.md)   
 [Worker Archetype](../../atl/reference/worker-archetype.md)   
 [Klassen](../../atl/reference/atl-classes.md)