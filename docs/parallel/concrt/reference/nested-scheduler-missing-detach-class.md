---
title: nested_scheduler_missing_detach-Klasse
ms.date: 11/04/2016
f1_keywords:
- nested_scheduler_missing_detach
- CONCRT/concurrency::nested_scheduler_missing_detach
- CONCRT/concurrency::nested_scheduler_missing_detach::nested_scheduler_missing_detach
helpviewer_keywords:
- nested_scheduler_missing_detach class
ms.assetid: 65d3f277-6d43-4160-97ef-caf8b26c1641
ms.openlocfilehash: db51f7b083cc0cbd9337fbbe5c672d190208f328
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394389"
---
# <a name="nestedschedulermissingdetach-class"></a>nested_scheduler_missing_detach-Klasse

Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn die Concurrency Runtime erkennt, dass versäumt wurde, die `CurrentScheduler::Detach`-Methode für einen Kontext aufzurufen, der mittels der `Attach`-Methode des `Scheduler`-Objekts an einen zweiten Planer angefügt wurde.

## <a name="syntax"></a>Syntax

```
class nested_scheduler_missing_detach : public std::exception;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[nested_scheduler_missing_detach](#ctor)|Überladen. Erstellt ein `nested_scheduler_missing_detach`-Objekt.|

## <a name="remarks"></a>Hinweise

Diese Ausnahme wird ausgelöst, nur, wenn Sie einen Planer in einen anderen, durch den Aufruf Schachteln der `Attach` Methode eine `Scheduler` Objekt in einem Kontext, der bereits im Besitz von oder an ein anderes Zeitplanungsmodul angefügt ist. Die Concurrency Runtime löst diese Ausnahme opportunistisch aus, wenn das Szenario als Hilfe beim Auffinden des Problems erkannt werden können. Nicht jede Instanz aufrufen, es sein, die `CurrentScheduler::Detach` Methode garantiert wird diese Ausnahme auslösen.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`exception`

`nested_scheduler_missing_detach`

## <a name="requirements"></a>Anforderungen

**Header:** concrt.h

**Namespace:** Parallelität

##  <a name="ctor"></a> nested_scheduler_missing_detach

Erstellt ein `nested_scheduler_missing_detach`-Objekt.

```
explicit _CRTIMP nested_scheduler_missing_detach(_In_z_ const char* _Message) throw();

nested_scheduler_missing_detach() throw();
```

### <a name="parameters"></a>Parameter

*_Message*<br/>
Eine beschreibende Fehlermeldung.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[Scheduler-Klasse](scheduler-class.md)
