---
title: ScheduleGroup-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ScheduleGroup
- CONCRT/concurrency::ScheduleGroup
- CONCRT/concurrency::ScheduleGroup::Id
- CONCRT/concurrency::ScheduleGroup::Reference
- CONCRT/concurrency::ScheduleGroup::Release
- CONCRT/concurrency::ScheduleGroup::ScheduleTask
dev_langs: C++
helpviewer_keywords: ScheduleGroup class
ms.assetid: 86d380ff-f2e8-411c-b1a8-22bd3079824a
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f1ca427842245701c1d8dfbcef946ef1586acbf0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
|[ID](#id)|Gibt einen Bezeichner für die Planungsgruppe zurück, der innerhalb des Planers eindeutig ist, zu dem die Gruppe gehört.|  
|[Verweis](#reference)|Inkrementiert den Verweiszähler dieser Planergruppe.|  
|[Version](#release)|Dekrementiert den Verweiszähler dieser Planergruppe.|  
|[ScheduleTask](#scheduletask)|Plant eine einfache Aufgabe innerhalb der Planungsgruppe.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `ScheduleGroup`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** concrt.h hinzu  
  
 **Namespace:** Parallelität  
  
##  <a name="id"></a>ID 

 Gibt einen Bezeichner für die Planungsgruppe zurück, der innerhalb des Planers eindeutig ist, zu dem die Gruppe gehört.  
  
```
virtual unsigned int Id() const = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Bezeichner für die Planungsgruppe, die innerhalb des Planers eindeutig ist, zu dem die Gruppe gehört.  
  
##  <a name="operator_delete"></a>Delete-Operator 

 Ein `ScheduleGroup` Objekt wird intern von der Laufzeit zerstört, sobald alle externen Verweise darauf freigegeben werden. Es kann nicht explizit gelöscht werden.  
  
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
 `_PObject`  
 Ein Zeiger auf das Objekt gelöscht werden soll.  
  
##  <a name="reference"></a>Referenz 

 Inkrementiert den Verweiszähler dieser Planergruppe.  
  
```
virtual unsigned int Reference() = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der neu inkrementierte Verweiszähler.  
  
### <a name="remarks"></a>Hinweise  
 Dies wird normalerweise zum Verwalten der Lebensdauer von der Planungsgruppe Zusammenstellung verwendet. Wenn der Verweiszähler für eine Planungsgruppe auf 0 (null) fällt, wird die Planungsgruppe von der Laufzeit gelöscht. Eine Planungsgruppe erstellt haben, verwenden entweder die [CurrentScheduler:: CreateScheduleGroup](currentscheduler-class.md#createschedulegroup) -Methode oder die [Scheduler:: CreateScheduleGroup](scheduler-class.md#createschedulegroup) Methode beginnt mit einer Verweisanzahl von einer.  
  
##  <a name="release"></a>Version 

 Dekrementiert den Verweiszähler dieser Planergruppe.  
  
```
virtual unsigned int Release() = 0;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der neu dekrementierte Verweiszähler.  
  
### <a name="remarks"></a>Hinweise  
 Dies wird normalerweise zum Verwalten der Lebensdauer von der Planungsgruppe Zusammenstellung verwendet. Wenn der Verweiszähler für eine Planungsgruppe auf 0 (null) fällt, wird die Planungsgruppe von der Laufzeit gelöscht. Nachdem Sie aufgerufen haben die `Release` Methode verweisen kann die angegebene Anzahl von Wiederholungen des Versuchs entfernen Sie die Erstellung, Anzahl und zusätzliche Verweise platziert, über die `Reference` -Methode, die Schedule-Gruppe nicht ausgenutzt werden kann. Auf diese Weise führt zu nicht definiertem Verhalten.  
  
 Eine Planungsgruppe ist einer bestimmten Planerinstanz zugeordnet. Sie müssen sicherstellen, dass alle Verweise auf die Planungsgruppe freigegeben werden, bevor alle Verweise auf den Planer freigegeben werden, da in der Planer zerstört wird führen können. Auf diese Weise andernfalls führt zu nicht definiertem Verhalten.  
  
##  <a name="dtor"></a>~ ScheduleGroup 

```
virtual ~ScheduleGroup();
```  
  
##  <a name="scheduletask"></a>ScheduleTask 

 Plant eine einfache Aufgabe innerhalb der Planungsgruppe.  
  
```
virtual void ScheduleTask(
    TaskProc _Proc,
    _Inout_opt_ void* _Data) = 0;
```  
  
### <a name="parameters"></a>Parameter  
 `_Proc`  
 Ein Zeiger auf die Funktion, die ausgeführt werden, um den Text der Lightweight-Aufgabe auszuführen.  
  
 `_Data`  
 Ein void-Zeiger auf die Daten, die in den Text der Aufgabe als Parameter übergeben werden.  
  
### <a name="remarks"></a>Hinweise  
 Aufrufen der `ScheduleTask` -Methode versetzt implizit einen Verweiszähler für die Planungsgruppe aus, die von der Laufzeit, zu einem geeigneten Zeitpunkt entfernt wird, nachdem der Task ausgeführt wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)   
 [CurrentScheduler-Klasse](currentscheduler-class.md)   
 [Scheduler-Klasse](scheduler-class.md)   
 [Taskplaner](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)



