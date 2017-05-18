---
title: ISchedulerProxy-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
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
dev_langs:
- C++
helpviewer_keywords:
- ISchedulerProxy structure
ms.assetid: af416973-7a1c-4c30-aa3b-4161c2aaea54
caps.latest.revision: 18
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 3dd95150022ad94f50b456c84f7dacd2d3cef7c5
ms.contentlocale: de-de
ms.lasthandoff: 03/17/2017

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
|[ISchedulerProxy:: BindContext](#bindcontext)|Ordnet einen Ausführungskontext ein Threadproxy, wenn er nicht bereits zugeordnet ist.|  
|[ISchedulerProxy:: CreateOversubscriber](#createoversubscriber)|Erstellt einen neuen virtuellen Prozessorstamm auf dem einer vorhandenen Ausführungsressource zugeordneten Hardwarethread.|  
|[ISchedulerProxy:: RequestInitialVirtualProcessors](#requestinitialvirtualprocessors)|Fordert eine anfängliche Zuordnung der Stämme virtueller Prozessoren an. Jeder virtuelle Prozessorstamm stellt die Fähigkeit, einen Thread auszuführen, der Arbeiten für den Planer ausführen können.|  
|[ISchedulerProxy:: Shutdown](#shutdown)|Der Ressourcen-Manager benachrichtigt, dass der Planer heruntergefahren wird. Dadurch wird der Ressourcen-Manager sofort alle dem Planer gewährten Ressourcen freizugeben.|  
|[ISchedulerProxy:: SubscribeCurrentThread](#subscribecurrentthread)|Registriert den aktuellen Thread mit der Ressourcen-Manager dem Planer zugeordnet.|  
|[ISchedulerProxy:: UnbindContext](#unbindcontext)|Hebt die Zuordnung eines Threadproxys aus dem angegebenen Ausführungskontext der `pContext` Parameter und an der Threadproxy-Factory den freien Pool zurück. Diese Methode darf nur aufgerufen werden, auf einem Ausführungskontext, der über gebunden war die [ISchedulerProxy:: BindContext](#bindcontext) Methode und noch nicht über wird gestartet der `pContext` Parameter ein [IThreadProxy:: SwitchTo](ithreadproxy-structure.md#switchto) -Methodenaufruf.|  
  
## <a name="remarks"></a>Hinweise  
 Der Ressourcen-Manager übergibt ein `ISchedulerProxy` Schnittstelle jedem Planer, der registriert zusammen mit den [IResourceManager:: RegisterScheduler](iresourcemanager-structure.md#registerscheduler) Methode.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `ISchedulerProxy`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrtrm.h  
  
 **Namespace:** Parallelität  
  
##  <a name="bindcontext"></a>ISchedulerProxy:: BindContext-Methode  
 Ordnet einen Ausführungskontext ein Threadproxy, wenn er nicht bereits zugeordnet ist.  
  
```
virtual void BindContext(_Inout_ IExecutionContext* pContext) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `pContext`  
 Eine Schnittstelle zum Ausführungskontext einen Threadproxy zugeordnet.  
  
### <a name="remarks"></a>Hinweise  
 In der Regel die [IThreadProxy:: SwitchTo](ithreadproxy-structure.md#switchto) -Methode bindet einen Threadproxy einem Ausführungskontext bei Bedarf. Es gibt jedoch Situationen, in denen es erforderlich, einen Kontext im voraus, um sicherzustellen, dass zu binden die `SwitchTo` Methode zu einem bereits gebundenen Kontext wechselt. Dies ist der Fall für eine UMS Kontext planen, wie sie Methoden aufrufen kann, die Speicher reservieren, und binden einen Threadproxy kann speicherbelegung umfassen, wenn ein Threadproxy in den freien Pool der Threadproxy-Factory nicht sofort verfügbar ist.  
  
 `invalid_argument`wird ausgelöst, wenn der Parameter `pContext` hat den Wert `NULL`.  
  
##  <a name="createoversubscriber"></a>ISchedulerProxy:: CreateOversubscriber-Methode  
 Erstellt einen neuen virtuellen Prozessorstamm auf dem einer vorhandenen Ausführungsressource zugeordneten Hardwarethread.  
  
```
virtual IVirtualProcessorRoot* CreateOversubscriber(_Inout_ IExecutionResource* pExecutionResource) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `pExecutionResource`  
 Eine `IExecutionResource` -Schnittstelle, die den Hardwarethread darstellt, überzeichnen.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine `IVirtualProcessorRoot`-Schnittstelle.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, wenn der Planer für einen begrenzten Zeitraum einen bestimmten Hardwarethread überzeichnen möchte. Wenn Sie mit dem virtuellen Prozessorstamm fertig sind, sollten Sie es an den Ressourcen-Manager zurückkehren, indem die [entfernen](iexecutionresource-structure.md#remove) Methode für die `IVirtualProcessorRoot` Schnittstelle.  
  
 Sie können sogar den Stamm eines vorhandenen virtuellen Prozessors überzeichnen, da die `IVirtualProcessorRoot` Schnittstelle erbt von der `IExecutionResource` Schnittstelle.  
  
##  <a name="requestinitialvirtualprocessors"></a>ISchedulerProxy:: RequestInitialVirtualProcessors-Methode  
 Fordert eine anfängliche Zuordnung der Stämme virtueller Prozessoren an. Jeder virtuelle Prozessorstamm stellt die Fähigkeit, einen Thread auszuführen, der Arbeiten für den Planer ausführen können.  
  
```
virtual IExecutionResource* RequestInitialVirtualProcessors(bool doSubscribeCurrentThread) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `doSubscribeCurrentThread`  
 Ob den aktuellen Thread abonnieren und während der Zuweisung für dieses Konto.  
  
### <a name="return-value"></a>Rückgabewert  
 Die `IExecutionResource` Schnittstelle für den aktuellen Thread, wenn der Parameter `doSubscribeCurrentThread` hat den Wert `true`. Wenn der Wert `false`, gibt die Methode `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Bevor ein Planer eine Arbeit ausführt, sollten sie diese Methode verwenden, um virtuelle Prozessorstämme vom Ressourcen-Manager anzufordern. Der Ressourcen-Manager greift auf die Richtlinie des Planers mit [GetPolicy](ischeduler-structure.md#getpolicy) und verwenden Sie die Werte für die Richtlinienschlüssel `MinConcurrency`, `MaxConcurrency` und `TargetOversubscriptionFactor` um zu bestimmen, wie viele Hardwarethreads anfänglich dem Planer zuzuweisen und wie viele Stämme virtueller Prozessoren für jeden Hardwarethread erstellen. Weitere Hinweise, wie Planerrichtlinien verwendet werden, um die ursprüngliche Zuordnung eines Planers zu bestimmen, finden Sie unter [PolicyElementKey](concurrency-namespace-enums.md).  
  
 Der Ressourcen-Manager gewährt Ressourcen an einen Planer durch Aufrufen der Methode [AddVirtualProcessors](ischeduler-structure.md#addvirtualprocessors) mit einer Liste der Stämme virtueller Prozessoren. Die Methode wird als Rückruf in den Planer aufgerufen, bevor diese Methode zurückgibt.  
  
 Wenn der Planer Abonnement für den aktuellen Thread angefordert, der Parameter `doSubscribeCurrentThread` auf `true`, gibt die Methode eine `IExecutionResource` Schnittstelle. Das Abonnement muss zu einem späteren Zeitpunkt beendet werden, mithilfe der [IExecutionResource:: Remove](iexecutionresource-structure.md#remove) Methode.  
  
 Wenn Sie bestimmen, welche Hardwarethreads ausgewählt werden, versucht der Ressourcen-Manager für Knoten Prozessoraffinität optimiert. Wenn das Abonnement für den aktuellen Thread angefordert wird, ist dies ein Hinweis, der der aktuelle Thread zur Teilnahme an der Arbeit mit dem Planer zugewiesen werden soll. In diesem Fall die zugeordneten virtuellen Prozessorstämme den Prozessorknoten befinden sich auf denen der aktuelle Thread, wenn möglich ausgeführt wird.  
  
 Das Abonnieren eines Threads wird die Abonnementebene des zugrunde liegenden Hardwarethreads um eins erhöht. Die Abonnementebene wird um eins reduziert, wenn das Abonnement beendet wird. Weitere Informationen zu Abonnementebenen finden Sie unter [IExecutionResource:: CurrentSubscriptionLevel](iexecutionresource-structure.md#currentsubscriptionlevel).  
  
##  <a name="shutdown"></a>ISchedulerProxy:: Shutdown-Methode  
 Der Ressourcen-Manager benachrichtigt, dass der Planer heruntergefahren wird. Dadurch wird der Ressourcen-Manager sofort alle dem Planer gewährten Ressourcen freizugeben.  
  
```
virtual void Shutdown() = 0;
```  
  
### <a name="remarks"></a>Hinweise  
 Alle `IExecutionContext` Schnittstellen den Planer durch das Abonnieren eines externen Threads mithilfe der Methoden empfangen `ISchedulerProxy::RequestInitialVirtualProcessors` oder `ISchedulerProxy::SubscribeCurrentThread` der Ressourcen-Manager zurückgegeben werden muss mit `IExecutionResource::Remove` , bevor ein Planer herunterfährt.  
  
 Wenn der Planer über deaktivierte virtuelle Prozessorstämme, müssen Sie Sie aktivieren, mit [IVirtualProcessorRoot:: Activate](ivirtualprocessorroot-structure.md#activate), und die Threadproxys darauf ausführen lassen die `Dispatch` Methode der Ausführungskontexte, die sie weiterleiten, bevor Sie aufrufen `Shutdown` auf ein.  
  
 Es ist nicht erforderlich für den Planer einzeln Zurückgeben aller der Stämme virtueller Prozessoren über Aufrufe von gewährt der Ressourcen-Manager die `Remove` Methode, da alle virtuellen Prozessorstämme beim Herunterfahren an den Ressourcen-Manager zurückgegeben werden.  
  
##  <a name="subscribecurrentthread"></a>ISchedulerProxy:: SubscribeCurrentThread-Methode  
 Registriert den aktuellen Thread mit der Ressourcen-Manager dem Planer zugeordnet.  
  
```
virtual IExecutionResource* SubscribeCurrentThread() = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die `IExecutionResource` Schnittstelle, die den aktuellen Thread in der Laufzeit darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, wenn soll der Ressourcen-Manager beim Zuordnen von Ressourcen zu Ihrem Planer und anderen Planern für den aktuellen Thread zu berücksichtigen. Es ist besonders nützlich, wenn der Thread plant zur Teilnahme an der Arbeit für den Planer, zusammen mit der Stämme virtueller Prozessoren in der Warteschlange, die der Planer vom Ressourcen-Manager empfängt. Der Ressourcen-Manager verwendet Informationen, um unnötige Überzeichnung von Hardwarethreads auf dem System zu verhindern.  
  
 Über diese Methode empfangene Ausführungsressource an den Ressourcen-Manager zurückgegeben werden soll mithilfe der [IExecutionResource:: Remove](iexecutionresource-structure.md#remove) Methode. Der aufrufende Thread den `Remove` Methode muss im gleichen Thread, der zuvor aufgerufen werden die `SubscribeCurrentThread` Methode.  
  
 Das Abonnieren eines Threads wird die Abonnementebene des zugrunde liegenden Hardwarethreads um eins erhöht. Die Abonnementebene wird um eins reduziert, wenn das Abonnement beendet wird. Weitere Informationen zu Abonnementebenen finden Sie unter [IExecutionResource:: CurrentSubscriptionLevel](iexecutionresource-structure.md#currentsubscriptionlevel).  
  
##  <a name="unbindcontext"></a>ISchedulerProxy:: UnbindContext-Methode  
 Hebt die Zuordnung eines Threadproxys aus dem angegebenen Ausführungskontext der `pContext` Parameter und an der Threadproxy-Factory den freien Pool zurück. Diese Methode darf nur aufgerufen werden, auf einem Ausführungskontext, der über gebunden war die [ISchedulerProxy:: BindContext](#bindcontext) Methode und noch nicht über wird gestartet der `pContext` Parameter ein [IThreadProxy:: SwitchTo](ithreadproxy-structure.md#switchto) -Methodenaufruf.  
  
```
virtual void UnbindContext(_Inout_ IExecutionContext* pContext) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `pContext`  
 Der Ausführungskontext auf den Threadproxy aufheben.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [IScheduler-Struktur](ischeduler-structure.md)   
 [IThreadProxy-Struktur](ithreadproxy-structure.md)   
 [IVirtualProcessorRoot-Struktur](ivirtualprocessorroot-structure.md)   
 [IResourceManager-Struktur](iresourcemanager-structure.md)

