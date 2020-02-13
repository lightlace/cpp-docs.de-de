---
title: context_self_unblock-Klasse
ms.date: 11/04/2016
f1_keywords:
- context_self_unblock
- CONCRT/concurrency::context_self_unblock
- CONCRT/concurrency::context_self_unblock::context_self_unblock
helpviewer_keywords:
- context_self_unblock class
ms.assetid: 9601cd28-4f40-4c2e-89ab-747068956331
ms.openlocfilehash: 883d5630251a6ea13afba1164f221a0da1773c17
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77143109"
---
# <a name="context_self_unblock-class"></a>context_self_unblock-Klasse

Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn die `Unblock`-Methode für ein `Context`-Objekt aufgerufen wird, das im gleichen Kontext aufgerufen wird. Das würde den Versuch eines angegebenen Kontexts zum Aufheben der eigenen Blockierung angeben.

## <a name="syntax"></a>Syntax

```cpp
class context_self_unblock : public std::exception;
```

## <a name="members"></a>Members

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[context_self_unblock](#ctor)|Ist überladen. Erstellt ein `context_self_unblock`-Objekt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`exception`

`context_self_unblock`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** ConcRT. h

**Namespace:** Parallelität

## <a name="ctor"></a>context_self_unblock

Erstellt ein `context_self_unblock`-Objekt.

```cpp
explicit _CRTIMP context_self_unblock(_In_z_ const char* _Message) throw();

context_self_unblock() throw();
```

### <a name="parameters"></a>Parameter

*_Message*<br/>
Eine beschreibende Fehlermeldung.

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace](concurrency-namespace.md)
