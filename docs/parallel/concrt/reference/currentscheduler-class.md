---
title: CurrentScheduler-Klasse
ms.date: 11/04/2016
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
helpviewer_keywords:
- CurrentScheduler class
ms.assetid: 31c20e0e-4cdf-49b4-8220-d726130aad2b
ms.openlocfilehash: a27ec7c25962b6addd26e61af8f33130d4c653ba
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62296152"
---
# <a name="currentscheduler-class"></a>CurrentScheduler-Klasse

Stellt eine Abstraktion für den aktuellen Planer dar, der dem aufrufenden Kontext zugeordnet ist.

## <a name="syntax"></a>Syntax

```
class CurrentScheduler;
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[Erstellen](#create)|Erstellt einen neuen Planer, deren Verhalten, durch beschrieben wird, die `_Policy` Parameter und an den aufrufenden Kontext angefügt wurde. Der neu erstellte Planer werden für den aktuellen Scheduler für den aufrufenden Kontext.|
|[CreateScheduleGroup](#createschedulegroup)|Überladen. Erstellt eine neue Planungsgruppe innerhalb des Planers, der dem aufrufenden Kontext zugeordnet. Die Version, die den Parameter akzeptiert `_Placement` bewirkt, dass Aufgaben innerhalb der Gruppe neu erstellten Zeitpläne Blockcontainer ausführen an der Position, die durch diesen Parameter angegeben werden.|
|[Trennen](#detach)|Trennt den aktuellen Planer aus dem aufrufenden Kontext und stellt den zuvor angefügten Planer als aktuellen Planer, wieder her, sofern vorhanden. Nach der Rückgabe dieser Methode wird im aufrufende Kontext dann vom Planer, der an den Kontext, der entweder bereits vorher angefügt wurde verwaltet die `CurrentScheduler::Create` oder `Scheduler::Attach` Methode.|
|[Get](#get)|Gibt einen Zeiger auf den Planer im aufrufenden Kontext, auch bezeichnet als aktuellen Planer zugeordnet.|
|[GetNumberOfVirtualProcessors](#getnumberofvirtualprocessors)|Gibt die aktuelle Anzahl virtueller Prozessoren für den Planer, der dem aufrufenden Kontext zugeordnet.|
|[GetPolicy](#getpolicy)|Gibt eine Kopie der Richtlinie, der mit der aktuelle Planer erstellt wurde.|
|[Id](#id)|Gibt einen eindeutigen Bezeichner für den aktuellen Planer zurück.|
|[IsAvailableLocation](#isavailablelocation)|Bestimmt, ob eine angegebene Position auf dem aktuellen Planer verfügbar ist.|
|[RegisterShutdownEvent](#registershutdownevent)|Bewirkt, dass das Windows-Ereignishandle zu, in übergeben der `_ShutdownEvent` -Parameter signalisiert wird, wenn der Planer dem aktuellen Kontext zugeordnet heruntergefahren wird, und zerstört. Zu dem Zeitpunkt, der das Ereignis signalisiert wird, ist die gesamte Arbeit, die auf den Planer geplant wurde abgeschlossen. Mehrere Herunterfahrereignisse können mit dieser Methode registriert werden.|
|[ScheduleTask](#scheduletask)|Überladen. Plant eine einfache Aufgabe innerhalb des Planers, der dem aufrufenden Kontext zugeordnet. Die einfache Aufgabe wird in einer Planungsgruppe aus, die durch die Laufzeit bestimmt platziert werden. Die Version, die den Parameter akzeptiert `_Placement` bewirkt, dass der Task ausgeführt wird, an der angegebenen Position für Blockcontainer werden.|

## <a name="remarks"></a>Hinweise

Wenn kein Planer (finden Sie unter [Scheduler](scheduler-class.md)) verknüpft ist, mit dem aufrufenden Kontext, viele Methoden innerhalb der `CurrentScheduler` Klasse führt in der Anlage der Standardplaner des Prozesses. Dies bedeutet möglicherweise auch, dass bei solch einem Aufruf der Standardplaner des Prozesses erstellt wird.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`CurrentScheduler`

## <a name="requirements"></a>Anforderungen

**Header:** concrt.h

**Namespace:** Parallelität

##  <a name="create"></a> Erstellen

Erstellt einen neuen Planer, deren Verhalten, durch beschrieben wird, die `_Policy` Parameter und an den aufrufenden Kontext angefügt wurde. Der neu erstellte Planer werden für den aktuellen Scheduler für den aufrufenden Kontext.

```
static void __cdecl Create(const SchedulerPolicy& _Policy);
```

### <a name="parameters"></a>Parameter

*_Policy*<br/>
Die Scheduler-Richtlinie, die das Verhalten des neu erstellten Zeitplanungsmoduls beschrieben wird.

### <a name="remarks"></a>Hinweise

Die Anlage des Zeitplanungsmoduls an den aufrufenden Kontext platziert einen Verweiszähler implizit auf den Planer.

Nach Erstellung ein Planers mit der `Create` -Methode, die Sie aufrufen müssen die [CurrentScheduler:: Detach](#detach) Methode an einem bestimmten Punkt in der Zukunft, damit der Planer beendet werden kann.

Wenn diese Methode aus einem Kontext aufgerufen wird, die bereits an einen anderen Planer angefügt ist, wird der vorhandene Scheduler als den vorherigen Planer gespeichert, und das neu erstellte Zeitplanungsmodul wird als aktueller Planer. Beim Aufrufen der `CurrentScheduler::Detach` Methode zu einem späteren Zeitpunkt, den vorherigen Planer als aktuellen Planer wiederhergestellt wird.

Diese Methode kann eine Vielzahl von Ausnahmen, einschließlich auslösen [Scheduler_resource_allocation_error](scheduler-resource-allocation-error-class.md) und [Invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md).

##  <a name="createschedulegroup"></a> CreateScheduleGroup

Erstellt eine neue Planungsgruppe innerhalb des Planers, der dem aufrufenden Kontext zugeordnet. Die Version, die den Parameter akzeptiert `_Placement` bewirkt, dass Aufgaben innerhalb der Gruppe neu erstellten Zeitpläne Blockcontainer ausführen an der Position, die durch diesen Parameter angegeben werden.

```
static ScheduleGroup* __cdecl CreateScheduleGroup();

static ScheduleGroup* __cdecl CreateScheduleGroup(location& _Placement);
```

### <a name="parameters"></a>Parameter

*_Placement*<br/>
Ein Verweis auf einen Speicherort, in dem die Aufgaben innerhalb der Planungsgruppe für Blockcontainer werden werden auf ausführen.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die neu erstellte Planungsgruppe. Dies `ScheduleGroup` Objekt verfügt über eine Initiale Verweisanzahl platziert.

### <a name="remarks"></a>Hinweise

Diese Methode führt dazu, dass der Standardplaner des Prozesses erstellt und/oder an den aufrufenden Kontext angefügt wird, wenn derzeit dem aufrufenden Kontext kein Planer zugeordnet ist.

Rufen Sie die [Version](schedulegroup-class.md#release) Methode für eine Planungsgruppe, wenn Sie Planungsarbeit dafür haben. Der Planer zerstört den Zeitplan Gruppe, wenn die gesamte Arbeit für sie in der Warteschlange abgeschlossen wurde.

Beachten Sie, dass wenn Sie explizit diesem Zeitplanungsmodul erstellt, Sie alle Verweise freigeben müssen Planungsgruppen, bevor Sie den Verweis auf den Planer, freigeben, indem trennen den aktuellen Kontext aus.

##  <a name="detach"></a> Trennen

Trennt den aktuellen Planer aus dem aufrufenden Kontext und stellt den zuvor angefügten Planer als aktuellen Planer, wieder her, sofern vorhanden. Nach der Rückgabe dieser Methode wird im aufrufende Kontext dann vom Planer, der an den Kontext, der entweder bereits vorher angefügt wurde verwaltet die `CurrentScheduler::Create` oder `Scheduler::Attach` Methode.

```
static void __cdecl Detach();
```

### <a name="remarks"></a>Hinweise

Die `Detach` Methode entfernt einen Verweiszähler implizit vom Planer.

Wenn keine Planer an den aufrufenden Kontext angefügt ist, das Aufrufen dieser Methode führt zu einem [Scheduler_not_attached](scheduler-not-attached-class.md) ausgelöste Ausnahme.

Interne und durch einen Zeitplan oder einen Kontext an, die angefügt wurde mithilfe einer anderen Methode als verwaltete ist Aufrufen dieser Methode aus einem Kontext, der die [Scheduler:: Attach](scheduler-class.md#attach) oder [CurrentScheduler:: Create](#create) -Methoden führt zu einer [Improper_scheduler_detach](improper-scheduler-detach-class.md) ausgelöste Ausnahme.

##  <a name="get"></a> Erhalten

Gibt einen Zeiger auf den Planer im aufrufenden Kontext, auch bezeichnet als aktuellen Planer zugeordnet.

```
static Scheduler* __cdecl Get();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf den Planer im aufrufenden Kontext (aktueller Planer) zugeordnet werden soll.

### <a name="remarks"></a>Hinweise

Diese Methode führt dazu, dass der Standardplaner des Prozesses erstellt und/oder an den aufrufenden Kontext angefügt wird, wenn derzeit dem aufrufenden Kontext kein Planer zugeordnet ist. Befindet sich kein weiterer Verweis auf die `Scheduler` von dieser Methode zurückgegebene Objekt.

##  <a name="getnumberofvirtualprocessors"></a> GetNumberOfVirtualProcessors

Gibt die aktuelle Anzahl virtueller Prozessoren für den Planer, der dem aufrufenden Kontext zugeordnet.

```
static unsigned int __cdecl GetNumberOfVirtualProcessors();
```

### <a name="return-value"></a>Rückgabewert

Wenn ein Planer im aufrufenden Kontext, der die aktuelle Anzahl virtueller Prozessoren für diesen Planer zugeordnet. andernfalls den Wert `-1`.

### <a name="remarks"></a>Hinweise

Diese Methode führt nicht in der Scheduler-Anlage, wenn der Kontext des aufrufende nicht bereits einem Planer zugeordnet ist.

Der Rückgabewert dieser Methode ist eine sofortige Sampling der Anzahl virtueller Prozessoren für den Planer, der dem aufrufenden Kontext zugeordnet. Dieser Wert kann veraltete Moment sein, die, den er zurückgegeben wird.

##  <a name="getpolicy"></a> GetPolicy

Gibt eine Kopie der Richtlinie, der mit der aktuelle Planer erstellt wurde.

```
static SchedulerPolicy __cdecl GetPolicy();
```

### <a name="return-value"></a>Rückgabewert

Eine Kopie der Richtlinie, der mit der aktuelle Planer erstellt wurde.

### <a name="remarks"></a>Hinweise

Diese Methode führt dazu, dass der Standardplaner des Prozesses erstellt und/oder an den aufrufenden Kontext angefügt wird, wenn derzeit dem aufrufenden Kontext kein Planer zugeordnet ist.

##  <a name="id"></a> Id

Gibt einen eindeutigen Bezeichner für den aktuellen Planer zurück.

```
static unsigned int __cdecl Id();
```

### <a name="return-value"></a>Rückgabewert

Wenn ein Planer im aufrufenden Kontext, einen eindeutigen Bezeichner für diese Planer zugeordnet. andernfalls den Wert `-1`.

### <a name="remarks"></a>Hinweise

Diese Methode führt nicht in der Scheduler-Anlage, wenn der Kontext des aufrufende nicht bereits einem Planer zugeordnet ist.

##  <a name="isavailablelocation"></a> IsAvailableLocation

Bestimmt, ob eine angegebene Position auf dem aktuellen Planer verfügbar ist.

```
static bool __cdecl IsAvailableLocation(const location& _Placement);
```

### <a name="parameters"></a>Parameter

*_Placement*<br/>
Ein Verweis auf die Position, an den aktuellen Planer zu Fragen.

### <a name="return-value"></a>Rückgabewert

Ein Hinweis auf, und zwar unabhängig davon, ob der Speicherort von angegeben die `_Placement` Argument auf den aktuellen Scheduler verfügbar ist.

### <a name="remarks"></a>Hinweise

Diese Methode führt nicht in der Scheduler-Anlage, wenn der Kontext des aufrufende nicht bereits einem Planer zugeordnet ist.

Beachten Sie, dass der Rückgabewert eine sofortige Stichprobe ist von, ob der angegebene Speicherort verfügbar ist. Bei mehreren Zeitplanungsmodulen kann dynamische ressourcenverwaltung hinzufügen oder entfernen Sie die nicht Ressourcen von Zeitplanungsmodulen zu einem beliebigen Zeitpunkt. In diesem Fall werden kann der angegebene Speicherort Verfügbarkeit ändern.

##  <a name="registershutdownevent"></a> RegisterShutdownEvent

Bewirkt, dass das Windows-Ereignishandle zu, in übergeben der `_ShutdownEvent` -Parameter signalisiert wird, wenn der Planer dem aktuellen Kontext zugeordnet heruntergefahren wird, und zerstört. Zu dem Zeitpunkt, der das Ereignis signalisiert wird, ist die gesamte Arbeit, die auf den Planer geplant wurde abgeschlossen. Mehrere Herunterfahrereignisse können mit dieser Methode registriert werden.

```
static void __cdecl RegisterShutdownEvent(HANDLE _ShutdownEvent);
```

### <a name="parameters"></a>Parameter

*_ShutdownEvent*<br/>
Ein Handle für ein Windows-Ereignis-Objekt, das von der Laufzeit signalisiert wird, wenn der Planer dem aktuellen Kontext zugeordnet heruntergefahren wird, und zerstört.

### <a name="remarks"></a>Hinweise

Wenn keine Planer an den aufrufenden Kontext angefügt ist, das Aufrufen dieser Methode führt zu einem [Scheduler_not_attached](scheduler-not-attached-class.md) ausgelöste Ausnahme.

##  <a name="scheduletask"></a> ScheduleTask

Plant eine einfache Aufgabe innerhalb des Planers, der dem aufrufenden Kontext zugeordnet. Die einfache Aufgabe wird in einer Planungsgruppe aus, die durch die Laufzeit bestimmt platziert werden. Die Version, die den Parameter akzeptiert `_Placement` bewirkt, dass der Task ausgeführt wird, an der angegebenen Position für Blockcontainer werden.

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

*_Proc*<br/>
Ein Zeiger auf die Funktion, die ausgeführt werden, um den Text der Aufgabe leicht durchführen.

*_Data*<br/>
Ein void-Zeiger auf die Daten, die in den Text der Aufgabe als Parameter übergeben werden.

*_Placement*<br/>
Ein Verweis auf einen Speicherort, in denen die einfache Aufgabe für Blockcontainer werden werden auf ausführen.

### <a name="remarks"></a>Hinweise

Diese Methode führt dazu, dass der Standardplaner des Prozesses erstellt und/oder an den aufrufenden Kontext angefügt wird, wenn derzeit dem aufrufenden Kontext kein Planer zugeordnet ist.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[Scheduler-Klasse](scheduler-class.md)<br/>
[PolicyElementKey](concurrency-namespace-enums.md)<br/>
[Aufgabenplanung](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)
