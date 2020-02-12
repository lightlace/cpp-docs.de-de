---
title: propagator_block-Klasse
ms.date: 11/04/2016
f1_keywords:
- propagator_block
- AGENTS/concurrency::propagator_block
- AGENTS/concurrency::propagator_block::propagator_block
- AGENTS/concurrency::propagator_block::propagate
- AGENTS/concurrency::propagator_block::send
- AGENTS/concurrency::propagator_block::decline_incoming_messages
- AGENTS/concurrency::propagator_block::initialize_source_and_target
- AGENTS/concurrency::propagator_block::link_source
- AGENTS/concurrency::propagator_block::process_input_messages
- AGENTS/concurrency::propagator_block::propagate_message
- AGENTS/concurrency::propagator_block::register_filter
- AGENTS/concurrency::propagator_block::remove_network_links
- AGENTS/concurrency::propagator_block::send_message
- AGENTS/concurrency::propagator_block::unlink_source
- AGENTS/concurrency::propagator_block::unlink_sources
helpviewer_keywords:
- propagator_block class
ms.assetid: 86aa75fd-eda5-42aa-aadf-25c0c1c9742d
ms.openlocfilehash: 340af181669cbbf4c5ba910aa3ee862bd40ba27f
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77138743"
---
# <a name="propagator_block-class"></a>propagator_block-Klasse

Die `propagator_block`-Klasse ist eine abstrakte Basisklasse für Meldungsblöcke, die sowohl Quelle als auch Ziel sind. Kombiniert die Funktion der `source_block`-Klasse mit der Funktion der `target_block`-Klasse.

## <a name="syntax"></a>Syntax

```cpp
template<class _TargetLinkRegistry, class _SourceLinkRegistry, class _MessageProcessorType = ordered_message_processor<typename _TargetLinkRegistry::type::type>>
class propagator_block : public source_block<_TargetLinkRegistry,
    _MessageProcessorType>,
public ITarget<typename _SourceLinkRegistry::type::source_type>;
```

### <a name="parameters"></a>Parameter

*_TargetLinkRegistry*<br/>
Die Link Registrierung, die zum Speichern der Ziellinks verwendet werden soll.

*_SourceLinkRegistry*<br/>
Die Link Registrierung, die zum Speichern der Quell Verknüpfungen verwendet werden soll.

*_MessageProcessorType*<br/>
Der Prozessortyp für die Nachrichtenverarbeitung.

## <a name="members"></a>Members

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|BESCHREIBUNG|
|----------|-----------------|
|`source_iterator`|Der Typ des Iterators für die `source_link_manager` für diese `propagator_block`.|

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[propagator_block](#ctor)|Erstellt ein `propagator_block`-Objekt.|
|[~ propagator_block-Dekonstruktor](#dtor)|Zerstört ein `propagator_block` -Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|BESCHREIBUNG|
|----------|-----------------|
|[Pixeln](#propagate)|Übergibt eine Nachricht asynchron aus einem Quell Block an diesen Zielblock.|
|[Senden](#send)|Initiiert eine Meldung zu diesem Block synchron. Wird von einem `ISource`-Block aufgerufen. Wenn diese Funktion abgeschlossen ist, wurde die Nachricht bereits in den-Block weitergegeben.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|BESCHREIBUNG|
|----------|-----------------|
|[decline_incoming_messages](#decline_incoming_messages)|Gibt dem-Block an, dass neue Nachrichten abgelehnt werden sollen.|
|[initialize_source_and_target](#initialize_source_and_target)|Initialisiert das Basisobjekt. Insbesondere muss das `message_processor` Objekt initialisiert werden.|
|[link_source](#link_source)|Verknüpft einen angegebenen Quell Block mit diesem `propagator_block`-Objekt.|
|[process_input_messages](#process_input_messages)|Verarbeiten von Eingabe Nachrichten. Dies ist nur für propagatorblöcke nützlich, die von source_block (außer Kraft setzungen [source_block::p rocess_input_messages](source-block-class.md#process_input_messages)abgeleitet werden.)|
|[propagate_message](#propagate_message)|Wenn diese Methode in einer abgeleiteten Klasse überschrieben wird, übergibt sie asynchron eine Nachricht von einem `ISource`-Block an dieses `propagator_block`-Objekt. Sie wird durch die `propagate`-Methode aufgerufen, wenn Sie von einem Quell Block aufgerufen wird.|
|[register_filter](#register_filter)|Registriert eine Filtermethode, die für jede empfangene Nachricht aufgerufen wird.|
|[remove_network_links](#remove_network_links)|Entfernt alle Quell-und Zielnetzwerk Verknüpfungen aus diesem `propagator_block` Objekt.|
|[send_message](#send_message)|Wenn diese Methode in einer abgeleiteten Klasse überschrieben wird, übergibt sie synchron eine Meldung von einem `ISource`-Block an dieses `propagator_block`-Objekt. Sie wird durch die `send`-Methode aufgerufen, wenn Sie von einem Quell Block aufgerufen wird.|
|[unlink_source](#unlink_source)|Entfernt die Verknüpfung eines angegebenen Quell Blocks mit diesem `propagator_block`-Objekt.|
|[unlink_sources](#unlink_sources)|Hebt die Verknüpfung aller Quell Blöcke von diesem `propagator_block` Objekt auf. (Überschreibt [ITarget:: unlink_sources](itarget-class.md#unlink_sources).)|

## <a name="remarks"></a>Bemerkungen

Um die mehrfache Vererbung zu vermeiden, erbt die `propagator_block` Klasse von der `source_block` Klasse und `ITarget` abstrakten Klasse. Die meisten Funktionen in der `target_block`-Klasse werden hier repliziert.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[ISource](isource-class.md)

[ITarget](itarget-class.md)

[source_block](source-block-class.md)

`propagator_block`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** agents.h

**Namespace:** Parallelität

## <a name="decline_incoming_messages"></a>decline_incoming_messages

Gibt dem-Block an, dass neue Nachrichten abgelehnt werden sollen.

```cpp
void decline_incoming_messages();
```

### <a name="remarks"></a>Bemerkungen

Diese Methode wird vom debugtor aufgerufen, um sicherzustellen, dass neue Nachrichten abgelehnt werden, während eine Zerstörung ausgeführt wird.

## <a name="initialize_source_and_target"></a>initialize_source_and_target

Initialisiert das Basisobjekt. Insbesondere muss das `message_processor` Objekt initialisiert werden.

```cpp
void initialize_source_and_target(
    _Inout_opt_ Scheduler* _PScheduler = NULL,
    _Inout_opt_ ScheduleGroup* _PScheduleGroup = NULL);
```

### <a name="parameters"></a>Parameter

*_PScheduler*<br/>
Der Planer, der zum Planen von Aufgaben verwendet werden soll.

*_PScheduleGroup*<br/>
Die Zeit Plan Gruppe, die zum Planen von Aufgaben verwendet werden soll.

## <a name="link_source"></a>link_source

Verknüpft einen angegebenen Quell Block mit diesem `propagator_block`-Objekt.

```cpp
virtual void link_source(_Inout_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>Parameter

*_PSource*<br/>
Ein Zeiger auf den `ISource` Block, der verknüpft werden soll.

## <a name="process_input_messages"></a>process_input_messages

Verarbeiten von Eingabe Nachrichten. Dies ist nur für propagatorblöcke nützlich, die von abgeleitet werden source_block

```cpp
virtual void process_input_messages(_Inout_ message<_Target_type>* _PMessage);
```

### <a name="parameters"></a>Parameter

*_PMessage*<br/>
Ein Zeiger auf die Meldung, die verarbeitet werden soll.

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

Die `propagate`-Methode wird von einem verknüpften Quell Block für einen Zielblock aufgerufen. Er fügt eine asynchrone Aufgabe zum Verarbeiten der Nachricht in die Warteschlange ein, wenn Sie nicht bereits in die Warteschlange eingereiht oder ausgeführt wird.

Die-Methode löst eine [Invalid_argument](../../../standard-library/invalid-argument-class.md) Ausnahme aus, wenn der `_PMessage`-oder `_PSource`-Parameter `NULL`ist.

## <a name="propagate_message"></a>propagate_message

Wenn diese Methode in einer abgeleiteten Klasse überschrieben wird, übergibt sie asynchron eine Nachricht von einem `ISource`-Block an dieses `propagator_block`-Objekt. Sie wird durch die `propagate`-Methode aufgerufen, wenn Sie von einem Quell Block aufgerufen wird.

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

## <a name="ctor"></a>propagator_block

Erstellt ein `propagator_block`-Objekt.

```cpp
propagator_block();
```

## <a name="dtor"></a>~ propagator_block

Zerstört ein `propagator_block` -Objekt.

```cpp
virtual ~propagator_block();
```

## <a name="register_filter"></a>register_filter

Registriert eine Filtermethode, die für jede empfangene Nachricht aufgerufen wird.

```cpp
void register_filter(filter_method const& _Filter);
```

### <a name="parameters"></a>Parameter

*_Filter*<br/>
Die Filtermethode.

## <a name="remove_network_links"></a>remove_network_links

Entfernt alle Quell-und Zielnetzwerk Verknüpfungen aus diesem `propagator_block` Objekt.

```cpp
void remove_network_links();
```

## <a name="send"></a>Senden

Initiiert eine Meldung zu diesem Block synchron. Wird von einem `ISource`-Block aufgerufen. Wenn diese Funktion abgeschlossen ist, wurde die Nachricht bereits in den-Block weitergegeben.

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

Diese Methode löst eine [Invalid_argument](../../../standard-library/invalid-argument-class.md) Ausnahme aus, wenn der `_PMessage`-oder `_PSource`-Parameter `NULL`ist.

## <a name="send_message"></a>send_message

Wenn diese Methode in einer abgeleiteten Klasse überschrieben wird, übergibt sie synchron eine Meldung von einem `ISource`-Block an dieses `propagator_block`-Objekt. Sie wird durch die `send`-Methode aufgerufen, wenn Sie von einem Quell Block aufgerufen wird.

```cpp
virtual message_status send_message(
    _Inout_ message<_Source_type> *,
    _Inout_ ISource<_Source_type> *);
```

### <a name="return-value"></a>Rückgabewert

Eine [Message_status](concurrency-namespace-enums.md) , die angibt, wie sich das Ziel für die Nachricht entschieden hat.

### <a name="remarks"></a>Bemerkungen

Standardmäßig gibt dieser Block `declined` zurück, es sei denn, er wird von einer abgeleiteten Klasse überschrieben.

## <a name="unlink_source"></a>unlink_source

Entfernt die Verknüpfung eines angegebenen Quell Blocks mit diesem `propagator_block`-Objekt.

```cpp
virtual void unlink_source(_Inout_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>Parameter

*_PSource*<br/>
Ein Zeiger auf den `ISource` Block, für den die Verknüpfung aufgehoben werden soll.

## <a name="unlink_sources"></a>unlink_sources

Hebt die Verknüpfung aller Quell Blöcke von diesem `propagator_block` Objekt auf.

```cpp
virtual void unlink_sources();
```

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[source_block-Klasse](source-block-class.md)<br/>
[ITarget-Klasse](itarget-class.md)
