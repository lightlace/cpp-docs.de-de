---
title: invalid_oversubscribe_operation-Klasse
ms.date: 11/04/2016
f1_keywords:
- invalid_oversubscribe_operation
- CONCRT/concurrency::invalid_oversubscribe_operation
- CONCRT/concurrency::invalid_oversubscribe_operation::invalid_oversubscribe_operation
helpviewer_keywords:
- invalid_oversubscribe_operation class
ms.assetid: 0a9c5f08-d5e6-4ad0-90a9-517472b3ac28
ms.openlocfilehash: 200743d41c1c45f2a957dba0716dd7aa07e3de76
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405312"
---
# <a name="invalidoversubscribeoperation-class"></a>invalid_oversubscribe_operation-Klasse

Diese Klasse beschreibt eine Ausnahme wird ausgelöst, wenn die `Context::Oversubscribe` Methode wird aufgerufen, mit der `_BeginOversubscription` Parametersatz zu **"false"** ohne einen vorherigen Aufruf an die `Context::Oversubscribe` -Methode mit der `_BeginOversubscription` Parametersatz zu **"true"**.

## <a name="syntax"></a>Syntax

```
class invalid_oversubscribe_operation : public std::exception;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[invalid_oversubscribe_operation](#ctor)|Überladen. Erstellt ein `invalid_oversubscribe_operation`-Objekt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`exception`

`invalid_oversubscribe_operation`

## <a name="requirements"></a>Anforderungen

**Header:** concrt.h

**Namespace:** Parallelität

##  <a name="ctor"></a> invalid_oversubscribe_operation

Erstellt ein `invalid_oversubscribe_operation`-Objekt.

```
explicit _CRTIMP invalid_oversubscribe_operation(_In_z_ const char* _Message) throw();

invalid_oversubscribe_operation() throw();
```

### <a name="parameters"></a>Parameter

*_Message*<br/>
Eine beschreibende Fehlermeldung.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)
