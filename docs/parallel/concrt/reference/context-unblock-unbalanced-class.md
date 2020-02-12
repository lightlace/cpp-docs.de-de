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
ms.openlocfilehash: 261ec96c1a83fbec423e6dbbfe403c4db53a2962
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77143095"
---
# <a name="context_unblock_unbalanced-class"></a>context_unblock_unbalanced-Klasse

Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn Aufrufe der `Block`-Methode und der `Unblock`-Methode eines `Context`-Objekts nicht ordnungsgemäß zugeordnet werden.

## <a name="syntax"></a>Syntax

```cpp
class context_unblock_unbalanced : public std::exception;
```

## <a name="members"></a>Members

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[context_unblock_unbalanced](#ctor)|Ist überladen. Erstellt ein `context_unblock_unbalanced`-Objekt.|

## <a name="remarks"></a>Bemerkungen

Aufrufe der Methoden `Block` und `Unblock` eines `Context` Objekts müssen immer ordnungsgemäß gekoppelt werden. Der Concurrency Runtime ermöglicht die Ausführung der Vorgänge in einer der beiden Reihenfolge. So kann z. b. ein Aufrufen von `Block` von einem `Unblock`aufgerufen werden oder umgekehrt. Diese Ausnahme wird ausgelöst, wenn beispielsweise zwei Aufrufe der `Unblock`-Methode in einer Zeile für ein `Context` Objekt erfolgen, das nicht blockiert war.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`exception`

`context_unblock_unbalanced`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** ConcRT. h

**Namespace:** Parallelität

## <a name="ctor"></a>context_unblock_unbalanced

Erstellt ein `context_unblock_unbalanced`-Objekt.

```cpp
explicit _CRTIMP context_unblock_unbalanced(_In_z_ const char* _Message) throw();

context_unblock_unbalanced() throw();
```

### <a name="parameters"></a>Parameter

*_Message*<br/>
Eine beschreibende Fehlermeldung.

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace](concurrency-namespace.md)
