---
title: uninitialized_object-Klasse
ms.date: 03/27/2019
f1_keywords:
- uninitialized_object
- AMPRT/uninitialized_object
- AMPRT/Concurrency::uninitialized_object
helpviewer_keywords:
- uninitialized_object class
ms.assetid: 6ae3c4e8-64a6-4511-a158-03be197b63af
ms.openlocfilehash: ef7ded0bf925d3430b70064c4979b75e08f9cf45
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77127698"
---
# <a name="uninitialized_object-class"></a>uninitialized_object-Klasse

Die Ausnahme, die ausgelöst wird, wenn ein nicht initialisiertes Objekt verwendet wird.

## <a name="syntax"></a>Syntax

```cpp
class uninitialized_object : public runtime_exception;
```

## <a name="members"></a>Members

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[uninitialized_object-Konstruktor](#uninitialized_object)|Initialisiert eine neue Instanz der Klasse `uninitialized_object`.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`exception`

`runtime_exception`

`uninitialized_object`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** amprt. h

**Namespace:** Parallelität

## <a name="uninitialized_object"></a>uninitialized_object

Erstellt eine neue Instanz der `uninitialized_object`-Ausnahme.

### <a name="syntax"></a>Syntax

```cpp
explicit uninitialized_object(
    const char * _Message ) throw();

uninitialized_object() throw();
```

### <a name="parameters"></a>Parameter

*_Message*<br/>
Eine Beschreibung des Fehlers.

### <a name="return-value"></a>Rückgabewert

Das `uninitialized_object` Exception-Objekt.

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)
