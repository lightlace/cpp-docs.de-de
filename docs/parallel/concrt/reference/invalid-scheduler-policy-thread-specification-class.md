---
title: invalid_scheduler_policy_thread_specification-Klasse
ms.date: 11/04/2016
f1_keywords:
- concrt/concurrency::invalid_scheduler_policy_thread_specification
helpviewer_keywords:
- invalid_scheduler_policy_thread_specification class
ms.assetid: 2d0fafb2-18f8-4284-8040-3db640d33303
ms.openlocfilehash: 26d09610c6bb9e0c87852c9804e094617b021273
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57278872"
---
# <a name="invalidschedulerpolicythreadspecification-class"></a>invalid_scheduler_policy_thread_specification-Klasse

Diese Klasse beschreibt eine Ausnahme, die bei dem Versuch ausgelöst wird, die Parallelitätsgrenzen eines `SchedulerPolicy`-Objekts so festzulegen, dass der Wert des `MinConcurrency`-Schlüssels kleiner ist, als der Wert des `MaxConcurrency`-Schlüssels.

## <a name="syntax"></a>Syntax

```
class invalid_scheduler_policy_thread_specification : public std::exception;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[invalid_scheduler_policy_thread_specification](invalid-scheduler-policy-value-class.md#ctor|Überladen. Erstellt ein `invalid_scheduler_policy_value`-Objekt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`exception`

`invalid_scheduler_policy_thread_specification`

## <a name="requirements"></a>Anforderungen

**Header:** concrt.h

**Namespace:** Parallelität
##  <a name="ctor"></a> invalid_scheduler_policy_thread_specification

Erstellt ein `invalid_scheduler_policy_value`-Objekt.

```
explicit _CRTIMP invalid_scheduler_policy_thread_specification(_In_z_ const char* _Message) throw();

invalid_scheduler_policy_thread_specification() throw();
```

### <a name="parameters"></a>Parameter

*_Message*<br/>
Eine beschreibende Fehlermeldung.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[SchedulerPolicy-Klasse](schedulerpolicy-class.md)
