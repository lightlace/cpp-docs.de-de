---
title: CurrentScheduler-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CurrentScheduler
- CONCRT/concurrency::CurrentScheduler
- CONCRT/concurrency::CurrentScheduler::Create
- CONCRT/concurrency::CurrentScheduler::CreateScheduleGroup
- CONCRT/concurrency::CurrentScheduler::Detach
- CONCRT/concurrency::CurrentScheduler::Get
- CONCRT/concurrency::CurrentScheduler::GetNumberOfVirtualProcessors
- CONCRT/concurrency::CurrentScheduler::GetPolicy
- CONCRT/concurrency::CurrentScheduler::Id
- CONCRT/concurrency::CurrentScheduler::IsAvailableLocation
- CONCRT/concurrency::CurrentScheduler::RegisterShutdownEvent
- CONCRT/concurrency::CurrentScheduler::ScheduleTask
dev_langs:
- C++
helpviewer_keywords:
- CurrentScheduler class
ms.assetid: 31c20e0e-4cdf-49b4-8220-d726130aad2b
caps.latest.revision: 20
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
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 9536dd28eeb375f3b9e018539cefb338812e340b
ms.lasthandoff: 03/17/2017

---
# <a name="currentscheduler-class"></a>CurrentScheduler-Klasse
Stellt eine Abstraktion für den aktuellen Planer dar, der dem aufrufenden Kontext zugeordnet ist.  
  
## <a name="syntax"></a>Syntax  
  
```
class CurrentScheduler;
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Erstellen](#create)|Erstellt einen neuen Planer, dessen Verhalten durch beschrieben, die `_Policy` Parameter an den aufrufenden Kontext angefügt. Der neu erstellte Planer wird der aktuelle Planer für den aufrufenden Kontext.|  
|[CreateScheduleGroup](#createschedulegroup)|Überladen. Erstellt eine neue Planungsgruppe innerhalb des Planers, der dem aufrufenden Kontext zugeordnet. Die Version, die die Parameter `_Placement` bewirkt, dass Aufgaben in die neu erstellte Planungsgruppe Blockcontainer ausführen an der Position, die durch diesen Parameter angegeben werden.|  
|[Trennen](#detach)|Trennt den aktuellen Planer vom aufrufenden Kontext und stellt den zuvor angefügten Planer als aktuellen Planer, wieder her, falls vorhanden. Nach dem Beenden dieser Methode im aufrufende Kontext wird dann vom Planer verwaltet, die an den Kontext, der entweder bereits vorher angefügt wurde der `CurrentScheduler::Create` oder `Scheduler::Attach` Methode.|  
|[Erhalten](#get)|Gibt einen Zeiger auf den Planer dem aufrufenden Kontext, auch bezeichnet als aktuellen Planer zugeordnet.|  
|[GetNumberOfVirtualProcessors](#getnumberofvirtualprocessors)|Gibt die aktuelle Anzahl virtueller Prozessoren für den Planer dem aufrufenden Kontext zugeordnet.|  
|[GetPolicy](#getpolicy)|Gibt eine Kopie der Richtlinie, der mit der aktuelle Planer erstellt wurde.|  
|[ID](#id)|Gibt einen eindeutigen Bezeichner für den aktuellen Planer zurück.|  
|[IsAvailableLocation](#isavailablelocation)|Bestimmt, ob eine angegebene Position des aktuellen Planers verfügbar ist.|  
|[RegisterShutdownEvent](#registershutdownevent)|Ursachen, die das Windows-Ereignishandle übergeben der `_ShutdownEvent` -Parameter signalisiert wird, wenn der Planer dem aktuellen Kontext zugeordnete herunterfährt und zerstört. Zu dem Zeitpunkt, der das Ereignis signalisiert wird, ist die gesamte Arbeit, die auf den Planer geplant wurde abgeschlossen. Mit dieser Methode können mehrere Herunterfahrereignisse registriert werden.|  
|[ScheduleTask](#scheduletask)|Überladen. Plant eine einfache Aufgabe innerhalb des Planers, der dem aufrufenden Kontext zugeordnet. Die einfache Aufgabe wird in einer Planungsgruppe aus, die durch die Laufzeit bestimmt platziert werden. Die Version, die die Parameter `_Placement` bewirkt, dass der Task Blockcontainer am angegebenen Speicherort ausgeführt werden.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn kein Planer (finden Sie unter [Scheduler](scheduler-class.md)) zugeordneten im aufrufenden Kontext, viele Methoden innerhalb der `CurrentScheduler` -Klasse Anlage der Standardplaner des Prozesses führen. Dies kann dazu führen, dass der Standardplaner des Prozesses während eines solchen Aufrufs erstellt wird.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CurrentScheduler`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h hinzu  
  
 **Namespace:** Parallelität  
  
##  <a name="create"></a>Erstellen 

 Erstellt einen neuen Planer, dessen Verhalten durch beschrieben, die `_Policy` Parameter an den aufrufenden Kontext angefügt. Der neu erstellte Planer wird der aktuelle Planer für den aufrufenden Kontext.  
  
```
static void __cdecl Create(const SchedulerPolicy& _Policy);
```  
  
### <a name="parameters"></a>Parameter  
 `_Policy`  
 Die Planerrichtlinie, die das Verhalten des neu erstellten Planers beschreibt.  
  
### <a name="remarks"></a>Hinweise  
 Das Anfügen des Planers an den aufrufenden Kontext platziert implizit einen Verweiszähler auf den Planer.  
  
 Nach der Erstellung eines Planers mit der `Create` -Methode, die Sie aufrufen müssen die [CurrentScheduler:: Detach](#detach) Methode zu einem bestimmten Zeitpunkt in der Zukunft, damit der Planer beendet werden kann.  
  
 Wenn diese Methode aus einem Kontext aufgerufen wird, die bereits an einen anderen Planer angefügt ist, wird der vorhandenen Planer als den vorherigen Planer gespeichert, und der neu erstellte Planer wird als aktueller Planer. Beim Aufrufen der `CurrentScheduler::Detach` -Methode zu einem späteren Zeitpunkt, den vorherigen Planer als aktuellen Planer wiederhergestellt wird.  
  
 Diese Methode kann eine Vielzahl von Ausnahmen auslösen, einschließlich auslösen [Scheduler_resource_allocation_error](scheduler-resource-allocation-error-class.md) und [Invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md).  
  
##  <a name="createschedulegroup"></a>CreateScheduleGroup 

 Erstellt eine neue Planungsgruppe innerhalb des Planers, der dem aufrufenden Kontext zugeordnet. Die Version, die die Parameter `_Placement` bewirkt, dass Aufgaben in die neu erstellte Planungsgruppe Blockcontainer ausführen an der Position, die durch diesen Parameter angegeben werden.  
  
```
static ScheduleGroup* __cdecl CreateScheduleGroup();

static ScheduleGroup* __cdecl CreateScheduleGroup(location& _Placement);
```  
  
### <a name="parameters"></a>Parameter  
 `_Placement`  
 Ein Verweis auf einen Speicherort, in dem die Aufgaben innerhalb der Planungsgruppe Blockcontainer werden werden ausgeführt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die neu erstellte Planungsgruppe. Diese `ScheduleGroup` Objekt verfügt über eine anfängliche Verweisanzahl platziert wird.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode führt dazu, dass der Standardplaner des Prozesses erstellt und/oder an den aufrufenden Kontext angefügt wird, wenn derzeit dem aufrufenden Kontext kein Planer zugeordnet ist.  
  
 Rufen Sie die [Version](schedulegroup-class.md#release) Methode für eine Planungsgruppe, wenn Sie Planungsarbeit dafür fertig sind. Der Planer zerstört die Planungsgruppe Gruppe, wenn die gesamte Arbeit für sie in der Warteschlange wurde abgeschlossen.  
  
 Beachten Sie, dass Sie diesen Planer explizit erstellt haben, alle Verweise auf Planungsgruppen freigeben müssen, bevor Sie den Verweis auf den Planer freigeben, indem Sie den aktuellen Kontext zu trennen.  
  
##  <a name="detach"></a>Trennen 

 Trennt den aktuellen Planer vom aufrufenden Kontext und stellt den zuvor angefügten Planer als aktuellen Planer, wieder her, falls vorhanden. Nach dem Beenden dieser Methode im aufrufende Kontext wird dann vom Planer verwaltet, die an den Kontext, der entweder bereits vorher angefügt wurde der `CurrentScheduler::Create` oder `Scheduler::Attach` Methode.  
  
```
static void __cdecl Detach();
```  
  
### <a name="remarks"></a>Hinweise  
 Die `Detach` -Methode entfernt implizit einen Verweiszähler aus dem Planer.  
  
 Wenn kein Planer an den aufrufenden Kontext angefügt ist, das Aufrufen dieser Methode führt zu einem [Scheduler_not_attached](scheduler-not-attached-class.md) ausgelöste Ausnahme.  
  
 Aufrufen dieser Methode aus einem Kontext ist eine interne, über einen Planer oder einen Kontext, der nicht mit einer Methode angefügt wurde der [Scheduler:: Attach](scheduler-class.md#attach) oder [CurrentScheduler:: Create](#create) Methoden, führt zu einer [Improper_scheduler_detach](improper-scheduler-detach-class.md) ausgelöste Ausnahme.  
  
##  <a name="get"></a>Erhalten 

 Gibt einen Zeiger auf den Planer dem aufrufenden Kontext, auch bezeichnet als aktuellen Planer zugeordnet.  
  
```
static Scheduler* __cdecl Get();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den Planer dem aufrufenden Kontext (dem aktuellen Planer) zugeordnet.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode führt dazu, dass der Standardplaner des Prozesses erstellt und/oder an den aufrufenden Kontext angefügt wird, wenn derzeit dem aufrufenden Kontext kein Planer zugeordnet ist. Befindet sich kein zusätzlicher Verweis auf die `Scheduler` von dieser Methode zurückgegebene Objekt.  
  
##  <a name="getnumberofvirtualprocessors"></a>GetNumberOfVirtualProcessors 

 Gibt die aktuelle Anzahl virtueller Prozessoren für den Planer dem aufrufenden Kontext zugeordnet.  
  
```
static unsigned int __cdecl GetNumberOfVirtualProcessors();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn ein Planer dem aufrufenden Kontext, die aktuelle Anzahl virtueller Prozessoren für diesen Planer zugeordnet. andernfalls der Wert `-1`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode führt nicht zu Scheduler-Anlage, wenn der aufrufende Kontext nicht bereits einem Planer zugeordnet ist.  
  
 Der Rückgabewert dieser Methode ist ein einleuchtendes Beispiel für die Anzahl virtueller Prozessoren für den Planer dem aufrufenden Kontext zugeordnet. Dieser Wert kann veraltete Zeitpunkt werden sie zurückgegeben wird.  
  
##  <a name="getpolicy"></a>GetPolicy 

 Gibt eine Kopie der Richtlinie, der mit der aktuelle Planer erstellt wurde.  
  
```
static SchedulerPolicy __cdecl GetPolicy();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Kopie der Richtlinie, mit der aktuelle Planer erstellt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode führt dazu, dass der Standardplaner des Prozesses erstellt und/oder an den aufrufenden Kontext angefügt wird, wenn derzeit dem aufrufenden Kontext kein Planer zugeordnet ist.  
  
##  <a name="id"></a>ID 

 Gibt einen eindeutigen Bezeichner für den aktuellen Planer zurück.  
  
```
static unsigned int __cdecl Id();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn ein Planer dem aufrufenden Kontext, einen eindeutigen Bezeichner für diesen Planer zugeordnet. andernfalls der Wert `-1`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode führt nicht zu Scheduler-Anlage, wenn der aufrufende Kontext nicht bereits einem Planer zugeordnet ist.  
  
##  <a name="isavailablelocation"></a>IsAvailableLocation 

 Bestimmt, ob eine angegebene Position des aktuellen Planers verfügbar ist.  
  
```
static bool __cdecl IsAvailableLocation(const location& _Placement);
```  
  
### <a name="parameters"></a>Parameter  
 `_Placement`  
 Ein Verweis auf die Position, an der aktuellen Planer zu Abfragen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Hinweis darauf, ob der Speicherort von angegeben der `_Placement` Argument steht auf den aktuellen Planer.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode führt nicht zu Scheduler-Anlage, wenn der aufrufende Kontext nicht bereits einem Planer zugeordnet ist.  
  
 Beachten Sie, dass der Rückgabewert eine sofortige Stichprobe ist, ob am angegebene Speicherort verfügbar ist. Bei mehreren Zeitplanungsmodulen kann dynamische Ressourcen-Manager hinzufügst oder Ressourcen aus den Zeitplanungsmodulen zu einem beliebigen Zeitpunkt. In diesem Fall werden kann die angegebene Position Verfügbarkeit ändern.  
  
##  <a name="registershutdownevent"></a>RegisterShutdownEvent 

 Ursachen, die das Windows-Ereignishandle übergeben der `_ShutdownEvent` -Parameter signalisiert wird, wenn der Planer dem aktuellen Kontext zugeordnete herunterfährt und zerstört. Zu dem Zeitpunkt, der das Ereignis signalisiert wird, ist die gesamte Arbeit, die auf den Planer geplant wurde abgeschlossen. Mit dieser Methode können mehrere Herunterfahrereignisse registriert werden.  
  
```
static void __cdecl RegisterShutdownEvent(HANDLE _ShutdownEvent);
```  
  
### <a name="parameters"></a>Parameter  
 `_ShutdownEvent`  
 Ein Handle für ein Windows-Ereignisobjekt, das von der Laufzeit signalisiert wird, wenn der Planer dem aktuellen Kontext zugeordnete herunterfährt und zerstört.  
  
### <a name="remarks"></a>Hinweise  
 Wenn kein Planer an den aufrufenden Kontext angefügt ist, das Aufrufen dieser Methode führt zu einem [Scheduler_not_attached](scheduler-not-attached-class.md) ausgelöste Ausnahme.  
  
##  <a name="scheduletask"></a>ScheduleTask 

 Plant eine einfache Aufgabe innerhalb des Planers, der dem aufrufenden Kontext zugeordnet. Die einfache Aufgabe wird in einer Planungsgruppe aus, die durch die Laufzeit bestimmt platziert werden. Die Version, die die Parameter `_Placement` bewirkt, dass der Task Blockcontainer am angegebenen Speicherort ausgeführt werden.  
  
```
static void __cdecl ScheduleTask(
    TaskProc _Proc,
    _Inout_opt_ void* _Data);

static void __cdecl ScheduleTask(
    TaskProc _Proc,
    _Inout_opt_ void* _Data,
    location& _Placement);
```  
  
### <a name="parameters"></a>Parameter  
 `_Proc`  
 Ein Zeiger auf die Funktion, die ausgeführt werden, um den Text der Aufgabe leicht durchführen.  
  
 `_Data`  
 Ein void-Zeiger auf die Daten, die in den Text der Aufgabe als Parameter übergeben werden.  
  
 `_Placement`  
 Ein Verweis auf einen Speicherort, in dem die Aufgabe leicht Blockcontainer werden wird ausgeführt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode führt dazu, dass der Standardplaner des Prozesses erstellt und/oder an den aufrufenden Kontext angefügt wird, wenn derzeit dem aufrufenden Kontext kein Planer zugeordnet ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [Scheduler-Klasse](scheduler-class.md)   
 [PolicyElementKey](concurrency-namespace-enums.md)   
 [Taskplaner](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)




