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
ms.openlocfilehash: 326a2dfc6837665adb4d46a6aaa8780052ad2b22
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57275273"
---
# <a name="defaultschedulerexists-class"></a>default_scheduler_exists-Klasse

Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, sobald die `Scheduler::SetDefaultSchedulerPolicy`-Methode aufgerufen wird, sofern ein Standardplaner bereits innerhalb des Prozesses vorhanden ist.

## <a name="syntax"></a>Syntax

```
class default_scheduler_exists : public std::exception;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[default_scheduler_exists](#ctor)|Überladen. Erstellt ein `default_scheduler_exists`-Objekt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`exception`

`default_scheduler_exists`

## <a name="requirements"></a>Anforderungen

**Header:** concrt.h

**Namespace:** Parallelität

##  <a name="ctor"></a> default_scheduler_exists

Erstellt ein `default_scheduler_exists`-Objekt.

```
explicit _CRTIMP default_scheduler_exists(_In_z_ const char* _Message) throw();

default_scheduler_exists() throw();
```

### <a name="parameters"></a>Parameter

*_Message*<br/>
Eine beschreibende Fehlermeldung.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)
