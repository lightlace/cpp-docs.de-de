---
title: location-Klasse
ms.date: 11/04/2016
f1_keywords:
- location
- CONCRT/concurrency::location
- CONCRT/concurrency::location::location
- CONCRT/concurrency::location::current
- CONCRT/concurrency::location::from_numa_node
helpviewer_keywords:
- location class
ms.assetid: c3289f51-5bf1-4dff-a18d-d0dab8e5d9c7
ms.openlocfilehash: ffb469ec5f5542b5037d31bfdb5fd1eaab47ed38
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50596535"
---
# <a name="location-class"></a>location-Klasse

Die Abstraktion eines physischen Speicherorts auf der Hardware.

## <a name="syntax"></a>Syntax

```
class location;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[location](#ctor)|Überladen. Erstellt ein `location`-Objekt.|
|[~ Location-Destruktor](#dtor)|Zerstört ein `location`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[Aktuelle](#current)|Gibt eine `location` Objekt, das die spezifischste Stelle, die den aufrufende Thread ausgeführt wird, darstellt.|
|[from_numa_node](#from_numa_node)|Gibt eine `location` Objekt, das einen bestimmten NUMA-Knoten darstellt.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[Operator!=](#operator_neq)|Bestimmt, ob zwei `location` Objekte darstellen, anderen Speicherort.|
|[operator=](#operator_eq)|Weist den Inhalt von einem anderen `location` -Objekts in dieses Objekt.|
|[operator==](#operator_eq_eq)|Bestimmt, ob zwei `location` Objekte darstellen, am gleichen Speicherort.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`location`

## <a name="requirements"></a>Anforderungen

**Header:** concrt.h hinzu

**Namespace:** Parallelität

##  <a name="dtor"></a> ~ Speicherort

Zerstört ein `location`-Objekt.

```
~location();
```

##  <a name="current"></a> Aktuelle

Gibt eine `location` Objekt, das die spezifischste Stelle, die den aufrufende Thread ausgeführt wird, darstellt.

```
static location __cdecl current();
```

### <a name="return-value"></a>Rückgabewert

Einen Speicherort, der die spezifischste Stelle darstellt, an der aufrufende Thread ausgeführt wird.

##  <a name="from_numa_node"></a> from_numa_node

Gibt eine `location` Objekt, das einen bestimmten NUMA-Knoten darstellt.

```
static location __cdecl from_numa_node(unsigned short _NumaNodeNumber);
```

### <a name="parameters"></a>Parameter

*_NumaNodeNumber*<br/>
Die NUMA-Knotennummer um einen Speicherort für zu erstellen.

### <a name="return-value"></a>Rückgabewert

Eine Position, die gemäß den NUMA-Knoten darstellt. die `_NumaNodeNumber` Parameter.

##  <a name="ctor"></a> Speicherort

Erstellt ein `location`-Objekt.

```
location();

location(
    const location& _Src);

location(
    T _LocationType,
    unsigned int _Id,
    unsigned int _BindingId = 0,
    _Inout_opt_ void* _PBinding = NULL);
```

### <a name="parameters"></a>Parameter

*_Src*<br/>

*_LocationType*<br/>

*_Id*<br/>

*_BindingId*<br/>

*_PBinding*<br/>
(Optional) Bindung Zeiger.

### <a name="remarks"></a>Hinweise

Ein Standardverzeichnis erstellt stellt das System als Ganzes dar.

##  <a name="operator_neq"></a> Operator! =

Bestimmt, ob zwei `location` Objekte darstellen, anderen Speicherort.

```
bool operator!= (const location& _Rhs) const;
```

### <a name="parameters"></a>Parameter

*_Rhs*<br/>
Operand `location`.

### <a name="return-value"></a>Rückgabewert

**"true"** Wenn die zwei Orten unterschiedlich sind, **"false"** andernfalls.

##  <a name="operator_eq"></a> Operator =

Weist den Inhalt von einem anderen `location` -Objekts in dieses Objekt.

```
location& operator= (const location& _Rhs);
```

### <a name="parameters"></a>Parameter

*_Rhs*<br/>
Das `location`-Quellobjekt.

### <a name="return-value"></a>Rückgabewert

##  <a name="operator_eq_eq"></a> Operator ==

Bestimmt, ob zwei `location` Objekte darstellen, am gleichen Speicherort.

```
bool operator== (const location& _Rhs) const;
```

### <a name="parameters"></a>Parameter

*_Rhs*<br/>
Operand `location`.

### <a name="return-value"></a>Rückgabewert

**"true"** Wenn es sich bei die beiden Standorten identisch sind und **"false"** andernfalls.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)
