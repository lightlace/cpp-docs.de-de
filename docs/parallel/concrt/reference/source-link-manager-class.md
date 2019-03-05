---
title: source_link_manager-Klasse
ms.date: 11/04/2016
f1_keywords:
- source_link_manager
- AGENTS/concurrency::source_link_manager
- AGENTS/concurrency::source_link_manager::source_link_manager
- AGENTS/concurrency::source_link_manager::add
- AGENTS/concurrency::source_link_manager::begin
- AGENTS/concurrency::source_link_manager::contains
- AGENTS/concurrency::source_link_manager::count
- AGENTS/concurrency::source_link_manager::reference
- AGENTS/concurrency::source_link_manager::register_target_block
- AGENTS/concurrency::source_link_manager::release
- AGENTS/concurrency::source_link_manager::remove
- AGENTS/concurrency::source_link_manager::set_bound
helpviewer_keywords:
- source_link_manager class
ms.assetid: 287487cf-e0fe-4c35-aa3c-24f081d1ddae
ms.openlocfilehash: d4979eaf9065183be646be72cfdd5a94500edf55
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57295200"
---
# <a name="sourcelinkmanager-class"></a>source_link_manager-Klasse

Das `source_link_manager`-Objekt verwaltet Meldungsblock-Netzwerklinks zu `ISource`-Blöcken.

## <a name="syntax"></a>Syntax

```
template<class _LinkRegistry>
class source_link_manager;
```

#### <a name="parameters"></a>Parameter

*_LinkRegistry*<br/>
Die Registrierung des Netzwerk-Link.

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|Beschreibung|
|----------|-----------------|
|`const_pointer`|Ein Typ, einen Zeiger auf eine `const` Element in einem `source_link_manager` Objekt.|
|`const_reference`|Ein Typ, einen Verweis auf eine `const` Element gespeichert wird, einem `source_link_manager` Objekt zum Lesen und Ausführen von const-Operationen.|
|`iterator`|Eine Typ, der einem Iterator bereitstellt, gelesen oder ändern Sie jedes Element in kann die `source_link_manager` Objekt.|
|`type`|Der Typ des Link-Registrierung, die von verwaltet die `source_link_manager` Objekt.|

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[source_link_manager](#ctor)|Erstellt ein `source_link_manager`-Objekt.|
|[~source_link_manager Destructor](#dtor)|Zerstört das `source_link_manager`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[add](#add)|Fügt einen Link "Quelle", um die `source_link_manager` Objekt.|
|[begin](#begin)|Gibt einen Iterator zurück, auf das erste Element in der `source_link_manager` Objekt.|
|[contains](#contains)|Sucht die `network_link_registry` innerhalb dieser `source_link_manager` -Objekt für einen angegebenen Block.|
|[count](#count)|Zählt die Anzahl der verknüpften Blöcken in der `source_link_manager` Objekt.|
|[Verweis](#reference)|Ruft einen Verweis auf die `source_link_manager` Objekt.|
|[register_target_block](#register_target_block)|Registriert den Zielblock, die solche enthalten `source_link_manager` Objekt.|
|[release](#release)|Gibt den Verweis frei, auf die `source_link_manager` Objekt.|
|[remove](#remove)|Entfernt einen Link von der `source_link_manager` Objekt.|
|[set_bound](#set_bound)|Legt die maximale Anzahl von quellverknüpfungen, die diese hinzugefügt werden können `source_link_manager` Objekt.|

## <a name="remarks"></a>Hinweise

Derzeit werden die Quellblöcke verweiszählung. Dies ist ein Wrapper auf eine `network_link_registry` -Objekt, das gleichzeitigen Zugriff auf die Links und bietet die Möglichkeit, die Links durch Rückrufe zu verweisen. Message Blocks ( `target_block`s oder `propagator_block`s) verwenden Sie diese Klasse sollte für ihre quellverknüpfungen.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`source_link_manager`

## <a name="requirements"></a>Anforderungen

**Header:** agents.h

**Namespace:** Parallelität

##  <a name="add"></a> Hinzufügen

Fügt einen Link "Quelle", um die `source_link_manager` Objekt.

```
void add(_EType _Link);
```

### <a name="parameters"></a>Parameter

*_Link*<br/>
Ein Zeiger auf einen Block hinzugefügt werden.

##  <a name="begin"></a> beginnen

Gibt einen Iterator zurück, auf das erste Element in der `source_link_manager` Objekt.

```
iterator begin();
```

### <a name="return-value"></a>Rückgabewert

Ein Iterator, der das erste Element in der `source_link_manager` Objekt.

### <a name="remarks"></a>Hinweise

Der Endzustand des Iterators wird angegeben, indem eine `NULL` Link.

##  <a name="contains"></a> Enthält

Sucht die `network_link_registry` innerhalb dieser `source_link_manager` -Objekt für einen angegebenen Block.

```
bool contains(_EType _Link);
```

### <a name="parameters"></a>Parameter

*_Link*<br/>
Ein Zeiger auf einen Block, der für die gesucht werden soll, in der `source_link_manager` Objekt.

### <a name="return-value"></a>Rückgabewert

**"true"** Wenn der angegebene Block gefunden wurde, **"false"** andernfalls.

##  <a name="count"></a> Anzahl

Zählt die Anzahl der verknüpften Blöcken in der `source_link_manager` Objekt.

```
size_t count();
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der verknüpften Blöcken in der `source_link_manager` Objekt.

##  <a name="reference"></a> Referenz

Ruft einen Verweis auf die `source_link_manager` Objekt.

```
void reference();
```

##  <a name="register_target_block"></a> register_target_block

Registriert den Zielblock, die solche enthalten `source_link_manager` Objekt.

```
void register_target_block(_Inout_ ITarget<typename _Block::source_type>* _PTarget);
```

### <a name="parameters"></a>Parameter

*_PTarget*<br/>
Der Zielblock enthält diese `source_link_manager` Objekt.

##  <a name="release"></a> Version

Gibt den Verweis frei, auf die `source_link_manager` Objekt.

```
void release();
```

##  <a name="remove"></a> Entfernen

Entfernt einen Link von der `source_link_manager` Objekt.

```
bool remove(_EType _Link);
```

### <a name="parameters"></a>Parameter

*_Link*<br/>
Ein Zeiger auf einen Block, wenn entfernt wurde gefunden.

### <a name="return-value"></a>Rückgabewert

**"true"** , wenn der Link wurde gefunden und entfernt, **"false"** andernfalls.

##  <a name="set_bound"></a> set_bound

Legt die maximale Anzahl von quellverknüpfungen, die diese hinzugefügt werden können `source_link_manager` Objekt.

```
void set_bound(size_t _MaxLinks);
```

### <a name="parameters"></a>Parameter

*_MaxLinks*<br/>
Die maximale Anzahl von Links.

##  <a name="ctor"></a> source_link_manager

Erstellt ein `source_link_manager`-Objekt.

```
source_link_manager();
```

##  <a name="dtor"></a> ~source_link_manager

Zerstört das `source_link_manager`-Objekt.

```
~source_link_manager();
```

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[single_link_registry-Klasse](single-link-registry-class.md)<br/>
[multi_link_registry-Klasse](multi-link-registry-class.md)
