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
ms.openlocfilehash: 388cc0082f69041368d1a444179855451d552ce6
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57264760"
---
# <a name="multilinkregistry-class"></a>multi_link_registry-Klasse

Das `multi_link_registry`-Objekt ist eine `network_link_registry`, die mehrere Quellblöcke oder mehrere Zielblöcke verwaltet.

## <a name="syntax"></a>Syntax

```
template<class _Block>
class multi_link_registry : public network_link_registry<_Block>;
```

#### <a name="parameters"></a>Parameter

*_Block*<br/>
Geben Sie die Blockdaten gespeichert werden, der `multi_link_registry` Objekt.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[multi_link_registry](#ctor)|Erstellt ein `multi_link_registry`-Objekt.|
|[~multi_link_registry Destructor](#dtor)|Zerstört das `multi_link_registry`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[add](#add)|Fügt einen Link zu der `multi_link_registry` Objekt. (Überschreibt [network_link_registry:: Add](network-link-registry-class.md#add).)|
|[begin](#begin)|Gibt einen Iterator zurück, auf das erste Element in der `multi_link_registry` Objekt. (Überschreibt [network_link_registry:: Begin](network-link-registry-class.md#begin).)|
|[contains](#contains)|Sucht die `multi_link_registry` -Objekt für einen angegebenen Block. (Überschreibt [network_link_registry:: Contains](network-link-registry-class.md#contains).)|
|[count](#count)|Zählt die Anzahl der Elemente in der `multi_link_registry` Objekt. (Überschreibt [network_link_registry:: Count](network-link-registry-class.md#count).)|
|[remove](#remove)|Entfernt einen Link von der `multi_link_registry` Objekt. (Überschreibt [network_link_registry:: Remove](network-link-registry-class.md#remove).)|
|[set_bound](#set_bound)|Legt eine Obergrenze für die Anzahl der Links, die die `multi_link_registry` Objekt enthalten kann.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[network_link_registry](network-link-registry-class.md)

`multi_link_registry`

## <a name="requirements"></a>Anforderungen

**Header:** agents.h

**Namespace:** Parallelität

##  <a name="add"></a> Hinzufügen

Fügt einen Link zu der `multi_link_registry` Objekt.

```
virtual void add(_EType _Link);
```

### <a name="parameters"></a>Parameter

*_Link*<br/>
Ein Zeiger auf einen Block hinzugefügt werden.

### <a name="remarks"></a>Hinweise

Löst die Methode eine [Invalid_link_target](invalid-link-target-class.md) Ausnahme, wenn der Link bereits in der Registrierung vorhanden ist, oder wenn eine Grenze wurde bereits festgelegt mit der `set_bound` -Funktion und ein Link wurde entfernt wurde.

##  <a name="begin"></a> beginnen

Gibt einen Iterator zurück, auf das erste Element in der `multi_link_registry` Objekt.

```
virtual iterator begin();
```

### <a name="return-value"></a>Rückgabewert

Ein Iterator, der das erste Element in der `multi_link_registry` Objekt.

### <a name="remarks"></a>Hinweise

Der Endzustand angegeben wird, durch eine `NULL` Link.

##  <a name="contains"></a> Enthält

Sucht die `multi_link_registry` -Objekt für einen angegebenen Block.

```
virtual bool contains(_EType _Link);
```

### <a name="parameters"></a>Parameter

*_Link*<br/>
Ein Zeiger auf einen Block, der für die gesucht werden soll, in der `multi_link_registry` Objekt.

### <a name="return-value"></a>Rückgabewert

**"true"** Wenn der angegebene Block gefunden wurde, **"false"** andernfalls.

##  <a name="count"></a> Anzahl

Zählt die Anzahl der Elemente in der `multi_link_registry` Objekt.

```
virtual size_t count();
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Elemente in der `multi_link_registry` Objekt.

##  <a name="ctor"></a> multi_link_registry

Erstellt ein `multi_link_registry`-Objekt.

```
multi_link_registry();
```

##  <a name="dtor"></a> ~multi_link_registry

Zerstört das `multi_link_registry`-Objekt.

```
virtual ~multi_link_registry();
```

### <a name="remarks"></a>Hinweise

Löst die Methode eine [Invalid_operation](invalid-operation-class.md) -Ausnahme aus, wenn aufgerufen, bevor alle Links entfernt werden.

##  <a name="remove"></a> Entfernen

Entfernt einen Link von der `multi_link_registry` Objekt.

```
virtual bool remove(_EType _Link);
```

### <a name="parameters"></a>Parameter

*_Link*<br/>
Ein Zeiger auf einen Block, wenn entfernt wurde gefunden.

### <a name="return-value"></a>Rückgabewert

**"true"** , wenn der Link wurde gefunden und entfernt, **"false"** andernfalls.

##  <a name="set_bound"></a> set_bound

Legt eine Obergrenze für die Anzahl der Links, die die `multi_link_registry` Objekt enthalten kann.

```
void set_bound(size_t _MaxLinks);
```

### <a name="parameters"></a>Parameter

*_MaxLinks*<br/>
Die maximale Anzahl von verknüpft ist, das die `multi_link_registry` Objekt enthalten kann.

### <a name="remarks"></a>Hinweise

Nachdem eine Grenze festgelegt ist, Aufheben der Verknüpfung eines Eintrags bewirkt, dass die `multi_link_registry` Objekt, das einen unveränderlichen Zustand wechselt, in denen nachfolgende Aufrufe von `add` löst eine `invalid_link_target` Ausnahme.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[single_link_registry-Klasse](single-link-registry-class.md)
