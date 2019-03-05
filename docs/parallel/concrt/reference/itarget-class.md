---
title: ITarget-Klasse
ms.date: 11/04/2016
f1_keywords:
- ITarget
- AGENTS/concurrency::ITarget
- AGENTS/concurrency::ITarget::propagate
- AGENTS/concurrency::ITarget::send
- AGENTS/concurrency::ITarget::supports_anonymous_source
- AGENTS/concurrency::ITarget::link_source
- AGENTS/concurrency::ITarget::unlink_source
- AGENTS/concurrency::ITarget::unlink_sources
helpviewer_keywords:
- ITarget class
ms.assetid: 5678db25-112a-4f72-be13-42e16b67c48b
ms.openlocfilehash: 59a0f66a0ba3b10c3307a835ff6ccaa216596538
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57295323"
---
# <a name="itarget-class"></a>ITarget-Klasse

Die `ITarget`-Klasse ist die Schnittstelle für alle Zielblöcke. Zielblöcke nehmen Meldungen auf, die von `ISource`-Blöcken angeboten werden.

## <a name="syntax"></a>Syntax

```
template<class T>
class ITarget;
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Der Datentyp der Nutzlast in den Nachrichten, die vom Zielblock akzeptiert.

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|Beschreibung|
|----------|-----------------|
|`filter_method`|Die Signatur einer Methode, die vom Block, der zurückgibt, verwendet eine `bool` um zu bestimmen, ob eine angebotene Nachricht akzeptiert werden soll.|
|`type`|Ein Typalias für `T`.|

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[~ ITarget-Destruktor](#dtor)|Zerstört das `ITarget`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[propagate](#propagate)|Ruft beim Überschreiben in einer abgeleiteten Klasse übergibt asynchron eine Meldung von einem Quellblock an diesen Zielblock.|
|[Senden](#send)|Ruft beim Überschreiben in einer abgeleiteten Klasse übergibt eine Nachricht synchron an den Zielblock.|
|[supports_anonymous_source](#supports_anonymous_source)|Ruft beim Überschreiben in einer abgeleiteten Klasse gibt "true" oder "false", je nachdem, ob die Nachrichtenblock akzeptiert Nachrichten, die angeboten, die von einer Quelle, die nicht verknüpft ist. Wenn die überschriebene Methode zurückgibt **"true"**, das Ziel kann keine angebotene Nachricht verschieben, wie die Nutzung von eine zurückgestellte Nachricht zu einem späteren Zeitpunkt die Quelle in seiner Sourse Link Registrierung identifiziert werden erforderlich sind.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[link_source](#link_source)|Ruft beim Überschreiben in einer abgeleiteten Klasse einen angegebenen Quellblock verknüpft, mit diesem `ITarget` Block.|
|[unlink_source](#unlink_source)|Ruft beim Überschreiben in einer abgeleiteten Klasse hebt die Verknüpfung mit einem angegebenen Quellblock aus diesem `ITarget` Block.|
|[unlink_sources](#unlink_sources)|Ruft beim Überschreiben in einer abgeleiteten Klasse hebt die Verknüpfung aller Quellblöcke dies `ITarget` Block.|

## <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [asynchrone Meldungsblöcke](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`ITarget`

## <a name="requirements"></a>Anforderungen

**Header:** agents.h

**Namespace:** Parallelität

##  <a name="dtor"></a> ~ITarget

Zerstört das `ITarget`-Objekt.

```
virtual ~ITarget();
```

##  <a name="link_source"></a> link_source

Ruft beim Überschreiben in einer abgeleiteten Klasse einen angegebenen Quellblock verknüpft, mit diesem `ITarget` Block.

```
virtual void link_source(_Inout_ ISource<T>* _PSource) = 0;
```

### <a name="parameters"></a>Parameter

*_PSource*<br/>
Die `ISource` blockieren, der mit dieser verknüpft `ITarget` Block.

### <a name="remarks"></a>Hinweise

Diese Funktion sollte nicht aufgerufen werden, direkt auf eine `ITarget` Block. Blöcke über miteinander verbunden werden soll die `link_target` Methode `ISource` -Blöcken, die aufgerufen werden, die `link_source` Methode auf dem entsprechenden Ziel.

##  <a name="propagate"></a> weitergeben

Ruft beim Überschreiben in einer abgeleiteten Klasse übergibt asynchron eine Meldung von einem Quellblock an diesen Zielblock.

```
virtual message_status propagate(
    _Inout_opt_ message<T>* _PMessage,
    _Inout_opt_ ISource<T>* _PSource) = 0;
```

### <a name="parameters"></a>Parameter

*_PMessage*<br/>
Ein Zeiger auf das `message`-Objekt.

*_PSource*<br/>
Ein Zeiger auf den Quellblock die Nachricht anbietet.

### <a name="return-value"></a>Rückgabewert

Ein [Message_status](concurrency-namespace-enums.md) Überblick, was das Ziel beschlossen, die Sie mit der Meldung.

### <a name="remarks"></a>Hinweise

Löst die Methode eine [Invalid_argument](../../../standard-library/invalid-argument-class.md) -Ausnahme aus, wenn entweder die `_PMessage` oder `_PSource` Parameter `NULL`.

##  <a name="send"></a> Senden

Ruft beim Überschreiben in einer abgeleiteten Klasse übergibt eine Nachricht synchron an den Zielblock.

```
virtual message_status send(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource) = 0;
```

### <a name="parameters"></a>Parameter

*_PMessage*<br/>
Ein Zeiger auf das `message`-Objekt.

*_PSource*<br/>
Ein Zeiger auf den Quellblock die Nachricht anbietet.

### <a name="return-value"></a>Rückgabewert

Ein [Message_status](concurrency-namespace-enums.md) Überblick, was das Ziel beschlossen, die Sie mit der Meldung.

### <a name="remarks"></a>Hinweise

Löst die Methode eine [Invalid_argument](../../../standard-library/invalid-argument-class.md) -Ausnahme aus, wenn entweder die `_PMessage` oder `_PSource` Parameter `NULL`.

Mithilfe der `send` Methode außerhalb der Nachrichteninitiierung und Weitergabe von Nachrichten innerhalb eines Netzwerks ist gefährlich, und kann zu einem Deadlock führen.

Wenn `send` zurückgegeben wird, die Nachricht entweder bereits akzeptiert, und wurde in den Zielblock übertragen, oder es vom Ziel abgelehnt wurde.

##  <a name="supports_anonymous_source"></a> supports_anonymous_source

Ruft beim Überschreiben in einer abgeleiteten Klasse gibt "true" oder "false", je nachdem, ob die Nachrichtenblock akzeptiert Nachrichten, die angeboten, die von einer Quelle, die nicht verknüpft ist. Wenn die überschriebene Methode zurückgibt **"true"**, das Ziel kann keine angebotene Nachricht verschieben, wie die Nutzung von eine zurückgestellte Nachricht zu einem späteren Zeitpunkt die Quelle in seiner Sourse Link Registrierung identifiziert werden erforderlich sind.

```
virtual bool supports_anonymous_source();
```

### <a name="return-value"></a>Rückgabewert

**"true"** , wenn der Block Nachricht von einer Quelle akzeptieren kann, die nicht verknüpft ist **"false"** andernfalls.

##  <a name="unlink_source"></a> unlink_source

Ruft beim Überschreiben in einer abgeleiteten Klasse hebt die Verknüpfung mit einem angegebenen Quellblock aus diesem `ITarget` Block.

```
virtual void unlink_source(_Inout_ ISource<T>* _PSource) = 0;
```

### <a name="parameters"></a>Parameter

*_PSource*<br/>
Die `ISource` Sperren aufgehoben wird, aus dieser `ITarget` Block.

### <a name="remarks"></a>Hinweise

Diese Funktion sollte nicht aufgerufen werden, direkt auf eine `ITarget` Block. Blöcke sollten getrennt werden, mithilfe der `unlink_target` oder `unlink_targets` Methoden `ISource` -Blöcken, die aufgerufen werden, die `unlink_source` Methode auf dem entsprechenden Ziel.

##  <a name="unlink_sources"></a> unlink_sources

Ruft beim Überschreiben in einer abgeleiteten Klasse hebt die Verknüpfung aller Quellblöcke dies `ITarget` Block.

```
virtual void unlink_sources() = 0;
```

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[ISource-Klasse](isource-class.md)
