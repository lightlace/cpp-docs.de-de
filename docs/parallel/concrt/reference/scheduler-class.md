---
title: Scheduler-Klasse
ms.date: 11/04/2016
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
helpviewer_keywords:
- Scheduler class
ms.assetid: 34cf7961-048d-4852-8a5c-a32f823e3506
ms.openlocfilehash: f27dace61b0764962a78695c2a4c6b180b09d7a3
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57287898"
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
|[Scheduler](#ctor)|Ein Objekt der `Scheduler` -Klasse kann nur mithilfe der Factorymethoden, erstellt oder implizit.|
|[~ Scheduler-Destruktor](#dtor)|Ein Objekt der `Scheduler` Klasse ist implizit zerstört werden, wenn alle externen Verweise darauf nicht mehr vorhanden.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[Anfügen](#attach)|Wird den Planer an den aufrufenden Kontext angefügt. Nach der Rückgabe dieser Methode der aufrufende Kontext vom Scheduler verwaltet wird, und der Scheduler wird als aktueller Planer.|
|[Erstellen](#create)|Erstellt einen neuen Planer, deren Verhalten, durch beschrieben wird, die `_Policy` platziert einen anfänglichen Verweis auf den Planer Parameter, und gibt einen Zeiger darauf zurück.|
|[CreateScheduleGroup](#createschedulegroup)|Überladen. Erstellt eine neue Planungsgruppe innerhalb des Planers an. Die Version, die den Parameter akzeptiert `_Placement` bewirkt, dass Aufgaben innerhalb der Gruppe neu erstellten Zeitpläne Blockcontainer ausführen an der Position, die durch diesen Parameter angegeben werden.|
|[GetNumberOfVirtualProcessors](#getnumberofvirtualprocessors)|Gibt die aktuelle Anzahl virtueller Prozessoren für den Planer zurück.|
|[GetPolicy](#getpolicy)|Gibt eine Kopie der Richtlinie, der der Planer erstellt wurde.|
|[Id](#id)|Gibt einen eindeutigen Bezeichner für den Planer zurück.|
|[IsAvailableLocation](#isavailablelocation)|Bestimmt, ob eine angegebene Position im Zeitplanungsmodul verfügbar ist.|
|[Verweis](#reference)|Inkrementiert den Verweiszähler für den Scheduler.|
|[RegisterShutdownEvent](#registershutdownevent)|Bewirkt, dass das Windows-Ereignishandle zu, in übergeben der `_Event` -Parameter signalisiert wird, wenn der Planer beendet wird und zerstört. Zu dem Zeitpunkt, der das Ereignis signalisiert wird, ist die gesamte Arbeit, die auf den Planer geplant wurde abgeschlossen. Mehrere Herunterfahrereignisse können mit dieser Methode registriert werden.|
|[Version](#release)|Dekrementiert den Scheduler Verweiszähler.|
|[ResetDefaultSchedulerPolicy](#resetdefaultschedulerpolicy)|Die Standardrichtlinie für den Scheduler zurückgesetzt auf die Common Language Runtime-Standardeinstellungen. Das nächste Mal, wenn, das ein Standard-Scheduler erstellt wird, das wird die Common Language runtimeeinstellungen der Standardrichtlinie verwendet.|
|[ScheduleTask](#scheduletask)|Überladen. Plant eine einfache Aufgabe innerhalb des Planers. Die einfache Aufgabe wird in einer Planungsgruppe aus, die durch die Laufzeit bestimmt platziert werden. Die Version, die den Parameter akzeptiert `_Placement` bewirkt, dass der Task ausgeführt wird, an der angegebenen Position für Blockcontainer werden.|
|[SetDefaultSchedulerPolicy](#setdefaultschedulerpolicy)|Können eine benutzerdefinierte Richtlinie verwendet werden, um die Standard-Scheduler zu erstellen. Diese Methode kann aufgerufen werden, nur dann, wenn kein Standard-Scheduler innerhalb des Prozesses vorhanden ist. Nachdem eine Standardrichtlinie festgelegt wurde, bleibt Sie aktiv, bis zum nächsten gültigen Aufruf entweder die `SetDefaultSchedulerPolicy` oder [ResetDefaultSchedulerPolicy](#resetdefaultschedulerpolicy) Methode.|

## <a name="remarks"></a>Hinweise

Die Concurrency Runtime-Planer verwendet Ausführungskontexte, die das Betriebssystem Ausführungskontexte, z. B. ein Thread zugeordnet, die zum Ausführen der Arbeitsprofils in die Warteschlange eingereiht, von der Anwendung. Zu jedem Zeitpunkt ist die nebenläufigkeitsebene eines Planers gleich der Anzahl virtueller Prozessoren, die vom Ressourcen-Manager erteilt. Ein virtueller Prozessor ist eine Abstraktion für eine Verarbeitungsressource und wird einem Hardwarethread des zugrunde liegenden Systems zugeordnet. Nur ein einzelner Planerkontext kann jeweils auf einem virtuellen Prozessor ausgeführt werden.

Die Concurrency Runtime erstellt einen Standardplaner pro Prozess, um parallele Arbeitsvorgänge auszuführen. Darüber hinaus können Sie einen eigenen Planer-Instanzen erstellen und manipulieren, indem diese Klasse.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`Scheduler`

## <a name="requirements"></a>Anforderungen

**Header:** concrt.h

**Namespace:** Parallelität

##  <a name="attach"></a> Anfügen

Wird den Planer an den aufrufenden Kontext angefügt. Nach der Rückgabe dieser Methode der aufrufende Kontext vom Scheduler verwaltet wird, und der Scheduler wird als aktueller Planer.

```
virtual void Attach() = 0;
```

### <a name="remarks"></a>Hinweise

Anfügen eines Planers implizit platziert einen Verweis auf den Planer.

An einem bestimmten Punkt in der Zukunft müssen Sie Aufrufen der [CurrentScheduler:: Detach](currentscheduler-class.md#detach) Methode, damit der Planer beendet werden kann.

Wenn diese Methode aus einem Kontext aufgerufen wird, die bereits an einen anderen Planer angefügt ist, wird der vorhandene Scheduler als den vorherigen Planer gespeichert, und das neu erstellte Zeitplanungsmodul wird als aktueller Planer. Beim Aufrufen der `CurrentScheduler::Detach` Methode zu einem späteren Zeitpunkt, den vorherigen Planer als aktuellen Planer wiederhergestellt wird.

Diese Methode löst eine [Improper_scheduler_attach](improper-scheduler-attach-class.md) -Ausnahme aus, wenn dieser Planer dem aktuellen Planer des aufrufenden Kontexts ist.

##  <a name="create"></a> Erstellen

Erstellt einen neuen Planer, deren Verhalten, durch beschrieben wird, die `_Policy` platziert einen anfänglichen Verweis auf den Planer Parameter, und gibt einen Zeiger darauf zurück.

```
static Scheduler* __cdecl Create(const SchedulerPolicy& _Policy);
```

### <a name="parameters"></a>Parameter

*_Policy*<br/>
Die Scheduler-Richtlinie, die Verhalten des neu erstellten Planers beschrieben wird.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf einen neu erstellten Planer. Dies `Scheduler` Objekt verfügt über eine Initiale Verweisanzahl platziert.

### <a name="remarks"></a>Hinweise

Nach Erstellung ein Planers mit der `Create` -Methode, die Sie aufrufen müssen die `Release` Methode an einem bestimmten Punkt in der Zukunft, um den Verweiszähler zu entfernen und des Planers beendet.

Ein Planer erstellt, die mit dieser Methode ist nicht an den aufrufenden Kontext angefügt. Sie können mit einem Kontext angefügt werden die [Anfügen](#attach) Methode.

Diese Methode kann eine Vielzahl von Ausnahmen, einschließlich auslösen [Scheduler_resource_allocation_error](scheduler-resource-allocation-error-class.md) und [Invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md).

##  <a name="createschedulegroup"></a> CreateScheduleGroup

Erstellt eine neue Planungsgruppe innerhalb des Planers an. Die Version, die den Parameter akzeptiert `_Placement` bewirkt, dass Aufgaben innerhalb der Gruppe neu erstellten Zeitpläne Blockcontainer ausführen an der Position, die durch diesen Parameter angegeben werden.

```
virtual ScheduleGroup* CreateScheduleGroup() = 0;

virtual ScheduleGroup* CreateScheduleGroup(location& _Placement) = 0;
```

### <a name="parameters"></a>Parameter

*_Placement*<br/>
Ein Verweis auf einen Speicherort, in dem die Aufgaben innerhalb der Planungsgruppe wird für Blockcontainer am ausführen.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die neu erstellte Planungsgruppe. Dies `ScheduleGroup` Objekt verfügt über eine Initiale Verweisanzahl platziert.

### <a name="remarks"></a>Hinweise

Rufen Sie die [Version](schedulegroup-class.md#release) Methode für eine Planungsgruppe, wenn Sie Planungsarbeit dafür haben. Der Planer zerstört den Zeitplan Gruppe, wenn die gesamte Arbeit für sie in der Warteschlange abgeschlossen wurde.

Beachten Sie, dass Sie diesem Zeitplanungsmodul explizit erstellt haben, alle Verweise freigeben müssen Planungsgruppen, bevor Sie die Verweise auf den Planer freigeben.

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

Ein eindeutiger Bezeichner für das Zeitplanungsmodul.

##  <a name="isavailablelocation"></a> IsAvailableLocation

Bestimmt, ob eine angegebene Position im Zeitplanungsmodul verfügbar ist.

```
virtual bool IsAvailableLocation(const location& _Placement) const = 0;
```

### <a name="parameters"></a>Parameter

*_Placement*<br/>
Ein Verweis auf die Position, an den Planer zu Fragen.

### <a name="return-value"></a>Rückgabewert

Ein Hinweis auf, und zwar unabhängig davon, ob der Speicherort von angegeben die `_Placement` Argument auf den Planer verfügbar ist.

### <a name="remarks"></a>Hinweise

Beachten Sie, dass der Rückgabewert eine sofortige Stichprobe ist von, ob der angegebene Speicherort verfügbar ist. Bei mehreren Zeitplanungsmodulen kann dynamische ressourcenverwaltung hinzufügen oder entfernen Sie die nicht Ressourcen von Zeitplanungsmodulen zu einem beliebigen Zeitpunkt. In diesem Fall werden kann der angegebene Speicherort Verfügbarkeit ändern.

##  <a name="reference"></a> Referenz

Inkrementiert den Verweiszähler für den Scheduler.

```
virtual unsigned int Reference() = 0 ;
```

### <a name="return-value"></a>Rückgabewert

Der neu inkrementiert Verweiszähler.

### <a name="remarks"></a>Hinweise

Dies wird normalerweise verwendet, zum Verwalten der Lebensdauer des Zeitplanungsmoduls für den Verbund. Wenn der Verweiszähler ein Scheduler-fällt 0 (null), der Scheduler wird heruntergefahren und Destruct selbst nachdem alle arbeiten, auf dem Zeitplanungsmodul wurde abgeschlossen.

Löst die Methode eine [Improper_scheduler_reference](improper-scheduler-reference-class.md) -Ausnahme aus, wenn der Verweiszähler vor dem Aufrufen der `Reference` Methode wurde von 0 (null) und der Aufruf erfolgt aus einem Kontext, der nicht vom Zeitplanungsmodul gehört.

##  <a name="registershutdownevent"></a> RegisterShutdownEvent

Bewirkt, dass das Windows-Ereignishandle zu, in übergeben der `_Event` -Parameter signalisiert wird, wenn der Planer beendet wird und zerstört. Zu dem Zeitpunkt, der das Ereignis signalisiert wird, ist die gesamte Arbeit, die auf den Planer geplant wurde abgeschlossen. Mehrere Herunterfahrereignisse können mit dieser Methode registriert werden.

```
virtual void RegisterShutdownEvent(HANDLE _Event) = 0;
```

### <a name="parameters"></a>Parameter

*_Event*<br/>
Ein Handle für ein Windows-Ereignis-Objekt, das von der Laufzeit signalisiert wird, wenn der Planer beendet wird und zerstört.

##  <a name="release"></a> Version

Dekrementiert den Scheduler Verweiszähler.

```
virtual unsigned int Release() = 0;
```

### <a name="return-value"></a>Rückgabewert

Der neu dekrementiert Verweiszähler.

### <a name="remarks"></a>Hinweise

Dies wird normalerweise verwendet, zum Verwalten der Lebensdauer des Zeitplanungsmoduls für den Verbund. Wenn der Verweiszähler ein Scheduler-fällt 0 (null), der Scheduler wird heruntergefahren und Destruct selbst nachdem alle arbeiten, auf dem Zeitplanungsmodul wurde abgeschlossen.

##  <a name="resetdefaultschedulerpolicy"></a> ResetDefaultSchedulerPolicy

Die Standardrichtlinie für den Scheduler zurückgesetzt auf die Common Language Runtime-Standardeinstellungen. Das nächste Mal, wenn, das ein Standard-Scheduler erstellt wird, das wird die Common Language runtimeeinstellungen der Standardrichtlinie verwendet.

```
static void __cdecl ResetDefaultSchedulerPolicy();
```

### <a name="remarks"></a>Hinweise

Diese Methode kann aufgerufen werden, während ein Standardplaner innerhalb des Prozesses vorhanden ist. Es wirkt sich nicht auf die Richtlinie von der vorhandenen Standard-Scheduler. Allerdings würde, wenn der Standard-Scheduler heruntergefahren wurden, und ein neuer Standardwert wurden zu einem späteren Zeitpunkt erstellt werden, das neue Zeitplanungsmodul Einstellungen der Standardrichtlinie der Common Language Runtime verwenden.

##  <a name="ctor"></a> Scheduler

Ein Objekt der `Scheduler` -Klasse kann nur mithilfe der Factorymethoden, erstellt oder implizit.

```
Scheduler();
```

### <a name="remarks"></a>Hinweise

Standardplaner des Prozesses wird implizit erstellt, wenn Sie viele der Common Language Runtime-Funktionen nutzen, die erfordern einen Planer an den aufrufenden Kontext angefügt werden. Methoden in der `CurrentScheduler` -Klasse und Funktionen der Ebenen PPL und die Agents in der Regel führen implizite Anlage.

Sie können auch einen Planer entweder explizit durch Erstellen der `CurrentScheduler::Create` Methode oder der `Scheduler::Create` Methode.

##  <a name="dtor"></a> ~ Scheduler

Ein Objekt der `Scheduler` Klasse ist implizit zerstört werden, wenn alle externen Verweise darauf nicht mehr vorhanden.

```
virtual ~Scheduler();
```

##  <a name="scheduletask"></a> ScheduleTask

Plant eine einfache Aufgabe innerhalb des Planers. Die einfache Aufgabe wird in einer Planungsgruppe aus, die durch die Laufzeit bestimmt platziert werden. Die Version, die den Parameter akzeptiert `_Placement` bewirkt, dass der Task ausgeführt wird, an der angegebenen Position für Blockcontainer werden.

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

*_Proc*<br/>
Ein Zeiger auf die Funktion, die ausgeführt werden, um den Text der Aufgabe leicht durchführen.

*_Data*<br/>
Ein void-Zeiger auf die Daten, die in den Text der Aufgabe als Parameter übergeben werden.

*_Placement*<br/>
Ein Verweis auf einen Speicherort, in denen die einfache Aufgabe für Blockcontainer werden werden auf ausführen.

##  <a name="setdefaultschedulerpolicy"></a> SetDefaultSchedulerPolicy

Können eine benutzerdefinierte Richtlinie verwendet werden, um die Standard-Scheduler zu erstellen. Diese Methode kann aufgerufen werden, nur dann, wenn kein Standard-Scheduler innerhalb des Prozesses vorhanden ist. Nachdem eine Standardrichtlinie festgelegt wurde, bleibt Sie aktiv, bis zum nächsten gültigen Aufruf entweder die `SetDefaultSchedulerPolicy` oder [ResetDefaultSchedulerPolicy](#resetdefaultschedulerpolicy) Methode.

```
static void __cdecl SetDefaultSchedulerPolicy(const SchedulerPolicy& _Policy);
```

### <a name="parameters"></a>Parameter

*_Policy*<br/>
Die Richtlinie als Standardrichtlinie Scheduler festgelegt werden.

### <a name="remarks"></a>Hinweise

Wenn die `SetDefaultSchedulerPolicy` Methode wird aufgerufen, wenn ein Standardplaner bereits innerhalb des Prozesses vorhanden ist, löst die Laufzeit eine [Default_scheduler_exists](default-scheduler-exists-class.md) Ausnahme.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[Scheduler-Klasse](scheduler-class.md)<br/>
[PolicyElementKey](concurrency-namespace-enums.md)<br/>
[Aufgabenplanung](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)
