---
title: invalid_multiple_scheduling-Klasse
ms.date: 11/04/2016
f1_keywords:
- invalid_multiple_scheduling
- CONCRT/concurrency::invalid_multiple_scheduling
- CONCRT/concurrency::invalid_multiple_scheduling::invalid_multiple_scheduling
helpviewer_keywords:
- invalid_multiple_scheduling class
ms.assetid: e9a47cb7-a778-4df7-92b0-3752119fd4c7
ms.openlocfilehash: a8b2a045ce94562dcba0019bc03aaa90c4d384a9
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77140903"
---
# <a name="invalid_multiple_scheduling-class"></a>invalid_multiple_scheduling-Klasse

Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn ein `task_handle`-Objekt mehrmals mittels der `run`-Methode eines `task_group`-Objekts oder `structured_task_group`-Objekts ohne einen zwischenzeitlichen Aufruf der `wait`-Methode oder `run_and_wait`-Methode geplant wird.

## <a name="syntax"></a>Syntax

```cpp
class invalid_multiple_scheduling : public std::exception;
```

## <a name="members"></a>Members

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[invalid_multiple_scheduling](#ctor)|Ist überladen. Erstellt ein `invalid_multiple_scheduling`-Objekt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`exception`

`invalid_multiple_scheduling`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** ConcRT. h

**Namespace:** Parallelität

## <a name="ctor"></a>invalid_multiple_scheduling

Erstellt ein `invalid_multiple_scheduling`-Objekt.

```cpp
explicit _CRTIMP invalid_multiple_scheduling(_In_z_ const char* _Message) throw();

invalid_multiple_scheduling() throw();
```

### <a name="parameters"></a>Parameter

*_Message*<br/>
Eine beschreibende Fehlermeldung.

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[task_handle-Klasse](task-handle-class.md)<br/>
[task_group-Klasse](task-group-class.md)<br/>
[run](task-group-class.md)<br/>
[Warte](task-group-class.md)<br/>
[run_and_wait](task-group-class.md)<br/>
[structured_task_group-Klasse](structured-task-group-class.md)
