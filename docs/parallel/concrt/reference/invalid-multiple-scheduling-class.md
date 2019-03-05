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
ms.openlocfilehash: 7c8ce0aefc12097a71e79933d34a116997c8105f
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57276359"
---
# <a name="invalidmultiplescheduling-class"></a>invalid_multiple_scheduling-Klasse

Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn ein `task_handle`-Objekt mehrmals mittels der `run`-Methode eines `task_group`-Objekts oder `structured_task_group`-Objekts ohne einen zwischenzeitlichen Aufruf der `wait`-Methode oder `run_and_wait`-Methode geplant wird.

## <a name="syntax"></a>Syntax

```
class invalid_multiple_scheduling : public std::exception;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[invalid_multiple_scheduling](#ctor)|Überladen. Erstellt ein `invalid_multiple_scheduling`-Objekt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`exception`

`invalid_multiple_scheduling`

## <a name="requirements"></a>Anforderungen

**Header:** concrt.h

**Namespace:** Parallelität

##  <a name="ctor"></a> invalid_multiple_scheduling

Erstellt ein `invalid_multiple_scheduling`-Objekt.

```
explicit _CRTIMP invalid_multiple_scheduling(_In_z_ const char* _Message) throw();

invalid_multiple_scheduling() throw();
```

### <a name="parameters"></a>Parameter

*_Message*<br/>
Eine beschreibende Fehlermeldung.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[task_handle-Klasse](task-handle-class.md)<br/>
[task_group-Klasse](task-group-class.md)<br/>
[run](task-group-class.md)<br/>
[wait](task-group-class.md)<br/>
[run_and_wait](task-group-class.md)<br/>
[structured_task_group-Klasse](structured-task-group-class.md)
