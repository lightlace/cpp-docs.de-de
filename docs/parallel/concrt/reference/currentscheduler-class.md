---
title: CurrentScheduler-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
helpviewer_keywords: CurrentScheduler class
ms.assetid: 31c20e0e-4cdf-49b4-8220-d726130aad2b
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ad1d49bb90a5f3c0732fd81851e34485e95f3ccb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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
|[Erstellen](#create)|Erstellt einen neuen Planer, deren Verhalten, durch beschrieben wird, die `_Policy` Parameter und fügt ihn an den aufrufenden Kontext. Der neu erstellte Planer werden die aktuellen Planer für den aufrufenden Kontext.|  
|[CreateScheduleGroup](#createschedulegroup)|Überladen. Erstellt eine neue Planungsgruppe innerhalb des Planers, der dem aufrufenden Kontext zugeordnet. Die Version, die den Parameter akzeptiert `_Placement` bewirkt, dass die Aufgaben innerhalb der neu erstellte Planungsgruppe auf Blockcontainer ausführen an der Position, die durch diesen Parameter angegeben werden.|  
|[Trennen](#detach)|Trennt den aktuellen Planer aus dem aufrufenden Kontext und den zuvor angefügten Planer als aktuellen Planer wiederhergestellt, sofern vorhanden. Nach dem Beenden dieser Methode wird im aufrufende Kontext dann vom Planer, die an den Kontext mit einer zuvor angefügt worden war verwaltet die `CurrentScheduler::Create` oder `Scheduler::Attach` Methode.|  
|[Get](#get)|Gibt einen Zeiger auf den Planer, die den aufrufenden Kontext, auch bezeichnet als aktuellen Planer zugeordnet.|  
|[GetNumberOfVirtualProcessors](#getnumberofvirtualprocessors)|Gibt die aktuelle Anzahl virtueller Prozessoren für den Planer, der dem aufrufenden Kontext zugeordnet.|  
|[GetPolicy](#getpolicy)|Gibt eine Kopie der Richtlinie, der mit der aktuelle Planer erstellt wurde.|  
|[ID](#id)|Gibt einen eindeutigen Bezeichner für den aktuellen Planer zurück.|  
|[IsAvailableLocation](#isavailablelocation)|Bestimmt, ob eine angegebene Position auf dem aktuellen Planer verfügbar ist.|  
|[RegisterShutdownEvent](#registershutdownevent)|Der Windows-Ereignishandle übergebene Ursachen der `_ShutdownEvent` -Parameter signalisiert wird, wenn der Planer dem aktuellen Kontext zugeordnete heruntergefahren und zerstört. Zum Zeitpunkt der das Ereignis signalisiert wird, ist die gesamte Arbeit, die auf den Planer geplant wurde abgeschlossen. Durch diese Methode können mehrere Herunterfahrereignisse registriert werden.|  
|[ScheduleTask](#scheduletask)|Überladen. Plant eine einfache Aufgabe innerhalb des Planers, der dem aufrufenden Kontext zugeordnet. Die einfache Aufgabe wird in einer Planungsgruppe aus, die durch die Laufzeit bestimmt platziert werden. Die Version, die den Parameter akzeptiert `_Placement` bewirkt, dass der Task Blockcontainer am angegebenen Speicherort ausgeführt werden.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn kein Planer (finden Sie unter [Planer](scheduler-class.md)) zugeordneten im aufrufenden Kontext, viele Methoden innerhalb der `CurrentScheduler` Klasse führt dazu, das Anfügen der Standardplaner des Prozesses. Dies bedeutet möglicherweise auch, dass der Standardplaner des Prozesses während solch ein Aufruf erstellt wird.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `CurrentScheduler`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h hinzu  
  
 **Namespace:** Parallelität  
  
##  <a name="create"></a>Erstellen 

 Erstellt einen neuen Planer, deren Verhalten, durch beschrieben wird, die `_Policy` Parameter und fügt ihn an den aufrufenden Kontext. Der neu erstellte Planer werden die aktuellen Planer für den aufrufenden Kontext.  
  
```
static void __cdecl Create(const SchedulerPolicy& _Policy);
```  
  
### <a name="parameters"></a>Parameter  
 `_Policy`  
 Die Planerrichtlinie, die das Verhalten des neu erstellten Zeitplanungsmoduls beschrieben wird.  
  
### <a name="remarks"></a>Hinweise  
 Das Anfügen der Planer an den aufrufenden Kontext platziert implizit einen Verweiszähler auf den Planer.  
  
 Nach der Erstellung eines Planers mit der `Create` -Methode, die Sie aufrufen müssen die [CurrentScheduler:: Detach](#detach) Methode irgendwann in der Zukunft, damit der Planer beendet werden kann.  
  
 Wenn diese Methode aus einem Kontext aufgerufen wird, die bereits an einen anderen Planer angefügt ist, das vorhandene Zeitplanungsmodul wird als den vorherigen Planer gespeichert, und die neu erstellte Zeitplanungsmodul wird als aktueller Planer. Beim Aufrufen der `CurrentScheduler::Detach` Methode zu einem späteren Zeitpunkt, den vorherigen Planer als aktuellen Planer wiederhergestellt wird.  
  
 Diese Methode kann eine Vielzahl von Ausnahmen, einschließlich auslösen [Scheduler_resource_allocation_error](scheduler-resource-allocation-error-class.md) und [Invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md).  
  
##  <a name="createschedulegroup"></a>CreateScheduleGroup 

 Erstellt eine neue Planungsgruppe innerhalb des Planers, der dem aufrufenden Kontext zugeordnet. Die Version, die den Parameter akzeptiert `_Placement` bewirkt, dass die Aufgaben innerhalb der neu erstellte Planungsgruppe auf Blockcontainer ausführen an der Position, die durch diesen Parameter angegeben werden.  
  
```
static ScheduleGroup* __cdecl CreateScheduleGroup();

static ScheduleGroup* __cdecl CreateScheduleGroup(location& _Placement);
```  
  
### <a name="parameters"></a>Parameter  
 `_Placement`  
 Ein Verweis auf einen Speicherort, in dem die Aufgaben innerhalb der Planungsgruppe Blockcontainer werden werden ausgeführt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die neu erstellte Planungsgruppe. Dies `ScheduleGroup` Objekt hat eine anfängliche Verweiszähler platziert sind.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode führt dazu, dass der Standardplaner des Prozesses erstellt und/oder an den aufrufenden Kontext angefügt wird, wenn derzeit dem aufrufenden Kontext kein Planer zugeordnet ist.  
  
 Rufen Sie die [Version](schedulegroup-class.md#release) -Methode für eine Planungsgruppe aus, wenn Sie planen Arbeit fertig sind. Der Planer zerstört den Zeitplan Gruppe, wenn die gesamte Arbeit für sie in der Warteschlange wurde abgeschlossen.  
  
 Beachten Sie, dass Sie diesen Planer explizit erstellt haben, alle Verweise auf Planungsgruppen freigeben müssen, bevor Sie den Verweis auf den Planer freigeben, trennen Sie den aktuellen Kontext aus.  
  
##  <a name="detach"></a>Trennen 

 Trennt den aktuellen Planer aus dem aufrufenden Kontext und den zuvor angefügten Planer als aktuellen Planer wiederhergestellt, sofern vorhanden. Nach dem Beenden dieser Methode wird im aufrufende Kontext dann vom Planer, die an den Kontext mit einer zuvor angefügt worden war verwaltet die `CurrentScheduler::Create` oder `Scheduler::Attach` Methode.  
  
```
static void __cdecl Detach();
```  
  
### <a name="remarks"></a>Hinweise  
 Die `Detach` -Methode entfernt implizit einen Verweiszähler vom Planer.  
  
 Wenn keine Planer an den aufrufenden Kontext zugeordnet ist, beim Aufrufen dieser Methode führt zu einem [Scheduler_not_attached](scheduler-not-attached-class.md) ausgelöste Ausnahme.  
  
 Beim Aufrufen dieser Methode von einem anderen Kontext ist eine interne, verwaltete ein Zeitplanungsmodul oder ein Kontext, der angefügt wurde mithilfe einer Methode, außer die [Scheduler:: Attach](scheduler-class.md#attach) oder [CurrentScheduler:: Create](#create) Methoden führt zu einer [Improper_scheduler_detach](improper-scheduler-detach-class.md) ausgelöste Ausnahme.  
  
##  <a name="get"></a>Erhalten 

 Gibt einen Zeiger auf den Planer, die den aufrufenden Kontext, auch bezeichnet als aktuellen Planer zugeordnet.  
  
```
static Scheduler* __cdecl Get();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den Planer, die den aufrufenden Kontext (dem aktuellen Planer) zugeordnet werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode führt dazu, dass der Standardplaner des Prozesses erstellt und/oder an den aufrufenden Kontext angefügt wird, wenn derzeit dem aufrufenden Kontext kein Planer zugeordnet ist. Befindet sich kein weiterer Verweis auf die `Scheduler` von dieser Methode zurückgegebene Objekt.  
  
##  <a name="getnumberofvirtualprocessors"></a>GetNumberOfVirtualProcessors 

 Gibt die aktuelle Anzahl virtueller Prozessoren für den Planer, der dem aufrufenden Kontext zugeordnet.  
  
```
static unsigned int __cdecl GetNumberOfVirtualProcessors();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn Sie ein Planer im aufrufenden Kontext, die aktuelle Anzahl virtueller Prozessoren für diesen Planer zugeordnet ist. andernfalls der Wert `-1`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode führt nicht zu Scheduler-Anlage, wenn im aufrufende Kontext nicht bereits einen Planer zugeordnet ist.  
  
 Der Rückgabewert dieser Methode wird eine sofortige Stichprobe von der Anzahl virtueller Prozessoren für den Planer, der dem aufrufenden Kontext zugeordnet. Dieser Wert kann veraltete Moment sein, die sie zurückgegeben werden.  
  
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
 Wenn Sie ein Planer im aufrufenden Kontext, der einen eindeutigen Bezeichner für diesen Planer zugeordnet ist. andernfalls der Wert `-1`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode führt nicht zu Scheduler-Anlage, wenn im aufrufende Kontext nicht bereits einen Planer zugeordnet ist.  
  
##  <a name="isavailablelocation"></a>IsAvailableLocation 

 Bestimmt, ob eine angegebene Position auf dem aktuellen Planer verfügbar ist.  
  
```
static bool __cdecl IsAvailableLocation(const location& _Placement);
```  
  
### <a name="parameters"></a>Parameter  
 `_Placement`  
 Ein Verweis auf die Position, an der aktuellen Planer zu Abfragen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Hinweis auf der Speicherort fest, ob durch angegeben die `_Placement` Argument auf den aktuellen Planer verfügbar ist.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode führt nicht zu Scheduler-Anlage, wenn im aufrufende Kontext nicht bereits einen Planer zugeordnet ist.  
  
 Beachten Sie, dass der Rückgabewert ist eine sofortige Stichprobe an, ob am angegebene Speicherort verfügbar ist. Bei mehreren verborgenen Zeitplanungsmodulen angezeigt kann dynamische ressourcenverwaltung hinzufügen oder Ressourcen von Zeitplanungsmodulen zu einem beliebigen Zeitpunkt einsenden. Dies geschehen soll, kann die angegebene Position ändern Sie die Verfügbarkeit.  
  
##  <a name="registershutdownevent"></a>RegisterShutdownEvent 

 Der Windows-Ereignishandle übergebene Ursachen der `_ShutdownEvent` -Parameter signalisiert wird, wenn der Planer dem aktuellen Kontext zugeordnete heruntergefahren und zerstört. Zum Zeitpunkt der das Ereignis signalisiert wird, ist die gesamte Arbeit, die auf den Planer geplant wurde abgeschlossen. Durch diese Methode können mehrere Herunterfahrereignisse registriert werden.  
  
```
static void __cdecl RegisterShutdownEvent(HANDLE _ShutdownEvent);
```  
  
### <a name="parameters"></a>Parameter  
 `_ShutdownEvent`  
 Ein Handle für ein Windows-Ereignisobjekt, das von der Laufzeit signalisiert wird, wenn der Planer dem aktuellen Kontext zugeordnete heruntergefahren und zerstört.  
  
### <a name="remarks"></a>Hinweise  
 Wenn keine Planer an den aufrufenden Kontext zugeordnet ist, beim Aufrufen dieser Methode führt zu einem [Scheduler_not_attached](scheduler-not-attached-class.md) ausgelöste Ausnahme.  
  
##  <a name="scheduletask"></a>ScheduleTask 

 Plant eine einfache Aufgabe innerhalb des Planers, der dem aufrufenden Kontext zugeordnet. Die einfache Aufgabe wird in einer Planungsgruppe aus, die durch die Laufzeit bestimmt platziert werden. Die Version, die den Parameter akzeptiert `_Placement` bewirkt, dass der Task Blockcontainer am angegebenen Speicherort ausgeführt werden.  
  
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
 Ein Zeiger auf die Funktion, die ausgeführt werden, um den Text der Lightweight-Aufgabe auszuführen.  
  
 `_Data`  
 Ein void-Zeiger auf die Daten, die in den Text der Aufgabe als Parameter übergeben werden.  
  
 `_Placement`  
 Ein Verweis auf einen Speicherort, in dem die Aufgabe Lightweight-Blockcontainer werden wird ausgeführt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode führt dazu, dass der Standardplaner des Prozesses erstellt und/oder an den aufrufenden Kontext angefügt wird, wenn derzeit dem aufrufenden Kontext kein Planer zugeordnet ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [Scheduler-Klasse](scheduler-class.md)   
 [PolicyElementKey](concurrency-namespace-enums.md)   
 [Taskplaner](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)



