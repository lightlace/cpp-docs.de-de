---
title: multi_link_registry-Klasse
ms.date: 11/04/2016
f1_keywords:
- multi_link_registry
- AGENTS/concurrency::multi_link_registry
- AGENTS/concurrency::multi_link_registry::multi_link_registry
- AGENTS/concurrency::multi_link_registry::add
- AGENTS/concurrency::multi_link_registry::begin
- AGENTS/concurrency::multi_link_registry::contains
- AGENTS/concurrency::multi_link_registry::count
- AGENTS/concurrency::multi_link_registry::remove
- AGENTS/concurrency::multi_link_registry::set_bound
helpviewer_keywords:
- multi_link_registry class
ms.assetid: b2aa73a8-e8a6-4255-b117-d07530c328b2
ms.openlocfilehash: e22df5ee65d0219a46065044385dca46aac297a3
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142376"
---
# <a name="multi_link_registry-class"></a>multi_link_registry-Klasse

Das `multi_link_registry`-Objekt ist eine `network_link_registry`, die mehrere Quellblöcke oder mehrere Zielblöcke verwaltet.

## <a name="syntax"></a>Syntax

```cpp
template<class _Block>
class multi_link_registry : public network_link_registry<_Block>;
```

### <a name="parameters"></a>Parameter

*_Block*<br/>
Der Block Datentyp, der im `multi_link_registry` Objekt gespeichert wird.

## <a name="members"></a>Members

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[multi_link_registry](#ctor)|Erstellt ein `multi_link_registry`-Objekt.|
|[~ multi_link_registry-Dekonstruktor](#dtor)|Zerstört das `multi_link_registry`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|BESCHREIBUNG|
|----------|-----------------|
|[add](#add)|Fügt dem `multi_link_registry` Objekt einen Link hinzu. (Überschreibt [network_link_registry:: Add](network-link-registry-class.md#add).)|
|[begin](#begin)|Gibt einen Iterator zum ersten Element im `multi_link_registry`-Objekt zurück. (Überschreibt [network_link_registry:: begin](network-link-registry-class.md#begin).)|
|[contains](#contains)|Durchsucht das `multi_link_registry`-Objekt nach einem angegebenen Block. (Überschreibt [network_link_registry:: enthält](network-link-registry-class.md#contains).)|
|[count](#count)|Zählt die Anzahl der Elemente im `multi_link_registry`-Objekt. (Überschreibt [network_link_registry:: count](network-link-registry-class.md#count).)|
|[remove](#remove)|Entfernt einen Link aus dem `multi_link_registry`-Objekt. (Überschreibt [network_link_registry:: Remove](network-link-registry-class.md#remove).)|
|[set_bound](#set_bound)|Legt eine obere Grenze für die Anzahl von Links fest, die das `multi_link_registry` Objekt enthalten kann.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[network_link_registry](network-link-registry-class.md)

`multi_link_registry`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** agents.h

**Namespace:** Parallelität

## <a name="add"></a>eren

Fügt dem `multi_link_registry` Objekt einen Link hinzu.

```cpp
virtual void add(_EType _Link);
```

### <a name="parameters"></a>Parameter

*_Link*<br/>
Ein Zeiger auf einen Block, der hinzugefügt werden soll.

### <a name="remarks"></a>Bemerkungen

Die-Methode löst eine [invalid_link_target](invalid-link-target-class.md) Ausnahme aus, wenn der Link bereits in der Registrierung vorhanden ist, oder wenn eine gebundene bereits mit der `set_bound`-Funktion festgelegt wurde und ein Link seit entfernt wurde.

## <a name="begin"></a>beginnen

Gibt einen Iterator zum ersten Element im `multi_link_registry`-Objekt zurück.

```cpp
virtual iterator begin();
```

### <a name="return-value"></a>Rückgabewert

Ein Iterator, der das erste Element im `multi_link_registry` Objekt adressiert.

### <a name="remarks"></a>Bemerkungen

Der Endzustand wird durch einen `NULL` Link angegeben.

## <a name="contains"></a>Inhalt

Durchsucht das `multi_link_registry`-Objekt nach einem angegebenen Block.

```cpp
virtual bool contains(_EType _Link);
```

### <a name="parameters"></a>Parameter

*_Link*<br/>
Ein Zeiger auf einen Block, der im `multi_link_registry` Objekt gesucht werden soll.

### <a name="return-value"></a>Rückgabewert

**true** , wenn der angegebene Block gefunden wurde, andernfalls **false** .

## <a name="count"></a>Countdown

Zählt die Anzahl der Elemente im `multi_link_registry`-Objekt.

```cpp
virtual size_t count();
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Elemente im `multi_link_registry`-Objekt.

## <a name="ctor"></a>multi_link_registry

Erstellt ein `multi_link_registry`-Objekt.

```cpp
multi_link_registry();
```

## <a name="dtor"></a>~ multi_link_registry

Zerstört das `multi_link_registry`-Objekt.

```cpp
virtual ~multi_link_registry();
```

### <a name="remarks"></a>Bemerkungen

Die-Methode löst eine [Invalid_operation](invalid-operation-class.md) Ausnahme aus, wenn Sie aufgerufen wird, bevor alle Links entfernt werden.

## <a name="remove"></a>aufgeh

Entfernt einen Link aus dem `multi_link_registry`-Objekt.

```cpp
virtual bool remove(_EType _Link);
```

### <a name="parameters"></a>Parameter

*_Link*<br/>
Ein Zeiger auf einen Block, der entfernt werden soll, sofern gefunden.

### <a name="return-value"></a>Rückgabewert

**true** , wenn der Link gefunden und entfernt wurde, andernfalls **false** .

## <a name="set_bound"></a>set_bound

Legt eine obere Grenze für die Anzahl von Links fest, die das `multi_link_registry` Objekt enthalten kann.

```cpp
void set_bound(size_t _MaxLinks);
```

### <a name="parameters"></a>Parameter

*_MaxLinks*<br/>
Die maximale Anzahl von Links, die das `multi_link_registry`-Objekt enthalten kann.

### <a name="remarks"></a>Bemerkungen

Nachdem eine gebundene festgelegt wurde, bewirkt das Aufheben der Verknüpfung eines Eintrags, dass das `multi_link_registry` Objekt in einen unveränderlichen Zustand wechselt, in dem weitere Aufrufe an `add` eine `invalid_link_target` Ausnahme auslösen.

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[single_link_registry-Klasse](single-link-registry-class.md)
