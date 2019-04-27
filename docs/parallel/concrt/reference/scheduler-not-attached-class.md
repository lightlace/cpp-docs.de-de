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
ms.openlocfilehash: be8a04c7cf6ef5aa4d6070e92df14e643395ef00
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160119"
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

**Header:** concrt.h

**Namespace:** Parallelität

##  <a name="ctor"></a> scheduler_not_attached

Erstellt ein `scheduler_not_attached`-Objekt.

```
explicit _CRTIMP scheduler_not_attached(_In_z_ const char* _Message) throw();

scheduler_not_attached() throw();
```

### <a name="parameters"></a>Parameter

*_Message*<br/>
Eine beschreibende Fehlermeldung.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[Scheduler-Klasse](scheduler-class.md)
