---
title: Klasse CNonStatelessWorker | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
caps.latest.revision: 21
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 804b87bf752aac5cecf64cb61b4d53d6269963f2
ms.lasthandoff: 02/24/2017

---
# <a name="cnonstatelessworker-class"></a>CNonStatelessWorker-Klasse
Erhält die Anfragen von einem Threadpool und übergibt sie an eine Worker-Objekt, das erstellt und zerstört wird bei jeder Anforderung.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class Worker>  
class CNonStatelessWorker
```  
  
#### <a name="parameters"></a>Parameter  
 *Worker*  
 Eine Worker-Thread-Klasse mit der [Worker Prototyp](../../atl/reference/worker-archetype.md) geeignet, für die Verarbeitung von Anforderungen für in die Warteschlange [CThreadPool](../../atl/reference/cthreadpool-class.md).  
  
## <a name="members"></a>Mitglieder  
  
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
 Diese Klasse ist für die Verwendung mit einem einfachen Arbeitsthread [CThreadPool](../../atl/reference/cthreadpool-class.md). Diese Klasse stellt alle Funktionen Anforderungsbehandlung eigene bereit. In diesem Fall instanziiert eine Instanz des *Worker* pro Anforderung und delegiert die Implementierung der Methoden auf diese Instanz.  
  
 Der Vorteil dieser Klasse ist, dass es sich um eine einfache Möglichkeit, ändern Sie das Zustandsmodell für vorhandene Worker-Thread-Klassen bereitstellt. `CThreadPool`einen einzelnen Worker für die Lebensdauer des Threads erstellt, wenn die Workerklasse den Zustand enthält, es in mehreren Anforderungen aufnehmen kann. Indem es einfach dieser Klasse in der `CNonStatelessWorker` Vorlage vor der Verwendung mit `CThreadPool`, die Lebensdauer von Arbeitskraft und den Status, er ist beschränkt auf eine einzelne Anforderung enthält.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlutil.h  
  
##  <a name="execute"></a>CNonStatelessWorker::Execute  
 Implementierung von [WorkerArchetype::Execute](worker-archetype.md#execute).  

  
```
void Execute(
    Worker::RequestType request,
    void* pvWorkerParam,
    OVERLAPPED* pOverlapped);
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erstellt eine Instanz der *Worker* Klasse auf dem Stapel und die Aufrufe [initialisieren](worker-archetype.md#initialize) für dieses Objekt. Wenn die Initialisierung erfolgreich ist, ruft diese Methode auch [ausführen](worker-archetype.md#execute) und [Terminate](worker-archetype.md#terminate) auf dasselbe Objekt.  

  
##  <a name="initialize"></a>CNonStatelessWorker::Initialize  
 Implementierung von [WorkerArchetype::Initialize](worker-archetype.md#initialize).  
  
```
BOOL Initialize(void* /* pvParam */) throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt immer TRUE zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Klasse führt keine Initialisierung `Initialize`.  
  
##  <a name="requesttype"></a>CNonStatelessWorker::RequestType  
 Implementierung von [WorkerArchetype::RequestType](worker-archetype.md#requesttype).  
  
```
typedef Worker::RequestType RequestType;
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Klasse behandelt denselben Typ von Arbeitsaufgabe wie die Klasse für die *Worker* Template-Parameter. Finden Sie unter [CNonStatelessWorker Übersicht über](../../atl/reference/cnonstatelessworker-class.md) Informationen.  
  
##  <a name="terminate"></a>CNonStatelessWorker::Terminate  
 Implementierung von [WorkerArchetype::Terminate](worker-archetype.md#terminate).  
  
```
void Terminate(void* /* pvParam */) throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Klasse führt keine Bereinigung `Terminate`.  
  
## <a name="see-also"></a>Siehe auch  
 [CThreadPool-Klasse](../../atl/reference/cthreadpool-class.md)   
 [Worker-Prototyp](../../atl/reference/worker-archetype.md)   
 [Klassen](../../atl/reference/atl-classes.md)

