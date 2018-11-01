---
title: message_processor-Klasse
ms.date: 11/04/2016
f1_keywords:
- message_processor
- AGENTS/concurrency::message_processor
- AGENTS/concurrency::message_processor::async_send
- AGENTS/concurrency::message_processor::sync_send
- AGENTS/concurrency::message_processor::wait
- AGENTS/concurrency::message_processor::process_incoming_message
helpviewer_keywords:
- message_processor class
ms.assetid: 23afb052-daa7-44ed-bf24-d2513db748da
ms.openlocfilehash: d6e45613e0b412b6b94dba3c4a435115e32c7d6a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50438219"
---
# <a name="messageprocessor-class"></a>message_processor-Klasse

Die `message_processor`-Klasse ist die abstrakte Basisklasse für die Verarbeitung von `message`-Objekten. Für die Reihenfolge der Meldungen besteht keine Garantie.

## <a name="syntax"></a>Syntax

```
template<class T>
class message_processor;
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Der Datentyp der Nutzlast innerhalb der Nachrichten von diesem verarbeitet `message_processor` Objekt.

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|Beschreibung|
|----------|-----------------|
|`type`|Ein Typalias für `T`.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[async_send](#async_send)|Ruft beim Überschreiben in einer abgeleiteten Klasse platziert Nachrichten asynchron in den Block.|
|[sync_send](#sync_send)|Ruft beim Überschreiben in einer abgeleiteten Klasse platziert Nachrichten synchron in den Block.|
|[wait](#wait)|Ruft beim Überschreiben in einer abgeleiteten Klasse wartet, bis alle asynchronen Vorgänge abgeschlossen.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[process_incoming_message](#process_incoming_message)|Führt beim Überschreiben in einer abgeleiteten Klasse die forward-Verarbeitung von Nachrichten in den Block aus. Wird einmal aufgerufen, jedes Mal, wenn eine neue Nachricht hinzugefügt wird, und befindet sich die Warteschlange leer sein.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`message_processor`

## <a name="requirements"></a>Anforderungen

**Header:** agents.h

**Namespace:** Parallelität

##  <a name="async_send"></a> async_send

Ruft beim Überschreiben in einer abgeleiteten Klasse platziert Nachrichten asynchron in den Block.

```
virtual void async_send(_Inout_opt_ message<T>* _Msg) = 0;
```

### <a name="parameters"></a>Parameter

*_Msg*<br/>
Ein `message` Objekt asynchron gesendet werden.

### <a name="remarks"></a>Hinweise

Implementierungen von ereignissprozessoren sollten diese Methode überschreiben.

##  <a name="process_incoming_message"></a> process_incoming_message

Führt beim Überschreiben in einer abgeleiteten Klasse die forward-Verarbeitung von Nachrichten in den Block aus. Wird einmal aufgerufen, jedes Mal, wenn eine neue Nachricht hinzugefügt wird, und befindet sich die Warteschlange leer sein.

```
virtual void process_incoming_message() = 0;
```

### <a name="remarks"></a>Hinweise

Message-Block-Implementierungen sollten diese Methode überschreiben.

##  <a name="sync_send"></a> sync_send

Ruft beim Überschreiben in einer abgeleiteten Klasse platziert Nachrichten synchron in den Block.

```
virtual void sync_send(_Inout_opt_ message<T>* _Msg) = 0;
```

### <a name="parameters"></a>Parameter

*_Msg*<br/>
Ein `message` Objekt, das synchron gesendet.

### <a name="remarks"></a>Hinweise

Implementierungen von ereignissprozessoren sollten diese Methode überschreiben.

##  <a name="wait"></a> Warte

Ruft beim Überschreiben in einer abgeleiteten Klasse wartet, bis alle asynchronen Vorgänge abgeschlossen.

```
virtual void wait() = 0;
```

### <a name="remarks"></a>Hinweise

Implementierungen von ereignissprozessoren sollten diese Methode überschreiben.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[ordered_message_processor-Klasse](ordered-message-processor-class.md)
