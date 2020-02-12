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
ms.openlocfilehash: 7a879fc2da2f963cd4b5ea5fcd7e9506f86ce051
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77140838"
---
# <a name="invalid_oversubscribe_operation-class"></a>invalid_oversubscribe_operation-Klasse

Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn die `Context::Oversubscribe`-Methode aufgerufen wird, wobei der `_BeginOversubscription`-Parameter ohne vorherige Aufruf der `Context::Oversubscribe`-Methode auf **false** festgelegt ist, wobei der `_BeginOversubscription`-Parameter auf **true**gesetzt ist.

## <a name="syntax"></a>Syntax

```cpp
class invalid_oversubscribe_operation : public std::exception;
```

## <a name="members"></a>Members

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[invalid_oversubscribe_operation](#ctor)|Ist überladen. Erstellt ein `invalid_oversubscribe_operation`-Objekt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`exception`

`invalid_oversubscribe_operation`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** ConcRT. h

**Namespace:** Parallelität

## <a name="ctor"></a>invalid_oversubscribe_operation

Erstellt ein `invalid_oversubscribe_operation`-Objekt.

```cpp
explicit _CRTIMP invalid_oversubscribe_operation(_In_z_ const char* _Message) throw();

invalid_oversubscribe_operation() throw();
```

### <a name="parameters"></a>Parameter

*_Message*<br/>
Eine beschreibende Fehlermeldung.

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace](concurrency-namespace.md)
