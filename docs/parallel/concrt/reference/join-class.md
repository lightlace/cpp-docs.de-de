---
title: Join-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- join
- AGENTS/concurrency::join
- AGENTS/concurrency::join::join
- AGENTS/concurrency::join::accept_message
- AGENTS/concurrency::join::consume_message
- AGENTS/concurrency::join::link_target_notification
- AGENTS/concurrency::join::propagate_message
- AGENTS/concurrency::join::propagate_to_any_targets
- AGENTS/concurrency::join::release_message
- AGENTS/concurrency::join::reserve_message
- AGENTS/concurrency::join::resume_propagation
dev_langs:
- C++
helpviewer_keywords:
- join class
ms.assetid: d2217119-70a1-40b6-809f-c1c13a571c3f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c960e73604a915dbb15c0efac958dc229c16b3b1
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46379527"
---
# <a name="join-class"></a>join-Klasse

Ein `join`-Meldungsblock ist ein geordneter `propagator_block` mit mehreren Quellen und einem einzelnen Ziel, der Meldungen vom Typ `T` aus allen Quellen kombiniert.

## <a name="syntax"></a>Syntax

```
template<class T,
    join_type _Jtype = non_greedy>
class join : public propagator_block<single_link_registry<ITarget<std::vector<T>>>,
    multi_link_registry<ISource<T>>>;
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Der Nutzlasttyp der Nachrichten hinzugefügt und vom Block weitergegeben.

*_Jtype*<br/>
Die Art der `join` Blocks, entweder `greedy` oder `non_greedy`

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[join](#ctor)|Überladen. Erstellt eine `join` Meldungsblock.|
|[~ join-Destruktor](#dtor)|Zerstört die `join` Block.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[accept_message](#accept_message)|Akzeptiert eine Meldung, die von diesem angeboten wurde `join` Meldungsblock, überträgt den Besitz an den Aufrufer.|
|[consume_message](#consume_message)|Nimmt eine Meldung, die zuvor von Angeboten die `join` -Meldungsblock und vom Ziel übertragen des Besitzes an den Aufrufer reserviert.|
|[link_target_notification](#link_target_notification)|Ein Rückruf, der benachrichtigt, dass ein neues Ziel mit dieser verknüpft wurde `join` Meldungsblock.|
|[propagate_message](#propagate_message)|Übergibt asynchron eine Nachricht von einem `ISource` Block, um diese `join` Meldungsblock. Wird aufgerufen, indem die `propagate` Methode, wenn Sie von einem Quellblock aufgerufen.|
|[propagate_to_any_targets](#propagate_to_any_targets)|Erstellt eine Meldung angezeigt, die eine eingehenden Nachricht aus der jeweiligen Quelle enthält, wenn sie alle eine Nachricht weitergegeben wurden. Diese Ausgabenachricht sendet auf jedes der zugehörigen Ziele.|
|[release_message](#release_message)|Gibt die nachrichtenreservierung einer vorherigen frei. (Überschreibt [source_block:: release_message](source-block-class.md#release_message).)|
|[reserve_message](#reserve_message)|Reserviert eine Meldung, die zuvor von diesem angebotenen `join` Meldungsblock. (Überschreibt [source_block:: reserve_message](source-block-class.md#reserve_message).)|
|[resume_propagation](#resume_propagation)|Weitergabe fortgesetzt, nachdem eine Reservierung freigegeben wurde. (Überschreibt [source_block:: resume_propagation](source-block-class.md#resume_propagation).)|

## <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [asynchrone Meldungsblöcke](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[ISource](isource-class.md)

[ITarget](itarget-class.md)

[source_block](source-block-class.md)

[propagator_block](propagator-block-class.md)

`join`

## <a name="requirements"></a>Anforderungen

**Header:** agents.h

**Namespace:** Parallelität

##  <a name="accept_message"></a> accept_message

Akzeptiert eine Meldung, die von diesem angeboten wurde `join` Meldungsblock, überträgt den Besitz an den Aufrufer.

```
virtual message<_OutputType>* accept_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parameter

*_MsgId*<br/>
Die `runtime_object_identity` von den angebotenen `message` Objekt.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die `message` Objekt, mit der Aufrufer jetzt besitzt.

##  <a name="consume_message"></a> consume_message

Nimmt eine Meldung, die zuvor von Angeboten die `join` -Meldungsblock und vom Ziel übertragen des Besitzes an den Aufrufer reserviert.

```
virtual message<_OutputType>* consume_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parameter

*_MsgId*<br/>
Die `runtime_object_identity` von der `message` -Objekt verarbeitet.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die `message` Objekt, mit der Aufrufer jetzt besitzt.

### <a name="remarks"></a>Hinweise

Ähnlich wie `accept`, steht aber immer durch einen Aufruf von ist `reserve`.

##  <a name="ctor"></a> Join

Erstellt eine `join` Meldungsblock.

```
join(
    size_t _NumInputs);

join(
    size_t _NumInputs,
    filter_method const& _Filter);

join(
    Scheduler& _PScheduler,
    size_t _NumInputs);

join(
    Scheduler& _PScheduler,
    size_t _NumInputs,
    filter_method const& _Filter);

join(
    ScheduleGroup& _PScheduleGroup,
    size_t _NumInputs);

join(
    ScheduleGroup& _PScheduleGroup,
    size_t _NumInputs,
    filter_method const& _Filter);
```

### <a name="parameters"></a>Parameter

*_NumInputs*<br/>
Die Anzahl von Eingaben, die diesem `join` Block werden darf.

*_Filter*<br/>
Eine Filterfunktion, die bestimmt, ob angebotene Nachrichten akzeptiert werden sollen.

*_PScheduler*<br/>
Das `Scheduler`-Objekt, in dem die Weiterleitungsaufgabe für den `join`-Meldungsblock geplant ist.

*_PScheduleGroup*<br/>
Das `ScheduleGroup`-Objekt, in dem die Weiterleitungsaufgabe für den `join`-Meldungsblock geplant ist. Das verwendete `Scheduler` -Objekt wird von der Planungsgruppe impliziert.

### <a name="remarks"></a>Hinweise

Die Runtime verwendet das Standardplanungsprogramm, wenn Sie den `_PScheduler` -Parameter oder den `_PScheduleGroup` -Parameter nicht angeben.

Der Typ `filter_method` ist ein Funktionselement mit Signatur `bool (T const &)` die aufgerufen wird, von diesem `join` Meldungsblock, um zu bestimmen, und zwar unabhängig davon, ob sie eine angebotene Nachricht akzeptiert werden sollte.

##  <a name="dtor"></a> ~ Join

Zerstört die `join` Block.

```
~join();
```

##  <a name="link_target_notification"></a> link_target_notification

Ein Rückruf, der benachrichtigt, dass ein neues Ziel mit dieser verknüpft wurde `join` Meldungsblock.

```
virtual void link_target_notification(_Inout_ ITarget<std::vector<T>> *);
```

##  <a name="propagate_message"></a> propagate_message

Übergibt asynchron eine Nachricht von einem `ISource` Block, um diese `join` Meldungsblock. Wird aufgerufen, indem die `propagate` Methode, wenn Sie von einem Quellblock aufgerufen.

```
message_status propagate_message(
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

Erstellt eine Meldung angezeigt, die eine eingehenden Nachricht aus der jeweiligen Quelle enthält, wenn sie alle eine Nachricht weitergegeben wurden. Diese Ausgabenachricht sendet auf jedes der zugehörigen Ziele.

```
void propagate_to_any_targets(_Inout_opt_ message<_OutputType> *);
```

##  <a name="release_message"></a> release_message

Gibt die nachrichtenreservierung einer vorherigen frei.

```
virtual void release_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parameter

*_MsgId*<br/>
Die `runtime_object_identity` von der `message` Objekt freigegeben wird.

##  <a name="reserve_message"></a> reserve_message

Reserviert eine Meldung, die zuvor von diesem angebotenen `join` Meldungsblock.

```
virtual bool reserve_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parameter

*_MsgId*<br/>
Die `runtime_object_identity` von den angebotenen `message` Objekt.

### <a name="return-value"></a>Rückgabewert

`true` Wenn die Nachricht erfolgreich reserviert wurde, `false` andernfalls.

### <a name="remarks"></a>Hinweise

Nach dem `reserve` aufgerufen wird, wenn zurückgegeben `true`, entweder `consume` oder `release` aufgerufen werden, um zu übernehmen oder den Besitz der Nachricht.

##  <a name="resume_propagation"></a> resume_propagation

Weitergabe fortgesetzt, nachdem eine Reservierung freigegeben wurde.

```
virtual void resume_propagation();
```

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[choice-Klasse](choice-class.md)<br/>
[multitype_join-Klasse](multitype-join-class.md)
