---
title: Scheduler-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrt/concurrency::Scheduler
dev_langs:
- C++
helpviewer_keywords:
- Scheduler class
ms.assetid: 34cf7961-048d-4852-8a5c-a32f823e3506
caps.latest.revision: 19
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
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: ea4de856528305020e8b082da3a55fcd27df3a64
ms.lasthandoff: 02/24/2017

---
# <a name="scheduler-class"></a>Scheduler-Klasse
Stellt eine Abstraktion für einen Concurrency Runtime-Planer dar.  
  
## <a name="syntax"></a>Syntax  
  
```
class Scheduler;
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="protected-constructors"></a>Geschützte Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Scheduler-Konstruktor](#ctor)|Ein Objekt von der `Scheduler` -Klasse kann nur mit Factorymethoden erstellt oder implizit.|  
|[~ Scheduler-Destruktor](#dtor)|Ein Objekt von der `Scheduler` -Klasse wird implizit zerstört, sobald alle externen Verweise mehr vorhanden sind.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Attach-Methode](#attach)|Fügt den Planer an den aufrufenden Kontext. Nach dem Beenden dieser Methode der aufrufende Kontext wird vom Planer verwaltet, und der Planer wird als aktueller Planer.|  
|[Create-Methode](#create)|Erstellt einen neuen Planer, dessen Verhalten durch beschrieben, die `_Policy` Parameter, platziert einen anfänglichen Verweis auf den Planer und gibt einen Zeiger darauf zurück.|  
|[CreateScheduleGroup-Methode](#createschedulegroup)|Überladen. Erstellt eine neue Planungsgruppe innerhalb des Planers. Die Version, die die Parameter `_Placement` bewirkt, dass Aufgaben in die neu erstellte Planungsgruppe Blockcontainer ausführen an der Position, die durch diesen Parameter angegeben werden.|  
|[GetNumberOfVirtualProcessors-Methode](#getnumberofvirtualprocessors)|Gibt die aktuelle Anzahl virtueller Prozessoren für den Planer zurück.|  
|[GetPolicy-Methode](#getpolicy)|Gibt eine Kopie der Richtlinie, der der Planer erstellt wurde.|  
|[ID-Methode](#id)|Gibt einen eindeutigen Bezeichner für den Planer zurück.|  
|[IsAvailableLocation-Methode](#isavailablelocation)|Bestimmt, ob eine angegebene Position im Zeitplanungsmodul verfügbar ist.|  
|[Reference-Methode](#reference)|Inkrementiert den Verweiszähler für den Planer.|  
|[RegisterShutdownEvent-Methode](#registershutdownevent)|Ursachen, die das Windows-Ereignishandle übergeben der `_Event` -Parameter signalisiert wird, wenn der Planer herunterfährt und zerstört. Zu dem Zeitpunkt, der das Ereignis signalisiert wird, ist die gesamte Arbeit, die auf den Planer geplant wurde abgeschlossen. Mit dieser Methode können mehrere Herunterfahrereignisse registriert werden.|  
|[Release-Methode](#release)|Scheduler Verweiszähler.|  
|[ResetDefaultSchedulerPolicy-Methode](#resetdefaultschedulerpolicy)|Die Standardrichtlinie für den Planer zurückgesetzt auf die Common Language Runtime-Standardeinstellungen. Das nächste Mal, das ein Standardplaner erstellt wird, das wird die Common Language Runtime Standardeinstellungen verwendet.|  
|[ScheduleTask-Methode](#scheduletask)|Überladen. Plant eine einfache Aufgabe innerhalb des Planers. Die einfache Aufgabe wird in einer Planungsgruppe aus, die durch die Laufzeit bestimmt platziert werden. Die Version, die die Parameter `_Placement` bewirkt, dass der Task Blockcontainer am angegebenen Speicherort ausgeführt werden.|  
|[SetDefaultSchedulerPolicy-Methode](#setdefaultschedulerpolicy)|Können eine benutzerdefinierte Richtlinie verwendet werden, um die Standard-Scheduler zu erstellen. Diese Methode kann aufgerufen werden, nur, wenn kein Standardplaner innerhalb des Prozesses vorhanden ist. Nachdem eine Standardrichtlinie festgelegt wurde, bleibt Sie aktiv, bis zum nächsten gültigen Aufruf entweder die `SetDefaultSchedulerPolicy` oder [ResetDefaultSchedulerPolicy](#resetdefaultschedulerpolicy) Methode.|  
  
## <a name="remarks"></a>Hinweise  
 Die Concurrency Runtime-Planer verwendet Ausführungskontexte, die das Betriebssystem Ausführungskontexte, z. B. ein Thread zugeordnet, die zum Ausführen der Arbeit in die Warteschlange eingereiht, von der Anwendung. Zu jedem Zeitpunkt ist die nebenläufigkeitsebene eines Planers gleich der Anzahl virtueller Prozessoren, die vom Ressourcen-Manager gewährt wurden. Ein virtueller Prozessor ist eine Abstraktion für eine Verarbeitungsressource und wird einem Hardwarethread des zugrunde liegenden Systems zugeordnet. Nur ein einzelner Planerkontext kann jeweils auf einem virtuellen Prozessor ausgeführt werden.  
  
 Die Concurrency Runtime erstellt einen Standardplaner pro Prozess, um Arbeit parallel auszuführen. Darüber hinaus können Sie Ihre eigenen Planer Instanzen erstellen und bearbeiten sie mit dieser Klasse.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `Scheduler`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h hinzu  
  
 **Namespace:** Parallelität  
  
##  <a name="a-nameattacha-attach"></a><a name="attach"></a>Anfügen 

 Fügt den Planer an den aufrufenden Kontext. Nach dem Beenden dieser Methode der aufrufende Kontext wird vom Planer verwaltet, und der Planer wird als aktueller Planer.  
  
```
virtual void Attach() = 0;
```  
  
### <a name="remarks"></a>Hinweise  
 Anfügen eines Planers wird implizit platziert einen Verweis auf den Planer.  
  
 Irgendwann in der Zukunft müssen Sie aufrufen, die [CurrentScheduler:: Detach](currentscheduler-class.md#detach) Methode, damit der Planer beendet werden kann.  
  
 Wenn diese Methode aus einem Kontext aufgerufen wird, die bereits an einen anderen Planer angefügt ist, wird der vorhandenen Planer als den vorherigen Planer gespeichert, und der neu erstellte Planer wird als aktueller Planer. Beim Aufrufen der `CurrentScheduler::Detach` -Methode zu einem späteren Zeitpunkt, den vorherigen Planer als aktuellen Planer wiederhergestellt wird.  
  
 Diese Methode löst eine [Improper_scheduler_attach](improper-scheduler-attach-class.md) -Ausnahme aus, wenn dieser Planer dem aktuellen Planer des aufrufenden Kontexts ist.  
  
##  <a name="a-namecreatea-create"></a><a name="create"></a>Erstellen 

 Erstellt einen neuen Planer, dessen Verhalten durch beschrieben, die `_Policy` Parameter, platziert einen anfänglichen Verweis auf den Planer und gibt einen Zeiger darauf zurück.  
  
```
static Scheduler* __cdecl Create(const SchedulerPolicy& _Policy);
```  
  
### <a name="parameters"></a>Parameter  
 `_Policy`  
 Die Planerrichtlinie, die Verhalten des neu erstellten Planers beschreibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf einen neu erstellten Planer. Diese `Scheduler` Objekt verfügt über eine anfängliche Verweisanzahl platziert wird.  
  
### <a name="remarks"></a>Hinweise  
 Nach der Erstellung eines Planers mit der `Create` -Methode, die Sie aufrufen müssen die `Release` Methode zu einem bestimmten Zeitpunkt in der Zukunft um die anfängliche Verweisanzahl entfernt und des Planers beendet.  
  
 Ein Planer erstellt wurde, mit dieser Methode wird nicht an den aufrufenden Kontext angefügt. Sie können mit einem Kontext angefügt werden die [Anfügen](#attach) Methode.  
  
 Diese Methode kann eine Vielzahl von Ausnahmen auslösen, einschließlich auslösen [Scheduler_resource_allocation_error](scheduler-resource-allocation-error-class.md) und [Invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md).  
  
##  <a name="a-namecreateschedulegroupa-createschedulegroup"></a><a name="createschedulegroup"></a>CreateScheduleGroup 

 Erstellt eine neue Planungsgruppe innerhalb des Planers. Die Version, die die Parameter `_Placement` bewirkt, dass Aufgaben in die neu erstellte Planungsgruppe Blockcontainer ausführen an der Position, die durch diesen Parameter angegeben werden.  
  
```
virtual ScheduleGroup* CreateScheduleGroup() = 0;

virtual ScheduleGroup* CreateScheduleGroup(location& _Placement) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `_Placement`  
 Ein Verweis auf einen Speicherort, in dem die Aufgaben innerhalb der Planungsgruppe wird Blockcontainer ausgeführt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die neu erstellte Planungsgruppe. Diese `ScheduleGroup` Objekt verfügt über eine anfängliche Verweisanzahl platziert wird.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie die [Version](schedulegroup-class.md#release) Methode für eine Planungsgruppe, wenn Sie Planungsarbeit dafür fertig sind. Der Planer zerstört die Planungsgruppe Gruppe, wenn die gesamte Arbeit für sie in der Warteschlange wurde abgeschlossen.  
  
 Beachten Sie, dass Sie diesen Planer explizit erstellt haben, alle Verweise auf Planungsgruppen freigeben müssen, bevor Sie die Verweise auf den Planer freigeben.  
  
##  <a name="a-namegetnumberofvirtualprocessorsa-getnumberofvirtualprocessors"></a><a name="getnumberofvirtualprocessors"></a>GetNumberOfVirtualProcessors 

 Gibt die aktuelle Anzahl virtueller Prozessoren für den Planer zurück.  
  
```
virtual unsigned int GetNumberOfVirtualProcessors() const = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktuelle Anzahl virtueller Prozessoren für den Planer.  
  
##  <a name="a-namegetpolicya-getpolicy"></a><a name="getpolicy"></a>GetPolicy 

 Gibt eine Kopie der Richtlinie, der der Planer erstellt wurde.  
  
```
virtual SchedulerPolicy GetPolicy() const = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Kopie der Richtlinie, der der Planer erstellt wurde.  
  
##  <a name="a-nameida-id"></a><a name="id"></a>ID 

 Gibt einen eindeutigen Bezeichner für den Planer zurück.  
  
```
virtual unsigned int Id() const = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein eindeutiger Bezeichner für den Planer.  
  
##  <a name="a-nameisavailablelocationa-isavailablelocation"></a><a name="isavailablelocation"></a>IsAvailableLocation 

 Bestimmt, ob eine angegebene Position im Zeitplanungsmodul verfügbar ist.  
  
```
virtual bool IsAvailableLocation(const location& _Placement) const = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `_Placement`  
 Ein Verweis auf die Position, an der Planer über Abfragen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Hinweis darauf, ob der Speicherort von angegeben der `_Placement` Argument auf den Planer verfügbar ist.  
  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, dass der Rückgabewert eine sofortige Stichprobe ist, ob am angegebene Speicherort verfügbar ist. Bei mehreren Zeitplanungsmodulen kann dynamische Ressourcen-Manager hinzufügst oder Ressourcen aus den Zeitplanungsmodulen zu einem beliebigen Zeitpunkt. In diesem Fall werden kann die angegebene Position Verfügbarkeit ändern.  
  
##  <a name="a-namereferencea-reference"></a><a name="reference"></a>Referenz 

 Inkrementiert den Verweiszähler für den Planer.  
  
```
virtual unsigned int Reference() = 0 ;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der neu inkrementierte Verweiszähler.  
  
### <a name="remarks"></a>Hinweise  
 Dies wird normalerweise verwendet, um die Lebensdauer des Planers für die Erstellung zu verwalten. Wenn der Verweiszähler ein Scheduler-greift auf&0; (null), der Planer wird heruntergefahren und Destruct selbst nachdem alle arbeiten, auf den Planer abgeschlossen wurde.  
  
 Die Methode löst eine [Improper_scheduler_reference](improper-scheduler-reference-class.md) -Ausnahme aus, wenn der Verweiszähler vor dem Aufrufen der `Reference` Methode NULL war und der Aufruf erfolgt aus einem Kontext, der nicht dem Planer gehört.  
  
##  <a name="a-nameregistershutdowneventa-registershutdownevent"></a><a name="registershutdownevent"></a>RegisterShutdownEvent 

 Ursachen, die das Windows-Ereignishandle übergeben der `_Event` -Parameter signalisiert wird, wenn der Planer herunterfährt und zerstört. Zu dem Zeitpunkt, der das Ereignis signalisiert wird, ist die gesamte Arbeit, die auf den Planer geplant wurde abgeschlossen. Mit dieser Methode können mehrere Herunterfahrereignisse registriert werden.  
  
```
virtual void RegisterShutdownEvent(HANDLE _Event) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `_Event`  
 Ein Handle für ein Windows-Ereignisobjekt, das von der Laufzeit signalisiert wird, wenn der Planer herunterfährt und zerstört.  
  
##  <a name="a-namereleasea-release"></a><a name="release"></a>Version 

 Scheduler Verweiszähler.  
  
```
virtual unsigned int Release() = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der neu dekrementierte Verweiszähler.  
  
### <a name="remarks"></a>Hinweise  
 Dies wird normalerweise verwendet, um die Lebensdauer des Planers für die Erstellung zu verwalten. Wenn der Verweiszähler ein Scheduler-greift auf&0; (null), der Planer wird heruntergefahren und Destruct selbst nachdem alle arbeiten, auf den Planer abgeschlossen wurde.  
  
##  <a name="a-nameresetdefaultschedulerpolicya-resetdefaultschedulerpolicy"></a><a name="resetdefaultschedulerpolicy"></a>ResetDefaultSchedulerPolicy 

 Die Standardrichtlinie für den Planer zurückgesetzt auf die Common Language Runtime-Standardeinstellungen. Das nächste Mal, das ein Standardplaner erstellt wird, das wird die Common Language Runtime Standardeinstellungen verwendet.  
  
```
static void __cdecl ResetDefaultSchedulerPolicy();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode kann aufgerufen werden, während ein Standardplaner innerhalb des Prozesses vorhanden ist. Die Richtlinie des vorhandenen Standardplaners sind davon nicht betroffen. Jedoch wenn Standardplaner wurden beendet, und ein neuer Standardwert zu einem späteren Zeitpunkt erstellt werden, verwenden die neue Planer die Common Language Runtime Standardeinstellungen.  
  
##  <a name="a-namectora-scheduler"></a><a name="ctor"></a>Scheduler 

 Ein Objekt von der `Scheduler` -Klasse kann nur mit Factorymethoden erstellt oder implizit.  
  
```
Scheduler();
```  
  
### <a name="remarks"></a>Hinweise  
 Standardplaner des Prozesses wird implizit erstellt, wenn Sie viele der Laufzeitfunktionen, wofür einen Planer an den aufrufenden Kontext angefügt werden muss. Methoden in der `CurrentScheduler` -Klasse und Funktionen der PPL und die Agents Ebenen normalerweise implizite Anlage ausführen.  
  
 Sie können auch einen Planer explizit durch Erstellen der `CurrentScheduler::Create` -Methode oder die `Scheduler::Create` Methode.  
  
##  <a name="a-namedtora-scheduler"></a><a name="dtor"></a>~ Scheduler 

 Ein Objekt von der `Scheduler` -Klasse wird implizit zerstört, sobald alle externen Verweise mehr vorhanden sind.  
  
```
virtual ~Scheduler();
```  
  
##  <a name="a-namescheduletaska-scheduletask"></a><a name="scheduletask"></a>ScheduleTask 

 Plant eine einfache Aufgabe innerhalb des Planers. Die einfache Aufgabe wird in einer Planungsgruppe aus, die durch die Laufzeit bestimmt platziert werden. Die Version, die die Parameter `_Placement` bewirkt, dass der Task Blockcontainer am angegebenen Speicherort ausgeführt werden.  
  
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
 Ein Zeiger auf die Funktion, die ausgeführt werden, um den Text der Aufgabe leicht durchführen.  
  
 `_Data`  
 Ein void-Zeiger auf die Daten, die in den Text der Aufgabe als Parameter übergeben werden.  
  
 `_Placement`  
 Ein Verweis auf einen Speicherort, in dem die Aufgabe leicht Blockcontainer werden wird ausgeführt.  
  
##  <a name="a-namesetdefaultschedulerpolicya-setdefaultschedulerpolicy"></a><a name="setdefaultschedulerpolicy"></a>SetDefaultSchedulerPolicy 

 Können eine benutzerdefinierte Richtlinie verwendet werden, um die Standard-Scheduler zu erstellen. Diese Methode kann aufgerufen werden, nur, wenn kein Standardplaner innerhalb des Prozesses vorhanden ist. Nachdem eine Standardrichtlinie festgelegt wurde, bleibt Sie aktiv, bis zum nächsten gültigen Aufruf entweder die `SetDefaultSchedulerPolicy` oder [ResetDefaultSchedulerPolicy](#resetdefaultschedulerpolicy) Methode.  
  
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
 [PolicyElementKey-Enumeration](concurrency-namespace-enums.md)   
 [Taskplaner](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)




