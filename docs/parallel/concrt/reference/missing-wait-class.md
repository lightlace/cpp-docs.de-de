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
ms.openlocfilehash: 68d24d710eec4fd602e64cc3cbde810db2b1a495
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62409966"
---
# <a name="missingwait-class"></a>missing_wait-Klasse

Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn es Aufgaben gibt, die noch für ein `task_group`-Objekt oder `structured_task_group`-Objekt geplant sind, während der Destruktor des Objekts ausgeführt wird. Diese Ausnahme wird nie ausgelöst, wenn der Destruktor aufgrund einer Stapelentladung als Ergebnis einer Ausnahme erreicht wird.

## <a name="syntax"></a>Syntax

```
class missing_wait : public std::exception;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[missing_wait](#ctor)|Überladen. Erstellt ein `missing_wait`-Objekt.|

## <a name="remarks"></a>Hinweise

Fehlende ausnahmeverlaufs, Sie sind verantwortlich für das Aufrufen von entweder die `wait` oder `run_and_wait` Methode eine `task_group` oder `structured_task_group` Objekt vor, dass dieses Objekt zerstört. Löst die Runtime diese Ausnahme als Hinweis auf, die Sie vergessen haben, rufen Sie die `wait` oder `run_and_wait` Methode.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`exception`

`missing_wait`

## <a name="requirements"></a>Anforderungen

**Header:** concrt.h

**Namespace:** Parallelität

##  <a name="ctor"></a> missing_wait

Erstellt ein `missing_wait`-Objekt.

```
explicit _CRTIMP missing_wait(_In_z_ const char* _Message) throw();

missing_wait() throw();
```

### <a name="parameters"></a>Parameter

*_Message*<br/>
Eine beschreibende Fehlermeldung.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[task_group-Klasse](task-group-class.md)<br/>
[wait](task-group-class.md)<br/>
[run_and_wait](task-group-class.md)<br/>
[structured_task_group-Klasse](structured-task-group-class.md)
