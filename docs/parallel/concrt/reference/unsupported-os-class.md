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
ms.openlocfilehash: 8277827aa8713ef57731a3e0da0898829b9fa9fe
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57289285"
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

**Header:** concrt.h

**Namespace:** Parallelität

##  <a name="ctor"></a> unsupported_os

Erstellt ein `unsupported_os`-Objekt.

```
explicit _CRTIMP unsupported_os(_In_z_ const char* _Message) throw();

unsupported_os() throw();
```

### <a name="parameters"></a>Parameter

*_Message*<br/>
Eine beschreibende Fehlermeldung.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)
