---
title: message_not_found-Klasse
ms.date: 11/04/2016
f1_keywords:
- message_not_found
- CONCRT/concurrency::message_not_found
- CONCRT/concurrency::message_not_found::message_not_found
helpviewer_keywords:
- message_not_found class
ms.assetid: a96b9995-5ad7-4600-83c8-c15e329ff10e
ms.openlocfilehash: da0a44b90346959756c1ef7c685bef234fe6e46a
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57296682"
---
# <a name="messagenotfound-class"></a>message_not_found-Klasse

Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn ein Meldungsblock keine angeforderte Meldung finden kann.

## <a name="syntax"></a>Syntax

```
class message_not_found : public std::exception;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[message_not_found](#ctor)|Überladen. Erstellt ein `message_not_found`-Objekt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`exception`

`message_not_found`

## <a name="requirements"></a>Anforderungen

**Header:** concrt.h

**Namespace:** Parallelität

##  <a name="ctor"></a> message_not_found

Erstellt ein `message_not_found`-Objekt.

```
explicit _CRTIMP message_not_found(_In_z_ const char* _Message) throw();

message_not_found() throw();
```

### <a name="parameters"></a>Parameter

*_Message*<br/>
Eine beschreibende Fehlermeldung.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[Asynchrone Nachrichtenblöcke](../../../parallel/concrt/asynchronous-message-blocks.md)
