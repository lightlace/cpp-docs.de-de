---
title: CNonStatelessWorker Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CNonStatelessWorker
- ATLUTIL/ATL::CNonStatelessWorker
- ATLUTIL/ATL::CNonStatelessWorker::RequestType
- ATLUTIL/ATL::CNonStatelessWorker::Execute
- ATLUTIL/ATL::CNonStatelessWorker::Initialize
- ATLUTIL/ATL::CNonStatelessWorker::Terminate
dev_langs:
- C++
helpviewer_keywords:
- CNonStatelessWorker class
ms.assetid: d00936c6-9e7d-49fb-b87d-417b963367d1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: de03ded4bc0021a8884f608d10368e3d09c11cf8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32359606"
---
# <a name="cnonstatelessworker-class"></a>CNonStatelessWorker-Klasse
Empfang von Anforderungen von einem Threadpool und übergibt sie bei jeder Anforderung an einen Worker-Objekt, das erstellt und zerstört wird.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class Worker>  
class CNonStatelessWorker
```  
  
#### <a name="parameters"></a>Parameter  
 *Worker*  
 Ein Arbeitsthread Threadklasse entsprechen, das mit der [Worker Urtyp](../../atl/reference/worker-archetype.md) geeignet, für die Verarbeitung von Anforderungen für in die Warteschlange [CThreadPool](../../atl/reference/cthreadpool-class.md).  
  
## <a name="members"></a>Member  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CNonStatelessWorker::RequestType](#requesttype)|Implementierung von [WorkerArchetype::RequestType](worker-archetype.md#requesttype).|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CNonStatelessWorker::Execute](#execute)|Implementierung von [WorkerArchetype::Execute](worker-archetype.md#execute).|  
|[CNonStatelessWorker::Initialize](#initialize)|Implementierung von [WorkerArchetype::Initialize](worker-archetype.md#initialize).|  
|[CNonStatelessWorker::Terminate](#terminate)|Implementierung von [WorkerArchetype::Terminate](worker-archetype.md#terminate).|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse ist für die Verwendung mit einem einfachen Arbeitsthread [CThreadPool](../../atl/reference/cthreadpool-class.md). Diese Klasse stellt keine anforderungsverarbeitung Funktionen, die eigene bereit. Stattdessen instanziiert eine Instanz des *Worker* pro Anforderung und übergibt die Implementierung der Methoden für diese Instanz.  
  
 Der Vorteil dieser Klasse ist, dass es sich um eine praktische Möglichkeit so ändern Sie das Zustandsmodell für vorhandene Klassen von Worker-Threads darstellt. `CThreadPool` Erstellen einen einzelnen Worker für die Lebensdauer des Threads, damit, wenn die Workerklasse den Zustand enthält, es in mehreren Anforderungen aufnehmen kann. Indem einfach dieser Klasse in der `CNonStatelessWorker` Vorlage vor der Verwendung mit `CThreadPool`, die Lebensdauer des Arbeitsthreads und der Status ist beschränkt auf eine einzelne Anforderung enthält.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlutil.h  
  
##  <a name="execute"></a>  CNonStatelessWorker::Execute  
 Implementierung von [WorkerArchetype::Execute](worker-archetype.md#execute).  

  
```
void Execute(
    Worker::RequestType request,
    void* pvWorkerParam,
    OVERLAPPED* pOverlapped);
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erstellt eine Instanz von der *Worker* Klasse auf dem Stapel und die Aufrufe [initialisieren](worker-archetype.md#initialize) für dieses Objekt. Wenn die Initialisierung erfolgreich ist, ruft diese Methode auch [Execute](worker-archetype.md#execute) und [terminieren](worker-archetype.md#terminate) auf dasselbe Objekt.  

  
##  <a name="initialize"></a>  CNonStatelessWorker::Initialize  
 Implementierung von [WorkerArchetype::Initialize](worker-archetype.md#initialize).  
  
```
BOOL Initialize(void* /* pvParam */) throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer "true" zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Klasse führt keine Initialisierungen `Initialize`.  
  
##  <a name="requesttype"></a>  CNonStatelessWorker::RequestType  
 Implementierung von [WorkerArchetype::RequestType](worker-archetype.md#requesttype).  
  
```
typedef Worker::RequestType RequestType;
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Klasse behandelt denselben Typ von Arbeitsaufgabe wie die Klasse für die die *Worker* Template-Parameter. Finden Sie unter [CNonStatelessWorker Übersicht](../../atl/reference/cnonstatelessworker-class.md) für Details.  
  
##  <a name="terminate"></a>  CNonStatelessWorker::Terminate  
 Implementierung von [WorkerArchetype::Terminate](worker-archetype.md#terminate).  
  
```
void Terminate(void* /* pvParam */) throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Klasse führt keine Bereinigung `Terminate`.  
  
## <a name="see-also"></a>Siehe auch  
 [CThreadPool-Klasse](../../atl/reference/cthreadpool-class.md)   
 [Worker Urtyp](../../atl/reference/worker-archetype.md)   
 [Klassen](../../atl/reference/atl-classes.md)
