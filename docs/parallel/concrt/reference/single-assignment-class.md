---
title: single_assignment-Klasse
ms.date: 11/04/2016
f1_keywords:
- single_assignment
- AGENTS/concurrency::single_assignment
- AGENTS/concurrency::single_assignment::single_assignment
- AGENTS/concurrency::single_assignment::has_value
- AGENTS/concurrency::single_assignment::value
- AGENTS/concurrency::single_assignment::accept_message
- AGENTS/concurrency::single_assignment::consume_message
- AGENTS/concurrency::single_assignment::link_target_notification
- AGENTS/concurrency::single_assignment::propagate_message
- AGENTS/concurrency::single_assignment::propagate_to_any_targets
- AGENTS/concurrency::single_assignment::release_message
- AGENTS/concurrency::single_assignment::reserve_message
- AGENTS/concurrency::single_assignment::resume_propagation
- AGENTS/concurrency::single_assignment::send_message
helpviewer_keywords:
- single_assignment class
ms.assetid: ccc34728-8de9-4e07-b83d-a36a58d9d2b9
ms.openlocfilehash: 436d0d4cc16ee18449178782b775a25bb1d8592a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62159911"
---
# <a name="singleassignment-class"></a>single_assignment-Klasse

Ein `single_assignment`-Meldungsblock ist ein geordneter `propagator_block` mit mehreren Zielen und mehreren Quellen, der eine einzelne, einmal beschreibbare `message` speichern kann.

## <a name="syntax"></a>Syntax

```
template<class T>
class single_assignment : public propagator_block<multi_link_registry<ITarget<T>>, multi_link_registry<ISource<T>>>;
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Der Nutzlasttyp der Nachricht gespeichert und vom Puffer weitergegeben.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[single_assignment](#ctor)|Überladen. Erstellt einen `single_assignment` -Meldungsblock.|
|[~ Single_assignment-Destruktor](#dtor)|Zerstört die `single_assignment` Meldungsblock.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[has_value](#has_value)|Überprüft, ob dies `single_assignment` Meldungsblock noch mit einem Wert initialisiert wurde.|
|[value](#value)|Ruft einen Verweis auf die aktuelle Nutzlast der Nachricht gespeichert werden, der `single_assignment` Meldungsblock.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[accept_message](#accept_message)|Akzeptiert eine Meldung, die von diesem angeboten wurde `single_assignment` Meldungsblock, eine Kopie der Nachricht an den Aufrufer zurückgegeben.|
|[consume_message](#consume_message)|Nimmt eine Meldung, die zuvor von Angeboten die `single_assignment` und reservierte vom Ziel eine Kopie der Nachricht an den Aufrufer zurückgegeben.|
|[link_target_notification](#link_target_notification)|Ein Rückruf, der benachrichtigt, dass ein neues Ziel mit dieser verknüpft wurde `single_assignment` Meldungsblock.|
|[propagate_message](#propagate_message)|Übergibt asynchron eine Nachricht von einem `ISource` Block, um diese `single_assignment` Meldungsblock. Wird aufgerufen, indem die `propagate` Methode, wenn Sie von einem Quellblock aufgerufen.|
|[propagate_to_any_targets](#propagate_to_any_targets)|Stellen die `message _PMessage` in diesem `single_assignment` Block messaging und bietet sie alle verknüpften Ziele.|
|[release_message](#release_message)|Gibt die nachrichtenreservierung einer vorherigen frei. (Überschreibt [source_block:: release_message](source-block-class.md#release_message).)|
|[reserve_message](#reserve_message)|Reserviert eine Meldung, die zuvor von diesem angebotenen `single_assignment` Meldungsblock. (Überschreibt [source_block:: reserve_message](source-block-class.md#reserve_message).)|
|[resume_propagation](#resume_propagation)|Weitergabe fortgesetzt, nachdem eine Reservierung freigegeben wurde. (Overrides [source_block::resume_propagation](source-block-class.md#resume_propagation).)|
|[send_message](#send_message)|Übergibt synchron eine Nachricht von einem `ISource` Block, um diese `single_assignment` Meldungsblock. Wird aufgerufen, indem die `send` Methode, wenn Sie von einem Quellblock aufgerufen.|

## <a name="remarks"></a>Hinweise

Ein `single_assignment` Meldungsblock Kopien jedes Ziel der Nachricht weitergegeben.

Weitere Informationen finden Sie unter [asynchrone Meldungsblöcke](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[ISource](isource-class.md)

[ITarget](itarget-class.md)

[source_block](source-block-class.md)

[propagator_block](propagator-block-class.md)

`single_assignment`

## <a name="requirements"></a>Anforderungen

**Header:** agents.h

**Namespace:** Parallelität

##  <a name="accept_message"></a> accept_message

Akzeptiert eine Meldung, die von diesem angeboten wurde `single_assignment` Meldungsblock, eine Kopie der Nachricht an den Aufrufer zurückgegeben.

```
virtual message<T>* accept_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parameter

*_MsgId*<br/>
Die `runtime_object_identity` von den angebotenen `message` Objekt.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die `message` Objekt, mit der Aufrufer jetzt besitzt.

### <a name="remarks"></a>Hinweise

Die `single_assignment` -Meldungsblock gibt Kopien der Nachricht, die Ziele, anstatt die zurzeit Nachricht übertragen.

##  <a name="consume_message"></a> consume_message

Nimmt eine Meldung, die zuvor von Angeboten die `single_assignment` und reservierte vom Ziel eine Kopie der Nachricht an den Aufrufer zurückgegeben.

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

Überprüft, ob dies `single_assignment` Meldungsblock noch mit einem Wert initialisiert wurde.

```
bool has_value() const;
```

### <a name="return-value"></a>Rückgabewert

**"true"** , wenn der Block einen Wert erhalten hat **"false"** andernfalls.

##  <a name="link_target_notification"></a> link_target_notification

Ein Rückruf, der benachrichtigt, dass ein neues Ziel mit dieser verknüpft wurde `single_assignment` Meldungsblock.

```
virtual void link_target_notification(_Inout_ ITarget<T>* _PTarget);
```

### <a name="parameters"></a>Parameter

*_PTarget*<br/>
Ein Zeiger auf das neu verknüpften Ziel.

##  <a name="propagate_message"></a> propagate_message

Übergibt asynchron eine Nachricht von einem `ISource` Block, um diese `single_assignment` Meldungsblock. Wird aufgerufen, indem die `propagate` Methode, wenn Sie von einem Quellblock aufgerufen.

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

Stellen die `message` `_PMessage` in diesem `single_assignment` Block messaging und bietet sie alle verknüpften Ziele.

```
virtual void propagate_to_any_targets(_Inout_opt_ message<T>* _PMessage);
```

### <a name="parameters"></a>Parameter

*_PMessage*<br/>
Ein Zeiger auf eine `message` , das von diesem `single_assignment` -Meldungsblock Besitzrechte übernommen hat.

##  <a name="release_message"></a> release_message

Gibt die nachrichtenreservierung einer vorherigen frei.

```
virtual void release_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parameter

*_MsgId*<br/>
Die `runtime_object_identity` von der `message` Objekt freigegeben wird.

##  <a name="reserve_message"></a> reserve_message

Reserviert eine Meldung, die zuvor von diesem angebotenen `single_assignment` Meldungsblock.

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

##  <a name="send_message"></a> send_message

Übergibt synchron eine Nachricht von einem `ISource` Block, um diese `single_assignment` Meldungsblock. Wird aufgerufen, indem die `send` Methode, wenn Sie von einem Quellblock aufgerufen.

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

##  <a name="ctor"></a> single_assignment

Erstellt einen `single_assignment` -Meldungsblock.

```
single_assignment();

single_assignment(
    filter_method const& _Filter);

single_assignment(
    Scheduler& _PScheduler);

single_assignment(
    Scheduler& _PScheduler,
    filter_method const& _Filter);

single_assignment(
    ScheduleGroup& _PScheduleGroup);

single_assignment(
    ScheduleGroup& _PScheduleGroup,
    filter_method const& _Filter);
```

### <a name="parameters"></a>Parameter

*_Filter*<br/>
Eine Filterfunktion, die bestimmt, ob angebotene Nachrichten akzeptiert werden sollen.

*_PScheduler*<br/>
Das `Scheduler` -Objekt, in dem die Weiterleitungsaufgabe für den `single_assignment` -Meldungsblock geplant ist.

*_PScheduleGroup*<br/>
Das `ScheduleGroup` -Objekt, in dem die Weiterleitungsaufgabe für den `single_assignment` -Meldungsblock geplant ist. Das verwendete `Scheduler` -Objekt wird von der Planungsgruppe impliziert.

### <a name="remarks"></a>Hinweise

Die Runtime verwendet das Standardplanungsprogramm, wenn Sie den `_PScheduler` -Parameter oder den `_PScheduleGroup` -Parameter nicht angeben.

Der Typ `filter_method` ist ein Funktionselement mit Signatur `bool (T const &)` die aufgerufen wird, von diesem `single_assignment` Meldungsblock, um zu bestimmen, und zwar unabhängig davon, ob sie eine angebotene Nachricht akzeptiert werden sollte.

##  <a name="dtor"></a> ~single_assignment

Zerstört die `single_assignment` Meldungsblock.

```
~single_assignment();
```

##  <a name="value"></a> Wert

Ruft einen Verweis auf die aktuelle Nutzlast der Nachricht gespeichert werden, der `single_assignment` Meldungsblock.

```
T const& value();
```

### <a name="return-value"></a>Rückgabewert

Die Nutzlast der gespeicherten Meldung.

### <a name="remarks"></a>Hinweise

Diese Methode wartet, bis eine Meldung eintrifft, wenn derzeit keine Meldung in gespeichert ist die `single_assignment` Meldungsblock.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[overwrite_buffer-Klasse](overwrite-buffer-class.md)<br/>
[unbounded_buffer-Klasse](unbounded-buffer-class.md)
