---
title: IScheduler-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IScheduler
- CONCRTRM/concurrency::IScheduler
- CONCRTRM/concurrency::IScheduler::IScheduler::AddVirtualProcessors
- CONCRTRM/concurrency::IScheduler::IScheduler::GetId
- CONCRTRM/concurrency::IScheduler::IScheduler::GetPolicy
- CONCRTRM/concurrency::IScheduler::IScheduler::NotifyResourcesExternallyBusy
- CONCRTRM/concurrency::IScheduler::IScheduler::NotifyResourcesExternallyIdle
- CONCRTRM/concurrency::IScheduler::IScheduler::RemoveVirtualProcessors
- CONCRTRM/concurrency::IScheduler::IScheduler::Statistics
dev_langs:
- C++
helpviewer_keywords:
- IScheduler structure
ms.assetid: 471de85a-2b1a-4b6d-ab81-2eff2737161e
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
ms.openlocfilehash: 24305fbdded1709ec51270b3a29a239b345a5679
ms.contentlocale: de-de
ms.lasthandoff: 03/17/2017

---
# <a name="ischeduler-structure"></a>IScheduler-Struktur
Eine Schnittstelle zu der Abstraktion eines Arbeitsplaners. Der Ressourcen-Manager der Concurrency Runtime kommuniziert mithilfe dieser Schnittstelle mit Arbeitsplanern.  
  
## <a name="syntax"></a>Syntax  
  
```
struct IScheduler;
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IScheduler:: AddVirtualProcessors](#addvirtualprocessors)|Die Verwendung bereit ein Planers mit einem Satz der Stämme virtueller Prozessoren. Jeder `IVirtualProcessorRoot` Schnittstelle darstellt, das Recht, einen einzelnen Thread auszuführen, der Arbeiten im Auftrag des Planers ausführen können.|  
|[IScheduler:: GetID](#getid)|Gibt einen eindeutigen Bezeichner für den Planer zurück.|  
|[IScheduler:: GetPolicy](#getpolicy)|Gibt eine Kopie der Richtlinie des Planers zurück. Weitere Informationen über Planerrichtlinien finden Sie unter [SchedulerPolicy](schedulerpolicy-class.md).|  
|[IScheduler:: NotifyResourcesExternallyBusy](#notifyresourcesexternallybusy)|Benachrichtigt diesen Planer, die die durch die Menge der Stämme virtueller Prozessoren im Array Hardwarethreads dargestellten `ppVirtualProcessorRoots` jetzt von anderen Planern verwendet werden.|  
|[IScheduler:: NotifyResourcesExternallyIdle](#notifyresourcesexternallyidle)|Benachrichtigt diesen Planer, die die durch die Menge der Stämme virtueller Prozessoren im Array Hardwarethreads dargestellten `ppVirtualProcessorRoots` nicht von anderen Planern verwendet werden.|  
|[IScheduler:: RemoveVirtualProcessors](#removevirtualprocessors)|Initiiert das Entfernen der Stämme virtueller Prozessoren, die für diesen Planer zuvor zugeordnet wurden.|  
|[IScheduler:: STATISTICS](#statistics)|Enthält Informationen, die im Zusammenhang mit der Aufgabe Eingang und Abschluss von Sätzen und Änderung der Länge der Warteschlange für einen Planer.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie einen benutzerdefinierten Planer, der mit dem Ressourcen-Manager kommuniziert implementieren, sollten Sie eine Implementierung bereitstellen der `IScheduler` Schnittstelle. Diese Schnittstelle ist ein Ende eine bidirektionale Kommunikation zwischen einem Planer und dem Ressourcen-Manager. Das andere Ende wird dargestellt, durch die `IResourceManager` und `ISchedulerProxy` Schnittstellen, die vom Ressourcen-Manager implementiert werden.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IScheduler`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrtrm.h  
  
 **Namespace:** Parallelität  
  
##  <a name="addvirtualprocessors"></a>IScheduler:: AddVirtualProcessors-Methode  
 Die Verwendung bereit ein Planers mit einem Satz der Stämme virtueller Prozessoren. Jeder `IVirtualProcessorRoot` Schnittstelle darstellt, das Recht, einen einzelnen Thread auszuführen, der Arbeiten im Auftrag des Planers ausführen können.  
  
```
virtual void AddVirtualProcessors(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `ppVirtualProcessorRoots`  
 Ein Array von `IVirtualProcessorRoot` Schnittstellen, die den virtuellen Prozessor darstellen Stämme, der Planer hinzugefügt werden.  
  
 `count`  
 Die Anzahl der `IVirtualProcessorRoot` Schnittstellen im Array.  
  
### <a name="remarks"></a>Hinweise  
 Der Ressourcen-Manager ruft die `AddVirtualProcessor` Methode, um einen Anfangssatz von Stämmen virtueller Prozessoren an einem Planer zu erteilen. Es könnte auch aufrufen, die Methode, um auf den Planer virtuelle Prozessorstämme hinzuzufügen, wenn sie Ressourcen unter Planern neu verteilt werden.  
  
##  <a name="getid"></a>IScheduler:: GetID-Methode  
 Gibt einen eindeutigen Bezeichner für den Planer zurück.  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine eindeutige ganzzahlige Bezeichner.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie die [GetSchedulerId](concurrency-namespace-functions.md) Funktion einen eindeutigen Bezeichner für das Objekt abrufen, implementiert die `IScheduler` -Schnittstelle, bevor Sie die Schnittstelle als Parameter für Methoden verwenden der Ressourcen-Manager angegeben. Ihnen wird erwartet, den gleichen Bezeichner zurückzugeben bei der `GetId` -Funktion aufgerufen.  
  
 Ein Bezeichner, der aus einer anderen Quelle erhalten konnte nicht definiertem Verhalten führen.  
  
##  <a name="getpolicy"></a>IScheduler:: GetPolicy-Methode  
 Gibt eine Kopie der Richtlinie des Planers zurück. Weitere Informationen über Planerrichtlinien finden Sie unter [SchedulerPolicy](schedulerpolicy-class.md).  
  
```
virtual SchedulerPolicy GetPolicy() const = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Kopie der Richtlinie des Planers.  
  
##  <a name="notifyresourcesexternallybusy"></a>IScheduler:: NotifyResourcesExternallyBusy-Methode  
 Benachrichtigt diesen Planer, die die durch die Menge der Stämme virtueller Prozessoren im Array Hardwarethreads dargestellten `ppVirtualProcessorRoots` jetzt von anderen Planern verwendet werden.  
  
```
virtual void NotifyResourcesExternallyBusy(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `ppVirtualProcessorRoots`  
 Ein Array von `IVirtualProcessorRoot` Schnittstellen mit den Hardwarethreads auf dem andere Planer ausgelastet.  
  
 `count`  
 Die Anzahl der `IVirtualProcessorRoot` Schnittstellen im Array.  
  
### <a name="remarks"></a>Hinweise  
 Es ist möglich, dass ein bestimmter Hardwarethread zur gleichen Zeit mehreren Planern zugewiesen werden. Ein Grund hierfür ist möglicherweise, dass nicht genügend Hardwarethreads auf dem System, das die minimale Parallelität für alle Planer zu erfüllen, ohne die Freigabe von Ressourcen vorhanden sind. Eine andere Möglichkeit ist, dass Ressourcen vorübergehend für andere Planer zugeordnet sind, wenn die besitzende Planer sie nicht über seine virtuellen Prozessorstämme in diesem Hardwarethread deaktiviert verwendet wird.  
  
 Die Abonnementebene eines Hardwarethreads wird durch die Anzahl der abonnierten Threads gekennzeichnet und aktiviert Stämme virtueller Prozessoren, die diesem Hardwarethread zugeordnet. Aus Sicht eines bestimmten Planers ist die externe Abonnementebene eines Hardwarethreads der Teil des Abonnements, die andere Planer beitragen. Benachrichtigung, dass Ressourcen extern ausgelastet sind an einen Planer gesendet, wenn externe Abonnementebene für einen Hardwarethread von&0; (null) in positive Region verschoben wird.  
  
 Benachrichtigungen über diese Methode nur für Planer, die eine Richtlinie gesendet werden, in denen der Wert für die `MinConcurrency` Richtlinienschlüssel ist gleich dem Wert für die `MaxConcurrency` Richtlinienschlüssel. Weitere Informationen über Planerrichtlinien finden Sie unter [SchedulerPolicy](schedulerpolicy-class.md).  
  
 Ein Planer, der für Benachrichtigungen qualifiziert Ruft die ab der ersten Benachrichtigungen bei der Erstellung, darüber informiert wird, ob die Ressourcen, die sie gerade zugewiesen wurde extern ausgelastet oder im Leerlauf sind.  
  
##  <a name="notifyresourcesexternallyidle"></a>IScheduler:: NotifyResourcesExternallyIdle-Methode  
 Benachrichtigt diesen Planer, die die durch die Menge der Stämme virtueller Prozessoren im Array Hardwarethreads dargestellten `ppVirtualProcessorRoots` nicht von anderen Planern verwendet werden.  
  
```
virtual void NotifyResourcesExternallyIdle(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `ppVirtualProcessorRoots`  
 Ein Array von `IVirtualProcessorRoot` Schnittstellen Hardwarethreads auf dem andere Planer im Leerlauf zugeordnet.  
  
 `count`  
 Die Anzahl der `IVirtualProcessorRoot` Schnittstellen im Array.  
  
### <a name="remarks"></a>Hinweise  
 Es ist möglich, dass ein bestimmter Hardwarethread zur gleichen Zeit mehreren Planern zugewiesen werden. Ein Grund hierfür ist möglicherweise, dass nicht genügend Hardwarethreads auf dem System, das die minimale Parallelität für alle Planer zu erfüllen, ohne die Freigabe von Ressourcen vorhanden sind. Eine andere Möglichkeit ist, dass Ressourcen vorübergehend für andere Planer zugeordnet sind, wenn die besitzende Planer sie nicht über seine virtuellen Prozessorstämme in diesem Hardwarethread deaktiviert verwendet wird.  
  
 Die Abonnementebene eines Hardwarethreads wird durch die Anzahl der abonnierten Threads gekennzeichnet und aktiviert Stämme virtueller Prozessoren, die diesem Hardwarethread zugeordnet. Aus Sicht eines bestimmten Planers ist die externe Abonnementebene eines Hardwarethreads der Teil des Abonnements, die andere Planer beitragen. Benachrichtigung, dass Ressourcen extern ausgelastet sind an einen Planer gesendet, wenn externe Abonnementebene für einen Hardwarethread auf&0; (null), von einer vorherigen positive Wert fällt.  
  
 Benachrichtigungen über diese Methode nur für Planer, die eine Richtlinie gesendet werden, in denen der Wert für die `MinConcurrency` Richtlinienschlüssel ist gleich dem Wert für die `MaxConcurrency` Richtlinienschlüssel. Weitere Informationen über Planerrichtlinien finden Sie unter [SchedulerPolicy](schedulerpolicy-class.md).  
  
 Ein Planer, der für Benachrichtigungen qualifiziert Ruft die ab der ersten Benachrichtigungen bei der Erstellung, darüber informiert wird, ob die Ressourcen, die sie gerade zugewiesen wurde extern ausgelastet oder im Leerlauf sind.  
  
##  <a name="removevirtualprocessors"></a>IScheduler:: RemoveVirtualProcessors-Methode  
 Initiiert das Entfernen der Stämme virtueller Prozessoren, die für diesen Planer zuvor zugeordnet wurden.  
  
```
virtual void RemoveVirtualProcessors(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `ppVirtualProcessorRoots`  
 Ein Array von `IVirtualProcessorRoot` Schnittstellen, die zu entfernenden virtuellen Prozessorstämme darstellen.  
  
 `count`  
 Die Anzahl der `IVirtualProcessorRoot` Schnittstellen im Array.  
  
### <a name="remarks"></a>Hinweise  
 Der Ressourcen-Manager ruft die `RemoveVirtualProcessors` Methode, um einen Anfangssatz der Stämme virtueller Prozessoren von einem Planer zu entfernen. Der Planer wird erwartet, dass das Aufrufen der [entfernen](iexecutionresource-structure.md#remove) -Methode für jede Schnittstelle, wenn die virtuellen Prozessorstämme nicht mehr benötigt werden. Verwenden Sie keine `IVirtualProcessorRoot` Schnittstelle, wenn Sie aufgerufen haben die `Remove` -Methode dafür auf.  
  
 Der Parameter `ppVirtualProcessorRoots` verweist auf ein Array von Schnittstellen. Im Satz der Stämme virtueller Prozessoren entfernt werden, nie die Stämme aktiviert wurden zurückgegeben werden kann, mithilfe der `Remove` Methode. Die Stammelemente, die aktiviert wurden und entweder Arbeit ausführen oder wurde deaktiviert und Arbeit, warten müssen asynchron zurückgegeben werden. Der Planer stellen jeder Versuch, den virtuellen Prozessorstamm so schnell wie möglich zu entfernen. Verzögern des Entfernens der virtuellen Prozessorstämme kann zu einer unbeabsichtigten Überzeichnung innerhalb des Planers führen.  
  
##  <a name="statistics"></a>IScheduler:: Statistics-Methode  
 Enthält Informationen, die im Zusammenhang mit der Aufgabe Eingang und Abschluss von Sätzen und Änderung der Länge der Warteschlange für einen Planer.  
  
```
virtual void Statistics(
    _Out_ unsigned int* pTaskCompletionRate,
    _Out_ unsigned int* pTaskArrivalRate,
    _Out_ unsigned int* pNumberOfTasksEnqueued) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `pTaskCompletionRate`  
 Die Anzahl der Aufgaben, die seit dem letzten Aufruf dieser Methode vom Planer abgeschlossen wurden.  
  
 `pTaskArrivalRate`  
 Die Anzahl der Aufgaben, die seit dem letzten Aufruf dieser Methode im Planer eingetroffen sind.  
  
 `pNumberOfTasksEnqueued`  
 Die Gesamtanzahl der Aufgaben in allen Scheduler-Warteschlangen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Ressourcen-Manager zum Erfassen von Statistiken für einen Planer aufgerufen. Die hier erfasste Statistik dienen zum Steuern des dynamischen Feedback-Algorithmen, um zu bestimmen, wann ist es angebracht, dem Planer weitere Ressourcen zuzuweisen, und wann Ressourcen entfernt werden sollen. Die vom Planer bereitgestellten Werte können optimistisch sein und müssen nicht unbedingt genau wider, die aktuelle Anzahl an.  
  
 Sie sollten diese Methode implementieren, wenn der Ressourcen-Manager Feedback über solche Dinge als Aufgabe Eingang verwenden, bestimmen, wie zum Ausgleichen von Ressourcen zwischen dem Planer und andere Planer mit dem Ressourcen-Manager registriert werden soll. Wenn keine Statistiken erfassen sollen, können Sie festlegen, dass die Richtlinienschlüssel `DynamicProgressFeedback` auf den Wert `DynamicProgressFeedbackDisabled` in der Richtlinie des Planers, und die Ressourcen-Manager nicht ruft diese Methode für den Planer.  
  
 Statistische Informationen vorhanden sind wird der Ressourcen-Manager Hardware Thread Abonnementstufen Ressource Zuweisung und Migration Entscheidungen verwenden. Weitere Informationen zu Abonnementebenen finden Sie unter [IExecutionResource:: CurrentSubscriptionLevel](iexecutionresource-structure.md#currentsubscriptionlevel).  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [PolicyElementKey](concurrency-namespace-enums.md)   
 [SchedulerPolicy-Klasse](schedulerpolicy-class.md)   
 [IExecutionContext-Struktur](iexecutioncontext-structure.md)   
 [IThreadProxy-Struktur](ithreadproxy-structure.md)   
 [IVirtualProcessorRoot-Struktur](ivirtualprocessorroot-structure.md)   
 [IResourceManager-Struktur](iresourcemanager-structure.md)

