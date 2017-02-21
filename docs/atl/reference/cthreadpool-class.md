---
title: "CThreadPool Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CThreadPool"
  - "ATL::CThreadPool"
  - "CThreadPool"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CThreadPool class"
ms.assetid: 06683718-01b9-413c-9481-2dc1734ec70f
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CThreadPool Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt einen Pool von Arbeitsthreads, die eine Warteschlange von Arbeitsaufgaben verarbeiten.  
  
## Syntax  
  
```  
  
      template <  
   class Worker,  
   class ThreadTraits = DefaultThreadTraits  
>  
class CThreadPool :  
   public IThreadPoolConfig  
```  
  
#### Parameter  
 *Worker*  
 Die Klasse in Übereinstimmung mit [Workerprototyp](../../atl/reference/worker-archetype.md), das den Code verwendet den Prozessarbeitsaufgaben in die Warteschlange gestellt im Threadpool bereitstellt.  
  
 `ThreadTraits`  
 Die Klasse, die die Funktion verwendet, um die Threads im Pool zu erstellen bereitstellt.  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CThreadPool::CThreadPool](../Topic/CThreadPool::CThreadPool.md)|Der Konstruktor für den Threadpool.|  
|[CThreadPool::~CThreadPool](../Topic/CThreadPool::~CThreadPool.md)|Der Destruktor für den Threadpool.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CThreadPool::AddRef](../Topic/CThreadPool::AddRef.md)|Implementierung von `IUnknown::AddRef`.|  
|[CThreadPool::GetNumThreads](../Topic/CThreadPool::GetNumThreads.md)|Rufen Sie diese Methode auf, um die Anzahl der Threads im Pool abzurufen.|  
|[CThreadPool::GetQueueHandle](../Topic/CThreadPool::GetQueueHandle.md)|Rufen Sie diese Methode auf, um das Handle des EA\-Abschlussanschlusses abzurufen, der verwendet wird, um Arbeitsaufgaben in die Warteschlange stellen.|  
|[CThreadPool::GetSize](../Topic/CThreadPool::GetSize.md)|Rufen Sie diese Methode auf, um die Anzahl der Threads im Pool abzurufen.|  
|[CThreadPool::GetTimeout](../Topic/CThreadPool::GetTimeout.md)|Rufen Sie diese Methode auf, um die maximale Zeit in Millisekunden abzurufen, dass der Threadpool auf einen Thread wartet, um herunterzufahren.|  
|[CThreadPool::Initialize](../Topic/CThreadPool::Initialize.md)|Rufen Sie diese Methode auf, um den Threadpool zu initialisieren.|  
|[CThreadPool::QueryInterface](../Topic/CThreadPool::QueryInterface.md)|Implementierung von **IUnknown::QueryInterface**.|  
|[CThreadPool::QueueRequest](../Topic/CThreadPool::QueueRequest.md)|Rufen Sie diese Methode auf, um eine von einem Thread im Pool behandelt werden Arbeitsaufgabe in die Warteschlange zu stellen.|  
|[CThreadPool::Release](../Topic/CThreadPool::Release.md)|Implementierung von `IUnknown::Release`.|  
|[CThreadPool::SetSize](../Topic/CThreadPool::SetSize.md)|Rufen Sie diese Methode auf, um die Anzahl der Threads im Pool festzulegen.|  
|[CThreadPool::SetTimeout](../Topic/CThreadPool::SetTimeout.md)|Rufen Sie diese Methode auf, um die maximale Zeit in Millisekunden festzulegen, dass der Threadpool auf einen Thread wartet, um herunterzufahren.|  
|[CThreadPool::Shutdown](../Topic/CThreadPool::Shutdown.md)|Rufen Sie diese Methode auf, um den Threadpool herunterzufahren.|  
  
## Hinweise  
 Threads im Pool werden erstellt und zerstört, wenn der Pool initialisiert, Größe geändert oder beendet wird.  Eine Instanz von Klasse *Worker* wird auf dem Stapel eines Arbeitsthreads im Pool erstellt.  Jede Instanz lebt während der Lebensdauer des Threads.  
  
 Fügen Sie unmittelbar nach Erstellung eines Threads, wird Worker::`Initialize` um das Objekt aufgerufen, das diesem Thread zugeordnet ist.  Fügen Sie unmittelbar vor Zerstörung eines Threads, wird Worker::`Terminate` aufgerufen.  Beide Methoden müssen ein **void\***\-Argument akzeptieren.  Der Wert dieses Arguments wird an den Threadpool durch den `pvWorkerParam`\-Parameter von [CThreadPool::Initialize](../Topic/CThreadPool::Initialize.md) übergeben.  
  
 Wenn es Arbeitsaufgaben in der Warteschlange und in den Arbeitsthreads gibt, die für Arbeit verfügbar sind, wird ein Arbeitsthread ein Element aus der Warteschlange ab und ruft die Methode des **Execute***Workerobjekts* für diesen Thread auf.  Drei Elemente werden dann an die Methode übergeben: das Element aus der Warteschlange, gleicher `pvWorkerParam` übergeben Worker::`Initialize` und zu Worker::`Terminate` und einen Zeiger auf die [ÜBERLAPPEND](http://msdn.microsoft.com/library/windows/desktop/ms684342)\-Struktur verwendet für die EA\-Abschlussanschlusswarteschlange.  
  
 Die *Workerklasse* deklariert den Typ der Elemente, die im Threadpool in die Warteschlange gestellt werden, indem eine Typdefinition, Worker::`RequestType` bereitstellt.  Dieser Typ muss in umgewandelt werden in und aus **ULONG\_PTR** anzeigen können.  
  
 Ein Beispiel einer *Worker* klasse ist [CNonStatelessWorker Class](../../atl/reference/cnonstatelessworker-class.md).  
  
## Vererbungshierarchie  
 `IUnknown`  
  
 [IThreadPoolConfig](../../atl/reference/ithreadpoolconfig-interface.md)  
  
 `CThreadPool`  
  
## Anforderungen  
 **Header:** atlutil.h  
  
## Siehe auch  
 [IThreadPoolConfig Interface](../../atl/reference/ithreadpoolconfig-interface.md)   
 [DefaultThreadTraits](../Topic/DefaultThreadTraits.md)   
 [Klassen](../../atl/reference/atl-classes.md)