---
title: network_link_registry-Klasse
ms.date: 11/04/2016
f1_keywords:
- network_link_registry
- AGENTS/concurrency::network_link_registry
- AGENTS/concurrency::network_link_registry::add
- AGENTS/concurrency::network_link_registry::begin
- AGENTS/concurrency::network_link_registry::contains
- AGENTS/concurrency::network_link_registry::count
- AGENTS/concurrency::network_link_registry::remove
helpviewer_keywords:
- network_link_registry class
ms.assetid: 3e7b4097-09f1-4252-964e-b15b8f7f7fc6
ms.openlocfilehash: 430190c11ec06a4f26eb9d8c4237552848420ad7
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77138891"
---
# <a name="network_link_registry-class"></a>network_link_registry-Klasse

Die abstrakte `network_link_registry`-Basisklasse verwaltet die Verknüpfung zwischen Quell- und Zielblöcken.

## <a name="syntax"></a>Syntax

```cpp
template<class _Block>
class network_link_registry;
```

### <a name="parameters"></a>Parameter

*_Block*<br/>
Der Block Datentyp, der in der `network_link_registry`gespeichert wird.

## <a name="members"></a>Members

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|BESCHREIBUNG|
|----------|-----------------|
|`const_pointer`|Ein Typ, der einen Zeiger auf ein `const` Element in einem `network_link_registry`-Objekt bereitstellt.|
|`const_reference`|Ein Typ, der einen Verweis auf ein `const` Element bereitstellt, das in einem `network_link_registry`-Objekt zum Lesen und Ausführen von Konstanten Vorgängen gespeichert ist.|
|`iterator`|Ein Typ, der einen Iterator bereitstellt, mit dem jedes Element in einem `network_link_registry` Objekt gelesen oder geändert werden kann.|
|`type`|Ein Typ, der den im `network_link_registry` Objekt gespeicherten Blocktyp darstellt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|BESCHREIBUNG|
|----------|-----------------|
|[add](#add)|Fügt beim Überschreiben in einer abgeleiteten Klasse einen Link zum `network_link_registry`-Objekt hinzu.|
|[begin](#begin)|Gibt beim Überschreiben in einer abgeleiteten Klasse einen Iterator an das erste Element im `network_link_registry` Objekt zurück.|
|[contains](#contains)|Durchsucht beim Überschreiben in einer abgeleiteten Klasse das `network_link_registry`-Objekt nach einem angegebenen Block.|
|[count](#count)|Gibt beim Überschreiben in einer abgeleiteten Klasse die Anzahl der Elemente im `network_link_registry` Objekt zurück.|
|[remove](#remove)|Entfernt beim Überschreiben in einer abgeleiteten Klasse einen angegebenen Block aus dem `network_link_registry`-Objekt.|

## <a name="remarks"></a>Bemerkungen

Der `network link registry` ist für den gleichzeitigen Zugriff nicht sicher.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`network_link_registry`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** agents.h

**Namespace:** Parallelität

## <a name="add"></a>eren

Fügt beim Überschreiben in einer abgeleiteten Klasse einen Link zum `network_link_registry`-Objekt hinzu.

```cpp
virtual void add(_EType _Link) = 0;
```

### <a name="parameters"></a>Parameter

*_Link*<br/>
Ein Zeiger auf einen Block, der hinzugefügt werden soll.

## <a name="begin"></a>beginnen

Gibt beim Überschreiben in einer abgeleiteten Klasse einen Iterator an das erste Element im `network_link_registry` Objekt zurück.

```cpp
virtual iterator begin() = 0;
```

### <a name="return-value"></a>Rückgabewert

Ein Iterator, der das erste Element im `network_link_registry` Objekt adressiert.

### <a name="remarks"></a>Bemerkungen

Der Endzustand des Iterators wird durch einen `NULL` Link angegeben.

## <a name="contains"></a>Inhalt

Durchsucht beim Überschreiben in einer abgeleiteten Klasse das `network_link_registry`-Objekt nach einem angegebenen Block.

```cpp
virtual bool contains(_EType _Link) = 0;
```

### <a name="parameters"></a>Parameter

*_Link*<br/>
Ein Zeiger auf einen Block, nach dem im `network_link_registry` Objekt gesucht wird.

### <a name="return-value"></a>Rückgabewert

**true** , wenn der Block gefunden wurde, andernfalls **false** .

## <a name="count"></a>Countdown

Gibt beim Überschreiben in einer abgeleiteten Klasse die Anzahl der Elemente im `network_link_registry` Objekt zurück.

```cpp
virtual size_t count() = 0;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Elemente im `network_link_registry`-Objekt.

## <a name="remove"></a>aufgeh

Entfernt beim Überschreiben in einer abgeleiteten Klasse einen angegebenen Block aus dem `network_link_registry`-Objekt.

```cpp
virtual bool remove(_EType _Link) = 0;
```

### <a name="parameters"></a>Parameter

*_Link*<br/>
Ein Zeiger auf einen Block, der entfernt werden soll, sofern gefunden.

### <a name="return-value"></a>Rückgabewert

**true** , wenn der Link gefunden und entfernt wurde, andernfalls **false** .

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[single_link_registry-Klasse](single-link-registry-class.md)<br/>
[multi_link_registry-Klasse](multi-link-registry-class.md)
