---
title: invalid_compute_domain-Klasse
ms.date: 11/04/2016
f1_keywords:
- invalid_compute_domain
- AMPRT/invalid_compute_domain
- AMPRT/Concurrency::invalid_compute_domain::invalid_compute_domain
helpviewer_keywords:
- invalid_compute_domain class
ms.assetid: ac7a7166-8bdb-4db1-8caf-ea129ab5117e
ms.openlocfilehash: 51fcd9e42bc4497131da5adb3dff72efb46537b3
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57296877"
---
# <a name="invalidcomputedomain-class"></a>invalid_compute_domain-Klasse

Die Ausnahme, die ausgelöst wird, wenn Sie einen Kernel nicht mithilfe der Compute-Domäne angegeben, an die Laufzeit starten die [Parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each) Aufrufsite.

## <a name="syntax"></a>Syntax

```
class invalid_compute_domain : public runtime_exception;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[Invalid_compute_domain-Konstruktor](#ctor)|Initialisiert eine neue Instanz der `invalid_compute_domain`-Klasse.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`exception`

`runtime_exception`

`invalid_compute_domain`

## <a name="requirements"></a>Anforderungen

**Header:** amprt.h

**Namespace:** Parallelität

## <a name="ctor"></a> invalid_compute_domain

Initialisiert eine neue Instanz der Klasse.

## <a name="syntax"></a>Syntax

```
explicit invalid_compute_domain(
    const char * _Message ) throw();

invalid_compute_domain() throw();
```

### <a name="parameters"></a>Parameter

*_Message*<br/>
Eine Beschreibung des Fehlers.

### <a name="return-value"></a>Rückgabewert

Eine Instanz der `invalid_compute_domain`-Klasse

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)
