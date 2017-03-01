---
title: IExecutionResource-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrtrm/concurrency::IExecutionResource
dev_langs:
- C++
helpviewer_keywords:
- IExecutionResource structure
ms.assetid: 6b27042b-b98c-4f7f-b831-566950af84cd
caps.latest.revision: 16
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
ms.sourcegitcommit: fa774c7f025b581d65c28d65d83e22ff2d798230
ms.openlocfilehash: 530fd40409a08be6ae13ad604deb5b85989b2964
ms.lasthandoff: 02/24/2017

---
# <a name="iexecutionresource-structure"></a>IExecutionResource-Struktur
Eine Abstraktion für einen Hardwarethread.  
  
## <a name="syntax"></a>Syntax  
  
```
struct IExecutionResource;
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IExecutionResource:: CurrentSubscriptionLevel-Methode](#currentsubscriptionlevel)|Gibt die Anzahl der aktivierten virtuellen Prozessorstämme und abonnierten externen Threads, die derzeit zugeordnete der zugrunde liegenden Hardwarethread, den diese Ausführungsressource darstellt.|  
|[IExecutionResource:: GetExecutionResourceId-Methode](#getexecutionresourceid)|Gibt einen eindeutigen Bezeichner für den Hardwarethread, den dieser Ausführungsressource darstellt.|  
|[IExecutionResource:: GetNodeId-Methode](#getnodeid)|Gibt einen eindeutigen Bezeichner für den Prozessorknoten, zu dem diese Ausführungsressource gehört.|  
|[IExecutionResource:: Remove-Methode](#remove)|Gibt diese Ausführungsressource an den Ressourcen-Manager zurück.|  
  
## <a name="remarks"></a>Hinweise  
 Ressourcen zur Ausführung können eigenständig oder Stämme virtueller Prozessoren zugeordnet. Eine eigenständige Ausführungsressource wird erstellt, wenn ein Thread in der Anwendung ein Threadabonnement erstellt. Die Methoden [ISchedulerProxy:: SubscribeThread](ischedulerproxy-structure.md#subscribecurrentthread) und [ISchedulerProxy:: RequestInitialVirtualProcessors](ischedulerproxy-structure.md#requestinitialvirtualprocessors) Threadabonnements erstellen und Zurückgeben einer `IExecutionResource` Schnittstelle, die das Abonnement darstellt. Erstellen eines Abonnements Thread ist eine Möglichkeit, dem Ressourcen-Manager zu informieren, die ein bestimmter Thread in die Arbeit einbezogen werden an einen Planer, zusammen mit der Stämme virtueller Prozessoren in der Warteschlange, die Ressourcen-Manager dem Planer zugewiesen. Der Ressourcen-Manager verwendet die Informationen zur Vermeidung von Hardwarethreads zu überzeichnen, wo er kann.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IExecutionResource`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrtrm.h  
  
 **Namespace:** Parallelität  
  
##  <a name="a-namecurrentsubscriptionlevela--iexecutionresourcecurrentsubscriptionlevel-method"></a><a name="currentsubscriptionlevel"></a>IExecutionResource:: CurrentSubscriptionLevel-Methode  
 Gibt die Anzahl der aktivierten virtuellen Prozessorstämme und abonnierten externen Threads, die derzeit zugeordnete der zugrunde liegenden Hardwarethread, den diese Ausführungsressource darstellt.  
  
```
virtual unsigned int CurrentSubscriptionLevel() const = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktuelle Abonnementebene.  
  
### <a name="remarks"></a>Hinweise  
 Die Abonnementebene besagt, wie viele aktive Threads dem Hardwarethread zugeordnet sind. Dies gilt nur für Threads, die den Ressourcen-Manager beachtet in Form von abonnierten Threads und virtuelle Prozessorstämme, die Threadproxys aktiv ausführen.  
  
 Aufrufen der Methode [ISchedulerProxy:: SubscribeCurrentThread](ischedulerproxy-structure.md#subscribecurrentthread), oder die Methode [ISchedulerProxy:: RequestInitialVirtualProcessors](ischedulerproxy-structure.md#requestinitialvirtualprocessors) mit dem Parameter `doSubscribeCurrentThread` auf den Wert festgelegt `true` wird die Abonnementebene eines Hardwarethreads um&1; erhöht. Sondern auch Zurückgeben einer `IExecutionResource` Schnittstelle, die das Abonnement darstellt. Ein entsprechender Aufruf von der [IExecutionResource:: Remove](#remove) verringert den Hardwarethread Abonnementebene um eins.  
  
 Aktivieren Sie den Stamm eines virtuellen Prozessors, mit der Methode [IVirtualProcessorRoot:: Activate](ivirtualprocessorroot-structure.md#activate) wird die Abonnementebene eines Hardwarethreads um&1; erhöht. Die Methoden [IVirtualProcessorRoot:: Deactivate](ivirtualprocessorroot-structure.md#deactivate), oder [IExecutionResource:: Remove](#remove) dekrementieren die Abonnementebene um eins, wenn für den Stamm eines aktivierten virtuellen Prozessors aufgerufen.  
  
 Der Ressourcen-Manager verwendet Ebene Abonnementinformationen als eine der Methoden zum bestimmen, wann Ressourcen zwischen Planern zu verschieben.  
  
##  <a name="a-namegetexecutionresourceida--iexecutionresourcegetexecutionresourceid-method"></a><a name="getexecutionresourceid"></a>IExecutionResource:: GetExecutionResourceId-Methode  
 Gibt einen eindeutigen Bezeichner für den Hardwarethread, den dieser Ausführungsressource darstellt.  
  
```
virtual unsigned int GetExecutionResourceId() const = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein eindeutiger Bezeichner für den Hardwarethread, der dieser Ausführungsressource zugrunde liegt.  
  
### <a name="remarks"></a>Hinweise  
 Jedem Hardwarethread wird von der Concurrency Runtime einen eindeutigen Bezeichner zugewiesen. Wenn mehrere Ausführungsressourcen einem Hardwarethread zugeordnet sind Thread, sie haben alle denselben Ausführungsressourcenbezeichner.  
  
##  <a name="a-namegetnodeida--iexecutionresourcegetnodeid-method"></a><a name="getnodeid"></a>IExecutionResource:: GetNodeId-Methode  
 Gibt einen eindeutigen Bezeichner für den Prozessorknoten, zu dem diese Ausführungsressource gehört.  
  
```
virtual unsigned int GetNodeId() const = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein eindeutiger Bezeichner für einen Prozessorknoten.  
  
### <a name="remarks"></a>Hinweise  
 Die Concurrency Runtime stellt Hardwarethreads auf dem System in Gruppen von Prozessorknoten dar. Knoten werden in der Regel von der Hardwaretopologie des Systems abgeleitet. Alle Prozessoren auf einem bestimmten Socket oder einem bestimmten NUMA-Knoten können z. B. auf demselben Prozessorknoten gehören. Der Ressourcen-Manager weist eindeutige Bezeichner zu diesen Knoten ab `0` bis und einschließlich `nodeCount - 1`, wobei `nodeCount` stellt die Gesamtzahl der Prozessorknoten auf dem System.  
  
 Die Anzahl der Knoten abgerufen werden kann, von der Funktion [GetProcessorNodeCount](concurrency-namespace-functions.md).  
  
##  <a name="a-nameremovea--iexecutionresourceremove-method"></a><a name="remove"></a>IExecutionResource:: Remove-Methode  
 Gibt diese Ausführungsressource an den Ressourcen-Manager zurück.  
  
```
virtual void Remove(_Inout_ IScheduler* pScheduler) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `pScheduler`  
 Eine Schnittstelle zum Ausführen der Anforderung zum Entfernen dieser Ausführungsressource Planer.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um eigenständige Ausführungsressourcen sowie Ausführungsressourcen Stämme virtueller Prozessoren an den Ressourcen-Manager zugeordnete zurückzugeben.  
  
 Ist dies eine eigenständige Ausführungsressource erhalten Sie von einer der Methoden [ISchedulerProxy:: SubscribeCurrentThread](ischedulerproxy-structure.md#subscribecurrentthread) oder [ISchedulerProxy:: RequestInitialVirtualProcessors](ischedulerproxy-structure.md#requestinitialvirtualprocessors), Aufrufen der Methode `Remove` Threadabonnement den, der die Ressource erstellt wurde darstellen. Sie sind erforderlich, um alle Threadabonnements beendet wird, vor dem Herunterfahren ein, und rufen müssen `Remove` von Threads, der das Abonnement erstellt.  
  
 Stämme virtueller Prozessoren, können zurückgegeben werden, der Ressourcen-Manager durch Aufrufen der `Remove` -Methode, da die Schnittstelle `IVirtualProcessorRoot` erbt von der `IExecutionResource` Schnittstelle. Müssen Sie möglicherweise Stamm eines virtuellen Prozessors zurückgeben, entweder als Reaktion auf einen Aufruf der [IScheduler:: RemoveVirtualProcessors](ischeduler-structure.md#removevirtualprocessors) -Methode, oder wenn Sie mit den Stamm eines überzeichneten virtuellen Prozessors fertig sind, Sie von erhalten, den [ISchedulerProxy:: CreateOversubscriber](ischedulerproxy-structure.md#createoversubscriber) Methode. Stämme virtueller Prozessoren, es gibt keine Einschränkungen in welchem Thread aufrufen kann die `Remove` Methode.  
  
 `invalid_argument`wird ausgelöst, wenn der Parameter `pScheduler` Wert `NULL`.  
  
 `invalid_operation`wird ausgelöst, wenn der Parameter `pScheduler` unterscheidet sich vom Planer, dass diese Ausführungsressource für oder, bei einer eigenständigen Ausführungsressource erstellt wurde, wenn der aktuelle Thread von dem Thread abweicht, das Threadabonnement erstellt hat.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [IVirtualProcessorRoot-Struktur](ivirtualprocessorroot-structure.md)

