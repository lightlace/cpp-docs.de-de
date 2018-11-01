---
title: unsupported_os-Klasse
ms.date: 11/04/2016
f1_keywords:
- unsupported_os
- CONCRT/concurrency::unsupported_os
- CONCRT/concurrency::unsupported_os::unsupported_os
helpviewer_keywords:
- unsupported_os class
ms.assetid: 6fa57636-341b-4b51-84cc-261d283ff736
ms.openlocfilehash: a776daf138b5fa2da0426afd38bdf7f67721c199
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50448268"
---
# <a name="unsupportedos-class"></a>unsupported_os-Klasse

Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn ein nicht unterstütztes Betriebssystem verwendet wird.

## <a name="syntax"></a>Syntax

```
class unsupported_os : public std::exception;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[unsupported_os](#ctor)|Überladen. Erstellt ein `unsupported_os`-Objekt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`exception`

`unsupported_os`

## <a name="requirements"></a>Anforderungen

**Header:** concrt.h hinzu

**Namespace:** Parallelität

##  <a name="ctor"></a> unsupported_os

Erstellt ein `unsupported_os`-Objekt.

```
explicit _CRTIMP unsupported_os(_In_z_ const char* _Message) throw();

unsupported_os() throw();
```

### <a name="parameters"></a>Parameter

*_Nachricht*<br/>
Eine beschreibende Fehlermeldung.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)
