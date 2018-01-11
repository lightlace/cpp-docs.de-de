---
title: IScheduler-Struktur | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
helpviewer_keywords: IScheduler structure
ms.assetid: 471de85a-2b1a-4b6d-ab81-2eff2737161e
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c639bd760b837923f3011e9209d923fef31f8aee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ischeduler-structure"></a>IScheduler-Struktur
Eine Schnittstelle zu der Abstraktion eines Arbeitsplaners. Der Ressourcen-Manager der Concurrency Runtime kommuniziert mithilfe dieser Schnittstelle mit Arbeitsplanern.  
  
## <a name="syntax"></a>Syntax  
  
```
struct IScheduler;
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IScheduler:: AddVirtualProcessors](#addvirtualprocessors)|Seine Verwendung bereit ein Planers mit einer Reihe von Stämme virtueller Prozessoren. Jede `IVirtualProcessorRoot` Schnittstelle darstellt, das Recht, die einen einzelnen Thread auszuführen, die Arbeit im Auftrag der Planer ausführen können.|  
|[IScheduler:: GetID](#getid)|Gibt einen eindeutigen Bezeichner für den Planer zurück.|  
|[IScheduler:: GetPolicy](#getpolicy)|Gibt eine Kopie der Richtlinie für den Planer zurück. Weitere Informationen über Planerrichtlinien finden Sie unter [SchedulerPolicy](schedulerpolicy-class.md).|  
|[IScheduler:: NotifyResourcesExternallyBusy](#notifyresourcesexternallybusy)|Benachrichtigt diesen Planer, die die Hardwarethreads durch die Menge der Stämme virtueller Prozessoren im Array dargestellt `ppVirtualProcessorRoots` jetzt von anderen Planern verwendet werden.|  
|[IScheduler:: NotifyResourcesExternallyIdle](#notifyresourcesexternallyidle)|Benachrichtigt diesen Planer, die die Hardwarethreads durch die Menge der Stämme virtueller Prozessoren im Array dargestellt `ppVirtualProcessorRoots` werden nicht von anderen Planern verwendet wird.|  
|[IScheduler:: RemoveVirtualProcessors](#removevirtualprocessors)|Initiiert das Entfernen der Stämme virtueller Prozessoren, die zuvor auf diesem Planer zugewiesen wurden.|  
|[IScheduler:: STATISTICS](#statistics)|Enthält Informationen, die im Zusammenhang mit der Aufgabe Eingang und Abschluss von Sätzen und Änderung der Länge der Warteschlange für einen Planer.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie einen benutzerdefinierten Planer, der mit dem Ressourcen-Manager kommuniziert implementieren, sollten Sie eine Implementierung bereitstellen der `IScheduler` Schnittstelle. Diese Schnittstelle ist ein Ende eines Kanals bidirektionale Kommunikation zwischen einem Planer und den Ressourcen-Manager. Das andere Ende wird dargestellt, indem die `IResourceManager` und `ISchedulerProxy` Schnittstellen, die vom Ressourcen-Manager implementiert werden.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `IScheduler`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrtrm.h  
  
 **Namespace:** Parallelität  
  
##  <a name="addvirtualprocessors"></a>IScheduler:: AddVirtualProcessors-Methode  
 Seine Verwendung bereit ein Planers mit einer Reihe von Stämme virtueller Prozessoren. Jede `IVirtualProcessorRoot` Schnittstelle darstellt, das Recht, die einen einzelnen Thread auszuführen, die Arbeit im Auftrag der Planer ausführen können.  
  
```
virtual void AddVirtualProcessors(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `ppVirtualProcessorRoots`  
 Ein Array von `IVirtualProcessorRoot` Stämme Schnittstellen, die den virtuellen Prozessor darstellt, auf den Planer hinzugefügt wird.  
  
 `count`  
 Die Anzahl der `IVirtualProcessorRoot` Schnittstellen im Array.  
  
### <a name="remarks"></a>Hinweise  
 Der Ressourcen-Manager ruft die `AddVirtualProcessor` Methode, um einen anfänglichen Satz von Stämme virtueller Prozessoren an einem Planer zu erteilen. Es könnte auch die Methode, um Stämme virtueller Prozessoren auf den Planer hinzufügen, wenn sie Ressourcen für Planer Nutzung-aufrufen.  
  
##  <a name="getid"></a>IScheduler:: GetID-Methode  
 Gibt einen eindeutigen Bezeichner für den Planer zurück.  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine eindeutige ganzzahlige Bezeichner.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie die [GetSchedulerId](concurrency-namespace-functions.md) Funktion, um einen eindeutigen Bezeichner für das Objekt abrufen, implementiert die `IScheduler` Schnittstelle, die vor der Verwendung von der Schnittstelle als Parameter für Methoden angegeben, der Ressourcen-Manager. Ihnen wird erwartet, den gleichen Bezeichner zurückzugeben bei der `GetId` Funktion aufgerufen wird.  
  
 Ein Bezeichner, der aus einer anderen Quelle abgerufen kann zu nicht definiertem Verhalten führen.  
  
##  <a name="getpolicy"></a>IScheduler:: GetPolicy-Methode  
 Gibt eine Kopie der Richtlinie für den Planer zurück. Weitere Informationen über Planerrichtlinien finden Sie unter [SchedulerPolicy](schedulerpolicy-class.md).  
  
```
virtual SchedulerPolicy GetPolicy() const = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Kopie des Planers Richtlinie.  
  
##  <a name="notifyresourcesexternallybusy"></a>IScheduler:: NotifyResourcesExternallyBusy-Methode  
 Benachrichtigt diesen Planer, die die Hardwarethreads durch die Menge der Stämme virtueller Prozessoren im Array dargestellt `ppVirtualProcessorRoots` jetzt von anderen Planern verwendet werden.  
  
```
virtual void NotifyResourcesExternallyBusy(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `ppVirtualProcessorRoots`  
 Ein Array von `IVirtualProcessorRoot` Schnittstellen, die das Zuordnen von Hardwarethreads auf dem anderen Planer ausgelastet zugeordnet.  
  
 `count`  
 Die Anzahl der `IVirtualProcessorRoot` Schnittstellen im Array.  
  
### <a name="remarks"></a>Hinweise  
 Es ist möglich, für einen bestimmten Hardwarethread gleichzeitig für mehrere Planer zugewiesen werden. Ein Grund dafür ist möglicherweise, dass nicht genügend Hardwarethreads auf dem System die minimale Parallelität für alle Zeitplanungsmodule nicht erfüllen, ohne die Freigabe von Ressourcen. Eine andere Möglichkeit ist, dass Ressourcen für andere Planer vorübergehend zugewiesen werden, wenn die besitzende Planer, nicht über alle virtuellen Prozessorstämme deaktiviert wird Hardware Thread verwendet wird.  
  
 Abonnementebene für einen Hardwarethread ist gekennzeichnet durch die Anzahl der abonnierten Threads und aktiviert Stämme virtueller Prozessoren, die diesem Hardwarethread zugeordnet. Aus Sicht eines bestimmten Planers ist die externe Abonnementebene für einen Hardwarethread der Teil des Abonnements, die andere Planer beitragen. Benachrichtigungen, dass Ressourcen extern ausgelastet sind werden an einen Planer gesendet, wenn externe Abonnementebene für einen Hardwarethread von 0 (null) in positive Territory verschoben wird.  
  
 Benachrichtigungen über diese Methode nur für Planer, die eine Richtlinie gesendet werden, in denen der Wert für die `MinConcurrency` Richtlinienschlüssel ist gleich dem Wert für die `MaxConcurrency` Richtlinienschlüssel. Weitere Informationen über Planerrichtlinien finden Sie unter [SchedulerPolicy](schedulerpolicy-class.md).  
  
 Ein Planer, der für Benachrichtigungen qualifiziert Ruft einen Satz der ersten Benachrichtigungen während der Erstellung, informiert sie, ob die Ressourcen, die sie soeben zugewiesen wurde extern ausgelastet oder im Leerlauf sind.  
  
##  <a name="notifyresourcesexternallyidle"></a>IScheduler:: NotifyResourcesExternallyIdle-Methode  
 Benachrichtigt diesen Planer, die die Hardwarethreads durch die Menge der Stämme virtueller Prozessoren im Array dargestellt `ppVirtualProcessorRoots` werden nicht von anderen Planern verwendet wird.  
  
```
virtual void NotifyResourcesExternallyIdle(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `ppVirtualProcessorRoots`  
 Ein Array von `IVirtualProcessorRoot` Schnittstellen Zuordnen von Hardwarethreads auf dem anderen Planer im Leerlauf zugeordnet.  
  
 `count`  
 Die Anzahl der `IVirtualProcessorRoot` Schnittstellen im Array.  
  
### <a name="remarks"></a>Hinweise  
 Es ist möglich, für einen bestimmten Hardwarethread gleichzeitig für mehrere Planer zugewiesen werden. Ein Grund dafür ist möglicherweise, dass nicht genügend Hardwarethreads auf dem System die minimale Parallelität für alle Zeitplanungsmodule nicht erfüllen, ohne die Freigabe von Ressourcen. Eine andere Möglichkeit ist, dass Ressourcen für andere Planer vorübergehend zugewiesen werden, wenn die besitzende Planer, nicht über alle virtuellen Prozessorstämme deaktiviert wird Hardware Thread verwendet wird.  
  
 Abonnementebene für einen Hardwarethread ist gekennzeichnet durch die Anzahl der abonnierten Threads und aktiviert Stämme virtueller Prozessoren, die diesem Hardwarethread zugeordnet. Aus Sicht eines bestimmten Planers ist die externe Abonnementebene für einen Hardwarethread der Teil des Abonnements, die andere Planer beitragen. Benachrichtigungen, dass Ressourcen extern ausgelastet sind werden an einen Planer gesendet, wenn externe Abonnementebene für einen Hardwarethread auf 0 (null) aus einem vorherigen positive Wert fällt.  
  
 Benachrichtigungen über diese Methode nur für Planer, die eine Richtlinie gesendet werden, in denen der Wert für die `MinConcurrency` Richtlinienschlüssel ist gleich dem Wert für die `MaxConcurrency` Richtlinienschlüssel. Weitere Informationen über Planerrichtlinien finden Sie unter [SchedulerPolicy](schedulerpolicy-class.md).  
  
 Ein Planer, der für Benachrichtigungen qualifiziert Ruft einen Satz der ersten Benachrichtigungen während der Erstellung, informiert sie, ob die Ressourcen, die sie soeben zugewiesen wurde extern ausgelastet oder im Leerlauf sind.  
  
##  <a name="removevirtualprocessors"></a>IScheduler:: RemoveVirtualProcessors-Methode  
 Initiiert das Entfernen der Stämme virtueller Prozessoren, die zuvor auf diesem Planer zugewiesen wurden.  
  
```
virtual void RemoveVirtualProcessors(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `ppVirtualProcessorRoots`  
 Ein Array von `IVirtualProcessorRoot` Schnittstellen, die der Stämme virtueller Prozessoren zu entfernenden darstellt.  
  
 `count`  
 Die Anzahl der `IVirtualProcessorRoot` Schnittstellen im Array.  
  
### <a name="remarks"></a>Hinweise  
 Der Ressourcen-Manager ruft die `RemoveVirtualProcessors` Methode, um wieder einen Satz von Stämme virtueller Prozessoren von einem Planer. Der Planer muss zum Aufrufen der [entfernen](iexecutionresource-structure.md#remove) -Methode für jede Schnittstelle, wenn sie mit der Stämme virtueller Prozessoren erfolgt. Verwenden Sie keine `IVirtualProcessorRoot` Schnittstelle, wenn Sie aufgerufen haben die `Remove` Methode auf.  
  
 Der Parameter `ppVirtualProcessorRoots` verweist auf ein Array von Schnittstellen. In der Gruppe der Stämme virtueller Prozessoren, die entfernt werden, die Stämme nie aktiviert sein kann zurückgegeben werden, sofort mit der `Remove` Methode. Die Stämme, die aktiviert sein und entweder Arbeit ausführen oder wurden deaktiviert und werden in die Arbeit eingehen, wartet sollte asynchron zurückgegeben werden. Der Planer achten jeder Versuch, den virtuellen Prozessorstamm so schnell wie möglich zu entfernen. Verzögern der Entfernung von der Stämme virtueller Prozessoren kann zu unbeabsichtigten Überzeichnung innerhalb des Planers führen.  
  
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
 Die Gesamtanzahl von Aufgaben in allen Scheduler-Warteschlangen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Ressourcen-Manager aufgerufen, um Statistiken für einen Planer zu erfassen. Die hier erfasste Statistik wird zum Steuern des dynamischen Feedback-Algorithmen, um zu bestimmen, wann sie mehr Ressourcen auf den Planer zugewiesen geeignet sind und wann vorwegzunehmen Ressourcen verwendet werden. Die Werte, die vom Planer bereitgestellten können optimistisch sein und müssen nicht unbedingt die aktuelle Anzahl korrekt widerspiegelt.  
  
 Sie sollten diese Methode implementieren, wenn Sie die Ressourcen-Manager Feedback über solche Dinge als Task Eingang zu verwenden, um die Ressource zwischen dem Planer und andere Planer mit dem Ressourcen-Manager registriert ausgewogenen bestimmen soll. Wenn Sie auswählen, nicht um die Statistik zusammenzustellen, legen Sie den Richtlinienschlüssel `DynamicProgressFeedback` auf den Wert `DynamicProgressFeedbackDisabled` in dem Planer Richtlinie und die Ressource-Manager nicht ruft diese Methode für den Planer.  
  
 In das Fehlen von statistischen Informationen verwenden der Ressourcen-Manager Hardware Thread Abonnementebenen Ressource Zuordnung und Migration Entscheidungen treffen. Weitere Informationen zu Abonnementebenen finden Sie unter [IExecutionResource:: CurrentSubscriptionLevel](iexecutionresource-structure.md#currentsubscriptionlevel).  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [PolicyElementKey](concurrency-namespace-enums.md)   
 [SchedulerPolicy-Klasse](schedulerpolicy-class.md)   
 [IExecutionContext-Struktur](iexecutioncontext-structure.md)   
 [IThreadProxy-Struktur](ithreadproxy-structure.md)   
 [IVirtualProcessorRoot-Struktur](ivirtualprocessorroot-structure.md)   
 [IResourceManager-Struktur](iresourcemanager-structure.md)
