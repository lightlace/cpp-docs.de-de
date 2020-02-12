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
ms.openlocfilehash: 253cd76182e1b6f85be3701663bd10c86c10e6ba
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142339"
---
# <a name="unsupported_os-class"></a>unsupported_os-Klasse

Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn ein nicht unterstütztes Betriebssystem verwendet wird.

## <a name="syntax"></a>Syntax

```cpp
class unsupported_os : public std::exception;
```

## <a name="members"></a>Members

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[unsupported_os](#ctor)|Ist überladen. Erstellt ein `unsupported_os`-Objekt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`exception`

`unsupported_os`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** ConcRT. h

**Namespace:** Parallelität

## <a name="ctor"></a>unsupported_os

Erstellt ein `unsupported_os`-Objekt.

### <a name="syntax"></a>Syntax

```cpp
explicit _CRTIMP unsupported_os(_In_z_ const char* _Message) throw();

unsupported_os() throw();
```

### <a name="parameters"></a>Parameter

*_Message*<br/>
Eine beschreibende Fehlermeldung.

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace](concurrency-namespace.md)
