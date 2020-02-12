---
title: uint_2-Klasse
ms.date: 11/04/2016
f1_keywords:
- amp_short_vectors/Concurrency::graphics::uint_2::set_xy
- amp_short_vectors/Concurrency::graphics::uint_2::y
- amp_short_vectors/Concurrency::graphics::uint_2::gr
- amp_short_vectors/Concurrency::graphics::uint_2::operator-
- amp_short_vectors/Concurrency::graphics::uint_2::get_x
- amp_short_vectors/Concurrency::graphics::uint_2::operator-=
- amp_short_vectors/Concurrency::graphics::uint_2::r
- amp_short_vectors/Concurrency::graphics::uint_2::yx
- amp_short_vectors/Concurrency::graphics::uint_2::operator--
- amp_short_vectors/Concurrency::graphics::uint_2::set_yx
- amp_short_vectors/Concurrency::graphics::uint_2::operator=
- amp_short_vectors/Concurrency::graphics::uint_2::set_x
- amp_short_vectors/Concurrency::graphics::uint_2::operator+=
- amp_short_vectors/Concurrency::graphics::uint_2::get_y
- amp_short_vectors/Concurrency::graphics::uint_2::xy
- amp_short_vectors/Concurrency::graphics::uint_2::x
- amp_short_vectors/Concurrency::graphics::uint_2::get_xy
- amp_short_vectors/Concurrency::graphics::uint_2::set_y
- amp_short_vectors/Concurrency::graphics::uint_2
- amp_short_vectors/Concurrency::graphics::uint_2::operator*=
- amp_short_vectors/Concurrency::graphics::uint_2::get_yx
- amp_short_vectors/Concurrency::graphics::uint_2::operator/=
- amp_short_vectors/Concurrency::graphics::uint_2::g
- amp_short_vectors/Concurrency::graphics::uint_2::operator++
- amp_short_vectors/Concurrency::graphics::uint_2::rg
ms.assetid: 9fcc9129-72b1-4da7-9012-4d3be15f1c52
ms.openlocfilehash: 5f01e4d50dc3fab8d7cb909d1ea2f3d1801f0db0
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77126209"
---
# <a name="uint_2-class"></a>uint_2-Klasse

Stellt einen kurzen Vektor von zwei ganze Zahlen ohne Vorzeichen dar.

## <a name="syntax"></a>Syntax

```cpp
class uint_2;
```

## <a name="members"></a>Members

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|BESCHREIBUNG|
|----------|-----------------|
|`value_type`||

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[uint_2-Konstruktor](#ctor)|Ist überladen. Standardkonstruktor, initialisiert alle Elemente mit 0.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|BESCHREIBUNG|
|----------|-----------------|
|uint_2::get_x||
|uint_2::get_xy||
|uint_2:: get_Y||
|uint_2::get_yx||
|uint_2::ref_g_Method||
|uint_2::ref_r_Method||
|uint_2::ref_x_Method||
|uint_2::ref_y_Method||
|uint_2:: set_X||
|uint_2::set_xy||
|uint_2:: set_Y||
|uint_2::set_yx||

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|uint_2:: Operator--||
|uint_2::operator%=||
|uint_2:: Operator & =||
|uint_2::operator*=||
|uint_2::operator/=||
|uint_2::operator^=||
|uint_2::operator&#124;=||
|uint_2::operator~||
|uint_2::operator++||
|uint_2::operator+=||
|uint_2:: Operator <\<=||
|uint_2::operator=||
|uint_2:: Operator-=||
|uint_2:: Operator > > =||

### <a name="public-constants"></a>Öffentliche Konstanten

|Name|BESCHREIBUNG|
|----------|-----------------|
|[Größen Konstante](#uint_2__size)||

### <a name="public-data-members"></a>Öffentliche Datenelemente

|Name|BESCHREIBUNG|
|----------|-----------------|
|uint_2::g||
|uint_2::gr||
|uint_2::r||
|uint_2::rg||
|uint_2::x||
|uint_2::xy||
|uint_2::y||
|uint_2::yx||

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`uint_2`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** amp_short_vectors. h

**Namespace:** Parallelität:: Grafiken

## <a name="ctor"></a>uint_2

Standardkonstruktor, initialisiert alle Elemente mit 0.

```cpp
uint_2() restrict(amp,
    cpu);

uint_2(
    unsigned int _V0,
    unsigned int _V1) restrict(amp,
    cpu);

uint_2(
    unsigned int _V) restrict(amp,
    cpu);

uint_2(
    const uint_2& _Other) restrict(amp,
    cpu);

explicit inline uint_2(
    const int_2& _Other) restrict(amp,
    cpu);

explicit inline uint_2(
    const float_2& _Other) restrict(amp,
    cpu);

explicit inline uint_2(
    const unorm_2& _Other) restrict(amp,
    cpu);

explicit inline uint_2(
    const norm_2& _Other) restrict(amp,
    cpu);

explicit inline uint_2(
    const double_2& _Other) restrict(amp,
    cpu);
```

### <a name="parameters"></a>Parameter

*_V0*<br/>
Der Wert, mit dem Element 0 initialisiert werden soll.

*_V1*<br/>
Der Wert, mit dem Element 1 initialisiert werden soll.

*_V*<br/>
Der Wert für die Initialisierung.

*_Other*<br/>
Das-Objekt, das zum Initialisieren von verwendet wird.

## <a name="uint_2__size"></a>Größe

```cpp
static const int size = 2;
```

## <a name="see-also"></a>Weitere Informationen

[Concurrency::graphics Namespace](concurrency-graphics-namespace.md)
