---
title: invalid_link_target-Klasse
ms.date: 11/04/2016
f1_keywords:
- invalid_link_target
- CONCRT/concurrency::invalid_link_target
- CONCRT/concurrency::invalid_link_target::invalid_link_target
helpviewer_keywords:
- invalid_link_target class
ms.assetid: 33b64885-34d8-4d4e-a893-02e9f19c958e
ms.openlocfilehash: bd3d82c06c174c69c60dec33592110f4de72ac99
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77141048"
---
# <a name="invalid_link_target-class"></a>invalid_link_target-Klasse

Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn die `link_target`-Methode eines Meldungsblocks aufgerufen wird und der Meldungsblock keine Verknüpfung mit dem Ziel erstellen kann. Dies kann das Ergebnis vom Überschreiten der Anzahl zulässiger Links für den Meldungsblock sein oder das Ergebnis von Versuchen, ein bestimmtes Ziel zweimal mit der gleichen Quelle zu verknüpfen.

## <a name="syntax"></a>Syntax

```cpp
class invalid_link_target : public std::exception;
```

## <a name="members"></a>Members

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[invalid_link_target](#ctor)|Ist überladen. Erstellt ein `invalid_link_target`-Objekt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`exception`

`invalid_link_target`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** ConcRT. h

**Namespace:** Parallelität

## <a name="ctor"></a>invalid_link_target

Erstellt ein `invalid_link_target`-Objekt.

```cpp
explicit _CRTIMP invalid_link_target(_In_z_ const char* _Message) throw();

invalid_link_target() throw();
```

### <a name="parameters"></a>Parameter

*_Message*<br/>
Eine beschreibende Fehlermeldung.

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[Asynchrone Nachrichtenblöcke](../../../parallel/concrt/asynchronous-message-blocks.md)
