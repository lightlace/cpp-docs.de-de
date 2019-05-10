---
title: unsupported_feature-Klasse
ms.date: 03/27/2019
f1_keywords:
- unsupported_feature
- AMPRT/unsupported_feature
- AMPRT/Concurrency::unsupported_feature
helpviewer_keywords:
- unsupported_feature class
ms.assetid: 6b1ab917-df13-48c7-9648-7cb2465a0ff5
ms.openlocfilehash: 451318bfbcfb9c5e002677556944e3499c0ed5fb
ms.sourcegitcommit: 00e26915924869cd7eb3c971a7d0604388abd316
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2019
ms.locfileid: "65525415"
---
# <a name="unsupportedfeature-class"></a>unsupported_feature-Klasse

Die Ausnahme, die ausgelöst wird, wenn eine nicht unterstützte Funktion verwendet wird.

## <a name="syntax"></a>Syntax

```
class unsupported_feature : public runtime_exception;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[Unsupported_feature-Konstruktor](#unsupported_feature)|Erstellt eine neue Instanz der `unsupported_feature`-Ausnahme.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`exception`

`runtime_exception`

`unsupported_feature`

## <a name="unsupported_feature"></a> unsupported_feature

  Erstellt eine neue Instanz der `unsupported_feature`-Ausnahme.

### <a name="syntax"></a>Syntax

```
explicit unsupported_feature(
    const char * _Message ) throw();

unsupported_feature() throw();
```

### <a name="parameters"></a>Parameter

*_Message*<br/>
Eine Beschreibung des Fehlers.

### <a name="return-value"></a>Rückgabewert

Das `unsupported_feature`-Objekt.

## <a name="requirements"></a>Anforderungen

**Header:** amprt.h

**Namespace:** Parallelität

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)
