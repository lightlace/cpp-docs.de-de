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
ms.openlocfilehash: 88944b2d935eebd0e031be1431c2a0f4efa3d760
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77139466"
---
# <a name="message_processor-class"></a>message_processor-Klasse

Die `message_processor`-Klasse ist die abstrakte Basisklasse für die Verarbeitung von `message`-Objekten. Für die Reihenfolge der Meldungen besteht keine Garantie.

## <a name="syntax"></a>Syntax

```cpp
template<class T>
class message_processor;
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der Datentyp der Nutzlast in Nachrichten, die von diesem `message_processor` Objekt verarbeitet werden.

## <a name="members"></a>Members

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|BESCHREIBUNG|
|----------|-----------------|
|`type`|Ein Typalias für `T`.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|BESCHREIBUNG|
|----------|-----------------|
|[async_send](#async_send)|Fügt beim Überschreiben in einer abgeleiteten Klasse Nachrichten asynchron in den-Block ein.|
|[sync_send](#sync_send)|Fügt beim Überschreiben in einer abgeleiteten Klasse Nachrichten synchron in den-Block ein.|
|[Warte](#wait)|Wartet beim Überschreiben in einer abgeleiteten Klasse darauf, dass alle asynchronen Vorgänge vollständig ausgeführt werden.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|BESCHREIBUNG|
|----------|-----------------|
|[process_incoming_message](#process_incoming_message)|Führt beim Überschreiben in einer abgeleiteten Klasse die vorwärts Verarbeitung von Nachrichten in den-Block aus. Wird jedes Mal aufgerufen, wenn eine neue Nachricht hinzugefügt wird und die Warteschlange als leer festgestellt wird.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`message_processor`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** agents.h

**Namespace:** Parallelität

## <a name="async_send"></a>async_send

Fügt beim Überschreiben in einer abgeleiteten Klasse Nachrichten asynchron in den-Block ein.

```cpp
virtual void async_send(_Inout_opt_ message<T>* _Msg) = 0;
```

### <a name="parameters"></a>Parameter

*_Msg*<br/>
Ein `message`-Objekt, das asynchron gesendet werden soll.

### <a name="remarks"></a>Bemerkungen

Prozessor Implementierungen sollten diese Methode überschreiben.

## <a name="process_incoming_message"></a>process_incoming_message

Führt beim Überschreiben in einer abgeleiteten Klasse die vorwärts Verarbeitung von Nachrichten in den-Block aus. Wird jedes Mal aufgerufen, wenn eine neue Nachricht hinzugefügt wird und die Warteschlange als leer festgestellt wird.

```cpp
virtual void process_incoming_message() = 0;
```

### <a name="remarks"></a>Bemerkungen

Nachrichtenblock Implementierungen sollten diese Methode überschreiben.

## <a name="sync_send"></a>sync_send

Fügt beim Überschreiben in einer abgeleiteten Klasse Nachrichten synchron in den-Block ein.

```cpp
virtual void sync_send(_Inout_opt_ message<T>* _Msg) = 0;
```

### <a name="parameters"></a>Parameter

*_Msg*<br/>
Ein `message`-Objekt, das synchron gesendet werden soll.

### <a name="remarks"></a>Bemerkungen

Prozessor Implementierungen sollten diese Methode überschreiben.

## <a name="wait"></a>Warte

Wartet beim Überschreiben in einer abgeleiteten Klasse darauf, dass alle asynchronen Vorgänge vollständig ausgeführt werden.

```cpp
virtual void wait() = 0;
```

### <a name="remarks"></a>Bemerkungen

Prozessor Implementierungen sollten diese Methode überschreiben.

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[ordered_message_processor-Klasse](ordered-message-processor-class.md)
