---
title: uninitialized_object-Klasse
ms.date: 11/04/2016
f1_keywords:
- uninitialized_object
- AMPRT/uninitialized_object
- AMPRT/Concurrency::uninitialized_object
helpviewer_keywords:
- uninitialized_object class
ms.assetid: 6ae3c4e8-64a6-4511-a158-03be197b63af
ms.openlocfilehash: 5dc03964e8ddef0cd1aab785316eabd98c39e59e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50544533"
---
# <a name="uninitializedobject-class"></a>uninitialized_object-Klasse

Die Ausnahme, die ausgelöst wird, wenn ein nicht initialisiertes Objekt verwendet wird.

## <a name="syntax"></a>Syntax

```
class uninitialized_object : public runtime_exception;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[Uninitialized_object-Konstruktor](#ctor)|Initialisiert eine neue Instanz der `uninitialized_object`-Klasse.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`exception`

`runtime_exception`

`uninitialized_object`

## <a name="requirements"></a>Anforderungen

**Header:** amprt.h

**Namespace:** Parallelität
## <a name="uninitialized_object__ctor"></a> unsupported_feature

Erstellt eine neue Instanz der unsupported_feature-Ausnahme.

### <a name="syntax"></a>Syntax

```
explicit unsupported_feature(
    const char * _Message ) throw();

unsupported_feature() throw();
```

### <a name="parameters"></a>Parameter

*_Nachricht*<br/>
Eine Beschreibung des Fehlers.

### <a name="return-value"></a>Rückgabewert

Das `unsupported_feature`-Objekt.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)
