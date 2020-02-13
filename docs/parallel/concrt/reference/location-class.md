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
ms.openlocfilehash: 7f45ff6d3092bd7c27e81adddca72c9411f752d1
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77139822"
---
# <a name="location-class"></a>location-Klasse

Die Abstraktion eines physischen Speicherorts auf der Hardware.

## <a name="syntax"></a>Syntax

```cpp
class location;
```

## <a name="members"></a>Members

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[location](#ctor)|Ist überladen. Erstellt ein `location`-Objekt.|
|[~ Location-debugtor](#dtor)|Zerstört ein `location` -Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|BESCHREIBUNG|
|----------|-----------------|
|[Strömung](#current)|Gibt ein `location` Objekt zurück, das den spezifischsten Ort darstellt, an dem der aufrufende Thread ausgeführt wird.|
|[from_numa_node](#from_numa_node)|Gibt ein `location` Objekt zurück, das einen angegebenen NUMA-Knoten darstellt.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[operator!=](#operator_neq)|Bestimmt, ob zwei `location`-Objekte einen anderen Speicherort darstellen.|
|[operator=](#operator_eq)|Weist der den Inhalt eines anderen `location` Objekts zu.|
|[operator==](#operator_eq_eq)|Bestimmt, ob zwei `location`-Objekte denselben Speicherort darstellen.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`location`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** ConcRT. h

**Namespace:** Parallelität

## <a name="dtor"></a>~ Speicherort

Zerstört ein `location` -Objekt.

```cpp
~location();
```

## <a name="current"></a>Strömung

Gibt ein `location` Objekt zurück, das den spezifischsten Ort darstellt, an dem der aufrufende Thread ausgeführt wird.

```cpp
static location __cdecl current();
```

### <a name="return-value"></a>Rückgabewert

Ein Speicherort, der den spezifischsten Speicherort darstellt, den der aufrufende Thread ausführt.

## <a name="from_numa_node"></a>from_numa_node

Gibt ein `location` Objekt zurück, das einen angegebenen NUMA-Knoten darstellt.

```cpp
static location __cdecl from_numa_node(unsigned short _NumaNodeNumber);
```

### <a name="parameters"></a>Parameter

*_NumaNodeNumber*<br/>
Die NUMA-Knotennummer, für die ein Speicherort erstellt werden soll.

### <a name="return-value"></a>Rückgabewert

Ein Speicherort, der den durch den `_NumaNodeNumber`-Parameter angegebenen NUMA-Knoten darstellt.

## <a name="ctor"></a>Hotels

Erstellt ein `location`-Objekt.

```cpp
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
Optionale Bindungs Zeiger.

### <a name="remarks"></a>Bemerkungen

Ein standardmäßiger erstellter Speicherort stellt das System als Ganzes dar.

## <a name="operator_neq"></a>Operator! =

Bestimmt, ob zwei `location`-Objekte einen anderen Speicherort darstellen.

```cpp
bool operator!= (const location& _Rhs) const;
```

### <a name="parameters"></a>Parameter

*_Rhs*<br/>
Operand-`location`.

### <a name="return-value"></a>Rückgabewert

**true** , wenn sich die beiden Speicherorte unterscheiden, andernfalls **false** .

## <a name="operator_eq"></a>Operator =

Weist der den Inhalt eines anderen `location` Objekts zu.

```cpp
location& operator= (const location& _Rhs);
```

### <a name="parameters"></a>Parameter

*_Rhs*<br/>
Das `location`-Quellobjekt.

### <a name="return-value"></a>Rückgabewert

## <a name="operator_eq_eq"></a>Operator = =

Bestimmt, ob zwei `location`-Objekte denselben Speicherort darstellen.

```cpp
bool operator== (const location& _Rhs) const;
```

### <a name="parameters"></a>Parameter

*_Rhs*<br/>
Operand-`location`.

### <a name="return-value"></a>Rückgabewert

**true** , wenn die beiden Speicherorte identisch sind, andernfalls **false** .

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace](concurrency-namespace.md)
