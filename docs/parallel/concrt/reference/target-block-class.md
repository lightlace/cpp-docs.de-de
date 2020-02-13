---
title: target_block-Klasse
ms.date: 11/04/2016
f1_keywords:
- target_block
- AGENTS/concurrency::target_block
- AGENTS/concurrency::target_block::target_block
- AGENTS/concurrency::target_block::propagate
- AGENTS/concurrency::target_block::send
- AGENTS/concurrency::target_block::async_send
- AGENTS/concurrency::target_block::decline_incoming_messages
- AGENTS/concurrency::target_block::enable_batched_processing
- AGENTS/concurrency::target_block::initialize_target
- AGENTS/concurrency::target_block::link_source
- AGENTS/concurrency::target_block::process_input_messages
- AGENTS/concurrency::target_block::process_message
- AGENTS/concurrency::target_block::propagate_message
- AGENTS/concurrency::target_block::register_filter
- AGENTS/concurrency::target_block::remove_sources
- AGENTS/concurrency::target_block::send_message
- AGENTS/concurrency::target_block::sync_send
- AGENTS/concurrency::target_block::unlink_source
- AGENTS/concurrency::target_block::unlink_sources
- AGENTS/concurrency::target_block::wait_for_async_sends
helpviewer_keywords:
- target_block class
ms.assetid: 3ce181b4-b94a-4894-bf7b-64fc09821f9f
ms.openlocfilehash: 4009133161133a99aeb0ee040f0c82fdbabecaa0
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142645"
---
# <a name="target_block-class"></a>target_block-Klasse

Die `target_block`-Klasse ist eine abstrakte Basisklasse, mit der grundlegende Linkmanagementfunktionalität und Fehlerüberprüfung für Nur-Ziel-Blöcke bereitgestellt werden.

## <a name="syntax"></a>Syntax

```cpp
template<class _SourceLinkRegistry, class _MessageProcessorType = ordered_message_processor<typename _SourceLinkRegistry::type::source_type>>
class target_block : public ITarget<typename _SourceLinkRegistry::type::source_type>;
```

### <a name="parameters"></a>Parameter

*_SourceLinkRegistry*<br/>
Die Link Registrierung, die zum Speichern der Quell Verknüpfungen verwendet werden soll.

*_MessageProcessorType*<br/>
Der Prozessortyp für die Nachrichtenverarbeitung.

## <a name="members"></a>Members

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|BESCHREIBUNG|
|----------|-----------------|
|`source_iterator`|Der Typ des Iterators für die `source_link_manager` für dieses `target_block`-Objekt.|

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[target_block](#ctor)|Erstellt ein `target_block`-Objekt.|
|[~ target_block-Dekonstruktor](#dtor)|Zerstört das `target_block`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|BESCHREIBUNG|
|----------|-----------------|
|[Pixeln](#propagate)|Übergibt eine Nachricht asynchron aus einem Quell Block an diesen Zielblock.|
|[Senden](#send)|Übergibt eine Nachricht synchron von einem Quell Block an diesen Zielblock.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|BESCHREIBUNG|
|----------|-----------------|
|[async_send](#async_send)|Sendet asynchron eine Nachricht zur Verarbeitung.|
|[decline_incoming_messages](#decline_incoming_messages)|Gibt dem-Block an, dass neue Nachrichten abgelehnt werden sollen.|
|[enable_batched_processing](#enable_batched_processing)|Aktiviert die Batch Verarbeitung für diesen Block.|
|[initialize_target](#initialize_target)|Initialisiert das Basisobjekt. Insbesondere muss das `message_processor` Objekt initialisiert werden.|
|[link_source](#link_source)|Verknüpft einen angegebenen Quell Block mit diesem `target_block`-Objekt.|
|[process_input_messages](#process_input_messages)|Verarbeitet Nachrichten, die als Eingaben empfangen werden.|
|[process_message](#process_message)|Verarbeitet beim Überschreiben in einer abgeleiteten Klasse eine Nachricht, die von diesem `target_block` Objekt akzeptiert wurde.|
|[propagate_message](#propagate_message)|Wenn diese Methode in einer abgeleiteten Klasse überschrieben wird, übergibt sie asynchron eine Nachricht von einem `ISource`-Block an dieses `target_block`-Objekt. Sie wird durch die `propagate`-Methode aufgerufen, wenn Sie von einem Quell Block aufgerufen wird.|
|[register_filter](#register_filter)|Registriert eine Filtermethode, die für jede empfangene Nachricht aufgerufen wird.|
|[remove_sources](#remove_sources)|Entbindet alle Quellen nach dem warten auf den Abschluss ausstehender asynchroner Sende Vorgänge.|
|[send_message](#send_message)|Wenn diese Methode in einer abgeleiteten Klasse überschrieben wird, übergibt sie synchron eine Meldung von einem `ISource`-Block an dieses `target_block`-Objekt. Sie wird durch die `send`-Methode aufgerufen, wenn Sie von einem Quell Block aufgerufen wird.|
|[sync_send](#sync_send)|Senden Sie eine Nachricht synchron zur Verarbeitung.|
|[unlink_source](#unlink_source)|Entfernt die Verknüpfung eines angegebenen Quell Blocks mit diesem `target_block`-Objekt.|
|[unlink_sources](#unlink_sources)|Hebt die Verknüpfung aller Quell Blöcke von diesem `target_block` Objekt auf. (Überschreibt [ITarget:: unlink_sources](itarget-class.md#unlink_sources).)|
|[wait_for_async_sends](#wait_for_async_sends)|Wartet, bis alle asynchronen Propagierungen vollständig sind.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[ITarget](itarget-class.md)

`target_block`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** agents.h

**Namespace:** Parallelität

## <a name="async_send"></a>async_send

Sendet asynchron eine Nachricht zur Verarbeitung.

```cpp
void async_send(_Inout_opt_ message<_Source_type>* _PMessage);
```

### <a name="parameters"></a>Parameter

*_PMessage*<br/>
Ein Zeiger auf die gesendete Nachricht.

## <a name="decline_incoming_messages"></a>decline_incoming_messages

Gibt dem-Block an, dass neue Nachrichten abgelehnt werden sollen.

```cpp
void decline_incoming_messages();
```

### <a name="remarks"></a>Bemerkungen

Diese Methode wird vom debugtor aufgerufen, um sicherzustellen, dass neue Nachrichten abgelehnt werden, während eine Zerstörung ausgeführt wird.

## <a name="enable_batched_processing"></a>enable_batched_processing

Aktiviert die Batch Verarbeitung für diesen Block.

```cpp
void enable_batched_processing();
```

## <a name="initialize_target"></a>initialize_target

Initialisiert das Basisobjekt. Insbesondere muss das `message_processor` Objekt initialisiert werden.

```cpp
void initialize_target(
    _Inout_opt_ Scheduler* _PScheduler = NULL,
    _Inout_opt_ ScheduleGroup* _PScheduleGroup = NULL);
```

### <a name="parameters"></a>Parameter

*_PScheduler*<br/>
Der Planer, der zum Planen von Aufgaben verwendet werden soll.

*_PScheduleGroup*<br/>
Die Zeit Plan Gruppe, die zum Planen von Aufgaben verwendet werden soll.

## <a name="link_source"></a>link_source

Verknüpft einen angegebenen Quell Block mit diesem `target_block`-Objekt.

```cpp
virtual void link_source(_Inout_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>Parameter

*_PSource*<br/>
Ein Zeiger auf den `ISource` Block, der verknüpft werden soll.

### <a name="remarks"></a>Bemerkungen

Diese Funktion sollte nicht direkt für ein `target_block` Objekt aufgerufen werden. Blöcke sollten mithilfe der `link_target`-Methode für `ISource` Blöcke verbunden werden, die die `link_source`-Methode für das entsprechende Ziel aufrufen.

## <a name="process_input_messages"></a>process_input_messages

Verarbeitet Nachrichten, die als Eingaben empfangen werden.

```cpp
virtual void process_input_messages(_Inout_ message<_Source_type>* _PMessage);
```

### <a name="parameters"></a>Parameter

*_PMessage*<br/>
Ein Zeiger auf die Meldung, die verarbeitet werden soll.

## <a name="process_message"></a>process_message

Verarbeitet beim Überschreiben in einer abgeleiteten Klasse eine Nachricht, die von diesem `target_block` Objekt akzeptiert wurde.

```cpp
virtual void process_message(message<_Source_type> *);
```

## <a name="propagate"></a>Pixeln

Übergibt eine Nachricht asynchron aus einem Quell Block an diesen Zielblock.

```cpp
virtual message_status propagate(
    _Inout_opt_ message<_Source_type>* _PMessage,
    _Inout_opt_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>Parameter

*_PMessage*<br/>
Ein Zeiger auf das `message`-Objekt.

*_PSource*<br/>
Ein Zeiger auf den Quell Block, der die Nachricht anbietet.

### <a name="return-value"></a>Rückgabewert

Eine [Message_status](concurrency-namespace-enums.md) , die angibt, wie sich das Ziel für die Nachricht entschieden hat.

### <a name="remarks"></a>Bemerkungen

Die-Methode löst eine [Invalid_argument](../../../standard-library/invalid-argument-class.md) Ausnahme aus, wenn der `_PMessage`-oder `_PSource`-Parameter `NULL`ist.

## <a name="propagate_message"></a>propagate_message

Wenn diese Methode in einer abgeleiteten Klasse überschrieben wird, übergibt sie asynchron eine Nachricht von einem `ISource`-Block an dieses `target_block`-Objekt. Sie wird durch die `propagate`-Methode aufgerufen, wenn Sie von einem Quell Block aufgerufen wird.

```cpp
virtual message_status propagate_message(
    _Inout_ message<_Source_type>* _PMessage,
    _Inout_ ISource<_Source_type>* _PSource) = 0;
```

### <a name="parameters"></a>Parameter

*_PMessage*<br/>
Ein Zeiger auf das `message`-Objekt.

*_PSource*<br/>
Ein Zeiger auf den Quell Block, der die Nachricht anbietet.

### <a name="return-value"></a>Rückgabewert

Eine [Message_status](concurrency-namespace-enums.md) , die angibt, wie sich das Ziel für die Nachricht entschieden hat.

## <a name="register_filter"></a>register_filter

Registriert eine Filtermethode, die für jede empfangene Nachricht aufgerufen wird.

```cpp
void register_filter(filter_method const& _Filter);
```

### <a name="parameters"></a>Parameter

*_Filter*<br/>
Die Filtermethode.

## <a name="remove_sources"></a>remove_sources

Entbindet alle Quellen nach dem warten auf den Abschluss ausstehender asynchroner Sende Vorgänge.

```cpp
void remove_sources();
```

### <a name="remarks"></a>Bemerkungen

Alle Ziel Blöcke sollten diese Routine aufrufen, um die Quellen in Ihrem debugtor zu entfernen.

## <a name="send"></a>Senden

Übergibt eine Nachricht synchron von einem Quell Block an diesen Zielblock.

```cpp
virtual message_status send(
    _Inout_ message<_Source_type>* _PMessage,
    _Inout_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>Parameter

*_PMessage*<br/>
Ein Zeiger auf das `message`-Objekt.

*_PSource*<br/>
Ein Zeiger auf den Quell Block, der die Nachricht anbietet.

### <a name="return-value"></a>Rückgabewert

Eine [Message_status](concurrency-namespace-enums.md) , die angibt, wie sich das Ziel für die Nachricht entschieden hat.

### <a name="remarks"></a>Bemerkungen

Die-Methode löst eine [Invalid_argument](../../../standard-library/invalid-argument-class.md) Ausnahme aus, wenn der `_PMessage`-oder `_PSource`-Parameter `NULL`ist.

Die Verwendung der `send` Methode außerhalb der Nachrichten Initiierung und die Weitergabe von Nachrichten innerhalb eines Netzwerks ist gefährlich und kann zu einem Deadlock führen.

Wenn `send` zurückgibt, wurde die Nachricht entweder bereits akzeptiert und in den Zielblock übertragen, oder Sie wurde vom Ziel abgelehnt.

## <a name="send_message"></a>send_message

Wenn diese Methode in einer abgeleiteten Klasse überschrieben wird, übergibt sie synchron eine Meldung von einem `ISource`-Block an dieses `target_block`-Objekt. Sie wird durch die `send`-Methode aufgerufen, wenn Sie von einem Quell Block aufgerufen wird.

```cpp
virtual message_status send_message(
    _Inout_ message<_Source_type> *,
    _Inout_ ISource<_Source_type> *);
```

### <a name="return-value"></a>Rückgabewert

Eine [Message_status](concurrency-namespace-enums.md) , die angibt, wie sich das Ziel für die Nachricht entschieden hat.

### <a name="remarks"></a>Bemerkungen

Standardmäßig gibt dieser Block `declined` zurück, es sei denn, er wird von einer abgeleiteten Klasse überschrieben.

## <a name="sync_send"></a>sync_send

Senden Sie eine Nachricht synchron zur Verarbeitung.

```cpp
void sync_send(_Inout_opt_ message<_Source_type>* _PMessage);
```

### <a name="parameters"></a>Parameter

*_PMessage*<br/>
Ein Zeiger auf die gesendete Nachricht.

## <a name="ctor"></a>target_block

Erstellt ein `target_block`-Objekt.

```cpp
target_block();
```

## <a name="dtor"></a>~ target_block

Zerstört das `target_block`-Objekt.

```cpp
virtual ~target_block();
```

## <a name="unlink_source"></a>unlink_source

Entfernt die Verknüpfung eines angegebenen Quell Blocks mit diesem `target_block`-Objekt.

```cpp
virtual void unlink_source(_Inout_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>Parameter

*_PSource*<br/>
Ein Zeiger auf den `ISource` Block, für den die Verknüpfung aufgehoben werden soll.

## <a name="unlink_sources"></a>unlink_sources

Hebt die Verknüpfung aller Quell Blöcke von diesem `target_block` Objekt auf.

```cpp
virtual void unlink_sources();
```

## <a name="wait_for_async_sends"></a>wait_for_async_sends

Wartet, bis alle asynchronen Propagierungen vollständig sind.

```cpp
void wait_for_async_sends();
```

### <a name="remarks"></a>Bemerkungen

Diese Methode wird von Message Block-Debuggern verwendet, um sicherzustellen, dass alle asynchronen Vorgänge Zeit bis zum Ende haben, bevor der-Block zerstört wird.

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[ITarget-Klasse](itarget-class.md)
