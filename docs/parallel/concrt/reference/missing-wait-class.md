---
title: missing_wait-Klasse
ms.date: 11/04/2016
f1_keywords:
- missing_wait
- CONCRT/concurrency::missing_wait
- CONCRT/concurrency::missing_wait::missing_wait
helpviewer_keywords:
- missing_wait class
ms.assetid: ff981875-bd43-47e3-806f-b03c9f418b18
ms.openlocfilehash: cf81d1ee6c144da210da5b1f37aca7910ae37bc8
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142388"
---
# <a name="missing_wait-class"></a>missing_wait-Klasse

Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn es Aufgaben gibt, die noch für ein `task_group`-Objekt oder `structured_task_group`-Objekt geplant sind, während der Destruktor des Objekts ausgeführt wird. Diese Ausnahme wird nie ausgelöst, wenn der Destruktor aufgrund einer Stapelentladung als Ergebnis einer Ausnahme erreicht wird.

## <a name="syntax"></a>Syntax

```cpp
class missing_wait : public std::exception;
```

## <a name="members"></a>Members

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[missing_wait](#ctor)|Ist überladen. Erstellt ein `missing_wait`-Objekt.|

## <a name="remarks"></a>Bemerkungen

Fehlender Ausnahme Fluss: Sie sind verantwortlich für das Aufrufen des `wait` oder `run_and_wait` der Methode eines `task_group` oder `structured_task_group` Objekts, bevor das Objekt destruct werden konnte. Die Laufzeit löst diese Ausnahme aus, wenn Sie vergessen haben, die `wait`-oder `run_and_wait`-Methode aufzurufen.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`exception`

`missing_wait`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** ConcRT. h

**Namespace:** Parallelität

## <a name="ctor"></a>missing_wait

Erstellt ein `missing_wait`-Objekt.

```cpp
explicit _CRTIMP missing_wait(_In_z_ const char* _Message) throw();

missing_wait() throw();
```

### <a name="parameters"></a>Parameter

*_Message*<br/>
Eine beschreibende Fehlermeldung.

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[task_group-Klasse](task-group-class.md)<br/>
[Warte](task-group-class.md)<br/>
[run_and_wait](task-group-class.md)<br/>
[structured_task_group-Klasse](structured-task-group-class.md)
