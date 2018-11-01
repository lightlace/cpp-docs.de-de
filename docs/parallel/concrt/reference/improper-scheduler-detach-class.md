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
ms.openlocfilehash: b2fc90656051be62528d0aac600fad67485c81f9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50643286"
---
# <a name="improperschedulerdetach-class"></a>improper_scheduler_detach-Klasse

Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn die `CurrentScheduler::Detach`-Methode für einen Kontext aufgerufen wird, der nicht mittels der `Attach`-Methode eines `Scheduler`-Objekts an einen Planer angefügt wurde.

## <a name="syntax"></a>Syntax

```
class improper_scheduler_detach : public std::exception;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[improper_scheduler_detach](#ctor)|Überladen. Erstellt ein `improper_scheduler_detach`-Objekt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`exception`

`improper_scheduler_detach`

## <a name="requirements"></a>Anforderungen

**Header:** concrt.h hinzu

**Namespace:** Parallelität

##  <a name="ctor"></a> improper_scheduler_detach

Erstellt ein `improper_scheduler_detach`-Objekt.

```
explicit _CRTIMP improper_scheduler_detach(_In_z_ const char* _Message) throw();

improper_scheduler_detach() throw();
```

### <a name="parameters"></a>Parameter

*_Nachricht*<br/>
Eine beschreibende Fehlermeldung.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[Scheduler-Klasse](scheduler-class.md)
