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
ms.openlocfilehash: 700d052b6f22c970387a3ab45d299538a5b74e1b
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77139539"
---
# <a name="message-class"></a>message-Klasse

Der grundlegende Nachrichtenumschlag, der die zwischen den Meldungsblöcken übergebene Datennutzlast enthält.

## <a name="syntax"></a>Syntax

```cpp
template<class T>
class message : public ::Concurrency::details::_Runtime_object;
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der Datentyp der Nutzlast in der Nachricht.

## <a name="members"></a>Members

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|BESCHREIBUNG|
|----------|-----------------|
|`type`|Ein Typalias für `T`.|

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[Nachricht](#ctor)|Ist überladen. Erstellt ein `message`-Objekt.|
|[~ Message-debugtor](#dtor)|Zerstört das `message`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|BESCHREIBUNG|
|----------|-----------------|
|[add_ref](#add_ref)|Fügt den Verweis Zähler für das `message` Objekt hinzu. Wird für Nachrichten Blöcke verwendet, die eine Verweis Zählung zum Bestimmen der Lebensdauer von Nachrichten benötigen.|
|[msg_id](#msg_id)|Gibt die ID des `message` Objekts zurück.|
|[remove_ref](#remove_ref)|Subtrahiert vom Verweis Zähler für das `message` Objekt. Wird für Nachrichten Blöcke verwendet, die eine Verweis Zählung zum Bestimmen der Lebensdauer von Nachrichten benötigen.|

### <a name="public-data-members"></a>Öffentliche Datenelemente

|Name|BESCHREIBUNG|
|----------|-----------------|
|[payload](#payload)|Die Nutzlast des `message` Objekts.|

## <a name="remarks"></a>Bemerkungen

Weitere Informationen finden Sie unter [asynchrone Nachrichten Blöcke](../../../parallel/concrt/asynchronous-message-blocks.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`message`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** agents.h

**Namespace:** Parallelität

## <a name="add_ref"></a>add_ref

Fügt den Verweis Zähler für das `message` Objekt hinzu. Wird für Nachrichten Blöcke verwendet, die eine Verweis Zählung zum Bestimmen der Lebensdauer von Nachrichten benötigen.

```cpp
long add_ref();
```

### <a name="return-value"></a>Rückgabewert

Der neue Wert des Verweis zählungs Werts.

## <a name="ctor"></a>Nachricht

Erstellt ein `message`-Objekt.

```cpp
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
Ein Verweis oder Zeiger auf ein `message` Objekt.

### <a name="remarks"></a>Bemerkungen

Der Konstruktor, der einen Zeiger auf ein `message` Objekt als Argument annimmt, löst eine [Invalid_argument](../../../standard-library/invalid-argument-class.md) Ausnahme aus, wenn der Parameter `_Msg` `NULL`ist.

## <a name="dtor"></a>~ Meldung

Zerstört das `message`-Objekt.

```cpp
virtual ~message();
```

## <a name="msg_id"></a>msg_id

Gibt die ID des `message` Objekts zurück.

```cpp
runtime_object_identity msg_id() const;
```

### <a name="return-value"></a>Rückgabewert

`runtime_object_identity` des `message`-Objekts.

## <a name="payload"></a>Nutz

Die Nutzlast des `message` Objekts.

```cpp
T const payload;
```

## <a name="remove_ref"></a>remove_ref

Subtrahiert vom Verweis Zähler für das `message` Objekt. Wird für Nachrichten Blöcke verwendet, die eine Verweis Zählung zum Bestimmen der Lebensdauer von Nachrichten benötigen.

```cpp
long remove_ref();
```

### <a name="return-value"></a>Rückgabewert

Der neue Wert des Verweis zählungs Werts.

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace](concurrency-namespace.md)
