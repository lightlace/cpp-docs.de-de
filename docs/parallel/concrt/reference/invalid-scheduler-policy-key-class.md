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
ms.openlocfilehash: 60d5a57ff9cb33a3d522c14514f5107844216852
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77143025"
---
# <a name="invalid_scheduler_policy_key-class"></a>invalid_scheduler_policy_key-Klasse

Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn ein ungültiger oder unbekannter Schlüssel an einen `SchedulerPolicy`-Objektkonstruktor übergeben wird, oder wenn der `SetPolicyValue`-Methode eines `SchedulerPolicy`-Objekts ein Schlüssel übergeben wird, der auf andere Weise geändert werden muss, z. B. die `SetConcurrencyLimits`-Methode.

## <a name="syntax"></a>Syntax

```cpp
class invalid_scheduler_policy_key : public std::exception;
```

## <a name="members"></a>Members

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[invalid_scheduler_policy_key](#ctor)|Ist überladen. Erstellt ein `invalid_scheduler_policy_key`-Objekt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`exception`

`invalid_scheduler_policy_key`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** ConcRT. h

**Namespace:** Parallelität

## <a name="ctor"></a>invalid_scheduler_policy_key

Erstellt ein `invalid_scheduler_policy_key`-Objekt.

```cpp
explicit _CRTIMP invalid_scheduler_policy_key(_In_z_ const char* _Message) throw();

invalid_scheduler_policy_key() throw();
```

### <a name="parameters"></a>Parameter

*_Message*<br/>
Eine beschreibende Fehlermeldung.

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[SchedulerPolicy-Klasse](schedulerpolicy-class.md)
