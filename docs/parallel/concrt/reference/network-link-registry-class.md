---
title: Network_link_registry-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- network_link_registry
- AGENTS/concurrency::network_link_registry
- AGENTS/concurrency::network_link_registry::add
- AGENTS/concurrency::network_link_registry::begin
- AGENTS/concurrency::network_link_registry::contains
- AGENTS/concurrency::network_link_registry::count
- AGENTS/concurrency::network_link_registry::remove
dev_langs:
- C++
helpviewer_keywords:
- network_link_registry class
ms.assetid: 3e7b4097-09f1-4252-964e-b15b8f7f7fc6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2798c4abe33e49d2ac6199ad6f9a1013805fde7b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46424416"
---
# <a name="networklinkregistry-class"></a>network_link_registry-Klasse

Die abstrakte `network_link_registry`-Basisklasse verwaltet die Verknüpfung zwischen Quell- und Zielblöcken.

## <a name="syntax"></a>Syntax

```
template<class _Block>
class network_link_registry;
```

#### <a name="parameters"></a>Parameter

*_Block*<br/>
Geben Sie die Blockdaten gespeichert werden, der `network_link_registry`.

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|Beschreibung|
|----------|-----------------|
|`const_pointer`|Ein Typ, einen Zeiger auf eine `const` Element in einem `network_link_registry` Objekt.|
|`const_reference`|Ein Typ, einen Verweis auf eine `const` Element gespeichert wird, einem `network_link_registry` Objekt zum Lesen und Ausführen von const-Operationen.|
|`iterator`|Eine Typ, der einem Iterator bereitstellt, gelesen oder ändern Sie jedes Element in kann ein `network_link_registry` Objekt.|
|`type`|Ein Typ, der in gespeicherten Blocktyp darstellt. die `network_link_registry` Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[add](#add)|Ruft beim Überschreiben in einer abgeleiteten Klasse fügt einen Link zu der `network_link_registry` Objekt.|
|[begin](#begin)|Ruft beim Überschreiben in einer abgeleiteten Klasse, gibt einen Iterator zum ersten Element in der `network_link_registry` Objekt.|
|[Enthält](#contains)|Sucht beim Überschreiben in einer abgeleiteten Klasse die `network_link_registry` -Objekt für einen angegebenen Block.|
|[count](#count)|Ruft beim Überschreiben in einer abgeleiteten Klasse gibt die Anzahl der Elemente in der `network_link_registry` Objekt.|
|[remove](#remove)|Ruft beim Überschreiben in einer abgeleiteten Klasse entfernt einen angegebenen Block aus der `network_link_registry` Objekt.|

## <a name="remarks"></a>Hinweise

Die `network link registry` ist nicht für den gleichzeitigen Zugriff sicher.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`network_link_registry`

## <a name="requirements"></a>Anforderungen

**Header:** agents.h

**Namespace:** Parallelität

##  <a name="add"></a> Hinzufügen

Ruft beim Überschreiben in einer abgeleiteten Klasse fügt einen Link zu der `network_link_registry` Objekt.

```
virtual void add(_EType _Link) = 0;
```

### <a name="parameters"></a>Parameter

*_Mit verknüpfen*<br/>
Ein Zeiger auf einen Block hinzugefügt werden.

##  <a name="begin"></a> beginnen

Ruft beim Überschreiben in einer abgeleiteten Klasse, gibt einen Iterator zum ersten Element in der `network_link_registry` Objekt.

```
virtual iterator begin() = 0;
```

### <a name="return-value"></a>Rückgabewert

Ein Iterator, der das erste Element in der `network_link_registry` Objekt.

### <a name="remarks"></a>Hinweise

Der Endzustand des Iterators wird angegeben, indem eine `NULL` Link.

##  <a name="contains"></a> Enthält

Sucht beim Überschreiben in einer abgeleiteten Klasse die `network_link_registry` -Objekt für einen angegebenen Block.

```
virtual bool contains(_EType _Link) = 0;
```

### <a name="parameters"></a>Parameter

*_Mit verknüpfen*<br/>
Ein Zeiger auf einen Block, der in gesucht wird die `network_link_registry` Objekt.

### <a name="return-value"></a>Rückgabewert

`true` Wenn der Block gefunden wurde, `false` andernfalls.

##  <a name="count"></a> Anzahl

Ruft beim Überschreiben in einer abgeleiteten Klasse gibt die Anzahl der Elemente in der `network_link_registry` Objekt.

```
virtual size_t count() = 0;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Elemente in der `network_link_registry` Objekt.

##  <a name="remove"></a> Entfernen

Ruft beim Überschreiben in einer abgeleiteten Klasse entfernt einen angegebenen Block aus der `network_link_registry` Objekt.

```
virtual bool remove(_EType _Link) = 0;
```

### <a name="parameters"></a>Parameter

*_Mit verknüpfen*<br/>
Ein Zeiger auf einen Block, wenn entfernt wurde gefunden.

### <a name="return-value"></a>Rückgabewert

`true` Wenn der Link wurde gefunden und entfernt, `false` andernfalls.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[single_link_registry-Klasse](single-link-registry-class.md)<br/>
[multi_link_registry-Klasse](multi-link-registry-class.md)
