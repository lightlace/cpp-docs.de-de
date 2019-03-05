---
title: overwrite_buffer-Klasse
ms.date: 11/04/2016
f1_keywords:
- overwrite_buffer
- AGENTS/concurrency::overwrite_buffer
- AGENTS/concurrency::overwrite_buffer::overwrite_buffer
- AGENTS/concurrency::overwrite_buffer::has_value
- AGENTS/concurrency::overwrite_buffer::value
- AGENTS/concurrency::overwrite_buffer::accept_message
- AGENTS/concurrency::overwrite_buffer::consume_message
- AGENTS/concurrency::overwrite_buffer::link_target_notification
- AGENTS/concurrency::overwrite_buffer::propagate_message
- AGENTS/concurrency::overwrite_buffer::propagate_to_any_targets
- AGENTS/concurrency::overwrite_buffer::release_message
- AGENTS/concurrency::overwrite_buffer::reserve_message
- AGENTS/concurrency::overwrite_buffer::resume_propagation
- AGENTS/concurrency::overwrite_buffer::send_message
- AGENTS/concurrency::overwrite_buffer::supports_anonymous_source
helpviewer_keywords:
- overwrite_buffer class
ms.assetid: 5cc428fe-3697-419c-9fb2-78f6181c9293
ms.openlocfilehash: adac6e220a60a49a2b9bfa9463f16f8956b08d2e
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57299308"
---
# <a name="overwritebuffer-class"></a>overwrite_buffer-Klasse

Ein `overwrite_buffer`-Meldungsblock ist ein geordneter `propagator_block` mit mehreren Zielen und mehreren Quellen, der jeweils eine einzelne Meldung speichern kann. Neue Meldungen überschreiben zuvor Gespeicherte.

## <a name="syntax"></a>Syntax

```
template<class T>
class overwrite_buffer : public propagator_block<multi_link_registry<ITarget<T>>, multi_link_registry<ISource<T>>>;
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Der Nutzlasttyp der Nachrichten gespeichert und vom Puffer weitergegeben.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[overwrite_buffer](#ctor)|Überladen. Erstellt eine `overwrite_buffer` Meldungsblock.|
|[~overwrite_buffer Destructor](#dtor)|Zerstört die `overwrite_buffer` Meldungsblock.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[has_value](#has_value)|Überprüft, ob dies `overwrite_buffer` -Meldungsblock ist einen Wert noch nicht.|
|[value](#value)|Ruft einen Verweis auf die aktuelle Nutzlast der Nachricht gespeichert werden, der `overwrite_buffer` Meldungsblock.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[accept_message](#accept_message)|Akzeptiert eine Meldung, die von diesem angeboten wurde `overwrite_buffer` Meldungsblock, eine Kopie der Nachricht an den Aufrufer zurückgegeben.|
|[consume_message](#consume_message)|Nimmt eine Meldung, die zuvor von Angeboten die `overwrite_buffer` -Meldungsblock und reserviert, die vom Ziel eine Kopie der Nachricht an den Aufrufer zurückgegeben.|
|[link_target_notification](#link_target_notification)|Ein Rückruf, der benachrichtigt, dass ein neues Ziel mit dieser verknüpft wurde `overwrite_buffer` Meldungsblock.|
|[propagate_message](#propagate_message)|Übergibt asynchron eine Nachricht von einem `ISource` Block, um diese `overwrite_buffer` Meldungsblock. Wird aufgerufen, indem die `propagate` Methode, wenn Sie von einem Quellblock aufgerufen.|
|[propagate_to_any_targets](#propagate_to_any_targets)|Stellen die `message _PMessage` in diesem `overwrite_buffer` Block messaging und bietet sie alle verknüpften Ziele.|
|[release_message](#release_message)|Gibt die nachrichtenreservierung einer vorherigen frei. (Überschreibt [source_block:: release_message](source-block-class.md#release_message).)|
|[reserve_message](#reserve_message)|Reserviert eine Meldung, die zuvor von diesem angebotenen `overwrite_buffer` Meldungsblock. (Überschreibt [source_block:: reserve_message](source-block-class.md#reserve_message).)|
|[resume_propagation](#resume_propagation)|Weitergabe fortgesetzt, nachdem eine Reservierung freigegeben wurde. (Overrides [source_block::resume_propagation](source-block-class.md#resume_propagation).)|
|[send_message](#send_message)|Übergibt synchron eine Nachricht von einem `ISource` Block, um diese `overwrite_buffer` Meldungsblock. Wird aufgerufen, indem die `send` Methode, wenn Sie von einem Quellblock aufgerufen.|
|[supports_anonymous_source](#supports_anonymous_source)|Überschreibt die `supports_anonymous_source` Methode, um anzugeben, dass dieser Block annehmen kann Nachrichten angeboten, von einer Quelle, die nicht verknüpft ist. (Überschreibt [ITarget:: Supports_anonymous_source](itarget-class.md#supports_anonymous_source).)|

## <a name="remarks"></a>Hinweise

Ein `overwrite_buffer` Meldungsblock Kopien der gespeicherten Nachricht auf jedes der zugehörigen Ziele weiter.

Weitere Informationen finden Sie unter [asynchrone Meldungsblöcke](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[ISource](isource-class.md)

[ITarget](itarget-class.md)

[source_block](source-block-class.md)

[propagator_block](propagator-block-class.md)

`overwrite_buffer`

## <a name="requirements"></a>Anforderungen

**Header:** agents.h

**Namespace:** Parallelität

##  <a name="accept_message"></a> accept_message

Akzeptiert eine Meldung, die von diesem angeboten wurde `overwrite_buffer` Meldungsblock, eine Kopie der Nachricht an den Aufrufer zurückgegeben.

```
virtual message<T>* accept_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parameter

*_MsgId*<br/>
Die `runtime_object_identity` von den angebotenen `message` Objekt.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die `message` Objekt, mit der Aufrufer jetzt besitzt.

### <a name="remarks"></a>Hinweise

Die `overwrite_buffer` -Meldungsblock gibt Kopien der Nachricht, die Ziele, anstatt die zurzeit Nachricht übertragen.

##  <a name="consume_message"></a> consume_message

Nimmt eine Meldung, die zuvor von Angeboten die `overwrite_buffer` -Meldungsblock und reserviert, die vom Ziel eine Kopie der Nachricht an den Aufrufer zurückgegeben.

```
virtual message<T>* consume_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parameter

*_MsgId*<br/>
Die `runtime_object_identity` von der `message` -Objekt verarbeitet.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die `message` Objekt, mit der Aufrufer jetzt besitzt.

### <a name="remarks"></a>Hinweise

Ähnlich wie `accept`, steht aber immer durch einen Aufruf von ist `reserve`.

##  <a name="has_value"></a> has_value

Überprüft, ob dies `overwrite_buffer` -Meldungsblock ist einen Wert noch nicht.

```
bool has_value() const;
```

### <a name="return-value"></a>Rückgabewert

**"true"** , wenn der Block einen Wert erhalten hat **"false"** andernfalls.

##  <a name="link_target_notification"></a> link_target_notification

Ein Rückruf, der benachrichtigt, dass ein neues Ziel mit dieser verknüpft wurde `overwrite_buffer` Meldungsblock.

```
virtual void link_target_notification(_Inout_ ITarget<T>* _PTarget);
```

### <a name="parameters"></a>Parameter

*_PTarget*<br/>
Ein Zeiger auf das neu verknüpften Ziel.

##  <a name="dtor"></a> ~overwrite_buffer

Zerstört die `overwrite_buffer` Meldungsblock.

```
~overwrite_buffer();
```

##  <a name="ctor"></a> overwrite_buffer

Erstellt eine `overwrite_buffer` Meldungsblock.

```
overwrite_buffer();

overwrite_buffer(
    filter_method const& _Filter);

overwrite_buffer(
    Scheduler& _PScheduler);

overwrite_buffer(
    Scheduler& _PScheduler,
    filter_method const& _Filter);

overwrite_buffer(
    ScheduleGroup& _PScheduleGroup);

overwrite_buffer(
    ScheduleGroup& _PScheduleGroup,
    filter_method const& _Filter);
```

### <a name="parameters"></a>Parameter

*_Filter*<br/>
Eine Filterfunktion, die bestimmt, ob angebotene Nachrichten akzeptiert werden sollen.

*_PScheduler*<br/>
Das `Scheduler` -Objekt, in dem die Weiterleitungsaufgabe für den `overwrite_buffer` -Meldungsblock geplant ist.

*_PScheduleGroup*<br/>
Das `ScheduleGroup` -Objekt, in dem die Weiterleitungsaufgabe für den `overwrite_buffer` -Meldungsblock geplant ist. Das verwendete `Scheduler` -Objekt wird von der Planungsgruppe impliziert.

### <a name="remarks"></a>Hinweise

Die Runtime verwendet das Standardplanungsprogramm, wenn Sie den `_PScheduler` -Parameter oder den `_PScheduleGroup` -Parameter nicht angeben.

Der Typ `filter_method` ist ein Funktionselement mit Signatur `bool (T const &)` die aufgerufen wird, von diesem `overwrite_buffer` Meldungsblock, um zu bestimmen, und zwar unabhängig davon, ob sie eine angebotene Nachricht akzeptiert werden sollte.

##  <a name="propagate_message"></a> propagate_message

Übergibt asynchron eine Nachricht von einem `ISource` Block, um diese `overwrite_buffer` Meldungsblock. Wird aufgerufen, indem die `propagate` Methode, wenn Sie von einem Quellblock aufgerufen.

```
virtual message_status propagate_message(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource);
```

### <a name="parameters"></a>Parameter

*_PMessage*<br/>
Ein Zeiger auf das `message`-Objekt.

*_PSource*<br/>
Ein Zeiger auf den Quellblock die Nachricht anbietet.

### <a name="return-value"></a>Rückgabewert

Ein [Message_status](concurrency-namespace-enums.md) Überblick, was das Ziel beschlossen, die Sie mit der Meldung.

##  <a name="propagate_to_any_targets"></a> propagate_to_any_targets

Stellen die `message _PMessage` in diesem `overwrite_buffer` Block messaging und bietet sie alle verknüpften Ziele.

```
virtual void propagate_to_any_targets(_Inout_ message<T>* _PMessage);
```

### <a name="parameters"></a>Parameter

*_PMessage*<br/>
Ein Zeiger auf eine `message` Objekt, das von diesem `overwrite_buffer` Besitzrechte übernommen hat.

### <a name="remarks"></a>Hinweise

Diese Methode überschreibt die aktuelle Meldung in die `overwrite_buffer` mit der neu angenommene Meldung `_PMessage`.

##  <a name="send_message"></a> send_message

Übergibt synchron eine Nachricht von einem `ISource` Block, um diese `overwrite_buffer` Meldungsblock. Wird aufgerufen, indem die `send` Methode, wenn Sie von einem Quellblock aufgerufen.

```
virtual message_status send_message(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource);
```

### <a name="parameters"></a>Parameter

*_PMessage*<br/>
Ein Zeiger auf das `message`-Objekt.

*_PSource*<br/>
Ein Zeiger auf den Quellblock die Nachricht anbietet.

### <a name="return-value"></a>Rückgabewert

Ein [Message_status](concurrency-namespace-enums.md) Überblick, was das Ziel beschlossen, die Sie mit der Meldung.

##  <a name="supports_anonymous_source"></a> supports_anonymous_source

Überschreibt die `supports_anonymous_source` Methode, um anzugeben, dass dieser Block annehmen kann Nachrichten angeboten, von einer Quelle, die nicht verknüpft ist.

```
virtual bool supports_anonymous_source();
```

### <a name="return-value"></a>Rückgabewert

**"true"** , weil der Block nicht verschieben wird angeboten Nachrichten.

##  <a name="release_message"></a> release_message

Gibt die nachrichtenreservierung einer vorherigen frei.

```
virtual void release_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parameter

*_MsgId*<br/>
Die `runtime_object_identity` von der `message` Objekt freigegeben wird.

##  <a name="reserve_message"></a> reserve_message

Reserviert eine Meldung, die zuvor von diesem angebotenen `overwrite_buffer` Meldungsblock.

```
virtual bool reserve_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parameter

*_MsgId*<br/>
Die `runtime_object_identity` von der `message` Objekt reserviert wird.

### <a name="return-value"></a>Rückgabewert

**"true"** , wenn die Nachricht erfolgreich reserviert wurde, **"false"** andernfalls.

### <a name="remarks"></a>Hinweise

Nach dem `reserve` aufgerufen wird, wenn zurückgegeben **"true"**, entweder `consume` oder `release` aufgerufen werden, um zu übernehmen oder den Besitz der Nachricht.

##  <a name="resume_propagation"></a> resume_propagation

Weitergabe fortgesetzt, nachdem eine Reservierung freigegeben wurde.

```
virtual void resume_propagation();
```

##  <a name="value"></a> Wert

Ruft einen Verweis auf die aktuelle Nutzlast der Nachricht gespeichert werden, der `overwrite_buffer` Meldungsblock.

```
T value();
```

### <a name="return-value"></a>Rückgabewert

Die Nutzlast der aktuell gespeicherten Nachricht.

### <a name="remarks"></a>Hinweise

Gespeicherte Wert in der `overwrite_buffer` können sofort nach dem Beenden dieser Methode ändern. Diese Methode wartet, bis eine Meldung eintrifft, wenn derzeit keine Meldung in gespeichert ist die `overwrite_buffer`.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[unbounded_buffer-Klasse](unbounded-buffer-class.md)<br/>
[single_assignment-Klasse](single-assignment-class.md)
