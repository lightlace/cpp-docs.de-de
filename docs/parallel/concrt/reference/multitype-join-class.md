---
title: multitype_join-Klasse
ms.date: 11/04/2016
f1_keywords:
- multitype_join
- AGENTS/concurrency::multitype_join
- AGENTS/concurrency::multitype_join::multitype_join
- AGENTS/concurrency::multitype_join::accept
- AGENTS/concurrency::multitype_join::acquire_ref
- AGENTS/concurrency::multitype_join::consume
- AGENTS/concurrency::multitype_join::link_target
- AGENTS/concurrency::multitype_join::release
- AGENTS/concurrency::multitype_join::release_ref
- AGENTS/concurrency::multitype_join::reserve
- AGENTS/concurrency::multitype_join::unlink_target
- AGENTS/concurrency::multitype_join::unlink_targets
helpviewer_keywords:
- multitype_join class
ms.assetid: 236e87a0-4867-49fd-869a-bef4010e49a7
ms.openlocfilehash: 4214c43fa0d0ab8fdd29ed54738c19f72a07267a
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77138952"
---
# <a name="multitype_join-class"></a>multitype_join-Klasse

Ein `multitype_join`-Meldungsblock ist ein Block mit mehreren Quellen und einem einzelnen Ziel, der Meldungen verschiedener Typen aus allen Quellen kombiniert und dem Ziel ein Tupel der kombinierten Meldungen bereitstellt.

## <a name="syntax"></a>Syntax

```cpp
template<
    typename T,
    join_type _Jtype = non_greedy
>
class multitype_join: public ISource<typename _Unwrap<T>::type>;
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der `tuple` Nutz Lasttyp der Nachrichten, die dem-Block hinzugefügt und weitergegeben werden.

*_Jtype*<br/>
Die Art der `join` blockieren, ist entweder `greedy` oder `non_greedy`

## <a name="members"></a>Members

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|BESCHREIBUNG|
|----------|-----------------|
|`type`|Ein Typalias für `T`.|

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[multitype_join](#ctor)|Ist überladen. Erstellt einen `multitype_join` -Meldungsblock.|
|[~ multitype_join-Dekonstruktor](#dtor)|Zerstört den `multitype_join`-Messaging-Block.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|BESCHREIBUNG|
|----------|-----------------|
|[erst](#accept)|Akzeptiert eine Meldung, die von diesem `multitype_join` Block angeboten wurde, und überträgt den Besitz an den Aufrufer.|
|[acquire_ref](#acquire_ref)|Erhält einen Verweis Zähler für diesen `multitype_join` Messaging Block, um das Löschen zu verhindern.|
|[Nutzen](#consume)|Verarbeitet eine Meldung, die zuvor vom `multitype_join` Messaging-Block bereitgestellt und vom Ziel erfolgreich reserviert wurde, und überträgt den Besitz an den Aufrufer.|
|[link_target](#link_target)|Verknüpft einen Zielblock mit diesem `multitype_join`-Messaging-Block.|
|[release](#release)|Gibt eine vorherige erfolgreiche Nachrichten Reservierung frei.|
|[release_ref](#release_ref)|Gibt einen Verweis Zähler für diesen `multiple_join` Messaging Block frei.|
|[reserve](#reserve)|Reserviert eine Meldung, die zuvor von diesem `multitype_join`-Nachrichtenblock angeboten wurde.|
|[unlink_target](#unlink_target)|Entfernt einen Zielblock von diesem `multitype_join`-Messaging-Block.|
|[unlink_targets](#unlink_targets)|Entfernt die Verknüpfung aller Ziele von diesem `multitype_join`-Messaging-Block. (Überschreibt [ISource:: unlink_targets](isource-class.md#unlink_targets).)|

## <a name="remarks"></a>Bemerkungen

Weitere Informationen finden Sie unter [asynchrone Nachrichten Blöcke](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[ISource](isource-class.md)

`multitype_join`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** agents.h

**Namespace:** Parallelität

## <a name="accept"></a>erst

Akzeptiert eine Meldung, die von diesem `multitype_join` Block angeboten wurde, und überträgt den Besitz an den Aufrufer.

```cpp
virtual message<_Destination_type>* accept(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>Parameter

*_MsgId*<br/>
Die `runtime_object_identity` des angebotenen `message` Objekts.

*_PTarget*<br/>
Ein Zeiger auf den Zielblock, der die `accept` Methode aufrufen.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die Nachricht, für die der Aufrufer nun den Besitz hat.

## <a name="acquire_ref"></a>acquire_ref

Erhält einen Verweis Zähler für diesen `multitype_join` Messaging Block, um das Löschen zu verhindern.

```cpp
virtual void acquire_ref(_Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>Parameter

*_PTarget*<br/>
Ein Zeiger auf den Zielblock, der diese Methode aufgerufen hat.

### <a name="remarks"></a>Bemerkungen

Diese Methode wird von einem `ITarget` Objekt aufgerufen, das während der `link_target` Methode mit dieser Quelle verknüpft wird.

## <a name="consume"></a>Verzehr

Verarbeitet eine Meldung, die zuvor vom `multitype_join` Messaging-Block bereitgestellt und vom Ziel erfolgreich reserviert wurde, und überträgt den Besitz an den Aufrufer.

```cpp
virtual message<_Destination_type>* consume(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>Parameter

*_MsgId*<br/>
Die `runtime_object_identity` des reservierten `message` Objekts.

*_PTarget*<br/>
Ein Zeiger auf den Zielblock, der die `consume` Methode aufrufen.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das `message` Objekt, für das der Aufrufer nun den Besitz hat.

### <a name="remarks"></a>Bemerkungen

Die `consume`-Methode ähnelt `accept`, aber muss immer ein `reserve` aufgerufen werden, der " **true**" zurückgegeben hat.

## <a name="link_target"></a>link_target

Verknüpft einen Zielblock mit diesem `multitype_join`-Messaging-Block.

```cpp
virtual void link_target(_Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>Parameter

*_PTarget*<br/>
Ein Zeiger auf einen `ITarget` Block, der mit diesem `multitype_join` Messaging Block verknüpft werden soll.

## <a name="ctor"></a>multitype_join

Erstellt einen `multitype_join` -Meldungsblock.

```cpp
explicit multitype_join(
    T _Tuple);

multitype_join(
    Scheduler& _PScheduler,
    T _Tuple);

multitype_join(
    ScheduleGroup& _PScheduleGroup,
    T _Tuple);

multitype_join(
    multitype_join&& _Join);
```

### <a name="parameters"></a>Parameter

*_Tuple*<br/>
Ein `tuple` von Quellen für diesen `multitype_join` -Meldungsblock.

*_PScheduler*<br/>
Das `Scheduler` -Objekt, in dem die Weiterleitungsaufgabe für den `multitype_join` -Meldungsblock geplant ist.

*_PScheduleGroup*<br/>
Das `ScheduleGroup` -Objekt, in dem die Weiterleitungsaufgabe für den `multitype_join` -Meldungsblock geplant ist. Das verwendete `Scheduler` -Objekt wird von der Planungsgruppe impliziert.

*_Join*<br/>
Ein `multitype_join` -Meldungsblock, aus dem kopiert werden soll. Beachten Sie, dass das ursprüngliche Objekt verwaist ist, sodass dies ein Bewegungskonstruktor ist.

### <a name="remarks"></a>Bemerkungen

Die Runtime verwendet das Standardplanungsprogramm, wenn Sie den `_PScheduler` -Parameter oder den `_PScheduleGroup` -Parameter nicht angeben.

Bewegungskonstruktion wird bei einer aktiven Sperre nicht ausgeführt, d. h., der Benutzer muss sicherstellen, dass zum Zeitpunkt der Bewegung keine einfachen Aufgaben aktiv sind. Andernfalls können zahlreiche Wettläufe auftreten, wodurch Ausnahmen oder inkonsistente Zuständen verursacht werden.

## <a name="dtor"></a>~ multitype_join

Zerstört den `multitype_join`-Messaging-Block.

```cpp
~multitype_join();
```

## <a name="release"></a>Abgabe

Gibt eine vorherige erfolgreiche Nachrichten Reservierung frei.

```cpp
virtual void release(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>Parameter

*_MsgId*<br/>
Die `runtime_object_identity` des `message` Objekts, das freigegeben wird.

*_PTarget*<br/>
Ein Zeiger auf den Zielblock, der die `release` Methode aufrufen.

## <a name="release_ref"></a>release_ref

Gibt einen Verweis Zähler für diesen `multiple_join` Messaging Block frei.

```cpp
virtual void release_ref(_Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>Parameter

*_PTarget*<br/>
Ein Zeiger auf den Zielblock, der diese Methode aufgerufen hat.

### <a name="remarks"></a>Bemerkungen

Diese Methode wird von einem `ITarget` Objekt aufgerufen, das von dieser Quelle entfernt wird. Der Quell Block darf alle für den Zielblock reservierten Ressourcen freigeben.

## <a name="reserve"></a>Schutz

Reserviert eine Meldung, die zuvor von diesem `multitype_join`-Nachrichtenblock angeboten wurde.

```cpp
virtual bool reserve(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>Parameter

*_MsgId*<br/>
Die `runtime_object_identity` des reservierten `message` Objekts.

*_PTarget*<br/>
Ein Zeiger auf den Zielblock, der die `reserve` Methode aufrufen.

### <a name="return-value"></a>Rückgabewert

`true`, wenn die Nachricht erfolgreich reserviert wurde, andernfalls `false`. Reservierungen können aus vielen Gründen fehlschlagen, z.b.: die Nachricht wurde bereits von einem anderen Ziel reserviert oder akzeptiert, die Quelle könnte Reservierungen ablehnen usw.

### <a name="remarks"></a>Bemerkungen

Nachdem Sie `reserve`aufgerufen haben, müssen Sie bei erfolgreicher Ausführung entweder `consume` oder `release` abrufen, um die Nachricht bzw. den Besitz der Nachricht zu übernehmen.

## <a name="unlink_target"></a>unlink_target

Entfernt einen Zielblock von diesem `multitype_join`-Messaging-Block.

```cpp
virtual void unlink_target(_Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>Parameter

*_PTarget*<br/>
Ein Zeiger auf einen `ITarget` Block, um die Verknüpfung mit diesem `multitype_join` Messaging Block aufzulösen.

## <a name="unlink_targets"></a>unlink_targets

Entfernt die Verknüpfung aller Ziele von diesem `multitype_join`-Messaging-Block.

```cpp
virtual void unlink_targets();
```

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[choice-Klasse](choice-class.md)<br/>
[join-Klasse](join-class.md)
