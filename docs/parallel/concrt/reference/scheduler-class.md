---
title: Scheduler-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- Scheduler
- CONCRT/concurrency::Scheduler
- CONCRT/concurrency::Scheduler::Scheduler
- CONCRT/concurrency::Scheduler::Attach
- CONCRT/concurrency::Scheduler::Create
- CONCRT/concurrency::Scheduler::CreateScheduleGroup
- CONCRT/concurrency::Scheduler::GetNumberOfVirtualProcessors
- CONCRT/concurrency::Scheduler::GetPolicy
- CONCRT/concurrency::Scheduler::Id
- CONCRT/concurrency::Scheduler::IsAvailableLocation
- CONCRT/concurrency::Scheduler::Reference
- CONCRT/concurrency::Scheduler::RegisterShutdownEvent
- CONCRT/concurrency::Scheduler::Release
- CONCRT/concurrency::Scheduler::ResetDefaultSchedulerPolicy
- CONCRT/concurrency::Scheduler::ScheduleTask
- CONCRT/concurrency::Scheduler::SetDefaultSchedulerPolicy
dev_langs:
- C++
helpviewer_keywords:
- Scheduler class
ms.assetid: 34cf7961-048d-4852-8a5c-a32f823e3506
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f7431776a27668fc1f1c465377f1e947eb36ab99
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="scheduler-class"></a>Scheduler-Klasse
Stellt eine Abstraktion für einen Concurrency Runtime-Planer dar.  
  
## <a name="syntax"></a>Syntax  
  
```
class Scheduler;
```  
  
## <a name="members"></a>Member  
  
### <a name="protected-constructors"></a>Geschützte Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Scheduler](#ctor)|Ein Objekt von der `Scheduler` -Klasse kann nur mit Factorymethoden, erstellt oder implizit.|  
|[~ Scheduler-Destruktor](#dtor)|Ein Objekt von der `Scheduler` Klasse wird implizit zerstört, sobald alle externen Verweise darauf nicht mehr vorhanden.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Anfügen](#attach)|Wird den Planer an den aufrufenden Kontext angefügt. Nach dem Beenden dieser Methode der aufrufende Kontext wird vom Planer verwaltet, und das Zeitplanungsmodul wird als aktueller Planer.|  
|[Create](#create)|Erstellt einen neuen Planer, deren Verhalten, durch beschrieben wird, die `_Policy` Parameter, platziert einen anfänglichen Verweis auf den Planer und gibt einen Zeiger darauf zurück.|  
|[CreateScheduleGroup](#createschedulegroup)|Überladen. Erstellt eine neue Planungsgruppe innerhalb des Planers. Die Version, die den Parameter akzeptiert `_Placement` bewirkt, dass die Aufgaben innerhalb der neu erstellte Planungsgruppe auf Blockcontainer ausführen an der Position, die durch diesen Parameter angegeben werden.|  
|[GetNumberOfVirtualProcessors](#getnumberofvirtualprocessors)|Gibt die aktuelle Anzahl virtueller Prozessoren für den Planer zurück.|  
|[GetPolicy](#getpolicy)|Gibt eine Kopie der Richtlinie, der der Planer erstellt wurde.|  
|[Id](#id)|Gibt einen eindeutigen Bezeichner für den Planer zurück.|  
|[IsAvailableLocation](#isavailablelocation)|Bestimmt, ob eine angegebene Position im Zeitplanungsmodul verfügbar ist.|  
|[Verweis](#reference)|Inkrementiert den Verweiszähler für den Planer.|  
|[RegisterShutdownEvent](#registershutdownevent)|Der Windows-Ereignishandle übergebene Ursachen der `_Event` -Parameter signalisiert wird, wenn der Planer herunterfährt und zerstört. Zum Zeitpunkt der das Ereignis signalisiert wird, ist die gesamte Arbeit, die auf den Planer geplant wurde abgeschlossen. Durch diese Methode können mehrere Herunterfahrereignisse registriert werden.|  
|[Version](#release)|Dekrementiert den Planer Verweiszähler.|  
|[ResetDefaultSchedulerPolicy](#resetdefaultschedulerpolicy)|Die Standardrichtlinie für den Planer zurückgesetzt auf die Common Language Runtime-Standardeinstellungen. Das nächste Mal, das ein Standardplaner erstellt wird, das wird die Standardrichtlinien der Common Language Runtime verwendet.|  
|[ScheduleTask](#scheduletask)|Überladen. Plant eine einfache Aufgabe innerhalb des Planers. Die einfache Aufgabe wird in einer Planungsgruppe aus, die durch die Laufzeit bestimmt platziert werden. Die Version, die den Parameter akzeptiert `_Placement` bewirkt, dass der Task Blockcontainer am angegebenen Speicherort ausgeführt werden.|  
|[SetDefaultSchedulerPolicy](#setdefaultschedulerpolicy)|Können eine benutzerdefinierte Richtlinie zu verwendende Standardplaner erstellen. Diese Methode kann aufgerufen werden, nur wenn kein Standardplaner innerhalb des Prozesses vorhanden ist. Nachdem eine Standardrichtlinie festgelegt wurde, bleibt Sie aktiv, bis zum nächsten gültigen Aufruf entweder die `SetDefaultSchedulerPolicy` oder [ResetDefaultSchedulerPolicy](#resetdefaultschedulerpolicy) Methode.|  
  
## <a name="remarks"></a>Hinweise  
 Die Concurrency Runtime-Planer verwendet Ausführungskontexte, die auf das Betriebssystem Ausführungskontexte, z. B. ein Thread zuordnen, können zum Ausführen der Arbeit in die Warteschlange gestellt, von der Anwendung. Zu jedem Zeitpunkt ist die nebenläufigkeitsebene eines Planers gleich der Anzahl virtueller Prozessoren, die vom Ressourcen-Manager gewährt. Ein virtueller Prozessor ist eine Abstraktion für eine Verarbeitungsressource und wird einem Hardwarethread des zugrunde liegenden Systems zugeordnet. Nur ein einzelner Planerkontext kann jeweils auf einem virtuellen Prozessor ausgeführt werden.  
  
 Die Concurrency Runtime erstellt einen Standardplaner pro Prozess, um parallele Arbeitsvorgänge auszuführen. Darüber hinaus können Sie eigene Scheduler-Instanzen erstellen und bearbeiten sie die Verwendung dieser Klasse.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `Scheduler`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h  
  
 **Namespace:** Parallelität  
  
##  <a name="attach"></a> Anfügen 

 Wird den Planer an den aufrufenden Kontext angefügt. Nach dem Beenden dieser Methode der aufrufende Kontext wird vom Planer verwaltet, und das Zeitplanungsmodul wird als aktueller Planer.  
  
```
virtual void Attach() = 0;
```  
  
### <a name="remarks"></a>Hinweise  
 Anfügen eines Planers implizit platziert einen Verweis auf den Planer.  
  
 Irgendwann in der Zukunft müssen Sie Aufrufen der [CurrentScheduler:: Detach](currentscheduler-class.md#detach) Methode, um der Planer beendet werden kann.  
  
 Wenn diese Methode aus einem Kontext aufgerufen wird, die bereits an einen anderen Planer angefügt ist, das vorhandene Zeitplanungsmodul wird als den vorherigen Planer gespeichert, und die neu erstellte Zeitplanungsmodul wird als aktueller Planer. Beim Aufrufen der `CurrentScheduler::Detach` Methode zu einem späteren Zeitpunkt, den vorherigen Planer als aktuellen Planer wiederhergestellt wird.  
  
 Diese Methode löst eine [Improper_scheduler_attach](improper-scheduler-attach-class.md) -Ausnahme aus, wenn dieser Planer der aktuellen Planer des aufrufenden Kontext ist.  
  
##  <a name="create"></a> Erstellen 

 Erstellt einen neuen Planer, deren Verhalten, durch beschrieben wird, die `_Policy` Parameter, platziert einen anfänglichen Verweis auf den Planer und gibt einen Zeiger darauf zurück.  
  
```
static Scheduler* __cdecl Create(const SchedulerPolicy& _Policy);
```  
  
### <a name="parameters"></a>Parameter  
 `_Policy`  
 Die Planerrichtlinie, die Verhalten des neu erstellten Planers beschreibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf einen neu erstellten Planer. Dies `Scheduler` Objekt hat eine anfängliche Verweiszähler platziert sind.  
  
### <a name="remarks"></a>Hinweise  
 Nach der Erstellung eines Planers mit der `Create` -Methode, die Sie aufrufen müssen die `Release` Methode irgendwann in der Zukunft, um den Verweiszähler zu entfernen und des Planers beendet.  
  
 Ein Planer erstellt, die mit dieser Methode ist nicht an den aufrufenden Kontext angefügt. Sie können mit einem Kontext angefügt werden die [Anfügen](#attach) Methode.  
  
 Diese Methode kann eine Vielzahl von Ausnahmen, einschließlich auslösen [Scheduler_resource_allocation_error](scheduler-resource-allocation-error-class.md) und [Invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md).  
  
##  <a name="createschedulegroup"></a> CreateScheduleGroup 

 Erstellt eine neue Planungsgruppe innerhalb des Planers. Die Version, die den Parameter akzeptiert `_Placement` bewirkt, dass die Aufgaben innerhalb der neu erstellte Planungsgruppe auf Blockcontainer ausführen an der Position, die durch diesen Parameter angegeben werden.  
  
```
virtual ScheduleGroup* CreateScheduleGroup() = 0;

virtual ScheduleGroup* CreateScheduleGroup(location& _Placement) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `_Placement`  
 Ein Verweis auf einen Speicherort, in dem die Aufgaben innerhalb der Planungsgruppe wird Blockcontainer ausgeführt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die neu erstellte Planungsgruppe. Dies `ScheduleGroup` Objekt hat eine anfängliche Verweiszähler platziert sind.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie die [Version](schedulegroup-class.md#release) -Methode für eine Planungsgruppe aus, wenn Sie planen Arbeit fertig sind. Der Planer zerstört den Zeitplan Gruppe, wenn die gesamte Arbeit für sie in der Warteschlange wurde abgeschlossen.  
  
 Beachten Sie, dass Sie diesen Planer explizit erstellt haben, alle Verweise auf Planungsgruppen freigeben müssen, bevor Sie die Verweise auf den Planer freigeben.  
  
##  <a name="getnumberofvirtualprocessors"></a> GetNumberOfVirtualProcessors 

 Gibt die aktuelle Anzahl virtueller Prozessoren für den Planer zurück.  
  
```
virtual unsigned int GetNumberOfVirtualProcessors() const = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktuelle Anzahl virtueller Prozessoren für den Planer.  
  
##  <a name="getpolicy"></a> GetPolicy 

 Gibt eine Kopie der Richtlinie, der der Planer erstellt wurde.  
  
```
virtual SchedulerPolicy GetPolicy() const = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Kopie der Richtlinie, der der Planer erstellt wurde.  
  
##  <a name="id"></a> Id 

 Gibt einen eindeutigen Bezeichner für den Planer zurück.  
  
```
virtual unsigned int Id() const = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein eindeutiger Bezeichner für den Planer.  
  
##  <a name="isavailablelocation"></a> IsAvailableLocation 

 Bestimmt, ob eine angegebene Position im Zeitplanungsmodul verfügbar ist.  
  
```
virtual bool IsAvailableLocation(const location& _Placement) const = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `_Placement`  
 Ein Verweis auf die Position, an der Planer über Abfragen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Hinweis auf der Speicherort fest, ob durch angegeben die `_Placement` Argument im Zeitplanungsmodul verfügbar ist.  
  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, dass der Rückgabewert ist eine sofortige Stichprobe an, ob am angegebene Speicherort verfügbar ist. Bei mehreren verborgenen Zeitplanungsmodulen angezeigt kann dynamische ressourcenverwaltung hinzufügen oder Ressourcen von Zeitplanungsmodulen zu einem beliebigen Zeitpunkt einsenden. Dies geschehen soll, kann die angegebene Position ändern Sie die Verfügbarkeit.  
  
##  <a name="reference"></a> Referenz 

 Inkrementiert den Verweiszähler für den Planer.  
  
```
virtual unsigned int Reference() = 0 ;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der neu inkrementierte Verweiszähler.  
  
### <a name="remarks"></a>Hinweise  
 Dies wird normalerweise zum Verwalten der Lebensdauer des Zeitplanungsmoduls für Komposition verwendet. Wenn der Verweiszähler des ein Planer fällt auf 0 (null), der Planer wird heruntergefahren und Destruct selbst nachdem alle arbeiten, auf dem Zeitplanungsmodul wurde abgeschlossen.  
  
 Die Methode löst eine [Improper_scheduler_reference](improper-scheduler-reference-class.md) -Ausnahme aus, wenn der Verweiszähler vor dem Aufrufen der `Reference` Methode wurde von 0 (null) und der Aufruf erfolgt aus einem Kontext, der nicht im Besitz des Planers ist.  
  
##  <a name="registershutdownevent"></a> RegisterShutdownEvent 

 Der Windows-Ereignishandle übergebene Ursachen der `_Event` -Parameter signalisiert wird, wenn der Planer herunterfährt und zerstört. Zum Zeitpunkt der das Ereignis signalisiert wird, ist die gesamte Arbeit, die auf den Planer geplant wurde abgeschlossen. Durch diese Methode können mehrere Herunterfahrereignisse registriert werden.  
  
```
virtual void RegisterShutdownEvent(HANDLE _Event) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `_Event`  
 Ein Handle für ein Windows-Ereignisobjekt, das von der Laufzeit signalisiert wird, wenn der Planer herunterfährt und zerstört.  
  
##  <a name="release"></a> Version 

 Dekrementiert den Planer Verweiszähler.  
  
```
virtual unsigned int Release() = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der neu dekrementierte Verweiszähler.  
  
### <a name="remarks"></a>Hinweise  
 Dies wird normalerweise zum Verwalten der Lebensdauer des Zeitplanungsmoduls für Komposition verwendet. Wenn der Verweiszähler des ein Planer fällt auf 0 (null), der Planer wird heruntergefahren und Destruct selbst nachdem alle arbeiten, auf dem Zeitplanungsmodul wurde abgeschlossen.  
  
##  <a name="resetdefaultschedulerpolicy"></a> ResetDefaultSchedulerPolicy 

 Die Standardrichtlinie für den Planer zurückgesetzt auf die Common Language Runtime-Standardeinstellungen. Das nächste Mal, das ein Standardplaner erstellt wird, das wird die Standardrichtlinien der Common Language Runtime verwendet.  
  
```
static void __cdecl ResetDefaultSchedulerPolicy();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode kann aufgerufen werden, während ein Standardplaner innerhalb des Prozesses vorhanden ist. Er wirkt sich nicht auf die Richtlinie des vorhandenen Standardplaner aus. Allerdings würde, wenn der Standardplaner wurden zum Herunterfahren und ein neuer Standardwert zu einem späteren Zeitpunkt erstellt werden, das neue Zeitplanungsmodul die Standardrichtlinien der Common Language Runtime verwenden.  
  
##  <a name="ctor"></a> Taskplaner 

 Ein Objekt von der `Scheduler` -Klasse kann nur mit Factorymethoden, erstellt oder implizit.  
  
```
Scheduler();
```  
  
### <a name="remarks"></a>Hinweise  
 Standardplaner des Prozesses wird implizit erstellt, wenn Sie viele der Common Language Runtime-Funktionen, wofür einen Planer an den aufrufenden Kontext angefügt werden müssen. Methoden in der `CurrentScheduler` Klasse und Funktionen von der PPL und die Agents Ebenen normalerweise implizite Anlage ausführen.  
  
 Sie können auch einen Planer entweder explizit durch Erstellen der `CurrentScheduler::Create` Methode oder die `Scheduler::Create` Methode.  
  
##  <a name="dtor"></a> ~ Scheduler 

 Ein Objekt von der `Scheduler` Klasse wird implizit zerstört, sobald alle externen Verweise darauf nicht mehr vorhanden.  
  
```
virtual ~Scheduler();
```  
  
##  <a name="scheduletask"></a> ScheduleTask 

 Plant eine einfache Aufgabe innerhalb des Planers. Die einfache Aufgabe wird in einer Planungsgruppe aus, die durch die Laufzeit bestimmt platziert werden. Die Version, die den Parameter akzeptiert `_Placement` bewirkt, dass der Task Blockcontainer am angegebenen Speicherort ausgeführt werden.  
  
```
virtual void ScheduleTask(
    TaskProc _Proc,
    _Inout_opt_ void* _Data) = 0;

virtual void ScheduleTask(
    TaskProc _Proc,
    _Inout_opt_ void* _Data,
    location& _Placement) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `_Proc`  
 Ein Zeiger auf die Funktion, die ausgeführt werden, um den Text der Lightweight-Aufgabe auszuführen.  
  
 `_Data`  
 Ein void-Zeiger auf die Daten, die in den Text der Aufgabe als Parameter übergeben werden.  
  
 `_Placement`  
 Ein Verweis auf einen Speicherort, in dem die Aufgabe Lightweight-Blockcontainer werden wird ausgeführt.  
  
##  <a name="setdefaultschedulerpolicy"></a> SetDefaultSchedulerPolicy 

 Können eine benutzerdefinierte Richtlinie zu verwendende Standardplaner erstellen. Diese Methode kann aufgerufen werden, nur wenn kein Standardplaner innerhalb des Prozesses vorhanden ist. Nachdem eine Standardrichtlinie festgelegt wurde, bleibt Sie aktiv, bis zum nächsten gültigen Aufruf entweder die `SetDefaultSchedulerPolicy` oder [ResetDefaultSchedulerPolicy](#resetdefaultschedulerpolicy) Methode.  
  
```
static void __cdecl SetDefaultSchedulerPolicy(const SchedulerPolicy& _Policy);
```  
  
### <a name="parameters"></a>Parameter  
 `_Policy`  
 Die Richtlinie als Standardrichtlinie Planer festgelegt werden.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die `SetDefaultSchedulerPolicy` Methode wird aufgerufen, wenn ein Standardplaner bereits innerhalb des Prozesses vorhanden ist, löst die Laufzeit eine [Default_scheduler_exists](default-scheduler-exists-class.md) Ausnahme.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [Scheduler-Klasse](scheduler-class.md)   
 [PolicyElementKey](concurrency-namespace-enums.md)   
 [Taskplaner](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)



