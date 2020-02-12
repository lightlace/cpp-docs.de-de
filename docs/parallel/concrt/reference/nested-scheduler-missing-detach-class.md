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
ms.openlocfilehash: 8c9553b036890c4ce28f1060bfe2f58ee1904935
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77138856"
---
# <a name="nested_scheduler_missing_detach-class"></a>nested_scheduler_missing_detach-Klasse

Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn die Concurrency Runtime erkennt, dass versäumt wurde, die `CurrentScheduler::Detach`-Methode für einen Kontext aufzurufen, der mittels der `Attach`-Methode des `Scheduler`-Objekts an einen zweiten Planer angefügt wurde.

## <a name="syntax"></a>Syntax

```cpp
class nested_scheduler_missing_detach : public std::exception;
```

## <a name="members"></a>Members

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[nested_scheduler_missing_detach](#ctor)|Ist überladen. Erstellt ein `nested_scheduler_missing_detach`-Objekt.|

## <a name="remarks"></a>Bemerkungen

Diese Ausnahme wird nur ausgelöst, wenn Sie einen Planer in einem anderen zusammenstellen, indem Sie die `Attach`-Methode eines `Scheduler` Objekts in einem Kontext aufrufen, der bereits im Besitz eines anderen Zeit Planungs Moduls ist oder einem anderen Planer zugeordnet ist. Der Concurrency Runtime löst diese Ausnahme opportunistisch aus, wenn er das Szenario als Hilfe beim Auffinden des Problems erkennen kann. Nicht jede Instanz von, die die `CurrentScheduler::Detach`-Methode nicht aufruft, wird garantiert diese Ausnahme auslösen.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`exception`

`nested_scheduler_missing_detach`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** ConcRT. h

**Namespace:** Parallelität

## <a name="ctor"></a>nested_scheduler_missing_detach

Erstellt ein `nested_scheduler_missing_detach`-Objekt.

```cpp
explicit _CRTIMP nested_scheduler_missing_detach(_In_z_ const char* _Message) throw();

nested_scheduler_missing_detach() throw();
```

### <a name="parameters"></a>Parameter

*_Message*<br/>
Eine beschreibende Fehlermeldung.

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[Scheduler-Klasse](scheduler-class.md)
