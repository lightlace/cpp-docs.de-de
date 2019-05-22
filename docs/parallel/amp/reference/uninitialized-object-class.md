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
ms.openlocfilehash: a977957fcb28a7f4c6c849c954026e2bda4e728c
ms.sourcegitcommit: a61d17cffdd50f1c3c6e082a01bbcbc85b6cc5a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2019
ms.locfileid: "65975159"
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
|[Uninitialized_object-Konstruktor](#uninitialized_object)|Initialisiert eine neue Instanz der `uninitialized_object`-Klasse.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`exception`

`runtime_exception`

`uninitialized_object`

## <a name="requirements"></a>Anforderungen

**Header:** amprt.h

**Namespace:** Parallelität

## <a name="uninitialized_object"></a> uninitialized_object

Erstellt eine neue Instanz der `uninitialized_object`-Ausnahme.

### <a name="syntax"></a>Syntax

```
explicit uninitialized_object(
    const char * _Message ) throw();

uninitialized_object() throw();
```

### <a name="parameters"></a>Parameter

*_Message*<br/>
Eine Beschreibung des Fehlers.

### <a name="return-value"></a>Rückgabewert

Die `uninitialized_object` Exception-Objekt.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)
