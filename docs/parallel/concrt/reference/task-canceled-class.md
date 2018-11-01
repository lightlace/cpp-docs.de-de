---
title: task_canceled-Klasse
ms.date: 11/04/2016
f1_keywords:
- task_canceled
- CONCRT/concurrency::task_canceled
- CONCRT/concurrency::task_canceled::task_canceled
helpviewer_keywords:
- task_canceled class
ms.assetid: c3f0b234-2cc1-435f-a48e-995f45b190be
ms.openlocfilehash: b17050deacd1dee0c1b08ffbc4056e957884cd3a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50617450"
---
# <a name="taskcanceled-class"></a>task_canceled-Klasse

Diese Klasse beschreibt eine Ausnahme, die von den PPL-Aufgaben ausgelöst wird, um das Abbrechen der aktuellen Aufgabe zu erzwingen. Es wird auch ausgelöst, durch die `get()` Methode [Aufgabe](/visualstudio/extensibility/debugger/task-class-internal-members), für eine abgebrochene Aufgabe.

## <a name="syntax"></a>Syntax

```
class task_canceled : public std::exception;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[task_canceled](#ctor)|Überladen. Erstellt ein `task_canceled`-Objekt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`exception`

`task_canceled`

## <a name="requirements"></a>Anforderungen

**Header:** concrt.h hinzu

**Namespace:** Parallelität

##  <a name="ctor"></a> task_canceled

Erstellt ein `task_canceled`-Objekt.

```
explicit _CRTIMP task_canceled(_In_z_ const char* _Message) throw();

task_canceled() throw();
```

### <a name="parameters"></a>Parameter

*_Nachricht*<br/>
Eine beschreibende Fehlermeldung.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)
