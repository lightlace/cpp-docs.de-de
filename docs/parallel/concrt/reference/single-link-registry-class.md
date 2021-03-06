---
title: single_link_registry-Klasse
ms.date: 11/04/2016
f1_keywords:
- single_link_registry
- AGENTS/concurrency::single_link_registry
- AGENTS/concurrency::single_link_registry::single_link_registry
- AGENTS/concurrency::single_link_registry::add
- AGENTS/concurrency::single_link_registry::begin
- AGENTS/concurrency::single_link_registry::contains
- AGENTS/concurrency::single_link_registry::count
- AGENTS/concurrency::single_link_registry::remove
helpviewer_keywords:
- single_link_registry class
ms.assetid: 09540a4e-c34e-4ff9-af49-21b8612b6ab3
ms.openlocfilehash: c29caf6d31df316e80b15fe6827c81e34ece8a18
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142720"
---
# <a name="single_link_registry-class"></a>single_link_registry-Klasse

Das `single_link_registry`-Objekt ist eine `network_link_registry`, die nur eine einzige Quelle oder einen einzigen Zielblock verwaltet.

## <a name="syntax"></a>Syntax

```cpp
template<class _Block>
class single_link_registry : public network_link_registry<_Block>;
```

### <a name="parameters"></a>Parameter

*_Block*<br/>
Der Block Datentyp, der im `single_link_registry` Objekt gespeichert wird.

## <a name="members"></a>Members

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[single_link_registry](#ctor)|Erstellt ein `single_link_registry`-Objekt.|
|[~ single_link_registry-Dekonstruktor](#dtor)|Zerstört das `single_link_registry`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|BESCHREIBUNG|
|----------|-----------------|
|[add](#add)|Fügt dem `single_link_registry` Objekt einen Link hinzu. (Überschreibt [network_link_registry:: Add](network-link-registry-class.md#add).)|
|[begin](#begin)|Gibt einen Iterator zum ersten Element im `single_link_registry`-Objekt zurück. (Überschreibt [network_link_registry:: begin](network-link-registry-class.md#begin).)|
|[contains](#contains)|Durchsucht das `single_link_registry`-Objekt nach einem angegebenen Block. (Überschreibt [network_link_registry:: enthält](network-link-registry-class.md#contains).)|
|[count](#count)|Zählt die Anzahl der Elemente im `single_link_registry`-Objekt. (Überschreibt [network_link_registry:: count](network-link-registry-class.md#count).)|
|[remove](#remove)|Entfernt einen Link aus dem `single_link_registry`-Objekt. (Überschreibt [network_link_registry:: Remove](network-link-registry-class.md#remove).)|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[network_link_registry](network-link-registry-class.md)

`single_link_registry`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** agents.h

**Namespace:** Parallelität

## <a name="add"></a>eren

Fügt dem `single_link_registry` Objekt einen Link hinzu.

```cpp
virtual void add(_EType _Link);
```

### <a name="parameters"></a>Parameter

*_Link*<br/>
Ein Zeiger auf einen Block, der hinzugefügt werden soll.

### <a name="remarks"></a>Bemerkungen

Die-Methode löst eine [invalid_link_target](invalid-link-target-class.md) Ausnahme aus, wenn in dieser Registrierung bereits ein Link vorhanden ist.

## <a name="begin"></a>beginnen

Gibt einen Iterator zum ersten Element im `single_link_registry`-Objekt zurück.

```cpp
virtual iterator begin();
```

### <a name="return-value"></a>Rückgabewert

Ein Iterator, der das erste Element im `single_link_registry` Objekt adressiert.

### <a name="remarks"></a>Bemerkungen

Der Endzustand wird durch einen `NULL` Link angegeben.

## <a name="contains"></a>Inhalt

Durchsucht das `single_link_registry`-Objekt nach einem angegebenen Block.

```cpp
virtual bool contains(_EType _Link);
```

### <a name="parameters"></a>Parameter

*_Link*<br/>
Ein Zeiger auf einen Block, der im `single_link_registry` Objekt gesucht werden soll.

### <a name="return-value"></a>Rückgabewert

**true** , wenn der Link gefunden wurde, andernfalls **false** .

## <a name="count"></a>Countdown

Zählt die Anzahl der Elemente im `single_link_registry`-Objekt.

```cpp
virtual size_t count();
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Elemente im `single_link_registry`-Objekt.

## <a name="remove"></a>aufgeh

Entfernt einen Link aus dem `single_link_registry`-Objekt.

```cpp
virtual bool remove(_EType _Link);
```

### <a name="parameters"></a>Parameter

*_Link*<br/>
Ein Zeiger auf einen Block, der entfernt werden soll, sofern gefunden.

### <a name="return-value"></a>Rückgabewert

**true** , wenn der Link gefunden und entfernt wurde, andernfalls **false** .

## <a name="ctor"></a>single_link_registry

Erstellt ein `single_link_registry`-Objekt.

```cpp
single_link_registry();
```

## <a name="dtor"></a>~ single_link_registry

Zerstört das `single_link_registry`-Objekt.

```cpp
virtual ~single_link_registry();
```

### <a name="remarks"></a>Bemerkungen

Die-Methode löst eine [Invalid_operation](invalid-operation-class.md) Ausnahme aus, wenn Sie vor dem Entfernen des Links aufgerufen wird.

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[multi_link_registry-Klasse](multi-link-registry-class.md)
