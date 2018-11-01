---
title: message-Klasse
ms.date: 11/04/2016
f1_keywords:
- message
- AGENTS/concurrency::message
- AGENTS/concurrency::message::message
- AGENTS/concurrency::message::add_ref
- AGENTS/concurrency::message::msg_id
- AGENTS/concurrency::message::remove_ref
- AGENTS/concurrency::message::payload
helpviewer_keywords:
- message class
ms.assetid: 3e1f3505-6c0c-486c-8191-666d0880ec62
ms.openlocfilehash: 6b0c37f61ef437662a4e624c3a81edb526e7464c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50636856"
---
# <a name="message-class"></a>message-Klasse

Der grundlegende Nachrichtenumschlag, der die zwischen den Meldungsblöcken übergebene Datennutzlast enthält.

## <a name="syntax"></a>Syntax

```
template<class T>
class message : public ::Concurrency::details::_Runtime_object;
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Der Datentyp der Nutzlast innerhalb der Nachricht.

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|Beschreibung|
|----------|-----------------|
|`type`|Ein Typalias für `T`.|

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[message](#ctor)|Überladen. Erstellt ein `message`-Objekt.|
|[~ message-Destruktor](#dtor)|Zerstört das `message`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[add_ref](#add_ref)|Fügt hinzu, um den Verweiszähler für den `message` Objekt. Verwendet für Meldungsblöcke, die verweiszählung, um die Lebensdauer der Meldung zu bestimmen.|
|[msg_id](#msg_id)|Gibt die ID des dem `message` Objekt.|
|[remove_ref](#remove_ref)|Subtrahiert von den Verweiszähler für den `message` Objekt. Verwendet für Meldungsblöcke, die verweiszählung, um die Lebensdauer der Meldung zu bestimmen.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[Nutzlast](#payload)|Die Nutzlast der `message` Objekt.|

## <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [asynchrone Meldungsblöcke](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`message`

## <a name="requirements"></a>Anforderungen

**Header:** agents.h

**Namespace:** Parallelität

##  <a name="add_ref"></a> add_ref

Fügt hinzu, um den Verweiszähler für den `message` Objekt. Verwendet für Meldungsblöcke, die verweiszählung, um die Lebensdauer der Meldung zu bestimmen.

```
long add_ref();
```

### <a name="return-value"></a>Rückgabewert

Der neue Wert des Verweiszählers.

##  <a name="ctor"></a> Nachricht

Erstellt ein `message`-Objekt.

```
message(
    T const& _P);

message(
    T const& _P,
    runtime_object_identity _Id);

message(
    message const& _Msg);

message(
    _In_ message const* _Msg);
```

### <a name="parameters"></a>Parameter

*_P*<br/>
Die Nutzlast dieser Nachricht.

*_Id*<br/>
Die eindeutige ID dieser Nachricht.

*_Msg*<br/>
Ein Verweis oder Zeiger auf eine `message` Objekt.

### <a name="remarks"></a>Hinweise

Der Konstruktor, einen Zeiger auf eine `message` Objekt wie ein Argument löst eine [Invalid_argument](../../../standard-library/invalid-argument-class.md) Ausnahme wenn der Parameter `_Msg` ist `NULL`.

##  <a name="dtor"></a> ~ Nachricht

Zerstört das `message`-Objekt.

```
virtual ~message();
```

##  <a name="msg_id"></a> msg_id

Gibt die ID des dem `message` Objekt.

```
runtime_object_identity msg_id() const;
```

### <a name="return-value"></a>Rückgabewert

Die `runtime_object_identity` von der `message` Objekt.

##  <a name="payload"></a> Nutzlast

Die Nutzlast der `message` Objekt.

```
T const payload;
```

##  <a name="remove_ref"></a> remove_ref

Subtrahiert von den Verweiszähler für den `message` Objekt. Verwendet für Meldungsblöcke, die verweiszählung, um die Lebensdauer der Meldung zu bestimmen.

```
long remove_ref();
```

### <a name="return-value"></a>Rückgabewert

Der neue Wert des Verweiszählers.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)
