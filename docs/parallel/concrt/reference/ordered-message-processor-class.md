---
title: ordered_message_processor-Klasse
ms.date: 11/04/2016
f1_keywords:
- ordered_message_processor
- AGENTS/concurrency::ordered_message_processor
- AGENTS/concurrency::ordered_message_processor::ordered_message_processor
- AGENTS/concurrency::ordered_message_processor::async_send
- AGENTS/concurrency::ordered_message_processor::initialize
- AGENTS/concurrency::ordered_message_processor::initialize_batched_processing
- AGENTS/concurrency::ordered_message_processor::sync_send
- AGENTS/concurrency::ordered_message_processor::wait
- AGENTS/concurrency::ordered_message_processor::process_incoming_message
helpviewer_keywords:
- ordered_message_processor class
ms.assetid: 787adfb7-7f79-4a70-864a-80e3b64088cd
ms.openlocfilehash: ea9ca799f36cac0d843a578eb7cef9c1e9c5cda6
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77138784"
---
# <a name="ordered_message_processor-class"></a>ordered_message_processor-Klasse

Ein `ordered_message_processor` ist ein `message_processor`, mit dem Meldungsblöcke Meldungen in der Reihenfolge verarbeiten können, in der sie empfangen wurden.

## <a name="syntax"></a>Syntax

```cpp
template<class T>
class ordered_message_processor : public message_processor<T>;
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der Nutz Lasttyp der Nachrichten, die vom Prozessor verarbeitet werden.

## <a name="members"></a>Members

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|BESCHREIBUNG|
|----------|-----------------|
|`type`|Ein Typalias für `T`.|

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[ordered_message_processor](#ctor)|Erstellt ein `ordered_message_processor`-Objekt.|
|[~ ordered_message_processor-Dekonstruktor](#dtor)|Zerstört das `ordered_message_processor`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|BESCHREIBUNG|
|----------|-----------------|
|[async_send](#async_send)|Fügt Nachrichten asynchron in die Warteschlange ein und startet einen Verarbeitungs Task, wenn dies noch nicht geschehen ist. (Überschreibt [message_processor:: async_send](message-processor-class.md#async_send).)|
|[Initialisieren](#initialize)|Initialisiert das `ordered_message_processor`-Objekt mit der entsprechenden Rückruffunktion, dem Scheduler und der Zeit Plan Gruppe.|
|[initialize_batched_processing](#initialize_batched_processing)|Nachrichtenverarbeitung im Batch Modus initialisieren|
|[sync_send](#sync_send)|Fügt Nachrichten synchron in die Warteschlange ein und startet einen Verarbeitungs Task, wenn dies noch nicht geschehen ist. (Überschreibt [message_processor:: sync_send](message-processor-class.md#sync_send).)|
|[Warte](#wait)|Ein Prozessor spezifischer Spin-Wait-Vorgang, der in debugktoren von Nachrichten Blöcken verwendet wird, um sicherzustellen, dass alle asynchronen Verarbeitungs Tasks Zeit bis zum Ende haben, bevor der Block zerstört wird. (Überschreibt [message_processor:: Wait](message-processor-class.md#wait).)|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|BESCHREIBUNG|
|----------|-----------------|
|[process_incoming_message](#process_incoming_message)|Die Verarbeitungs Funktion, die asynchron aufgerufen wird. Er entfernt Nachrichten aus der Warteschlange und beginnt mit der Verarbeitung. (Überschreibt [message_processor::p rocess_incoming_message](message-processor-class.md#process_incoming_message).)|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[message_processor](message-processor-class.md)

`ordered_message_processor`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** agents.h

**Namespace:** Parallelität

## <a name="async_send"></a>async_send

Fügt Nachrichten asynchron in die Warteschlange ein und startet einen Verarbeitungs Task, wenn dies noch nicht geschehen ist.

```cpp
virtual void async_send(_Inout_opt_ message<T>* _Msg);
```

### <a name="parameters"></a>Parameter

*_Msg*<br/>
Ein Zeiger auf eine Meldung.

## <a name="initialize"></a>Initialisieren

Initialisiert das `ordered_message_processor`-Objekt mit der entsprechenden Rückruffunktion, dem Scheduler und der Zeit Plan Gruppe.

```cpp
void initialize(
    _Inout_opt_ Scheduler* _PScheduler,
    _Inout_opt_ ScheduleGroup* _PScheduleGroup,
    _Handler_method const& _Handler);
```

### <a name="parameters"></a>Parameter

*_PScheduler*<br/>
Ein Zeiger auf den Scheduler, der zum Planen einfacher Aufgaben verwendet werden soll.

*_PScheduleGroup*<br/>
Ein Zeiger auf die Zeit Plan Gruppe, die für die Planung einfacher Aufgaben verwendet werden soll.

*_Handler*<br/>
Der während des Rückrufs aufgerufene handlerfunktor.

## <a name="initialize_batched_processing"></a>initialize_batched_processing

Nachrichtenverarbeitung im Batch Modus initialisieren

```cpp
virtual void initialize_batched_processing(
    _Handler_method const& _Processor,
    _Propagator_method const& _Propagator);
```

### <a name="parameters"></a>Parameter

*_Processor*<br/>
Der während des Rückrufs aufgerufene prozessorfunktor.

*_Propagator*<br/>
Der während des Rückrufs aufgerufene propagatorfunktor.

## <a name="ctor"></a>ordered_message_processor

Erstellt ein `ordered_message_processor`-Objekt.

```cpp
ordered_message_processor();
```

### <a name="remarks"></a>Bemerkungen

Diese `ordered_message_processor` plant keine asynchronen oder synchronen Handler, bis die `initialize`-Funktion aufgerufen wird.

## <a name="dtor"></a>~ ordered_message_processor

Zerstört das `ordered_message_processor`-Objekt.

```cpp
virtual ~ordered_message_processor();
```

### <a name="remarks"></a>Bemerkungen

Wartet auf alle ausstehenden asynchronen Vorgänge, bevor der Prozessor zerstört wird.

## <a name="process_incoming_message"></a>process_incoming_message

Die Verarbeitungs Funktion, die asynchron aufgerufen wird. Er entfernt Nachrichten aus der Warteschlange und beginnt mit der Verarbeitung.

```cpp
virtual void process_incoming_message();
```

## <a name="sync_send"></a>sync_send

Fügt Nachrichten synchron in die Warteschlange ein und startet einen Verarbeitungs Task, wenn dies noch nicht geschehen ist.

```cpp
virtual void sync_send(_Inout_opt_ message<T>* _Msg);
```

### <a name="parameters"></a>Parameter

*_Msg*<br/>
Ein Zeiger auf eine Meldung.

## <a name="wait"></a>Warte

Ein Prozessor spezifischer Spin-Wait-Vorgang, der in debugktoren von Nachrichten Blöcken verwendet wird, um sicherzustellen, dass alle asynchronen Verarbeitungs Tasks Zeit bis zum Ende haben, bevor der Block zerstört wird.

```cpp
virtual void wait();
```

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace](concurrency-namespace.md)
