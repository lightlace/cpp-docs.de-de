---
title: Improper_scheduler_reference-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- improper_scheduler_reference
- CONCRT/concurrency::improper_scheduler_reference
- CONCRT/concurrency::improper_scheduler_reference::improper_scheduler_reference
dev_langs:
- C++
helpviewer_keywords:
- improper_scheduler_reference class
ms.assetid: 434a7512-7796-4255-92a7-f3bf71c6a7a7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c5a061ca3c7bb39d90608685e04b62da9b2e83fb
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46410415"
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

**Header:** concrt.h hinzu

**Namespace:** Parallelität

##  <a name="ctor"></a> improper_scheduler_reference

Erstellt ein `improper_scheduler_reference`-Objekt.

```
explicit _CRTIMP improper_scheduler_reference(_In_z_ const char* _Message) throw();

improper_scheduler_reference() throw();
```

### <a name="parameters"></a>Parameter

*_Nachricht*<br/>
Eine beschreibende Fehlermeldung.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[Scheduler-Klasse](scheduler-class.md)
