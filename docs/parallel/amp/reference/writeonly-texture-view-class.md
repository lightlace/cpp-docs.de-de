---
title: writeonly_texture_view-Klasse
ms.date: 11/04/2016
f1_keywords:
- writeonly_texture_view
- AMP_GRAPHICS/writeonly_texture_view
- AMP_GRAPHICS/Concurrency::graphics::writeonly_texture_view
- AMP_GRAPHICS/Concurrency::graphics::writeonly_texture_view::set
- AMP_GRAPHICS/Concurrency::graphics::rank Constant
ms.assetid: 8d117ad3-0a1c-41ae-b29c-7c95fdd4d04d
ms.openlocfilehash: 8978a548ed246c59d7e7f007f1180685c7343a14
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77126239"
---
# <a name="writeonly_texture_view-class"></a>writeonly_texture_view-Klasse

Bietet lesegeschützten Zugriff auf eine Textur.

## <a name="syntax"></a>Syntax

```cpp
template <
    typename value_type,
    int _Rank
>
class writeonly_texture_view;

template <
    typename value_type,
    int _Rank
>
class writeonly_texture_view<value_type, _Rank> : public details::_Texture_base<value_type, _Rank>;
```

### <a name="parameters"></a>Parameter

*value_type*<br/>
Der Typ der Elemente in der Textur.

*_Rank*<br/>
Der Rang der Textur.

## <a name="members"></a>Members

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|BESCHREIBUNG|
|----------|-----------------|
|`scalar_type`||
|`value_type`|Der Typ der Elemente in der Textur.|

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[writeonly_texture_view-Konstruktor](#ctor)|Initialisiert eine neue Instanz der Klasse `writeonly_texture_view`.|
|[~ writeonly_texture_view-Dekonstruktor](#ctor)|Zerstört das `writeonly_texture_view`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|BESCHREIBUNG|
|----------|-----------------|
|[set](#set)|Legt den Wert des Elements am angegebenen Index ab.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[operator=](#operator_eq)|Kopiert das angegebene `writeonly_texture_view` Objekt in dieses Objekt.|

### <a name="public-constants"></a>Öffentliche Konstanten

|Name|BESCHREIBUNG|
|----------|-----------------|
|[Rank-Konstante](#rank)|Ruft den Rang des `writeonly_texture_view`-Objekts ab.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`_Texture_base`

`writeonly_texture_view`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** amp_graphics. h

**Namespace:** Parallelität:: Grafiken

## <a name="dtor"></a>~ writeonly_texture_view

Zerstört das `writeonly_texture_view`-Objekt.

```cpp
~writeonly_texture_view() restrict(amp,cpu);
```

## <a name="operator_eq"></a>Operator =

Kopiert das angegebene `writeonly_texture_view` Objekt in dieses Objekt.

```cpp
writeonly_texture_view<value_type, _Rank>& operator= (
    const writeonly_texture_view<value_type, _Rank>& _Other) restrict(amp,cpu);
```

### <a name="parameters"></a>Parameter

*_Other*<br/>
`writeonly_texture_view` Objekt, aus dem kopiert werden soll.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das `writeonly_texture_view`-Objekt.

## <a name="rank"></a>gehören

Ruft den Rang des `writeonly_texture_view`-Objekts ab.

```cpp
static const int rank = _Rank;
```

## <a name="set"></a>Set

Legt den Wert des Elements am angegebenen Index ab.

```cpp
void set(
    const index<_Rank>& _Index,
    const value_type& value) const restrict(amp);
```

### <a name="parameters"></a>Parameter

*_Index*<br/>
Der Index des Elements.

*value*<br/>
Der neue Wert des Elements.

## <a name="ctor"></a>writeonly_texture_view

Initialisiert eine neue Instanz der Klasse `writeonly_texture_view`.

```cpp
writeonly_texture_view(
    texture<value_type,
    _Rank>& _Src) restrict(amp);

writeonly_texture_view(
    const writeonly_texture_view<value_type,
    _Rank>& _Src) restrict(amp,cpu);
```

### <a name="parameters"></a>Parameter

*_Rank*<br/>
Der Rang der Textur.

*value_type*<br/>
Der Typ der Elemente in der Textur.

*_Src*<br/>
Die Textur, die verwendet wird, um die `writeonly_texture_view`zu erstellen.

## <a name="see-also"></a>Weitere Informationen

[Concurrency::graphics Namespace](concurrency-graphics-namespace.md)
