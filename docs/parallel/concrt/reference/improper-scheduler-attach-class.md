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
ms.openlocfilehash: 617c71115b8a1354dbb1d9998791564f0a5d18de
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50614707"
---
# <a name="improperschedulerattach-class"></a>improper_scheduler_attach-Klasse

Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn die `Attach`-Methode für ein `Scheduler`-Objekt aufgerufen wird, das bereits an den aktuellen Kontext angefügt wurde.

## <a name="syntax"></a>Syntax

```
class improper_scheduler_attach : public std::exception;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[improper_scheduler_attach](#ctor)|Überladen. Erstellt ein `improper_scheduler_attach`-Objekt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`exception`

`improper_scheduler_attach`

## <a name="requirements"></a>Anforderungen

**Header:** concrt.h hinzu

**Namespace:** Parallelität

##  <a name="ctor"></a> improper_scheduler_attach

Erstellt ein `improper_scheduler_attach`-Objekt.

```
explicit _CRTIMP improper_scheduler_attach(_In_z_ const char* _Message) throw();

improper_scheduler_attach() throw();
```

### <a name="parameters"></a>Parameter

*_Nachricht*<br/>
Eine beschreibende Fehlermeldung.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[Scheduler-Klasse](scheduler-class.md)
