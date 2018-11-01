---
title: norm_2-Klasse
ms.date: 11/04/2016
f1_keywords:
- amp_short_vectors/Concurrency::graphics::norm_2::set_x
- amp_short_vectors/Concurrency::graphics::norm_2::set_xy
- amp_short_vectors/Concurrency::graphics::norm_2::g
- amp_short_vectors/Concurrency::graphics::norm_2::get_yx
- amp_short_vectors/Concurrency::graphics::norm_2::set_yx
- amp_short_vectors/Concurrency::graphics::norm_2::operator-=
- amp_short_vectors/Concurrency::graphics::norm_2::operator/=
- amp_short_vectors/Concurrency::graphics::norm_2::operator*=
- amp_short_vectors/Concurrency::graphics::norm_2::yx
- amp_short_vectors/Concurrency::graphics::norm_2::y
- amp_short_vectors/Concurrency::graphics::norm_2::xy
- amp_short_vectors/Concurrency::graphics::norm_2::operator++
- amp_short_vectors/Concurrency::graphics::norm_2::operator-
- amp_short_vectors/Concurrency::graphics::norm_2::rg
- amp_short_vectors/Concurrency::graphics::norm_2::operator=
- amp_short_vectors/Concurrency::graphics::norm_2::get_y
- amp_short_vectors/Concurrency::graphics::norm_2::r
- amp_short_vectors/Concurrency::graphics::norm_2::get_x
- amp_short_vectors/Concurrency::graphics::norm_2::get_xy
- amp_short_vectors/Concurrency::graphics::norm_2::gr
- amp_short_vectors/Concurrency::graphics::norm_2::set_y
- amp_short_vectors/Concurrency::graphics::norm_2::x
- amp_short_vectors/Concurrency::graphics::norm_2::operator+=
- amp_short_vectors/Concurrency::graphics::norm_2
- amp_short_vectors/Concurrency::graphics::norm_2::operator--
ms.assetid: 80703f9b-61f4-414a-93fd-bc774f7d3393
ms.openlocfilehash: ebf1a80a695f1d25652f239f66d8d40c0e1099ec
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50542215"
---
# <a name="norm2-class"></a>norm_2-Klasse

Stellt einen kurzen Vektor aus zwei normalen Zahlen dar.

## <a name="syntax"></a>Syntax

```
class norm_2;
```

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|Beschreibung|
|----------|-----------------|
|`value_type`||

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[norm_2-Konstruktor](#ctor)|Überladen. Standardkonstruktor, initialisiert alle Elemente mit 0.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|norm_2::get_x||
|norm_2::get_xy||
|norm_2:: get_Y||
|norm_2::get_yx||
|norm_2::ref_g||
|norm_2::ref_r||
|norm_2::ref_x||
|norm_2::ref_y||
|norm_2::set_x||
|norm_2:: set_xy||
|norm_2:: set_y||
|norm_2::set_yx||

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|norm_2::-||
|norm_2:::||
|norm_2::operator*=||
|norm_2::operator/=||
|norm_2:: Operator++-||
|norm_2::operator+=||
|norm_2::operator=||
|norm_2:: Operator-=||

### <a name="public-constants"></a>Öffentliche Konstanten

|name|Beschreibung|
|----------|-----------------|
|[Size-Konstante](#norm_2__size)||

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|norm_2::g||
|norm_2::gr||
|norm_2::r||
|norm_2::rg||
|norm_2:: x||
|norm_2:: XY||
|norm_2::y||
|norm_2::yx||

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`norm_2`

## <a name="requirements"></a>Anforderungen

**Header:** amp_short_vectors.h

**Namespace:** Concurrency:: Graphics

##  <a name="ctor"></a> norm_2

Standardkonstruktor, initialisiert alle Elemente mit 0.

```
norm_2() restrict(amp,
    cpu);

norm_2(
    norm _V0,
    norm _V1) restrict(amp,
    cpu);

norm_2(
    float _V0,
    float _V1) restrict(amp,
    cpu);

norm_2(
    unorm _V0,
    unorm _V1) restrict(amp,
    cpu);

norm_2(
    norm _V) restrict(amp,
    cpu);

explicit norm_2(
    float _V) restrict(amp,
    cpu);

norm_2(
    const norm_2& _Other) restrict(amp,
    cpu);

explicit inline norm_2(
    const uint_2& _Other) restrict(amp,
    cpu);

explicit inline norm_2(
    const int_2& _Other) restrict(amp,
    cpu);

explicit inline norm_2(
    const float_2& _Other) restrict(amp,
    cpu);

explicit inline norm_2(
    const unorm_2& _Other) restrict(amp,
    cpu);

explicit inline norm_2(
    const double_2& _Other) restrict(amp,
    cpu);
```

### <a name="parameters"></a>Parameter

*_V0*<br/>
Der Wert, der 0-Element zu initialisieren.

*_V1*<br/>
Der Wert 1 Element initialisiert werden.

*_V*<br/>
Der Wert für die Initialisierung.

*_Sonstige*<br/>
Das Objekt, das zum Initialisieren verwendet.

##  <a name="norm_2__size"></a> Größe

```
static const int size = 2;
```

## <a name="see-also"></a>Siehe auch

[Concurrency::graphics Namespace](concurrency-graphics-namespace.md)
