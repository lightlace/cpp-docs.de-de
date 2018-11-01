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
ms.openlocfilehash: 5cb7fc951a4c62f4d299ce7d394e9f8268d7ed74
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50622169"
---
# <a name="contextselfunblock-class"></a>context_self_unblock-Klasse

Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn die `Unblock`-Methode für ein `Context`-Objekt aufgerufen wird, das im gleichen Kontext aufgerufen wird. Das würde den Versuch eines angegebenen Kontexts zum Aufheben der eigenen Blockierung angeben.

## <a name="syntax"></a>Syntax

```
class context_self_unblock : public std::exception;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[context_self_unblock](#ctor)|Überladen. Erstellt ein `context_self_unblock`-Objekt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`exception`

`context_self_unblock`

## <a name="requirements"></a>Anforderungen

**Header:** concrt.h hinzu

**Namespace:** Parallelität

##  <a name="ctor"></a> context_self_unblock

Erstellt ein `context_self_unblock`-Objekt.

```
explicit _CRTIMP context_self_unblock(_In_z_ const char* _Message) throw();

context_self_unblock() throw();
```

### <a name="parameters"></a>Parameter

*_Nachricht*<br/>
Eine beschreibende Fehlermeldung.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)
