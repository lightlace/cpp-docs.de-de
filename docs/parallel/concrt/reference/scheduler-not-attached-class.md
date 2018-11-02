---
title: scheduler_not_attached-Klasse
ms.date: 11/04/2016
f1_keywords:
- scheduler_not_attached
- CONCRT/concurrency::scheduler_not_attached
- CONCRT/concurrency::scheduler_not_attached::scheduler_not_attached
helpviewer_keywords:
- scheduler_not_attached class
ms.assetid: 26001970-b400-463b-be3d-8623359c399a
ms.openlocfilehash: 159202445f95e8fbac93902dec43fc0f99180e8e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50560666"
---
# <a name="schedulernotattached-class"></a>scheduler_not_attached-Klasse

Diese Klasse beschreibt eine Ausnahme, die bei Ausführen eines Vorgangs ausgelöst wird, der erfordert, dass ein Planer an den aktuellen Kontext angefügt wird, und einer nicht.

## <a name="syntax"></a>Syntax

```
class scheduler_not_attached : public std::exception;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[scheduler_not_attached](#ctor)|Überladen. Erstellt ein `scheduler_not_attached`-Objekt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`exception`

`scheduler_not_attached`

## <a name="requirements"></a>Anforderungen

**Header:** concrt.h hinzu

**Namespace:** Parallelität

##  <a name="ctor"></a> scheduler_not_attached

Erstellt ein `scheduler_not_attached`-Objekt.

```
explicit _CRTIMP scheduler_not_attached(_In_z_ const char* _Message) throw();

scheduler_not_attached() throw();
```

### <a name="parameters"></a>Parameter

*_Nachricht*<br/>
Eine beschreibende Fehlermeldung.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[Scheduler-Klasse](scheduler-class.md)
