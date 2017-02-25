---
title: "CWorkerThread Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CWorkerThread<ThreadTraits>"
  - "ATL::CWorkerThread"
  - "ATL.CWorkerThread"
  - "ATL.CWorkerThread<ThreadTraits>"
  - "CWorkerThread"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWorkerThread class"
ms.assetid: be79a832-1345-4a36-a13e-a406cc65286f
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 27
---
# CWorkerThread Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse erstellt einen Arbeitsthread oder verwendet eine vorhandene, wartet auf eine oder mehrere Kernelobjekthandles und führt eine angegebene Clientfunktion aus, wenn eines der Handles signalisiert wird.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
      template <  
class ThreadTraits= DefaultThreadTraits  
>  
class CWorkerThread  
```  
  
#### Parameter  
 `ThreadTraits`  
 Die Klasse, die die Threaderstellungsfunktion, wie [CRTThreadTraits](../../atl/reference/crtthreadtraits-class.md) oder [Win32ThreadTraits](../../atl/reference/win32threadtraits-class.md) bereitstellt.  
  
## Mitglieder  
  
### Geschützte Strukturen  
  
|Name|Description|  
|----------|-----------------|  
|`WorkerClientEntry`||  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CWorkerThread::CWorkerThread](../Topic/CWorkerThread::CWorkerThread.md)|Der Konstruktor für den Arbeitsthread.|  
|[CWorkerThread::~CWorkerThread](../Topic/CWorkerThread::~CWorkerThread.md)|Der Destruktor für den Arbeitsthread.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CWorkerThread::AddHandle](../Topic/CWorkerThread::AddHandle.md)|Rufen Sie diese Methode auf, um das Handle eines Objekts wait\-fähigen der Liste hinzuzufügen, die durch den Arbeitsthread gespeichert werden.|  
|[CWorkerThread::AddTimer](../Topic/CWorkerThread::AddTimer.md)|Rufen Sie diese Methode auf, um einen regelmäßigen waitable Zeitgeber der Liste hinzuzufügen, die durch den Arbeitsthread gespeichert werden.|  
|[CWorkerThread::GetThreadHandle](../Topic/CWorkerThread::GetThreadHandle.md)|Rufen Sie diese Methode auf, um das Threadhandle des Arbeitsthreads abzurufen.|  
|[CWorkerThread::GetThreadId](../Topic/CWorkerThread::GetThreadId.md)|Rufen Sie diese Methode auf, um die Thread\-IDs des Arbeitsthreads abzurufen.|  
|[CWorkerThread::Initialize](../Topic/CWorkerThread::Initialize.md)|Rufen Sie diese Methode auf, um den Arbeitsthread zu initialisieren.|  
|[CWorkerThread::RemoveHandle](../Topic/CWorkerThread::RemoveHandle.md)|Rufen Sie diese Methode auf, um ein Handle aus der Liste der wait\-fähigen Objekten zu entfernen.|  
|[CWorkerThread::Shutdown](../Topic/CWorkerThread::Shutdown.md)|Rufen Sie diese Methode auf, um den Arbeitsthread herunterzufahren.|  
  
## Hinweise  
  
### So CWorkerThread verwenden  
  
1.  Erstellen Sie eine Instanz dieser Klasse.  
  
2.  Aufruf [CWorkerThread::Initialize](../Topic/CWorkerThread::Initialize.md).  
  
3.  Aufruf [CWorkerThread::AddHandle](../Topic/CWorkerThread::AddHandle.md) mit dem Handle eines Kernelobjekts und einen Zeiger auf eine Implementierung von [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md).  
  
     – oder –  
  
     Rufen Sie [CWorkerThread::AddTimer](../Topic/CWorkerThread::AddTimer.md) mit einem Zeiger auf eine Implementierung von [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md) auf.  
  
4.  Implementieren Sie [IWorkerThreadClient::Execute](../Topic/IWorkerThreadClient::Execute.md), um eine Aktion auszuführen, wenn das Handle oder der Zeitgeber signalisiert wird.  
  
5.  Um ein Objekt aus der Liste der wait\-fähigen Objekte zu entfernen, rufen Sie [CWorkerThread::RemoveHandle](../Topic/CWorkerThread::RemoveHandle.md) auf.  
  
6.  Um den Thread zu beenden, rufen Sie [CWorkerThread::Shutdown](../Topic/CWorkerThread::Shutdown.md) auf.  
  
## Anforderungen  
 **Header:** atlutil.h  
  
## Siehe auch  
 [DefaultThreadTraits](../Topic/DefaultThreadTraits.md)   
 [Klassen](../../atl/reference/atl-classes.md)   
 [Multithreading: Erstellen von Arbeitsthreads](../../parallel/multithreading-creating-worker-threads.md)   
 [IWorkerThreadClient Interface](../../atl/reference/iworkerthreadclient-interface.md)