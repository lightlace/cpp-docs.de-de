---
title: Propagator_block-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- propagator_block class
ms.assetid: 86aa75fd-eda5-42aa-aadf-25c0c1c9742d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 94fd117f43dac30aef33bef9e085f5f2fcd9d2f2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46376530"
---
# <a name="propagatorblock-class"></a>propagator_block-Klasse

Die `propagator_block`-Klasse ist eine abstrakte Basisklasse für Meldungsblöcke, die sowohl Quelle als auch Ziel sind. Kombiniert die Funktion der `source_block`-Klasse mit der Funktion der `target_block`-Klasse.

## <a name="syntax"></a>Syntax

```
template<class _TargetLinkRegistry, class _SourceLinkRegistry, class _MessageProcessorType = ordered_message_processor<typename _TargetLinkRegistry::type::type>>
class propagator_block : public source_block<_TargetLinkRegistry,
    _MessageProcessorType>,
public ITarget<typename _SourceLinkRegistry::type::source_type>;
```

#### <a name="parameters"></a>Parameter

*_TargetLinkRegistry*<br/>
Der Link-Registrierung für die mit die Ziellinks verwendet werden soll.

*_SourceLinkRegistry*<br/>
Die Registrierung der Link zur Aufnahme der quellverknüpfungen verwendet werden.

*_MessageProcessorType*<br/>
Der Prozessortyp für die Nachrichtenverarbeitung.

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|Beschreibung|
|----------|-----------------|
|`source_iterator`|Der Typ des Iterators für die `source_link_manager` für diesen `propagator_block`.|

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[propagator_block](#ctor)|Erstellt ein `propagator_block`-Objekt.|
|[~ Propagator_block-Destruktor](#dtor)|Zerstört ein `propagator_block`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[propagate](#propagate)|Übergibt eine Nachricht asynchron von einem Quellblock mit diesem Zielblock.|
|[Senden](#send)|Synchron initiiert eine Nachricht an diesen Block aus. Wird aufgerufen, indem ein `ISource` Block. Wenn diese Funktion abgeschlossen ist, wird die Nachricht bereits in den Block weitergegeben wurden.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[decline_incoming_messages](#decline_incoming_messages)|Zeigt den Block an, dass neue Nachrichten abgelehnt werden sollte.|
|[initialize_source_and_target](#initialize_source_and_target)|Initialisiert das Basisobjekt. Insbesondere die `message_processor` -Objekt muss initialisiert werden.|
|[link_source](#link_source)|Verknüpft einen angegebenen Quellblock mit diesem `propagator_block` Objekt.|
|[process_input_messages](#process_input_messages)|Eingabe verarbeiten von Nachrichten. Dies ist nur nützlich für weitergabeblöcke, die von Source_block abgeleitet werden (überschreibt [source_block:: process_input_messages](source-block-class.md#process_input_messages).)|
|[propagate_message](#propagate_message)|Ruft beim Überschreiben in einer abgeleiteten Klasse diese Methode übergibt eine Meldung asynchron aus einem `ISource` Block, um diese `propagator_block` Objekt. Wird aufgerufen, indem die `propagate` Methode, wenn Sie von einem Quellblock aufgerufen.|
|[register_filter](#register_filter)|Registriert eine Filtermethode, die für jede empfangene Nachricht aufgerufen wird.|
|[remove_network_links](#remove_network_links)|Entfernt alle Quell- und Netzwerkverbindungen aus diesem `propagator_block` Objekt.|
|[send_message](#send_message)|Diese Methode übergibt beim Überschreiben in einer abgeleiteten Klasse synchron eine Nachricht von einem `ISource` Block, um diese `propagator_block` Objekt. Wird aufgerufen, indem die `send` Methode, wenn Sie von einem Quellblock aufgerufen.|
|[unlink_source](#unlink_source)|Hebt die Verknüpfung mit einem angegebenen Quellblock aus diesem `propagator_block` Objekt.|
|[unlink_sources](#unlink_sources)|Hebt die Verknüpfung aller Quellblöcke dies `propagator_block` Objekt. (Überschreibt [ITarget:: Unlink_sources](itarget-class.md#unlink_sources).)|

## <a name="remarks"></a>Hinweise

Mehrfache Vererbung vermeiden der `propagator_block` Klasse erbt von der `source_block` Klasse und `ITarget` abstrakte Klasse. Die meisten Funktionen in der `target_block` Klasse wird hier repliziert.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[ISource](isource-class.md)

[ITarget](itarget-class.md)

[source_block](source-block-class.md)

`propagator_block`

## <a name="requirements"></a>Anforderungen

**Header:** agents.h

**Namespace:** Parallelität

##  <a name="decline_incoming_messages"></a> decline_incoming_messages

Zeigt den Block an, dass neue Nachrichten abgelehnt werden sollte.

```
void decline_incoming_messages();
```

### <a name="remarks"></a>Hinweise

Diese Methode wird aufgerufen, durch den Destruktor, um sicherzustellen, dass neue Nachrichten abgelehnt werden, während Zerstörung ausgeführt wird.

##  <a name="initialize_source_and_target"></a> initialize_source_and_target

Initialisiert das Basisobjekt. Insbesondere die `message_processor` -Objekt muss initialisiert werden.

```
void initialize_source_and_target(
    _Inout_opt_ Scheduler* _PScheduler = NULL,
    _Inout_opt_ ScheduleGroup* _PScheduleGroup = NULL);
```

### <a name="parameters"></a>Parameter

*_PScheduler*<br/>
Der Planer zum Planen von Aufgaben verwendet werden soll.

*_PScheduleGroup*<br/>
Der Planungsgruppe zum Planen von Aufgaben verwendet werden soll.

##  <a name="link_source"></a> link_source

Verknüpft einen angegebenen Quellblock mit diesem `propagator_block` Objekt.

```
virtual void link_source(_Inout_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>Parameter

*_PSource*<br/>
Ein Zeiger auf die `ISource` Block, der verknüpft werden soll.

##  <a name="process_input_messages"></a> process_input_messages

Eingabe verarbeiten von Nachrichten. Dies ist nur nützlich für weitergabeblöcke, die von Source_block abgeleitet werden

```
virtual void process_input_messages(_Inout_ message<_Target_type>* _PMessage);
```

### <a name="parameters"></a>Parameter

*_PMessage*<br/>
Ein Zeiger auf die Meldung, die verarbeitet werden soll.

##  <a name="propagate"></a> weitergeben

Übergibt eine Nachricht asynchron von einem Quellblock mit diesem Zielblock.

```
virtual message_status propagate(
    _Inout_opt_ message<_Source_type>* _PMessage,
    _Inout_opt_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>Parameter

*_PMessage*<br/>
Ein Zeiger auf das `message`-Objekt.

*_PSource*<br/>
Ein Zeiger auf den Quellblock die Nachricht anbietet.

### <a name="return-value"></a>Rückgabewert

Ein [Message_status](concurrency-namespace-enums.md) Überblick, was das Ziel beschlossen, die Sie mit der Meldung.

### <a name="remarks"></a>Hinweise

Die `propagate` Methode für ein Zielblock, von einem Block verknüpfte Quelle aufgerufen wird. Es reiht eine asynchrone Aufgabe, die Meldung zu behandeln, wenn nicht bereits in der Warteschlange steht oder ausführen.

Löst die Methode eine [Invalid_argument](../../../standard-library/invalid-argument-class.md) -Ausnahme aus, wenn entweder die `_PMessage` oder `_PSource` Parameter `NULL`.

##  <a name="propagate_message"></a> propagate_message

Ruft beim Überschreiben in einer abgeleiteten Klasse diese Methode übergibt eine Meldung asynchron aus einem `ISource` Block, um diese `propagator_block` Objekt. Wird aufgerufen, indem die `propagate` Methode, wenn Sie von einem Quellblock aufgerufen.

```
virtual message_status propagate_message(
    _Inout_ message<_Source_type>* _PMessage,
    _Inout_ ISource<_Source_type>* _PSource) = 0;
```

### <a name="parameters"></a>Parameter

*_PMessage*<br/>
Ein Zeiger auf das `message`-Objekt.

*_PSource*<br/>
Ein Zeiger auf den Quellblock die Nachricht anbietet.

### <a name="return-value"></a>Rückgabewert

Ein [Message_status](concurrency-namespace-enums.md) Überblick, was das Ziel beschlossen, die Sie mit der Meldung.

##  <a name="ctor"></a> propagator_block

Erstellt ein `propagator_block`-Objekt.

```
propagator_block();
```

##  <a name="dtor"></a> ~ Propagator_block

Zerstört ein `propagator_block`-Objekt.

```
virtual ~propagator_block();
```

##  <a name="register_filter"></a> register_filter

Registriert eine Filtermethode, die für jede empfangene Nachricht aufgerufen wird.

```
void register_filter(filter_method const& _Filter);
```

### <a name="parameters"></a>Parameter

*_Filter*<br/>
Die Filtermethode.

##  <a name="remove_network_links"></a> remove_network_links

Entfernt alle Quell- und Netzwerkverbindungen aus diesem `propagator_block` Objekt.

```
void remove_network_links();
```

##  <a name="send"></a> Senden

Synchron initiiert eine Nachricht an diesen Block aus. Wird aufgerufen, indem ein `ISource` Block. Wenn diese Funktion abgeschlossen ist, wird die Nachricht bereits in den Block weitergegeben wurden.

```
virtual message_status send(
    _Inout_ message<_Source_type>* _PMessage,
    _Inout_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>Parameter

*_PMessage*<br/>
Ein Zeiger auf das `message`-Objekt.

*_PSource*<br/>
Ein Zeiger auf den Quellblock die Nachricht anbietet.

### <a name="return-value"></a>Rückgabewert

Ein [Message_status](concurrency-namespace-enums.md) Überblick, was das Ziel beschlossen, die Sie mit der Meldung.

### <a name="remarks"></a>Hinweise

Diese Methode löst eine [Invalid_argument](../../../standard-library/invalid-argument-class.md) -Ausnahme aus, wenn entweder die `_PMessage` oder `_PSource` -Parameter ist `NULL`.

##  <a name="send_message"></a> send_message

Diese Methode übergibt beim Überschreiben in einer abgeleiteten Klasse synchron eine Nachricht von einem `ISource` Block, um diese `propagator_block` Objekt. Wird aufgerufen, indem die `send` Methode, wenn Sie von einem Quellblock aufgerufen.

```
virtual message_status send_message(
    _Inout_ message<_Source_type> *,
    _Inout_ ISource<_Source_type> *);
```

### <a name="return-value"></a>Rückgabewert

Ein [Message_status](concurrency-namespace-enums.md) Überblick, was das Ziel beschlossen, die Sie mit der Meldung.

### <a name="remarks"></a>Hinweise

Standardmäßig gibt dieser Block `declined` , sofern nicht durch eine abgeleitete Klasse überschrieben.

##  <a name="unlink_source"></a> unlink_source

Hebt die Verknüpfung mit einem angegebenen Quellblock aus diesem `propagator_block` Objekt.

```
virtual void unlink_source(_Inout_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>Parameter

*_PSource*<br/>
Ein Zeiger auf die `ISource` Block, der getrennt werden soll.

##  <a name="unlink_sources"></a> unlink_sources

Hebt die Verknüpfung aller Quellblöcke dies `propagator_block` Objekt.

```
virtual void unlink_sources();
```

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[source_block-Klasse](source-block-class.md)<br/>
[ITarget-Klasse](itarget-class.md)
