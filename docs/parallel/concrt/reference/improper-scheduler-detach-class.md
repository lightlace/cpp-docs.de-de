---
title: improper_scheduler_detach-Klasse
ms.date: 11/04/2016
f1_keywords:
- improper_scheduler_detach
- CONCRT/concurrency::improper_scheduler_detach
- CONCRT/concurrency::improper_scheduler_detach::improper_scheduler_detach
helpviewer_keywords:
- improper_scheduler_detach class
ms.assetid: 30132102-c900-4951-a470-b63b4e3aa2d2
ms.openlocfilehash: 2f5ad16893a898d4258762b25fea3d557607a3f8
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77141152"
---
# <a name="improper_scheduler_detach-class"></a>improper_scheduler_detach-Klasse

Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn die `CurrentScheduler::Detach`-Methode für einen Kontext aufgerufen wird, der nicht mittels der `Attach`-Methode eines `Scheduler`-Objekts an einen Planer angefügt wurde.

## <a name="syntax"></a>Syntax

```cpp
class improper_scheduler_detach : public std::exception;
```

## <a name="members"></a>Members

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[improper_scheduler_detach](#ctor)|Ist überladen. Erstellt ein `improper_scheduler_detach`-Objekt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`exception`

`improper_scheduler_detach`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** ConcRT. h

**Namespace:** Parallelität

## <a name="ctor"></a>improper_scheduler_detach

Erstellt ein `improper_scheduler_detach`-Objekt.

```cpp
explicit _CRTIMP improper_scheduler_detach(_In_z_ const char* _Message) throw();

improper_scheduler_detach() throw();
```

### <a name="parameters"></a>Parameter

*_Message*<br/>
Eine beschreibende Fehlermeldung.

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[Scheduler-Klasse](scheduler-class.md)
