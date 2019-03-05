---
title: invalid_scheduler_policy_value-Klasse
ms.date: 11/04/2016
f1_keywords:
- concrt/concurrency::invalid_scheduler_policy_value
helpviewer_keywords:
- invalid_scheduler_policy_value class
ms.assetid: 8c533e3f-2774-4192-8616-b2313b859bf7
ms.openlocfilehash: 8b8e233769d859aac102d0554a6987e9b7201473
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57301440"
---
# <a name="invalidschedulerpolicyvalue-class"></a>invalid_scheduler_policy_value-Klasse

Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn der Richtlinienschlüssel eines `SchedulerPolicy`-Objekts auf einen ungültigen Wert für diesen Schlüssel festgelegt wird.

## <a name="syntax"></a>Syntax

```
class invalid_scheduler_policy_value : public std::exception;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[invalid_scheduler_policy_value](invalid-scheduler-policy-thread-specification-class.md#ctor|Überladen. Erstellt ein `invalid_scheduler_policy_value`-Objekt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`exception`

`invalid_scheduler_policy_value`

## <a name="requirements"></a>Anforderungen

**Header:** concrt.h

**Namespace:** Parallelität

##  <a name="ctor"></a> invalid_scheduler_policy_value

Erstellt ein `invalid_scheduler_policy_value`-Objekt.

```
explicit _CRTIMP invalid_scheduler_policy_value(_In_z_ const char* _Message) throw();

invalid_scheduler_policy_value() throw();
```

### <a name="parameters"></a>Parameter

*_Message*<br/>
Eine beschreibende Fehlermeldung.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[SchedulerPolicy-Klasse](schedulerpolicy-class.md)
