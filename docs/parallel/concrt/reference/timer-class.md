---
title: timer-Klasse
ms.date: 11/04/2016
f1_keywords:
- timer
- AGENTS/concurrency::timer
- AGENTS/concurrency::timer::timer
- AGENTS/concurrency::timer::pause
- AGENTS/concurrency::timer::start
- AGENTS/concurrency::timer::stop
- AGENTS/concurrency::timer::accept_message
- AGENTS/concurrency::timer::consume_message
- AGENTS/concurrency::timer::link_target_notification
- AGENTS/concurrency::timer::propagate_to_any_targets
- AGENTS/concurrency::timer::release_message
- AGENTS/concurrency::timer::reserve_message
- AGENTS/concurrency::timer::resume_propagation
helpviewer_keywords:
- timer class
ms.assetid: 4f4dea51-de9f-40f9-93f5-dd724c567b49
ms.openlocfilehash: c39afc565a7ec775600b9c9fb6f15a89acdef57b
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142529"
---
# <a name="timer-class"></a>timer-Klasse

Ein `timer`-Meldungsblock ist ein `source_block` mit einem einzelnen Ziel, der nach Ablauf einer bestimmten Zeitspanne oder in bestimmten Intervallen eine Meldung an sein Ziel senden kann.

## <a name="syntax"></a>Syntax

```cpp
template<class T>
class timer : public Concurrency::details::_Timer, public source_block<single_link_registry<ITarget<T>>>;
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der Nutz Lasttyp der Ausgabemeldungen dieses Blocks.

## <a name="members"></a>Members

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[Messer](#ctor)|Ist überladen. Erstellt einen `timer` Messaging Block, der eine bestimmte Meldung nach einem angegebenen Intervall auslöst.|
|[~ Timer-Dekonstruktor](#dtor)|Zerstört einen `timer`-Messaging-Block.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|BESCHREIBUNG|
|----------|-----------------|
|[Brechung](#pause)|Hält den `timer` Messaging-Block an. Wenn es sich um einen wiederholten `timer` Messaging Block handelt, kann er mit einem nachfolgenden `start()`-Befehl neu gestartet werden. Bei nicht wiederholenden Timern hat dies denselben Effekt wie ein `stop`-Aufruf.|
|[start](#start)|Startet den `timer` Messaging-Block. Die angegebene Anzahl von Millisekunden nach dem Aufruf von wird der angegebene Wert als `message`weitergegeben.|
|[stop](#stop)|Hält den `timer` Messaging-Block an.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|BESCHREIBUNG|
|----------|-----------------|
|[accept_message](#accept_message)|Akzeptiert eine Meldung, die von diesem `timer` Messaging Block angeboten wurde, und überträgt den Besitz an den Aufrufer.|
|[consume_message](#consume_message)|Verarbeitet eine Meldung, die zuvor vom-`timer` angeboten und vom Ziel reserviert wurde, und überträgt den Besitz an den Aufrufer.|
|[link_target_notification](#link_target_notification)|Ein Rückruf, der benachrichtigt, dass ein neues Ziel mit diesem `timer`-Nachrichtenblock verknüpft wurde.|
|[propagate_to_any_targets](#propagate_to_any_targets)|Versucht, die Meldung, die vom `timer`-Block erzeugt wurde, für alle verknüpften Ziele anzubieten.|
|[release_message](#release_message)|Gibt eine vorherige Nachrichten Reservierung frei. (Überschreibt [source_block:: release_message](source-block-class.md#release_message).)|
|[reserve_message](#reserve_message)|Reserviert eine Meldung, die zuvor von diesem `timer`-Nachrichtenblock angeboten wurde. (Überschreibt [source_block:: reserve_message](source-block-class.md#reserve_message).)|
|[resume_propagation](#resume_propagation)|Setzt die Verteilung fort, nachdem eine Reservierung freigegeben wurde. (Überschreibt [source_block:: resume_propagation](source-block-class.md#resume_propagation).)|

## <a name="remarks"></a>Bemerkungen

Weitere Informationen finden Sie unter [asynchrone Nachrichten Blöcke](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[ISource](isource-class.md)

[source_block](source-block-class.md)

`timer`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** agents.h

**Namespace:** Parallelität

## <a name="accept_message"></a>accept_message

Akzeptiert eine Meldung, die von diesem `timer` Messaging Block angeboten wurde, und überträgt den Besitz an den Aufrufer.

```cpp
virtual message<T>* accept_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parameter

*_MsgId*<br/>
Die `runtime_object_identity` des angebotenen `message` Objekts.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das `message` Objekt, für das der Aufrufer nun den Besitz hat.

## <a name="consume_message"></a>consume_message

Verarbeitet eine Meldung, die zuvor vom-`timer` angeboten und vom Ziel reserviert wurde, und überträgt den Besitz an den Aufrufer.

```cpp
virtual message<T>* consume_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parameter

*_MsgId*<br/>
Die `runtime_object_identity` des verbrauchten `message` Objekts.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das `message` Objekt, für das der Aufrufer nun den Besitz hat.

### <a name="remarks"></a>Bemerkungen

Ähnlich wie bei `accept`, dem aber immer ein Aufruf`reserve`vorangestellt ist.

## <a name="link_target_notification"></a>link_target_notification

Ein Rückruf, der benachrichtigt, dass ein neues Ziel mit diesem `timer`-Nachrichtenblock verknüpft wurde.

```cpp
virtual void link_target_notification(_Inout_ ITarget<T>* _PTarget);
```

### <a name="parameters"></a>Parameter

*_PTarget*<br/>
Ein Zeiger auf das neu verknüpfte Ziel.

## <a name="pause"></a>Brechung

Hält den `timer` Messaging-Block an. Wenn es sich um einen wiederholten `timer` Messaging Block handelt, kann er mit einem nachfolgenden `start()`-Befehl neu gestartet werden. Bei nicht wiederholenden Timern hat dies denselben Effekt wie ein `stop`-Aufruf.

```cpp
void pause();
```

## <a name="propagate_to_any_targets"></a>propagate_to_any_targets

Versucht, die Meldung, die vom `timer`-Block erzeugt wurde, für alle verknüpften Ziele anzubieten.

```cpp
virtual void propagate_to_any_targets(_Inout_opt_ message<T> *);
```

## <a name="release_message"></a>release_message

Gibt eine vorherige Nachrichten Reservierung frei.

```cpp
virtual void release_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parameter

*_MsgId*<br/>
Die `runtime_object_identity` des `message` Objekts, das freigegeben wird.

## <a name="reserve_message"></a>reserve_message

Reserviert eine Meldung, die zuvor von diesem `timer`-Nachrichtenblock angeboten wurde.

```cpp
virtual bool reserve_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>Parameter

*_MsgId*<br/>
Die `runtime_object_identity` des reservierten `message` Objekts.

### <a name="return-value"></a>Rückgabewert

**true** , wenn die Nachricht erfolgreich reserviert wurde, andernfalls **false** .

### <a name="remarks"></a>Bemerkungen

Wenn `reserve` aufgerufen wird, muss entweder `consume` oder `release` aufgerufen **werden, um**den Besitz der Nachricht zu übernehmen oder freizugeben.

## <a name="resume_propagation"></a>resume_propagation

Setzt die Verteilung fort, nachdem eine Reservierung freigegeben wurde.

```cpp
virtual void resume_propagation();
```

## <a name="start"></a>begonnen

Startet den `timer` Messaging-Block. Die angegebene Anzahl von Millisekunden nach dem Aufruf von wird der angegebene Wert als `message`weitergegeben.

```cpp
void start();
```

## <a name="stop"></a>anzuhalten

Hält den `timer` Messaging-Block an.

```cpp
void stop();
```

## <a name="ctor"></a>Messer

Erstellt einen `timer` Messaging Block, der eine bestimmte Meldung nach einem angegebenen Intervall auslöst.

```cpp
timer(
    unsigned int _Ms,
    T const& value,
    ITarget<T>* _PTarget = NULL,
    bool _Repeating = false);

timer(
    Scheduler& _Scheduler,
    unsigned int _Ms,
    T const& value,
    _Inout_opt_ ITarget<T>* _PTarget = NULL,
    bool _Repeating = false);

timer(
    ScheduleGroup& _ScheduleGroup,
    unsigned int _Ms,
    T const& value,
    _Inout_opt_ ITarget<T>* _PTarget = NULL,
    bool _Repeating = false);
```

### <a name="parameters"></a>Parameter

*_Ms*<br/>
Die Anzahl der Millisekunden, die nach dem Start des Starts ververgehen müssen, damit die angegebene Nachricht nachgelagert weitergegeben wird.

*value*<br/>
Der Wert, der nach unten weitergegeben wird, wenn der Timer abläuft.

*_PTarget*<br/>
Das Ziel, an das der Timer seine Nachricht weitergibt.

*_Repeating*<br/>
True gibt an, dass der Timer in regelmäßigen Abständen alle `_Ms` Millisekunden ausgelöst wird.

*_Scheduler*<br/>
Das `Scheduler` Objekt, in dem der propagierungs Task für den `timer` Messaging-Block geplant ist, wird geplant.

*_ScheduleGroup*<br/>
Das `ScheduleGroup` -Objekt, in dem die Weiterleitungsaufgabe für den `timer` -Meldungsblock geplant ist. Das verwendete `Scheduler` -Objekt wird von der Planungsgruppe impliziert.

### <a name="remarks"></a>Bemerkungen

Die Runtime verwendet das Standardplanungsprogramm, wenn Sie den `_Scheduler` -Parameter oder den `_ScheduleGroup` -Parameter nicht angeben.

## <a name="dtor"></a>~ Timer

Zerstört einen `timer`-Messaging-Block.

```cpp
~timer();
```

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace](concurrency-namespace.md)
