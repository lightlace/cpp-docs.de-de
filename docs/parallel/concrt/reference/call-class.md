---
title: call-Klasse
ms.date: 11/04/2016
f1_keywords:
- call
- AGENTS/concurrency::call
- AGENTS/concurrency::call::call
- AGENTS/concurrency::call::process_input_messages
- AGENTS/concurrency::call::process_message
- AGENTS/concurrency::call::propagate_message
- AGENTS/concurrency::call::send_message
- AGENTS/concurrency::call::supports_anonymous_source
helpviewer_keywords:
- call class
ms.assetid: 1521970a-1e9c-4b0c-a681-d18e40976f49
ms.openlocfilehash: 445e368ced9d9c8faf30351ecaeecc4e1b8a59f2
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142837"
---
# <a name="call-class"></a>call-Klasse

Ein `call`-Meldungsblock ist ein geordneter `target_block` mit mehreren Quellen, der eine bestimmte Funktion aufruft, wenn eine Nachricht empfangen wird.

## <a name="syntax"></a>Syntax

```cpp
template<class T, class _FunctorType = std::function<void(T const&)>>
class call : public target_block<multi_link_registry<ISource<T>>>;
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der Nutz Lasttyp der Nachrichten, die an diesen Block weitergegeben werden.

*_FunctorType*<br/>
Die Signatur von Funktionen, die dieser Block annehmen kann.

## <a name="members"></a>Members

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[erfordern](#ctor)|Ist überladen. Erstellt einen `call` -Meldungsblock.|
|[~ aufrudedekonstruktor](#dtor)|Zerstört den `call`-Messaging-Block.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|BESCHREIBUNG|
|----------|-----------------|
|[process_input_messages](#process_input_messages)|Führt die Funktion "-Rückruf" für die Eingabe Nachrichten aus.|
|[process_message](#process_message)|Verarbeitet eine Nachricht, die von diesem `call`-Nachrichtenblock akzeptiert wurde.|
|[propagate_message](#propagate_message)|Übergibt eine Nachricht asynchron von einem `ISource`-Block an diesen `call`-Messaging-Block. Sie wird durch die `propagate`-Methode aufgerufen, wenn Sie von einem Quell Block aufgerufen wird.|
|[send_message](#send_message)|Übergibt eine Nachricht synchron von einem `ISource`-Block an diesen `call`-Messaging-Block. Sie wird durch die `send`-Methode aufgerufen, wenn Sie von einem Quell Block aufgerufen wird.|
|[supports_anonymous_source](#supports_anonymous_source)|Überschreibt die `supports_anonymous_source`-Methode, um anzugeben, dass dieser Block Nachrichten akzeptieren kann, die ihm von einer nicht verknüpften Quelle angeboten werden. (Überschreibt [ITarget:: supports_anonymous_source](itarget-class.md#supports_anonymous_source).)|

## <a name="remarks"></a>Bemerkungen

Weitere Informationen finden Sie unter [asynchrone Nachrichten Blöcke](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[ITarget](itarget-class.md)

[target_block](target-block-class.md)

`call`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** agents.h

**Namespace:** Parallelität

## <a name="ctor"></a>erfordern

Erstellt einen `call` -Meldungsblock.

```cpp
call(
    _Call_method const& _Func);

call(
    _Call_method const& _Func,
    filter_method const& _Filter);

call(
    Scheduler& _PScheduler,
    _Call_method const& _Func);

call(
    Scheduler& _PScheduler,
    _Call_method const& _Func,
    filter_method const& _Filter);

call(
    ScheduleGroup& _PScheduleGroup,
    _Call_method const& _Func);

call(
    ScheduleGroup& _PScheduleGroup,
    _Call_method const& _Func,
    filter_method const& _Filter);
```

### <a name="parameters"></a>Parameter

*_Func*<br/>
Eine Funktion, die für jede akzeptierte Nachricht aufgerufen wird.

*_Filter*<br/>
Eine Filterfunktion, die bestimmt, ob angebotene Nachrichten akzeptiert werden sollen.

*_PScheduler*<br/>
Das `Scheduler` -Objekt, in dem die Weiterleitungsaufgabe für den `call` -Meldungsblock geplant ist.

*_PScheduleGroup*<br/>
Das `ScheduleGroup` -Objekt, in dem die Weiterleitungsaufgabe für den `call` -Meldungsblock geplant ist. Das verwendete `Scheduler` -Objekt wird von der Planungsgruppe impliziert.

### <a name="remarks"></a>Bemerkungen

Die Runtime verwendet das Standardplanungsprogramm, wenn Sie den `_PScheduler` -Parameter oder den `_PScheduleGroup` -Parameter nicht angeben.

Der Typ `_Call_method` ist ein Funktor mit Signatur `void (T const &)` der von diesem `call` Messaging Block aufgerufen wird, um eine Nachricht zu verarbeiten.

Der Typ `filter_method` ist ein Funktor mit Signatur `bool (T const &)` der von diesem `call` Messaging Block aufgerufen wird, um zu bestimmen, ob er eine angebotene Nachricht akzeptieren soll.

## <a name="dtor"></a>~-Aufrufe

Zerstört den `call`-Messaging-Block.

```cpp
~call();
```

## <a name="process_input_messages"></a>process_input_messages

Führt die Funktion "-Rückruf" für die Eingabe Nachrichten aus.

```cpp
virtual void process_input_messages(_Inout_ message<T>* _PMessage);
```

### <a name="parameters"></a>Parameter

*_PMessage*<br/>
Ein Zeiger auf die Meldung, die behandelt werden soll.

## <a name="process_message"></a>process_message

Verarbeitet eine Nachricht, die von diesem `call`-Nachrichtenblock akzeptiert wurde.

```cpp
virtual void process_message(_Inout_ message<T>* _PMessage);
```

### <a name="parameters"></a>Parameter

*_PMessage*<br/>
Ein Zeiger auf die Meldung, die behandelt werden soll.

## <a name="propagate_message"></a>propagate_message

Übergibt eine Nachricht asynchron von einem `ISource`-Block an diesen `call`-Messaging-Block. Sie wird durch die `propagate`-Methode aufgerufen, wenn Sie von einem Quell Block aufgerufen wird.

```cpp
virtual message_status propagate_message(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource);
```

### <a name="parameters"></a>Parameter

*_PMessage*<br/>
Ein Zeiger auf das `message`-Objekt.

*_PSource*<br/>
Ein Zeiger auf den Quell Block, der die Nachricht anbietet.

### <a name="return-value"></a>Rückgabewert

Eine [Message_status](concurrency-namespace-enums.md) , die angibt, wie sich das Ziel für die Nachricht entschieden hat.

## <a name="send_message"></a>send_message

Übergibt eine Nachricht synchron von einem `ISource`-Block an diesen `call`-Messaging-Block. Sie wird durch die `send`-Methode aufgerufen, wenn Sie von einem Quell Block aufgerufen wird.

```cpp
virtual message_status send_message(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource);
```

### <a name="parameters"></a>Parameter

*_PMessage*<br/>
Ein Zeiger auf das `message`-Objekt.

*_PSource*<br/>
Ein Zeiger auf den Quell Block, der die Nachricht anbietet.

### <a name="return-value"></a>Rückgabewert

Eine [Message_status](concurrency-namespace-enums.md) , die angibt, wie sich das Ziel für die Nachricht entschieden hat.

## <a name="supports_anonymous_source"></a>supports_anonymous_source

Überschreibt die `supports_anonymous_source`-Methode, um anzugeben, dass dieser Block Nachrichten akzeptieren kann, die ihm von einer nicht verknüpften Quelle angeboten werden.

```cpp
virtual bool supports_anonymous_source();
```

### <a name="return-value"></a>Rückgabewert

**true** , weil der-Block angebotene Nachrichten nicht verschiebt.

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[transformer-Klasse](transformer-class.md)
