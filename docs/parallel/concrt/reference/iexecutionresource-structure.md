---
title: IExecutionResource-Struktur | Microsoft-Dokumentation
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
ms.openlocfilehash: 9704fc4340d52a32be4571d4cb6f4a7f8af4b67e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46026945"
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
|[IExecutionResource::CurrentSubscriptionLevel](#currentsubscriptionlevel)|Gibt zurück, die Anzahl der aktivierten virtuellen Stämme und abonnierten externen Threads, die derzeit zugeordnet sind, mit dem zugrunde liegenden Hardwarethread, den diese Ausführungsressource darstellt.|  
|[IExecutionResource::GetExecutionResourceId](#getexecutionresourceid)|Gibt einen eindeutigen Bezeichner für den Hardwarethread, den diese Ausführungsressource darstellt.|  
|[IExecutionResource::GetNodeId](#getnodeid)|Gibt einen eindeutigen Bezeichner für den Knoten für Prozessor, zu dem diese Ausführungsressource gehört.|  
|[IExecutionResource::Remove](#remove)|Gibt diese Ausführungsressource an den Resource Manager zurück.|  
  
## <a name="remarks"></a>Hinweise  
 Ressourcen zur Ausführung können eigenständig oder Stämme virtueller Prozessoren zugeordnet. Eine eigenständige Ausführungsressource wird erstellt, wenn ein Thread in Ihrer Anwendung ein Thread erstellt. Die Methoden [ISchedulerProxy:: SubscribeThread](ischedulerproxy-structure.md#subscribecurrentthread) und [ISchedulerProxy:: RequestInitialVirtualProcessors](ischedulerproxy-structure.md#requestinitialvirtualprocessors) Threadabonnements erstellen und Zurückgeben einer `IExecutionResource` Schnittstelle darstellt. die das Abonnement. Erstellen eines Thread-Abonnements ist, dass eine Möglichkeit, den Ressourcen-Manager darüber zu informieren, die ein bestimmter Thread in die Arbeit einbezogen werden, der einem Planer, zusammen mit der Stämme virtueller Prozessoren in die Warteschlange eingereiht, die der Scheduler-Ressourcen-Manager zuweist. Der Ressourcen-Manager verwendet die Informationen um zu vermeiden, Überabonnierung Hardwarethreads können, in denen es verwendet wird.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IExecutionResource`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrtrm.h  
  
 **Namespace:** Parallelität  
  
##  <a name="currentsubscriptionlevel"></a>  IExecutionResource:: CurrentSubscriptionLevel-Methode  
 Gibt zurück, die Anzahl der aktivierten virtuellen Stämme und abonnierten externen Threads, die derzeit zugeordnet sind, mit dem zugrunde liegenden Hardwarethread, den diese Ausführungsressource darstellt.  
  
```
virtual unsigned int CurrentSubscriptionLevel() const = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktuelle Abonnementstufe.  
  
### <a name="remarks"></a>Hinweise  
 Die Abonnementstufe teilt Ihnen mit, wie viele aktive Threads mit der Hardwarethread verknüpft sind. Dies schließt nur die Threads, die den Ressourcen-Manager beachtet in Form von abonnierten Threads und Stämme virtueller Prozessoren, die aktiv Threadproxys ausgeführt werden.  
  
 Aufrufen der Methode [ISchedulerProxy:: SubscribeCurrentThread](ischedulerproxy-structure.md#subscribecurrentthread), oder die Methode [ISchedulerProxy:: RequestInitialVirtualProcessors](ischedulerproxy-structure.md#requestinitialvirtualprocessors) mit dem Parameter `doSubscribeCurrentThread` legen Sie auf den Wert `true`wird die Abonnementstufe des einen Hardwarethread um 1 erhöht. Sondern auch Zurückgeben einer `IExecutionResource` Schnittstelle, die das Abonnement darstellt. Einen zugehörigen Aufruf an die [IExecutionResource:: Remove](#remove) verringert die Hardwarethread Abonnementstufe um eins.  
  
 Das Aktivieren von einem virtuellen Prozessorstamm, die mit der Methode [IVirtualProcessorRoot:: Activate](ivirtualprocessorroot-structure.md#activate) wird die Abonnementstufe des einen Hardwarethread um 1 erhöht. Die Methoden [IVirtualProcessorRoot:: Deactivate](ivirtualprocessorroot-structure.md#deactivate), oder [IExecutionResource:: Remove](#remove) verringern Sie die Abonnementebene um eins, wenn auf einen aktivierten virtuellen Prozessorstamm aufgerufen.  
  
 Der Ressourcen-Manager verwendet die Ebene Abonnementinformationen als eines der Möglichkeiten, um zu bestimmen, wann Ressourcen Zeitplanungsmodulen zu verschieben.  
  
##  <a name="getexecutionresourceid"></a>  IExecutionResource:: GetExecutionResourceId-Methode  
 Gibt einen eindeutigen Bezeichner für den Hardwarethread, den diese Ausführungsressource darstellt.  
  
```
virtual unsigned int GetExecutionResourceId() const = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein eindeutiger Bezeichner für den zugrunde liegenden diese Ausführungsressource Hardwarethread.  
  
### <a name="remarks"></a>Hinweise  
 Jeden Hardwarethread erhält einen eindeutigen Bezeichner von der Concurrency Runtime. Falls mehrere Ressourcen zur Ausführung zugeordnete sind Threads, sie haben alle den gleichen Ressourcenbezeichner für die Ausführung.  
  
##  <a name="getnodeid"></a>  IExecutionResource:: GetNodeId-Methode  
 Gibt einen eindeutigen Bezeichner für den Knoten für Prozessor, zu dem diese Ausführungsressource gehört.  
  
```
virtual unsigned int GetNodeId() const = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein eindeutiger Bezeichner für einen Prozessorknoten.  
  
### <a name="remarks"></a>Hinweise  
 Die Concurrency Runtime stellt Hardwarethreads auf dem System in Gruppen von Prozessorknoten dar. Knoten werden in der Regel von der Hardwaretopologie des Systems abgeleitet. Beispielsweise können alle Prozessoren auf einem bestimmten Socket oder einen bestimmten NUMA-Knoten zu dem gleichen Prozessorknoten gehören. Der Ressourcen-Manager weist eine eindeutige Bezeichner auf diese Knoten beginnend mit `0` bis zu und einschließlich `nodeCount - 1`, wobei `nodeCount` stellt die Gesamtzahl der Prozessorknoten auf dem System.  
  
 Die Anzahl der Knoten erhalten Sie von der Funktion [GetProcessorNodeCount](concurrency-namespace-functions.md).  
  
##  <a name="remove"></a>  IExecutionResource:: Remove-Methode  
 Gibt diese Ausführungsressource an den Resource Manager zurück.  
  
```
virtual void Remove(_Inout_ IScheduler* pScheduler) = 0;
```  
  
### <a name="parameters"></a>Parameter  
*pScheduler*<br/>
Eine Schnittstelle mit dem Planer, der die Anforderung zum Entfernen dieser Ausführungsressource.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um eigenständige Ausführungsressourcen sowie Ausführung zugeordnete virtuelle Prozessorstämme an den Resource Manager zurückzugeben.  
  
 Ist dies eine eigenständige Ausführungsressource erhalten Sie von einer der Methoden [ISchedulerProxy:: SubscribeCurrentThread](ischedulerproxy-structure.md#subscribecurrentthread) oder [ISchedulerProxy:: RequestInitialVirtualProcessors](ischedulerproxy-structure.md#requestinitialvirtualprocessors), wird beim Aufruf der Methode `Remove` endet das Threadabonnement, das die Ressource, um erstellt wurde darstellen. Sie sind erforderlich, um alle Threadabonnements beendet wird, vor dem Herunterfahren eines Scheduler-Proxys und aufrufen, müssen `Remove` von Threads, der das Abonnement erstellt.  
  
 Stämme virtueller Prozessoren zu verwenden, können zurückgegeben werden an den Resource Manager durch Aufrufen der `Remove` -Methode, da die Schnittstelle `IVirtualProcessorRoot` erbt von der `IExecutionResource` Schnittstelle. Möglicherweise müssen Sie einem virtuellen Prozessorstamm entweder als Reaktion auf einen Aufruf zum Zurückgeben der [IScheduler:: RemoveVirtualProcessors](ischeduler-structure.md#removevirtualprocessors) -Methode, oder wenn Sie mit der Stamm eines überzeichneten virtuellen Prozessors haben Sie abgerufen haben die [ ISchedulerProxy:: CreateOversubscriber](ischedulerproxy-structure.md#createoversubscriber) Methode. Für virtuelle Prozessorstämme, es gibt keine Einschränkungen in welchem Thread aufrufen, kann die `Remove` Methode.  
  
 `invalid_argument` wird ausgelöst, wenn der Parameter `pScheduler` nastaven NA hodnotu `NULL`.  
  
 `invalid_operation` wird ausgelöst, wenn der Parameter `pScheduler` unterscheidet sich von der Scheduler, dass diese Ausführungsressource, oder können bei einer eigenständigen Ausführung erstellt wurde, wenn der aktuelle Thread aus dem Thread unterscheidet, die die Threadabonnement erstellt haben.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [IVirtualProcessorRoot-Struktur](ivirtualprocessorroot-structure.md)
