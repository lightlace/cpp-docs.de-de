---
title: improper_scheduler_reference-Klasse
ms.date: 11/04/2016
f1_keywords:
- improper_scheduler_reference
- CONCRT/concurrency::improper_scheduler_reference
- CONCRT/concurrency::improper_scheduler_reference::improper_scheduler_reference
helpviewer_keywords:
- improper_scheduler_reference class
ms.assetid: 434a7512-7796-4255-92a7-f3bf71c6a7a7
ms.openlocfilehash: 121e61447775cdcb5d7f5f1187c5d4cc6b7d68b7
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57265651"
---
# <a name="improperschedulerreference-class"></a>improper_scheduler_reference-Klasse

Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn die `Reference`-Methode für ein `Scheduler`-Objekt aufgerufen wird, das aus einem Kontext heruntergefahren wird, der nicht Teil dieses Planers ist.

## <a name="syntax"></a>Syntax

```
class improper_scheduler_reference : public std::exception;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[improper_scheduler_reference](#ctor)|Überladen. Erstellt ein `improper_scheduler_reference`-Objekt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`exception`

`improper_scheduler_reference`

## <a name="requirements"></a>Anforderungen

**Header:** concrt.h

**Namespace:** Parallelität

##  <a name="ctor"></a> improper_scheduler_reference

Erstellt ein `improper_scheduler_reference`-Objekt.

```
explicit _CRTIMP improper_scheduler_reference(_In_z_ const char* _Message) throw();

improper_scheduler_reference() throw();
```

### <a name="parameters"></a>Parameter

*_Message*<br/>
Eine beschreibende Fehlermeldung.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[Scheduler-Klasse](scheduler-class.md)
