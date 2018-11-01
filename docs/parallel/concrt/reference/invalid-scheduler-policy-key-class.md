---
title: invalid_scheduler_policy_key-Klasse
ms.date: 11/04/2016
f1_keywords:
- invalid_scheduler_policy_key
- CONCRT/concurrency::invalid_scheduler_policy_key
- CONCRT/concurrency::invalid_scheduler_policy_key::invalid_scheduler_policy_key
helpviewer_keywords:
- invalid_scheduler_policy_key class
ms.assetid: 6a7c42fe-9bc4-4a02-bebb-99fe9ef9817d
ms.openlocfilehash: 775b98d2394dce04b362e92927db1a408b8e1656
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50677408"
---
# <a name="invalidschedulerpolicykey-class"></a>invalid_scheduler_policy_key-Klasse

Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn ein ungültiger oder unbekannter Schlüssel an einen `SchedulerPolicy`-Objektkonstruktor übergeben wird, oder wenn der `SetPolicyValue`-Methode eines `SchedulerPolicy`-Objekts ein Schlüssel übergeben wird, der auf andere Weise geändert werden muss, z. B. die `SetConcurrencyLimits`-Methode.

## <a name="syntax"></a>Syntax

```
class invalid_scheduler_policy_key : public std::exception;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[invalid_scheduler_policy_key](#ctor)|Überladen. Erstellt ein `invalid_scheduler_policy_key`-Objekt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`exception`

`invalid_scheduler_policy_key`

## <a name="requirements"></a>Anforderungen

**Header:** concrt.h hinzu

**Namespace:** Parallelität

##  <a name="ctor"></a> invalid_scheduler_policy_key

Erstellt ein `invalid_scheduler_policy_key`-Objekt.

```
explicit _CRTIMP invalid_scheduler_policy_key(_In_z_ const char* _Message) throw();

invalid_scheduler_policy_key() throw();
```

### <a name="parameters"></a>Parameter

*_Nachricht*<br/>
Eine beschreibende Fehlermeldung.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[SchedulerPolicy-Klasse](schedulerpolicy-class.md)
