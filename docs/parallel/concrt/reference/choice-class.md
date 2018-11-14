---
title: choice-Klasse
ms.date: 11/04/2016
f1_keywords:
- choice
- AGENTS/concurrency::choice
- AGENTS/concurrency::choice::choice
- AGENTS/concurrency::choice::accept
- AGENTS/concurrency::choice::acquire_ref
- AGENTS/concurrency::choice::consume
- AGENTS/concurrency::choice::has_value
- AGENTS/concurrency::choice::index
- AGENTS/concurrency::choice::link_target
- AGENTS/concurrency::choice::release
- AGENTS/concurrency::choice::release_ref
- AGENTS/concurrency::choice::reserve
- AGENTS/concurrency::choice::unlink_target
- AGENTS/concurrency::choice::unlink_targets
- AGENTS/concurrency::choice::value
helpviewer_keywords:
- choice class
ms.assetid: 4157a539-d5c2-4161-b1ab-536ce2888397
ms.openlocfilehash: 60b09b674bec58a7d35a9a37d9a8f4c40d8cd522
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2018
ms.locfileid: "51522726"
---
# <a name="choice-class"></a>choice-Klasse

Ein `choice`-Meldungsblock ist ein Block mit mehreren Quellen und einem einzelnen Ziel, der eine Kontrollflussinteraktion zwischen mehreren Quellen darstellt. Der Auswahlblock wartet, bis eine von mehreren Quellen eine Meldung erzeugt, und gibt den Index der Quelle, von der die Meldung erzeugt wurde, weiter.

## <a name="syntax"></a>Syntax

```
template<
    class T
>
class choice: public ISource<size_t>;
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Ein `tuple`-basierten Typ, der die Nutzlast der Eingabequellen darstellt.

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|Beschreibung|
|----------|-----------------|
|`type`|Ein Typalias für `T`.|

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[Auswahl](#ctor)|Überladen. Erstellt einen `choice` -Meldungsblock.|
|[~ Choice-Destruktor](#dtor)|Zerstört die `choice` Meldungsblock.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[accept](#accept)|Akzeptiert eine Meldung, die von diesem angeboten wurde `choice` Block übertragen des Besitzes an den Aufrufer.|
|[acquire_ref](#acquire_ref)|Eine Verweisanzahl dazu `choice` Meldungsblock, um löschen zu verhindern.|
|[Nutzen](#consume)|Nimmt eine Meldung, die zuvor von diesem angebotenen `choice` -Meldungsblock und erfolgreich vom Ziel übertragen des Besitzes an den Aufrufer reserviert.|
|[has_value](#has_value)|Überprüft, ob dies `choice` Meldungsblock noch mit einem Wert initialisiert wurde.|
|[index](#index)|Gibt einen Index in die `tuple` , die vom ausgewählten Element darstellt, die `choice` Meldungsblock.|
|[link_target](#link_target)|Verknüpft einen Zielblock mit diesem `choice` Meldungsblock.|
|[release](#release)|Gibt die nachrichtenreservierung einer vorherigen erfolgreichen frei.|
|[release_ref](#release_ref)|Gibt einen Verweiszähler für diese `choice` Meldungsblock.|
|[reserve](#reserve)|Reserviert eine Meldung, die zuvor von diesem angebotenen `choice` Meldungsblock.|
|[unlink_target](#unlink_target)|Hebt die Verknüpfung mit einem Zielblock und dadurch `choice` Meldungsblock.|
|[unlink_targets](#unlink_targets)|Hebt die Verknüpfung alle Ziele aus diesem `choice` Meldungsblock. (Überschreibt [ISource:: Unlink_targets](isource-class.md#unlink_targets).)|
|[Wert](#value)|Ruft die Meldung ab, dessen Index, indem ausgewählt wurde, die `choice` Meldungsblock.|

## <a name="remarks"></a>Hinweise

Der Auswahlblock wird sichergestellt, dass nur eine der eingehenden Nachrichten verwendet wird.

Weitere Informationen finden Sie unter [asynchrone Meldungsblöcke](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[ISource](isource-class.md)

`choice`

## <a name="requirements"></a>Anforderungen

**Header:** agents.h

**Namespace:** Parallelität

##  <a name="accept"></a> Akzeptieren

Akzeptiert eine Meldung, die von diesem angeboten wurde `choice` Block übertragen des Besitzes an den Aufrufer.

```
virtual message<size_t>* accept(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>Parameter

*_MsgId*<br/>
Die `runtime_object_identity` von den angebotenen `message` Objekt.

*_PTarget*<br/>
Ein Zeiger auf den Zielblock, der aufgerufen wird, wird die `accept` Methode.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die Meldung, der der Aufrufer jetzt besitzt.

##  <a name="acquire_ref"></a> acquire_ref

Eine Verweisanzahl dazu `choice` Meldungsblock, um löschen zu verhindern.

```
virtual void acquire_ref(_Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>Parameter

*_PTarget*<br/>
Ein Zeiger auf den Zielblock, der diese Methode aufruft.

### <a name="remarks"></a>Hinweise

Diese Methode wird aufgerufen, indem ein `ITarget` -Objekt, das mit der Quelle während der zu verknüpfenden der `link_target` Methode.

##  <a name="ctor"></a> Auswahl

Erstellt einen `choice` -Meldungsblock.

```
explicit choice(
    T _Tuple);

choice(
    Scheduler& _PScheduler,
    T _Tuple);

choice(
    ScheduleGroup& _PScheduleGroup,
    T _Tuple);

choice(
    choice&& _Choice);
```

### <a name="parameters"></a>Parameter

*_Tuple*<br/>
Ein `tuple` von Quellen für die Auswahl.

*_PScheduler*<br/>
Das `Scheduler` -Objekt, in dem die Weiterleitungsaufgabe für den `choice` -Meldungsblock geplant ist.

*_PScheduleGroup*<br/>
Das `ScheduleGroup` -Objekt, in dem die Weiterleitungsaufgabe für den `choice` -Meldungsblock geplant ist. Das verwendete `Scheduler` -Objekt wird von der Planungsgruppe impliziert.

*_Choice*<br/>
Ein `choice` -Meldungsblock, aus dem kopiert werden soll. Beachten Sie, dass das ursprüngliche Objekt verwaist ist, sodass dies ein Bewegungskonstruktor ist.

### <a name="remarks"></a>Hinweise

Die Runtime verwendet das Standardplanungsprogramm, wenn Sie den `_PScheduler` -Parameter oder den `_PScheduleGroup` -Parameter nicht angeben.

Bewegungskonstruktion wird bei einer aktiven Sperre nicht ausgeführt, d. h., der Benutzer muss sicherstellen, dass zum Zeitpunkt der Bewegung keine einfachen Aufgaben aktiv sind. Andernfalls können zahlreiche Wettläufe auftreten, wodurch Ausnahmen oder inkonsistente Zuständen verursacht werden.

##  <a name="dtor"></a> ~ Choice

Zerstört die `choice` Meldungsblock.

```
~choice();
```

##  <a name="consume"></a> Nutzen

Nimmt eine Meldung, die zuvor von diesem angebotenen `choice` -Meldungsblock und erfolgreich vom Ziel übertragen des Besitzes an den Aufrufer reserviert.

```
virtual message<size_t>* consume(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>Parameter

*_MsgId*<br/>
Die `runtime_object_identity` des reservierten `message` Objekt.

*_PTarget*<br/>
Ein Zeiger auf den Zielblock, der aufgerufen wird, wird die `consume` Methode.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die `message` Objekt, mit der Aufrufer jetzt besitzt.

### <a name="remarks"></a>Hinweise

Die `consume` -Methode ist vergleichbar mit `accept`, jedoch immer durch einen Aufruf von vorangestellt werden muss `reserve` zurückgegebenen **"true"**.

##  <a name="has_value"></a> has_value

Überprüft, ob dies `choice` Meldungsblock noch mit einem Wert initialisiert wurde.

```
bool has_value() const;
```

### <a name="return-value"></a>Rückgabewert

**"true"** , wenn der Block einen Wert erhalten hat **"false"** andernfalls.

##  <a name="index"></a> Index

Gibt einen Index in die `tuple` , die vom ausgewählten Element darstellt, die `choice` Meldungsblock.

```
size_t index();
```

### <a name="return-value"></a>Rückgabewert

Der Message-Index.

### <a name="remarks"></a>Hinweise

Die Nutzlast der Nachricht kann extrahiert werden, mithilfe der `get` Methode.

##  <a name="link_target"></a> link_target

Verknüpft einen Zielblock mit diesem `choice` Meldungsblock.

```
virtual void link_target(_Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>Parameter

*_PTarget*<br/>
Ein Zeiger auf ein `ITarget` Block, um Sie zu diesem link `choice` Meldungsblock.

##  <a name="release"></a> Version

Gibt die nachrichtenreservierung einer vorherigen erfolgreichen frei.

```
virtual void release(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>Parameter

*_MsgId*<br/>
Die `runtime_object_identity` von der `message` Objekt freigegeben wird.

*_PTarget*<br/>
Ein Zeiger auf den Zielblock, der aufgerufen wird, wird die `release` Methode.

##  <a name="release_ref"></a> release_ref

Gibt einen Verweiszähler für diese `choice` Meldungsblock.

```
virtual void release_ref(_Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>Parameter

*_PTarget*<br/>
Ein Zeiger auf den Zielblock, der diese Methode aufruft.

### <a name="remarks"></a>Hinweise

Diese Methode wird aufgerufen, indem ein `ITarget` -Objekt, das von dieser Quelle aufgehoben wird, ist. Der Quellblock darf für den Zielblock reservierten Ressourcen freizugeben.

##  <a name="reserve"></a> Hostreserven

Reserviert eine Meldung, die zuvor von diesem angebotenen `choice` Meldungsblock.

```
virtual bool reserve(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>Parameter

*_MsgId*<br/>
Die `runtime_object_identity` von der `message` Objekt reserviert wird.

*_PTarget*<br/>
Ein Zeiger auf den Zielblock, der aufgerufen wird, wird die `reserve` Methode.

### <a name="return-value"></a>Rückgabewert

**"true"** , wenn die Nachricht erfolgreich reserviert wurde, **"false"** andernfalls. Reservierungen können für viele Gründe, z. B. Fehler auftreten: die Nachricht wurde bereits reserviert oder von einem anderen Ziel akzeptiert wird, kann die Quelle Reservierungen verweigern und so weiter.

### <a name="remarks"></a>Hinweise

Nach dem Aufruf von `reserve`, wenn dies gelingt, müssen Sie entweder Aufrufen `consume` oder `release` zum Erstellen oder den Besitz der Nachricht bzw. aufgeben.

##  <a name="unlink_target"></a> unlink_target

Hebt die Verknüpfung mit einem Zielblock und dadurch `choice` Meldungsblock.

```
virtual void unlink_target(_Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>Parameter

*_PTarget*<br/>
Ein Zeiger auf ein `ITarget` Block, um diese aufheben `choice` Meldungsblock.

##  <a name="unlink_targets"></a> unlink_targets

Hebt die Verknüpfung alle Ziele aus diesem `choice` Meldungsblock.

```
virtual void unlink_targets();
```

### <a name="remarks"></a>Hinweise

Diese Methode muss nicht von der Destruktor aufgerufen werden, da der Destruktor für die interne `single_assignment` Block ordnungsgemäß löst.

##  <a name="value"></a> Wert

Ruft die Meldung ab, dessen Index, indem ausgewählt wurde, die `choice` Meldungsblock.

```
template <
    typename _Payload_type
>
_Payload_type const& value();
```

### <a name="parameters"></a>Parameter

*_Payload_type*<br/>
Der Typ der Nutzlast der Nachricht.

### <a name="return-value"></a>Rückgabewert

Die Nutzlast der Nachricht.

### <a name="remarks"></a>Hinweise

Da eine `choice` -Meldungsblock kann verschiedene Nutzlasttypen Eingaben annehmen, müssen Sie den Typ der Nutzlast beim Abruf angeben. Sie können bestimmen, den Typ basierend auf dem Ergebnis der `index` Methode.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[join-Klasse](join-class.md)<br/>
[single_assignment-Klasse](single-assignment-class.md)
