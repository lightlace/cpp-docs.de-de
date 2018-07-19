---
title: IExecutionResource-Struktur | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- IExecutionResource
- CONCRTRM/concurrency::IExecutionResource
- CONCRTRM/concurrency::IExecutionResource::IExecutionResource::CurrentSubscriptionLevel
- CONCRTRM/concurrency::IExecutionResource::IExecutionResource::GetExecutionResourceId
- CONCRTRM/concurrency::IExecutionResource::IExecutionResource::GetNodeId
- CONCRTRM/concurrency::IExecutionResource::IExecutionResource::Remove
dev_langs:
- C++
helpviewer_keywords:
- IExecutionResource structure
ms.assetid: 6b27042b-b98c-4f7f-b831-566950af84cd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dc69c30f30d25179427ee8e59c536bb7cb5b483d
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33692128"
---
# <a name="iexecutionresource-structure"></a>IExecutionResource-Struktur
Eine Abstraktion für einen Hardwarethread.  
  
## <a name="syntax"></a>Syntax  
  
```
struct IExecutionResource;
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IExecutionResource::CurrentSubscriptionLevel](#currentsubscriptionlevel)|Gibt die Anzahl der aktivierten virtuellen Prozessors Stämme und abonnierten externen Threads, die derzeit zugewiesen ist, mit der Hardwarethread des zugrunde liegenden, den diese Ausführungsressource darstellt.|  
|[IExecutionResource::GetExecutionResourceId](#getexecutionresourceid)|Gibt einen eindeutigen Bezeichner für die Hardwarethread, den diese Ausführungsressource darstellt.|  
|[IExecutionResource::GetNodeId](#getnodeid)|Gibt einen eindeutigen Bezeichner für den Prozessorknoten, zu der diese Ausführungsressource gehört.|  
|[IExecutionResource::Remove](#remove)|Gibt diese Ausführungsressource an den Ressourcen-Manager zurück.|  
  
## <a name="remarks"></a>Hinweise  
 Ressourcen zur Ausführung können eigenständig oder Stämme virtueller Prozessoren zugeordnet. Eine eigenständige Ausführungsressource wird erstellt, wenn ein Thread in der Anwendung ein Thread erstellt. Die Methoden [ISchedulerProxy:: SubscribeThread](ischedulerproxy-structure.md#subscribecurrentthread) und [RequestInitialVirtualProcessors](ischedulerproxy-structure.md#requestinitialvirtualprocessors) Threadabonnements erstellen und Zurückgeben einer `IExecutionResource` Schnittstelle darstellt. die das Abonnement. Erstellen eines Abonnements Thread ist eine Möglichkeit, den Ressourcen-Manager zu informieren, die ein bestimmter Thread in die Arbeit einbezogen werden für einen Planer, zusammen mit der Stämme virtueller Prozessoren in der Warteschlange, die Ressourcen-Manager auf den Planer zugewiesen. Der Ressourcen-Manager verwendet die Informationen um zu vermeiden, eine Überabonnierung von Hardwarethreads können, in denen es verwendet wird.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IExecutionResource`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrtrm.h  
  
 **Namespace:** Parallelität  
  
##  <a name="currentsubscriptionlevel"></a>  IExecutionResource:: CurrentSubscriptionLevel-Methode  
 Gibt die Anzahl der aktivierten virtuellen Prozessors Stämme und abonnierten externen Threads, die derzeit zugewiesen ist, mit der Hardwarethread des zugrunde liegenden, den diese Ausführungsressource darstellt.  
  
```
virtual unsigned int CurrentSubscriptionLevel() const = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das aktuelle Abonnementebene.  
  
### <a name="remarks"></a>Hinweise  
 Abonnementebene Aufschluss darüber, wie viele ausgeführten Threads die Hardwarethread zugeordnet sind. Dies schließt nur Threads ab, die die Ressourcen-Manager ist bewusst in Form von abonnierten Threads und Stämme virtueller Prozessoren, die aktiv Threadproxys ausgeführt werden.  
  
 Aufrufen der Methode [ISchedulerProxy:: SubscribeCurrentThread](ischedulerproxy-structure.md#subscribecurrentthread), oder die Methode [RequestInitialVirtualProcessors](ischedulerproxy-structure.md#requestinitialvirtualprocessors) mit dem Parameter `doSubscribeCurrentThread` legen Sie auf den Wert `true`Abonnementebene für einen Hardwarethread um eins erhöht. Sie auch Zurückgeben einer `IExecutionResource` Schnittstelle, die das Abonnement darstellt. Ein entsprechender Aufruf von der [IExecutionResource:: Remove](#remove) verringert die Hardwarethread Abonnementebene um eins.  
  
 Das Aktivieren von einem virtuellen Prozessorstamm mithilfe der Methode [IVirtualProcessorRoot](ivirtualprocessorroot-structure.md#activate) Abonnementebene für einen Hardwarethread um eins erhöht. Die Methoden [IVirtualProcessorRoot:: Deactivate](ivirtualprocessorroot-structure.md#deactivate), oder [IExecutionResource:: Remove](#remove) Abonnementebene Einerschritten beim Aufrufen auf einer aktivierten virtuellen Prozessorstamm zu verringern.  
  
 Der Ressourcen-Manager verwendet die Ebene Abonnementinformationen als eines der Möglichkeiten, um zu bestimmen, wann das Verschieben von Ressourcen zwischen Planern.  
  
##  <a name="getexecutionresourceid"></a>  IExecutionResource:: GetExecutionResourceId-Methode  
 Gibt einen eindeutigen Bezeichner für die Hardwarethread, den diese Ausführungsressource darstellt.  
  
```
virtual unsigned int GetExecutionResourceId() const = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein eindeutiger Bezeichner für die zugrunde liegende diese Ausführungsressource Hardwarethread.  
  
### <a name="remarks"></a>Hinweise  
 Jede Hardwarethread wird von der Concurrency Runtime einen eindeutigen Bezeichner zugewiesen. Wenn mehrere Ausführungsressourcen, die entsprechende Hardware sind Thread, sie haben alle den gleichen Ressourcenbezeichner für die Ausführung.  
  
##  <a name="getnodeid"></a>  IExecutionResource:: GetNodeId-Methode  
 Gibt einen eindeutigen Bezeichner für den Prozessorknoten, zu der diese Ausführungsressource gehört.  
  
```
virtual unsigned int GetNodeId() const = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein eindeutiger Bezeichner für einen Prozessorknoten.  
  
### <a name="remarks"></a>Hinweise  
 Die Concurrency Runtime stellt Hardwarethreads auf dem System in Gruppen von Prozessorknoten dar. Knoten werden in der Regel von der Hardwaretopologie des Systems abgeleitet. Beispielsweise können alle Prozessoren auf einem bestimmten Socket oder einem bestimmten NUMA-Knoten auf dem gleichen Prozessorknoten gehören. Der Ressourcen-Manager weist eindeutige Bezeichner zu diesen Knoten ab `0` bis zu und einschließlich `nodeCount - 1`, wobei `nodeCount` stellt die Gesamtzahl der Prozessorknoten auf dem System.  
  
 Die Anzahl der Knoten abgerufen werden kann, von der Funktion [GetProcessorNodeCount](concurrency-namespace-functions.md).  
  
##  <a name="remove"></a>  IExecutionResource:: Remove-Methode  
 Gibt diese Ausführungsressource an den Ressourcen-Manager zurück.  
  
```
virtual void Remove(_Inout_ IScheduler* pScheduler) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `pScheduler`  
 Eine Schnittstelle auf den Planer Ausführen der Anforderung zum Entfernen dieser Ausführungsressource.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um eigenständige Ausführungsressourcen sowie Ausführungsressourcen Stämme virtueller Prozessoren zum Ressourcen-Manager zugeordnet zurückzugeben.  
  
 Ist dies eine eigenständige Ausführungsressource erhalten Sie von einer der Methoden [ISchedulerProxy:: SubscribeCurrentThread](ischedulerproxy-structure.md#subscribecurrentthread) oder [RequestInitialVirtualProcessors](ischedulerproxy-structure.md#requestinitialvirtualprocessors)wird beim Aufrufen der Methode `Remove` endet die Threadabonnement, das die Ressource erstellt wurde darstellen. Sie sind erforderlich, um alle Threadabonnements zu beenden, bevor Sie einen Planerproxy heruntergefahren und aufrufen, müssen `Remove` aus Threads, der das Abonnement erstellt.  
  
 Stämme virtueller Prozessoren zu, können zurückgegeben werden, der Ressourcen-Manager durch Aufrufen der `Remove` -Methode, da die Schnittstelle `IVirtualProcessorRoot` erbt von der `IExecutionResource` Schnittstelle. Möglicherweise müssen Sie einem virtuellen Prozessorstamm entweder als Antwort auf einen Aufruf zum Zurückgeben der [IScheduler:: RemoveVirtualProcessors](ischeduler-structure.md#removevirtualprocessors) -Methode, oder wenn Sie mit den Stamm eines überzeichneten virtuellen Prozessors Sie erworben haben haben, aus der [ ISchedulerProxy:: CreateOversubscriber](ischedulerproxy-structure.md#createoversubscriber) Methode. Stämme virtueller Prozessoren, es gibt keine Einschränkungen für die Bestimmung des Threads aufgerufen werden soll, können die `Remove` Methode.  
  
 `invalid_argument` wird ausgelöst, wenn der Parameter `pScheduler` festgelegt ist, um `NULL`.  
  
 `invalid_operation` wird ausgelöst, wenn der Parameter `pScheduler` unterscheidet sich vom Planer, dass diese Ausführungsressource, oder können Sie mit der eine eigenständige Ausführungsressource erstellt wurde ist der aktuelle Thread anderen als den Thread, der das Threadabonnement erstellt.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [IVirtualProcessorRoot-Struktur](ivirtualprocessorroot-structure.md)
