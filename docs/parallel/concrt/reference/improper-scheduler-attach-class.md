---
title: improper_scheduler_attach-Klasse
ms.date: 11/04/2016
f1_keywords:
- improper_scheduler_attach
- CONCRT/concurrency::improper_scheduler_attach
- CONCRT/concurrency::improper_scheduler_attach::improper_scheduler_attach
helpviewer_keywords:
- improper_scheduler_attach class
ms.assetid: 5a76da0a-091b-4748-8f62-b3a28f674f9e
ms.openlocfilehash: 85adf3f919d94a82f5a68a5cd9e5f44cdca10006
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77141229"
---
# <a name="improper_scheduler_attach-class"></a>improper_scheduler_attach-Klasse

Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn die `Attach`-Methode für ein `Scheduler`-Objekt aufgerufen wird, das bereits an den aktuellen Kontext angefügt wurde.

## <a name="syntax"></a>Syntax

```cpp
class improper_scheduler_attach : public std::exception;
```

## <a name="members"></a>Members

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[improper_scheduler_attach](#ctor)|Ist überladen. Erstellt ein `improper_scheduler_attach`-Objekt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`exception`

`improper_scheduler_attach`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** ConcRT. h

**Namespace:** Parallelität

## <a name="ctor"></a>improper_scheduler_attach

Erstellt ein `improper_scheduler_attach`-Objekt.

```cpp
explicit _CRTIMP improper_scheduler_attach(_In_z_ const char* _Message) throw();

improper_scheduler_attach() throw();
```

### <a name="parameters"></a>Parameter

*_Message*<br/>
Eine beschreibende Fehlermeldung.

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[Scheduler-Klasse](scheduler-class.md)
