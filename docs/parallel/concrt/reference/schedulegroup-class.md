---
title: ScheduleGroup-Klasse
ms.date: 11/04/2016
f1_keywords:
- ScheduleGroup
- CONCRT/concurrency::ScheduleGroup
- CONCRT/concurrency::ScheduleGroup::Id
- CONCRT/concurrency::ScheduleGroup::Reference
- CONCRT/concurrency::ScheduleGroup::Release
- CONCRT/concurrency::ScheduleGroup::ScheduleTask
helpviewer_keywords:
- ScheduleGroup class
ms.assetid: 86d380ff-f2e8-411c-b1a8-22bd3079824a
ms.openlocfilehash: ce7734a1330f2d6e495565338879764482439d09
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62337543"
---
# <a name="schedulegroup-class"></a>ScheduleGroup-Klasse

Stellt die Abstraktion für eine Planungsgruppe dar. In Planungsgruppen werden Sätze verwandter Arbeitsaufgaben organisiert, die von einer gemeinsamen Planung profitieren. Die kann entweder zeitlich durch das Ausführen einer anderen Aufgabe in der gleichen Gruppe vor dem Wechsel in eine andere Gruppe, oder räumlich durch das Ausführen mehrerer Elemente innerhalb der gleichen Gruppe auf dem gleichen NUMA-Knoten oder physischem Socket geschehen.

## <a name="syntax"></a>Syntax

```
class ScheduleGroup;
```

## <a name="members"></a>Member

### <a name="protected-constructors"></a>Geschützte Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[~ ScheduleGroup-Destruktor](#dtor)||

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[Id](#id)|Gibt einen Bezeichner für die Planungsgruppe zurück, der innerhalb des Planers eindeutig ist, zu dem die Gruppe gehört.|
|[Verweis](#reference)|Inkrementiert den Verweiszähler dieser Planergruppe.|
|[Version](#release)|Dekrementiert den Verweiszähler dieser Planergruppe.|
|[ScheduleTask](#scheduletask)|Plant eine einfache Aufgabe innerhalb der Planungsgruppe.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`ScheduleGroup`

## <a name="requirements"></a>Anforderungen

**Header:** concrt.h

**Namespace:** Parallelität

##  <a name="id"></a> Id

Gibt einen Bezeichner für die Planungsgruppe zurück, der innerhalb des Planers eindeutig ist, zu dem die Gruppe gehört.

```
virtual unsigned int Id() const = 0;
```

### <a name="return-value"></a>Rückgabewert

Ein Bezeichner für die Planungsgruppe, die innerhalb des Planers eindeutig ist, der die Gruppe gehört.

##  <a name="operator_delete"></a> Delete-Operator

Ein `ScheduleGroup` Objekt wird intern von der Laufzeit zerstört, wenn alle externen Verweise darauf freigegeben werden. Es kann nicht explizit gelöscht werden.

```
void operator delete(
    void* _PObject);

void operator delete(
    void* _PObject,
    int,
const char *,
    int);
```

### <a name="parameters"></a>Parameter

*_PObject*<br/>
Ein Zeiger auf das Objekt, das gelöscht werden.

##  <a name="reference"></a> Referenz

Inkrementiert den Verweiszähler dieser Planergruppe.

```
virtual unsigned int Reference() = 0;
```

### <a name="return-value"></a>Rückgabewert

Der neu inkrementiert Verweiszähler.

### <a name="remarks"></a>Hinweise

Dies wird normalerweise zum Verwalten der Lebensdauer der Gruppe "Zeitplan" für die Komposition verwendet. Wenn der Verweiszähler des einer Planungsgruppe aus 0 (null) fällt, wird die Planungsgruppe von der Laufzeit gelöscht. Eine Zeitplan-Gruppe erstellt haben, verwenden entweder die [CurrentScheduler:: CreateScheduleGroup](currentscheduler-class.md#createschedulegroup) -Methode, oder die [Scheduler:: CreateScheduleGroup](scheduler-class.md#createschedulegroup) Methode beginnt mit einer Verweisanzahl von einem.

##  <a name="release"></a> Version

Dekrementiert den Verweiszähler dieser Planergruppe.

```
virtual unsigned int Release() = 0;
```

### <a name="return-value"></a>Rückgabewert

Der neu dekrementiert Verweiszähler.

### <a name="remarks"></a>Hinweise

Dies wird normalerweise zum Verwalten der Lebensdauer der Gruppe "Zeitplan" für die Komposition verwendet. Wenn der Verweiszähler des einer Planungsgruppe aus 0 (null) fällt, wird die Planungsgruppe von der Laufzeit gelöscht. Nach dem Sie aufgerufen haben die `Release` Methode verweisen kann die bestimmte Anzahl von Malen So entfernen Sie die Erstellung, Anzahl und zusätzliche Verweise eingefügt der `Reference` -Methode, Sie können nicht die Planungsgruppe weiter nutzen. Dies führt zu nicht definiertem Verhalten.

Eine Planungsgruppe ist ein bestimmtes Zeitplanungsmodul-Instanz zugeordnet. Sie müssen sicherstellen, dass alle Verweise auf die Planungsgruppe freigegeben werden, bevor alle Verweise auf den Planer veröffentlicht werden, da in der Planer zerstört führen können. Andernfalls kann dies nicht definiertem Verhalten.

##  <a name="dtor"></a> ~ScheduleGroup

```
virtual ~ScheduleGroup();
```

##  <a name="scheduletask"></a> ScheduleTask

Plant eine einfache Aufgabe innerhalb der Planungsgruppe.

```
virtual void ScheduleTask(
    TaskProc _Proc,
    _Inout_opt_ void* _Data) = 0;
```

### <a name="parameters"></a>Parameter

*_Proc*<br/>
Ein Zeiger auf die Funktion, die ausgeführt werden, um den Text der Aufgabe leicht durchführen.

*_Data*<br/>
Ein void-Zeiger auf die Daten, die in den Text der Aufgabe als Parameter übergeben werden.

### <a name="remarks"></a>Hinweise

Aufrufen der `ScheduleTask` -Methode setzt implizit einen Verweiszähler für die Planungsgruppe, die von der Laufzeit, zu einem geeigneten Zeitpunkt entfernt wird, nachdem der Task ausgeführt wird.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[CurrentScheduler-Klasse](currentscheduler-class.md)<br/>
[Scheduler-Klasse](scheduler-class.md)<br/>
[Aufgabenplanung](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)
