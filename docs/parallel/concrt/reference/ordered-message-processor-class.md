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
ms.openlocfilehash: c6e09ff862f0725cc508e3e390dbfa3cc12f7daa
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50545963"
---
# <a name="orderedmessageprocessor-class"></a>ordered_message_processor-Klasse

Ein `ordered_message_processor` ist ein `message_processor`, mit dem Meldungsblöcke Meldungen in der Reihenfolge verarbeiten können, in der sie empfangen wurden.

## <a name="syntax"></a>Syntax

```
template<class T>
class ordered_message_processor : public message_processor<T>;
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Der Nutzlasttyp der Nachrichten, die vom Prozessor verarbeitet werden soll.

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|Beschreibung|
|----------|-----------------|
|`type`|Ein Typalias für `T`.|

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[ordered_message_processor](#ctor)|Erstellt ein `ordered_message_processor`-Objekt.|
|[~ Ordered_message_processor-Destruktor](#dtor)|Zerstört das `ordered_message_processor`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[async_send](#async_send)|Asynchron in eine Warteschlange Nachrichten und eine Verarbeitungsaufgabe beginnt, wenn dies nicht bereits geschehen ist. (Überschreibt [message_processor:: async_send](message-processor-class.md#async_send).)|
|[initialize](#initialize)|Initialisiert die `ordered_message_processor` -Objekt mit der entsprechenden Callback-Funktion, den Planer und Zeitplan.|
|[initialize_batched_processing](#initialize_batched_processing)|Initialisieren Sie als Batch erstellte Nachricht verarbeiten|
|[sync_send](#sync_send)|Synchrone Nachrichten in eine Warteschlange und eine Verarbeitungsaufgabe beginnt, wenn dies nicht bereits geschehen ist. (Überschreibt [message_processor:: sync_send](message-processor-class.md#sync_send).)|
|[wait](#wait)|Einer prozessorspezifischen Spin-Wartezeit in Destruktoren von Nachrichtenblöcken verwendet, um sicherzustellen, dass alle Aufgaben für die asynchrone Verarbeitung abgeschlossen ist, bevor der Block zerstören können. (Überschreibt [message_processor:: wait](message-processor-class.md#wait).)|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[process_incoming_message](#process_incoming_message)|Die Processing-Funktion, die asynchron aufgerufen wird. Es entfernt Nachrichten und beginnt mit ihrer Verarbeitung. (Überschreibt [message_processor:: process_incoming_message](message-processor-class.md#process_incoming_message).)|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[message_processor](message-processor-class.md)

`ordered_message_processor`

## <a name="requirements"></a>Anforderungen

**Header:** agents.h

**Namespace:** Parallelität

##  <a name="async_send"></a> async_send

Asynchron in eine Warteschlange Nachrichten und eine Verarbeitungsaufgabe beginnt, wenn dies nicht bereits geschehen ist.

```
virtual void async_send(_Inout_opt_ message<T>* _Msg);
```

### <a name="parameters"></a>Parameter

*_Msg*<br/>
Ein Zeiger auf eine Nachricht.

##  <a name="initialize"></a> Initialisieren

Initialisiert die `ordered_message_processor` -Objekt mit der entsprechenden Callback-Funktion, den Planer und Zeitplan.

```
void initialize(
    _Inout_opt_ Scheduler* _PScheduler,
    _Inout_opt_ ScheduleGroup* _PScheduleGroup,
    _Handler_method const& _Handler);
```

### <a name="parameters"></a>Parameter

*_PScheduler*<br/>
Ein Zeiger auf den Zeitplan an, für die Planung von einfachen Aufgaben verwendet werden.

*_PScheduleGroup*<br/>
Ein Zeiger auf die Planungsgruppe zum Planen von Lightweight-Aufgaben verwendet werden soll.

*_Handler*<br/>
Der Handlerfunktionselement während des Rückrufs aufgerufen.

##  <a name="initialize_batched_processing"></a> initialize_batched_processing

Initialisieren Sie als Batch erstellte Nachricht verarbeiten

```
virtual void initialize_batched_processing(
    _Handler_method const& _Processor,
    _Propagator_method const& _Propagator);
```

### <a name="parameters"></a>Parameter

*_Processor*<br/>
Die Prozessor-Funktionselement während der Rückruf aufgerufen wird.

*_Propagator*<br/>
Die Propagierung Funktionselement während des Rückrufs aufgerufen.

##  <a name="ctor"></a> ordered_message_processor

Erstellt ein `ordered_message_processor`-Objekt.

```
ordered_message_processor();
```

### <a name="remarks"></a>Hinweise

Dies `ordered_message_processor` werde nicht planen, asynchrone oder synchrone Handlern, bis die `initialize` -Funktion aufgerufen wird.

##  <a name="dtor"></a> ~ordered_message_processor

Zerstört das `ordered_message_processor`-Objekt.

```
virtual ~ordered_message_processor();
```

### <a name="remarks"></a>Hinweise

Wartet darauf, alle ausstehenden asynchronen Prozesse vor dem Zerstören des Prozessors.

##  <a name="process_incoming_message"></a> process_incoming_message

Die Processing-Funktion, die asynchron aufgerufen wird. Es entfernt Nachrichten und beginnt mit ihrer Verarbeitung.

```
virtual void process_incoming_message();
```

##  <a name="sync_send"></a> sync_send

Synchrone Nachrichten in eine Warteschlange und eine Verarbeitungsaufgabe beginnt, wenn dies nicht bereits geschehen ist.

```
virtual void sync_send(_Inout_opt_ message<T>* _Msg);
```

### <a name="parameters"></a>Parameter

*_Msg*<br/>
Ein Zeiger auf eine Nachricht.

##  <a name="wait"></a> Warte

Einer prozessorspezifischen Spin-Wartezeit in Destruktoren von Nachrichtenblöcken verwendet, um sicherzustellen, dass alle Aufgaben für die asynchrone Verarbeitung abgeschlossen ist, bevor der Block zerstören können.

```
virtual void wait();
```

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)
