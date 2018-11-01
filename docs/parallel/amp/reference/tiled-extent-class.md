---
title: tiled_extent-Klasse
ms.date: 11/04/2016
f1_keywords:
- tiled_extent
- AMP/tiled_extent
- AMP/Concurrency::tiled_extent::tiled_extent
- AMP/Concurrency::tiled_extent::get_tile_extent
- AMP/Concurrency::tiled_extent::pad
- AMP/Concurrency::tiled_extent::truncate
- AMP/Concurrency::tiled_extent::tile_dim0
- AMP/Concurrency::tiled_extent::tile_dim1
- AMP/Concurrency::tiled_extent::tile_dim2
- AMP/Concurrency::tiled_extent::tile_extent
ms.assetid: 671ecaf8-c7b0-4ac8-bbdc-e30bd92da7c0
ms.openlocfilehash: 77d16eefa61fb30614cb6527792014cc8655abe0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50476894"
---
# <a name="tiledextent-class"></a>tiled_extent-Klasse

Ein `tiled_extent`-Objekt ist ein `extent`-Objekt einer bis drei Dimensionen, das den "extent"-Bereich in ein-, zwei- oder dreidimensionale Kacheln unterteilt.

### <a name="syntax"></a>Syntax

```
template <
    int _Dim0,
    int _Dim1,
    int _Dim2
>
class tiled_extent : public Concurrency::extent<3>;

template <
    int _Dim0,
    int _Dim1
>
class tiled_extent<_Dim0, _Dim1, 0> : public Concurrency::extent<2>;

template <
    int _Dim0
>
class tiled_extent<_Dim0, 0, 0> : public Concurrency::extent<1>;
```

### <a name="parameters"></a>Parameter

*_Dim0*<br/>
Die Länge der wichtigsten Dimension.

*_Dim1*<br/>
Die Länge der zweitwichtigsten Dimension.

*_Dim2*<br/>
Die Länge der unwichtigsten Dimension.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[Tiled_extent-Konstruktor](#ctor)|Initialisiert eine neue Instanz der `tiled_extent`-Klasse.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[get_tile_extent](#get_tile_extent)|Gibt ein `extent`-Objekt zurück, das die Werte der `tiled_extent`-Vorlagenargumente `_Dim0`, `_Dim1` und `_Dim2` erfasst.|
|[pad](#pad)|Gibt ein neues `tiled_extent`-Objekt mit den Wertebereichen zurück, die aufgerundet werden, um durch die Kacheldimensionen teilbar zu sein.|
|[truncate](#truncate)|Gibt ein neues `tiled_extent`-Objekt mit den Wertebereichen zurück, die abgerundet werden, um durch die Kacheldimensionen teilbar zu sein.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[operator=](#operator_eq)|Kopiert den Inhalt des angegebenen `tiled_index`-Objekts in dieses Objekt.|

### <a name="public-constants"></a>Öffentliche Konstanten

|name|Beschreibung|
|----------|-----------------|
|[tile_dim0-Konstante](#tile_dim0)|Speichert die Länge der wichtigsten Dimension.|
|[tile_dim1-Konstante](#tile_dim1)|Speichert die Länge der zweitwichtigsten Dimension.|
|[tile_dim2-Konstante](#tile_dim2)|Speichert die Länge der unwichtigsten Dimension.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[tile_extent](#tile_extent)|Ruft ein `extent`-Objekt ab, das die Werte der `tiled_extent`-Vorlagenargumente `_Dim0`, `_Dim1` und `_Dim2` erfasst.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`extent`

`tiled_extent`

## <a name="requirements"></a>Anforderungen

**Header:** amp.h

**Namespace:** Parallelität

## <a name="ctor"> </a>  Tiled_extent-Konstruktor

Initialisiert eine neue Instanz der `tiled_extent`-Klasse.

### <a name="syntax"></a>Syntax

```
tiled_extent();

tiled_extent(
    const Concurrency::extent<rank>& _Other );

tiled_extent(
    const tiled_extent& _Other );
```

### <a name="parameters"></a>Parameter

*_Sonstige*<br/>
Das `extent`- oder `tiled_extent`-Objekt, in das kopiert werden soll.

## <a name="get_tile_extent"> </a>  get_tile_extent

Gibt eine `extent` -Objekt, das die Werte der erfasst die `tiled_extent` Vorlagenargumente `_Dim0`, `_Dim1`, und `_Dim2`.

### <a name="syntax"></a>Syntax

```
Concurrency::extent<rank> get_tile_extent() const restrict(amp,cpu);
```

### <a name="return-value"></a>Rückgabewert

Ein `extent`-Objekt, das die Dimensionen dieser `tiled_extent`-Instanz erfasst.

## <a name="pad"> </a>  Auffüllzeichen

Gibt ein neues `tiled_extent`-Objekt mit den Wertebereichen zurück, die aufgerundet werden, um durch die Kacheldimensionen teilbar zu sein.

### <a name="syntax"></a>Syntax

```
tiled_extent pad() const;
```

### <a name="return-value"></a>Rückgabewert

Das neue `tiled_extent`-Objekts, nach Wert.
## <a name="truncate"> </a>  Abschneiden

Gibt ein neues `tiled_extent`-Objekt mit den Wertebereichen zurück, die abgerundet werden, um durch die Kacheldimensionen teilbar zu sein.

### <a name="syntax"></a>Syntax

```
tiled_extent truncate() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt ein neues `tiled_extent`-Objekt mit den Wertebereichen zurück, die abgerundet werden, um durch die Kacheldimensionen teilbar zu sein.

## <a name="operator_eq"> </a>  Operator =

Kopiert den Inhalt des angegebenen `tiled_index`-Objekts in dieses Objekt.

### <a name="syntax"></a>Syntax

```
tiled_extent&  operator= (
    const tiled_extent& _Other ) restrict (amp, cpu);
```

### <a name="parameters"></a>Parameter

*_Sonstige*<br/>
Das `tiled_index`-Objekt, aus dem kopiert werden soll.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf diese `tiled_index`-Instanz.

## <a name="tile_dim0"> </a>  tile_dim0

Speichert die Länge der wichtigsten Dimension.

### <a name="syntax"></a>Syntax

```
static const int tile_dim0 = _Dim0;
```

## <a name="tile_dim1"> </a>  tile_dim1

Speichert die Länge der zweitwichtigsten Dimension.

### <a name="syntax"></a>Syntax

```
static const int tile_dim1 = _Dim1;
```

## <a name="tile_dim2"> </a>  tile_dim2

Speichert die Länge der unwichtigsten Dimension.

### <a name="syntax"></a>Syntax

```
static const int tile_dim2 = _Dim2;
```

## <a name="tile_extent"> </a>  tile_extent
  Ruft eine `extent` -Objekt, das die Werte der erfasst die `tiled_extent` Vorlagenargumente `_Dim0`, `_Dim1`, und `_Dim2`.

### <a name="syntax"></a>Syntax

```
__declspec(property(get= get_tile_extent)) Concurrency::extent<rank> tile_extent;
```

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)
