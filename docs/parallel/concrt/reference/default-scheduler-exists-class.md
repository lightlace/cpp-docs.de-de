---
title: default_scheduler_exists-Klasse
ms.date: 11/04/2016
f1_keywords:
- default_scheduler_exists
- CONCRT/concurrency::default_scheduler_exists
- CONCRT/concurrency::default_scheduler_exists::default_scheduler_exists
helpviewer_keywords:
- default_scheduler_exists class
ms.assetid: f6e575e2-4e0f-455a-9e06-54f462ce0c1c
ms.openlocfilehash: eed5dd242beb4c4cd481f22635e0d5f71c28d7e6
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77139187"
---
# <a name="default_scheduler_exists-class"></a>default_scheduler_exists-Klasse

Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, sobald die `Scheduler::SetDefaultSchedulerPolicy`-Methode aufgerufen wird, sofern ein Standardplaner bereits innerhalb des Prozesses vorhanden ist.

## <a name="syntax"></a>Syntax

```cpp
class default_scheduler_exists : public std::exception;
```

## <a name="members"></a>Members

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[default_scheduler_exists](#ctor)|Ist überladen. Erstellt ein `default_scheduler_exists`-Objekt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`exception`

`default_scheduler_exists`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** ConcRT. h

**Namespace:** Parallelität

## <a name="ctor"></a>default_scheduler_exists

Erstellt ein `default_scheduler_exists`-Objekt.

```cpp
explicit _CRTIMP default_scheduler_exists(_In_z_ const char* _Message) throw();

default_scheduler_exists() throw();
```

### <a name="parameters"></a>Parameter

*_Message*<br/>
Eine beschreibende Fehlermeldung.

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace](concurrency-namespace.md)
