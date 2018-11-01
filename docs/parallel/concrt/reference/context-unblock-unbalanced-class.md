---
title: context_unblock_unbalanced-Klasse
ms.date: 11/04/2016
f1_keywords:
- context_unblock_unbalanced
- CONCRT/concurrency::context_unblock_unbalanced
- CONCRT/concurrency::context_unblock_unbalanced::context_unblock_unbalanced
helpviewer_keywords:
- context_unblock_unbalanced class
ms.assetid: a76066c8-19dd-44fa-959a-6941ec1b0d2d
ms.openlocfilehash: cc2ef970fa354da4abb7351cb4f1188451887552
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50525926"
---
# <a name="contextunblockunbalanced-class"></a>context_unblock_unbalanced-Klasse

Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn Aufrufe der `Block`-Methode und der `Unblock`-Methode eines `Context`-Objekts nicht ordnungsgemäß zugeordnet werden.

## <a name="syntax"></a>Syntax

```
class context_unblock_unbalanced : public std::exception;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[context_unblock_unbalanced](#ctor)|Überladen. Erstellt ein `context_unblock_unbalanced`-Objekt.|

## <a name="remarks"></a>Hinweise

Aufrufe von der `Block` und `Unblock` Methoden eine `Context` Objekt muss immer ordnungsgemäß kombiniert werden. Die Concurrency Runtime ermöglicht, die Vorgänge in beliebiger Reihenfolge ausgeführt wird. Z. B. einen Aufruf von `Block` kann durch einen Aufruf folgen `Unblock`, oder umgekehrt. Diese Ausnahme wird ausgelöst, wenn, z. B. zwei Aufrufe der `Unblock` Methode in einer Zeile vorgenommen wurden, auf eine `Context` Objekt, das nicht gesperrt wurde.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`exception`

`context_unblock_unbalanced`

## <a name="requirements"></a>Anforderungen

**Header:** concrt.h hinzu

**Namespace:** Parallelität

##  <a name="ctor"></a> context_unblock_unbalanced

Erstellt ein `context_unblock_unbalanced`-Objekt.

```
explicit _CRTIMP context_unblock_unbalanced(_In_z_ const char* _Message) throw();

context_unblock_unbalanced() throw();
```

### <a name="parameters"></a>Parameter

*_Nachricht*<br/>
Eine beschreibende Fehlermeldung.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)
