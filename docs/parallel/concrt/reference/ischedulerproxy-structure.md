---
title: ISchedulerProxy-Struktur | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ISchedulerProxy
- CONCRTRM/concurrency::ISchedulerProxy
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::BindContext
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::CreateOversubscriber
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::RequestInitialVirtualProcessors
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::Shutdown
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::SubscribeCurrentThread
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::UnbindContext
dev_langs: C++
helpviewer_keywords: ISchedulerProxy structure
ms.assetid: af416973-7a1c-4c30-aa3b-4161c2aaea54
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d650df9c77b6a99c7ee9982caa88e8eb7c1b8d9d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="ischedulerproxy-structure"></a>ISchedulerProxy-Struktur
Die Schnittstelle, über die Planer mit dem Ressourcen-Manager der Concurrency Runtime kommunizieren, um die Ressourcenzuordnung auszuhandeln.  
  
## <a name="syntax"></a>Syntax  
  
```
struct ISchedulerProxy;
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[ISchedulerProxy:: BindContext](#bindcontext)|Ordnet einen Ausführungskontext ein Threadproxy, wenn es nicht bereits einem zugeordnet ist.|  
|[ISchedulerProxy:: CreateOversubscriber](#createoversubscriber)|Erstellt einen neuen virtuellen Prozessorstamm auf dem einer vorhandenen Ausführungsressource zugeordneten Hardwarethread.|  
|[ISchedulerProxy:: RequestInitialVirtualProcessors](#requestinitialvirtualprocessors)|Fordert eine anfängliche Zuordnung der Stämme virtueller Prozessoren an. Jeder virtuelle Prozessorstamm stellt die Möglichkeit, ein Thread auszuführen, die Arbeit für den Planer ausführen können.|  
|[ISchedulerProxy:: Shutdown](#shutdown)|Benachrichtigt den Ressourcen-Manager, dass der Planer beendet wird. Dies bewirkt, dass alle Ressourcen, die auf den Planer gewährt sofort freigeben der Ressourcen-Manager.|  
|[ISchedulerProxy:: SubscribeCurrentThread](#subscribecurrentthread)|Registriert den aktuellen Thread mit dem Ressourcen-Manager für diesen Planer zuordnen.|  
|[ISchedulerProxy:: UnbindContext](#unbindcontext)|Hebt die Zuordnung eines Threadproxys aus dem Ausführungskontext, der gemäß der `pContext` Parameter und gibt ihn an die Thread-Proxy-Factory freien Pool zurück. Diese Methode kann nur aufgerufen werden, auf einem Ausführungskontext, der über gebunden war die [BindContext](#bindcontext) Methode und noch nicht über wird gestartet der `pContext` Parameter ein [IThreadProxy:: SwitchTo ](ithreadproxy-structure.md#switchto) -Methodenaufruf.|  
  
## <a name="remarks"></a>Hinweise  
 Der Ressourcen-Manager übergibt eine `ISchedulerProxy` Schnittstelle, um jedes Zeitplanungsmodul, das zusammen mit registriert die [IResourceManager:: RegisterScheduler](iresourcemanager-structure.md#registerscheduler) Methode.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `ISchedulerProxy`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrtrm.h  
  
 **Namespace:** Parallelität  
  
##  <a name="bindcontext"></a>ISchedulerProxy:: BindContext-Methode  
 Ordnet einen Ausführungskontext ein Threadproxy, wenn es nicht bereits einem zugeordnet ist.  
  
```
virtual void BindContext(_Inout_ IExecutionContext* pContext) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `pContext`  
 Eine Schnittstelle zum Ausführungskontext, ein Threadproxy zugeordnet werden soll.  
  
### <a name="remarks"></a>Hinweise  
 In der Regel wird die [IThreadProxy:: SwitchTo](ithreadproxy-structure.md#switchto) Methode bindet einen Threadproxy zu einem Ausführungskontext bei Bedarf. Es gibt jedoch Situationen es erforderlich ist, um einen Kontext im voraus, um sicherzustellen, dass binden die `SwitchTo` Methode wechselt zu einem bereits gebundenen Kontext. Dies ist die Groß-/Kleinschreibung auf ein UMS Kontext planen, wie sie Methoden aufrufen kann, die belegt werden, und binden einen Threadproxy möglicherweise speicherbelegung umfassen, wenn ein Threadproxy in den freien Pool mit der Threadproxy-Factory nicht sofort verfügbar ist.  
  
 `invalid_argument`wird ausgelöst, wenn der Parameter `pContext` hat den Wert `NULL`.  
  
##  <a name="createoversubscriber"></a>ISchedulerProxy:: CreateOversubscriber-Methode  
 Erstellt einen neuen virtuellen Prozessorstamm auf dem einer vorhandenen Ausführungsressource zugeordneten Hardwarethread.  
  
```
virtual IVirtualProcessorRoot* CreateOversubscriber(_Inout_ IExecutionResource* pExecutionResource) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `pExecutionResource`  
 Ein `IExecutionResource` Schnittstelle, die den Hardwarethread darstellt überzeichnen werden sollen.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine `IVirtualProcessorRoot`-Schnittstelle.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, wenn der Planer für einen begrenzten Zeitraum einen bestimmten Hardwarethread überzeichnen möchte. Sobald Sie mit der virtuellen Prozessorstamm fertig sind, sollten Sie es auf die Ressourcen-Manager zurückkehren, indem die [entfernen](iexecutionresource-structure.md#remove) Methode für die `IVirtualProcessorRoot` Schnittstelle.  
  
 Sie können auch einen vorhandenen virtuellen Prozessorstamm überzeichnen, da die `IVirtualProcessorRoot` Schnittstelle erbt von der `IExecutionResource` Schnittstelle.  
  
##  <a name="requestinitialvirtualprocessors"></a>ISchedulerProxy:: RequestInitialVirtualProcessors-Methode  
 Fordert eine anfängliche Zuordnung der Stämme virtueller Prozessoren an. Jeder virtuelle Prozessorstamm stellt die Möglichkeit, ein Thread auszuführen, die Arbeit für den Planer ausführen können.  
  
```
virtual IExecutionResource* RequestInitialVirtualProcessors(bool doSubscribeCurrentThread) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `doSubscribeCurrentThread`  
 Ob abonnieren den aktuellen Thread, und berücksichtigen sie bei der Ressourcenzuordnung.  
  
### <a name="return-value"></a>Rückgabewert  
 Die `IExecutionResource` Schnittstelle für den aktuellen Thread, wenn der Parameter `doSubscribeCurrentThread` hat den Wert `true`. Wenn der Wert `false`, gibt die Methode `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Bevor Sie ein Planer keine Arbeiten ausgeführt wird, sollten sie diese Methode verwenden, um Stämme virtueller Prozessoren vom Ressourcen-Manager anzufordern. Der Ressourcen-Manager wird die Richtlinie des Planers Zugriff mit [GetPolicy](ischeduler-structure.md#getpolicy) und verwenden Sie die Werte für die Richtlinienschlüssel `MinConcurrency`, `MaxConcurrency` und `TargetOversubscriptionFactor` um zu bestimmen, wie viele Hardwarethreads Zuweisen der Scheduler anfänglich und wie viele Stämme virtueller Prozessoren für jeden Hardwarethread zu erstellen. Weitere Informationen, wie Planerrichtlinien verwendet werden, um einen Planer anfängliche Zuordnung zu bestimmen, finden Sie unter [PolicyElementKey](concurrency-namespace-enums.md).  
  
 Der Ressourcen-Manager gewährt Ressourcen an einen Planer durch Aufrufen der Methode [AddVirtualProcessors](ischeduler-structure.md#addvirtualprocessors) mit einer Liste der Stämme virtueller Prozessoren. Die Methode wird als Rückruf in den Planer aufgerufen, bevor diese Methode zurückgegeben.  
  
 Wenn der Planer Abonnement für den aktuellen Thread angefordert, der Parameter `doSubscribeCurrentThread` auf `true`, die Methode gibt ein `IExecutionResource` Schnittstelle. Das Abonnement muss zu einem späteren Zeitpunkt beendet werden, mithilfe der [IExecutionResource:: Remove](iexecutionresource-structure.md#remove) Methode.  
  
 Beim bestimmen, welche Hardwarethreads ausgewählt sind, versucht der Ressourcen-Manager, die Prozessoraffinität-Knoten zu optimieren. Wenn Abonnements für den aktuellen Thread angefordert wird, ist dies ein Hinweis, der der aktuelle Thread beabsichtigt zur Teilnahme an der Arbeit, die auf diesem Planer zugewiesen. In diesem Fall die Stämme zugeordneten virtuellen Prozessoren die Prozessorknoten befinden sich auf denen der aktuelle Thread auf, wenn möglich ausgeführt wird.  
  
 Das Abonnieren eines Threads Abonnementebene des zugrunde liegenden Hardwarethreads wird um eins erhöht. Abonnementebene wird um eins verringert, wenn das Abonnement beendet wird. Weitere Informationen zu Abonnementebenen finden Sie unter [IExecutionResource:: CurrentSubscriptionLevel](iexecutionresource-structure.md#currentsubscriptionlevel).  
  
##  <a name="shutdown"></a>ISchedulerProxy:: Shutdown-Methode  
 Benachrichtigt den Ressourcen-Manager, dass der Planer beendet wird. Dies bewirkt, dass alle Ressourcen, die auf den Planer gewährt sofort freigeben der Ressourcen-Manager.  
  
```
virtual void Shutdown() = 0;
```  
  
### <a name="remarks"></a>Hinweise  
 Alle `IExecutionContext` Schnittstellen für den Planer, die als Ergebnis ein externes Threads, die mit den Methoden abonnieren empfangen `ISchedulerProxy::RequestInitialVirtualProcessors` oder `ISchedulerProxy::SubscribeCurrentThread` muss zurückgegeben werden, um die Ressourcen-Manager mit `IExecutionResource::Remove` , bevor ein Planer herunterfährt.  
  
 Wenn der Planer über deaktivierte Stämme virtueller Prozessoren, müssen Sie Sie aktivieren, mit [IVirtualProcessorRoot](ivirtualprocessorroot-structure.md#activate), und haben die Threadproxys darauf ausführen lassen die `Dispatch` Methode der Ausführung Kontexte sie verteilen sind, bevor Sie aufrufen `Shutdown` auf einen Planerproxy.  
  
 Es ist nicht erforderlich für das Zeitplanungsmodul einzeln Zurückgeben aller der Stämme virtueller Prozessoren über Aufrufe von gewährt der Ressourcen-Manager die `Remove` Methode, da alle virtuellen Prozessorstämme beim Herunterfahren des Computers, der Ressourcen-Manager zurückgegeben werden.  
  
##  <a name="subscribecurrentthread"></a>ISchedulerProxy:: SubscribeCurrentThread-Methode  
 Registriert den aktuellen Thread mit dem Ressourcen-Manager für diesen Planer zuordnen.  
  
```
virtual IExecutionResource* SubscribeCurrentThread() = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die `IExecutionResource` Schnittstelle, die den aktuellen Thread in der Laufzeit darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, wenn der Ressourcen-Manager für den aktuellen Thread berücksichtigen Sie beim Zuordnen von Ressourcen zu Ihrem Planer und andere Planer verwendet werden soll. Er ist besonders nützlich, wenn der Thread plant zur Teilnahme an der Arbeit für den Planer, zusammen mit der Stämme virtueller Prozessoren in der Warteschlange, die der Planer vom Ressourcen-Manager empfängt. Der Ressourcen-Manager verwendet Informationen, um unnötige Überzeichnung von Hardwarethreads auf dem System zu verhindern.  
  
 Über diese Methode empfangene Ausführungsressource zum Ressourcen-Manager zurückgegeben werden soll mithilfe der [IExecutionResource:: Remove](iexecutionresource-structure.md#remove) Methode. Der aufrufende Thread den `Remove` Methode muss im selben Thread, der zuvor aufgerufen werden der `SubscribeCurrentThread` Methode.  
  
 Das Abonnieren eines Threads Abonnementebene des zugrunde liegenden Hardwarethreads wird um eins erhöht. Abonnementebene wird um eins verringert, wenn das Abonnement beendet wird. Weitere Informationen zu Abonnementebenen finden Sie unter [IExecutionResource:: CurrentSubscriptionLevel](iexecutionresource-structure.md#currentsubscriptionlevel).  
  
##  <a name="unbindcontext"></a>ISchedulerProxy:: UnbindContext-Methode  
 Hebt die Zuordnung eines Threadproxys aus dem Ausführungskontext, der gemäß der `pContext` Parameter und gibt ihn an die Thread-Proxy-Factory freien Pool zurück. Diese Methode kann nur aufgerufen werden, auf einem Ausführungskontext, der über gebunden war die [BindContext](#bindcontext) Methode und noch nicht über wird gestartet der `pContext` Parameter ein [IThreadProxy:: SwitchTo ](ithreadproxy-structure.md#switchto) -Methodenaufruf.  
  
```
virtual void UnbindContext(_Inout_ IExecutionContext* pContext) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `pContext`  
 Der Ausführungskontext, dessen Threadproxy aufheben.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [IScheduler-Struktur](ischeduler-structure.md)   
 [IThreadProxy-Struktur](ithreadproxy-structure.md)   
 [IVirtualProcessorRoot-Struktur](ivirtualprocessorroot-structure.md)   
 [IResourceManager-Struktur](iresourcemanager-structure.md)
