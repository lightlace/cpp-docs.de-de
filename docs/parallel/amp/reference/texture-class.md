---
title: Texture-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
f1_keywords:
- texture
- AMP_GRAPHICS/texture
- AMP_GRAPHICS/concurrency::graphics::texture::texture
- AMP_GRAPHICS/concurrency::graphics::texture::copy_to
- AMP_GRAPHICS/concurrency::graphics::texture::data
- AMP_GRAPHICS/concurrency::graphics::texture::get
- AMP_GRAPHICS/concurrency::graphics::texture::get_associated_accelerator_view
- AMP_GRAPHICS/concurrency::graphics::texture::get_depth_pitch
- AMP_GRAPHICS/concurrency::graphics::texture::get_row_pitch
- AMP_GRAPHICS/concurrency::graphics::texture::set
- AMP_GRAPHICS/concurrency::graphics::texture::rank
- AMP_GRAPHICS/concurrency::graphics::texture::associated_accelerator_view
- AMP_GRAPHICS/concurrency::graphics::texture::depth_pitch
- AMP_GRAPHICS/concurrency::graphics::texture::row_pitch
dev_langs:
- C++
ms.assetid: 16e85d4d-e80a-474a-995d-8bf63fbdf34c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7ae251ace53f8a2a591a311cd389f7084099988e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46420124"
---
# <a name="texture-class"></a>texture-Klasse

Eine Textur ist ein Datenaggregat in einem `accelerator_view`-Objekt in der extent-Domäne. Es ist eine Auflistung von Variablen, eine für jedes Element in einer extent-Domäne. Jede Variable enthält einen Wert mit dem C++ primitivem Typ entspricht ( `unsigned int`, `int`, `float`, `double`), ein skalarer Typ ( `norm`, oder `unorm`), oder einem kurzen vektortyp entspricht.

## <a name="syntax"></a>Syntax

```
template <typename value_type,  int _Rank>
class texture;
```

#### <a name="parameters"></a>Parameter

*value_type*<br/>
Der Typ der Elemente in der Textur.

*_Rank*<br/>
Der Rang der Textur.

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|Beschreibung|
|----------|-----------------|
|`scalar_type`|Skalare Typen.|
|`value_type`|Werttypen.|

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[Texture-Konstruktor](#ctor)|Initialisiert eine neue Instanz der `texture`-Klasse.|
|[~ texture-Destruktor](#ctor)|Zerstört das `texture`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[copy_to](#copy_to)|Kopiert die `texture` Objekt, das das Ziel, indem Sie eine tiefe Kopie.|
|[data](#data)|Gibt einen CPU-Zeiger auf Rohdaten dieser Textur zurück.|
|[get](#get)|Gibt den Wert des Elements am angegebenen Index zurück.|
|[get_associated_accelerator_view](#get_associated_accelerator_view)|Gibt die ["accelerator_view"](accelerator-view-class.md) , das gewünschte Ziel zum Kopieren dieser Textur.|
|[get_depth_pitch](#get_depth_pitch)|Gibt die Anzahl von Bytes zwischen jedem Tiefensegment in einer 3D-Stagingtextur auf der CPU zurück.|
|[get_row_pitch](#get_row_pitch)|Gibt die Anzahl von Bytes zwischen jeder Zeile in einer 2D- oder 3D-Stagingtextur auf der CPU zurück.|
|[set](#set)|Legt den Wert des Elements am angegebenen Index ab.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[operator()](#operator_call)|Gibt den Elementwert zurück, der von den Parametern angegeben wird.|
|[operator[]](#operator_at)|Gibt das Element am angegebenen Index zurück.|
|[operator=](#operator_eq)|Kopiert das angegebene [Textur](texture-class.md) -Objekts in dieses Objekt.|

### <a name="public-constants"></a>Öffentliche Konstanten

|name|Beschreibung|
|----------|-----------------|
|[Rank-Konstante](#rank)|Ruft den Rang des `texture`-Objekts ab.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[associated_accelerator_view](#associated_accelerator_view)|Ruft die ["accelerator_view"](accelerator-view-class.md) , das gewünschte Ziel zum Kopieren dieser Textur.|
|[depth_pitch](#depth_pitch)|Ruft die Anzahl von Bytes zwischen jedem Tiefensegment in einer 3D-Stagingtextur auf der CPU ab.|
|[row_pitch](#row_pitch)|Ruft die Anzahl von Bytes zwischen jeder Zeile in einer 2D- oder 3D-Stagingtextur auf der CPU zurück.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`_Texture_base`

`texture`

## <a name="requirements"></a>Anforderungen

**Header:** amp_graphics.h

**Namespace:** Concurrency:: Graphics

##  <a name="dtor"></a> ~ Texture

Zerstört das `texture`-Objekt.

```
~texture() restrict(cpu);
```

##  <a name="associated_accelerator_view"></a> associated_accelerator_view

Ruft die ["accelerator_view"](accelerator-view-class.md) , das gewünschte Ziel zum Kopieren dieser Textur.

```
__declspec(property(get= get_associated_accelerator_view)) Concurrency::accelerator_view associated_accelerator_view;
```

##  <a name="copy_to"></a> copy_to

Kopiert die `texture` Objekt, das das Ziel, indem Sie eine tiefe Kopie.

```
void copy_to(texture& _Dest) const;
void copy_to(writeonly_texture_view<value_type, _Rank>& _Dest) const;
```

### <a name="parameters"></a>Parameter

*_Dest*<br/>
Das Objekt, in das kopiert werden soll.

*_Rank*<br/>
Der Rang der Textur.

*value_type*<br/>
Der Typ der Elemente in der Textur.

##  <a name="data"></a> Daten

Gibt einen CPU-Zeiger auf Rohdaten dieser Textur zurück.

```
void* data() restrict(cpu);

const void* data() const restrict(cpu);
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die Rohdaten der Textur.

##  <a name="depth_pitch"></a> depth_pitch

Ruft die Anzahl von Bytes zwischen jedem Tiefensegment in einer 3D-Stagingtextur auf der CPU ab.

```
__declspec(property(get= get_depth_pitch)) unsigned int depth_pitch;
```

##  <a name="get"></a> Erhalten

Gibt den Wert des Elements am angegebenen Index zurück.

```
const value_type get(const index<_Rank>& _Index) const restrict(amp);
```

### <a name="parameters"></a>Parameter

*_Index*<br/>
Der Index des Elements.

### <a name="return-value"></a>Rückgabewert

Der Wert des Elements am angegebenen Index.

##  <a name="get_associated_accelerator_view"></a> get_associated_accelerator_view

Gibt das accelerator_view-Objekt zurück, das das gewünschte Ziel zum Kopieren dieser Textur ist.

```
Concurrency::accelerator_view get_associated_accelerator_view() const restrict(cpu);
```

### <a name="return-value"></a>Rückgabewert

Die ["accelerator_view"](accelerator-view-class.md) , das gewünschte Ziel zum Kopieren dieser Textur.

##  <a name="get_depth_pitch"></a> get_depth_pitch

Gibt die Anzahl von Bytes zwischen jedem Tiefensegment in einer 3D-Stagingtextur auf der CPU zurück.

```
unsigned int get_depth_pitch() const restrict(cpu);
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl von Bytes zwischen jedem Tiefensegment in einer 3D-Stagingtextur auf der CPU.

##  <a name="get_row_pitch"></a> get_row_pitch

Gibt die Anzahl von Bytes zwischen jeder Zeile in einer zweidimensionalen Stagingtextur oder zwischen jeder Zeile eines Tiefensegments in einer dreidimensionalen Stagingtextur zurück.

```
unsigned int get_row_pitch() const restrict(cpu);
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl von Bytes zwischen jeder Zeile in einer zweidimensionalen Stagingtextur oder zwischen jeder Zeile eines Tiefensegments in einer dreidimensionalen Stagingtextur.

##  <a name="operator_call"></a> Operator()

Gibt den Elementwert zurück, der von den Parametern angegeben wird.

```
const value_type operator() (
    const index<_Rank>& _Index) const restrict(amp);

const value_type operator() (
    int _I0) const restrict(amp);

const value_type operator() (
    int _I0,
    int _I1) const restrict(amp);

const value_type operator() (
    int _I0,
    int _I1,
    int _I2) const restrict(amp);
```

### <a name="parameters"></a>Parameter

*_Index*<br/>
Der Index.

*_I0*<br/>
Die wichtigste Komponente des Index.

*_I1*<br/>
Die zweitwichtigste Komponente des Index.

*_I2*<br/>
Die unwichtigste Komponente des Index.

*_Rank*<br/>
Der Rang des Index.

### <a name="return-value"></a>Rückgabewert

Der Elementwert, der von den Parametern angegeben wird.

##  <a name="operator_at"></a> []-Operator

Gibt das Element am angegebenen Index zurück.

```
const value_type operator[] (const index<_Rank>& _Index) const restrict(amp);

const value_type operator[] (int _I0) const restrict(amp);
```

### <a name="parameters"></a>Parameter

*_Index*<br/>
Der Index.

*_I0*<br/>
Der Index.

### <a name="return-value"></a>Rückgabewert

Das Element am angegebenen Index.

##  <a name="operator_eq"></a> Operator =

Kopiert das angegebene [Textur](texture-class.md) -Objekts in dieses Objekt.

```
texture& operator= (
    const texture& _Other);

texture& operator= (
    texture<value_type, _Rank>&& _Other);
```

### <a name="parameters"></a>Parameter

*_Sonstige*<br/>
Das `texture`-Objekt, aus dem kopiert werden soll.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das `texture`-Objekt.

##  <a name="rank"></a> Rang

Ruft den Rang des `texture`-Objekts ab.

```
static const int rank = _Rank;
```

##  <a name="row_pitch"></a> row_pitch

Ruft die Anzahl von Bytes zwischen jeder Zeile in einer 2D- oder 3D-Stagingtextur auf der CPU zurück.

```
__declspec(property(get= get_row_pitch)) unsigned int row_pitch;
```

##  <a name="set"></a> Legen Sie

Legt den Wert des Elements am angegebenen Index ab.

```
void set(
    const index<_Rank>& _Index,
    const value_type& value) restrict(amp);
```

### <a name="parameters"></a>Parameter

*_Index*<br/>
Der Index des Elements.

*_Rank*<br/>
Der Rang des Index.

*Wert*<br/>
Der neue Wert des Elements.

##  <a name="ctor"></a> Textur

Initialisiert eine neue Instanz der `texture`-Klasse.

```
texture(const Concurrency::extent<_Rank>& _Ext) restrict(cpu);

texture(int _E0) restrict(cpu);

texture(int _E0, int _E1) restrict(cpu);

texture(int _E0, int _E1, int _E2) restrict(cpu);

texture(
    const Concurrency::extent<_Rank>& _Ext,
    const Concurrency::accelerator_view& _Av) restrict(cpu);

texture(
    int _E0,
    const Concurrency::accelerator_view& _Av) restrict(cpu);

texture(
    int _E0,
    int _E1,
    const Concurrency::accelerator_view& _Av) restrict(cpu);

texture(
    int _E0,
    int _E1,
    int _E2,
    const Concurrency::accelerator_view& _Av) restrict(cpu);

template<typename _Input_iterator>
texture(
    const Concurrency::extent<_Rank>& _Ext,
    _Input_iterator _Src_first,
    _Input_iterator _Src_last) restrict(cpu);

template<typename _Input_iterator>
texture(
    int _E0, _Input_iterator _Src_first, _Input_iterator _Src_last) restrict(cpu);

template<typename _Input_iterator>
texture(
    int _E0,
    int _E1,
    _Input_iterator _Src_first,
    _Input_iterator _Src_last) restrict(cpu);

template<typename _Input_iterator>
texture(
    int _E0,
    int _E1,
    int _E2,
    _Input_iterator _Src_first,
    _Input_iterator _Src_last) restrict(cpu);

template<typename _Input_iterator>
texture(
    const Concurrency::extent<_Rank>& _Ext,
    _Input_iterator _Src_first,
    _Input_iterator _Src_last,
    const Concurrency::accelerator_view& _Av) restrict(cpu);

template<typename _Input_iterator>
texture(
    int _E0,
    _Input_iterator _Src_first,
    _Input_iterator _Src_last,
    const Concurrency::accelerator_view& _Av) restrict(cpu);

template<typename _Input_iterator>
texture(
    int _E0,
    int _E1,
    _Input_iterator _Src_first,
    _Input_iterator _Src_last,
    const Concurrency::accelerator_view& _Av) restrict(cpu);

template<typename _Input_iterator>
texture(
    int _E0,
    int _E1,
    int _E2,
    _Input_iterator _Src_first,
    _Input_iterator _Src_last,
    const Concurrency::accelerator_view& _Av) restrict(cpu))  ;

texture(
    int _E0,
    unsigned int _Bits_per_scalar_element) restrict(cpu);

texture(
    int _E0,
    int _E1,
    unsigned int _Bits_per_scalar_element) restrict(cpu);

texture(
    int _E0,
    int _E1,
    int _E2,
    unsigned int _Bits_per_scalar_element) restrict(cpu);

texture(
    const Concurrency::extent<_Rank>& _Ext,
    unsigned int _Bits_per_scalar_element,
    const Concurrency::accelerator_view& _Av) restrict(cpu);

texture(
    int _E0,
    unsigned int _Bits_per_scalar_element,
    const Concurrency::accelerator_view& _Av)  ;

texture(
    int _E0,
    int _E1,
    unsigned int _Bits_per_scalar_element,
    const Concurrency::accelerator_view& _Av) restrict(cpu);

texture(
    int _E0,
    int _E1,
    int _E2,
    unsigned int _Bits_per_scalar_element,
    const Concurrency::accelerator_view& _Av) restrict(cpu);

texture(
    const Concurrency::extent<_Rank>& _Ext,
    _In_ void* _Source,
    unsigned int _Src_byte_size,
    unsigned int _Bits_per_scalar_element) restrict(cpu);

texture(
    int _E0,
    _In_ void* _Source,
    unsigned int _Src_byte_size,
    unsigned int _Bits_per_scalar_element) restrict(cpu);

texture(
    int _E0,
    int _E1,
    _In_ void* _Source,
    unsigned int _Src_byte_size,
    unsigned int _Bits_per_scalar_element) restrict(cpu);

texture(
    int _E0,
    int _E1,
    int _E2,
    _In_ void* _Source,
    unsigned int _Src_byte_size,
    unsigned int _Bits_per_scalar_element) restrict(cpu);

texture(
    const Concurrency::extent<_Rank>& _Ext,
    _In_ void* _Source,
    unsigned int _Src_byte_size,
    unsigned int _Bits_per_scalar_element,
    const Concurrency::accelerator_view& _Av)  ;

texture(
    int _E0,
    _In_ void* _Source,
    unsigned int _Src_byte_size,
    unsigned int _Bits_per_scalar_element,
    const Concurrency::accelerator_view& _Av) restrict(cpu);

texture(
    int _E0,
    int _E1,
    _In_ void* _Source,
    unsigned int _Src_byte_size,
    unsigned int _Bits_per_scalar_element,
    const Concurrency::accelerator_view& _Av) restrict(cpu);

texture(
    int _E0,
    int _E1,
    int _E2,
    _In_ void* _Source,
    unsigned int _Src_byte_size,
    unsigned int _Bits_per_scalar_element,
    const Concurrency::accelerator_view& _Av) restrict(cpu);

texture(
    const texture& _Src,
    const Concurrency::accelerator_view& _Acc_view);

texture(
    texture&& _Other);

texture(
    const Concurrency::extent<_Rank>& _Ext,
    unsigned int _Bits_per_scalar_element,
    const Concurrency::accelerator_view& _Av);

texture(
    const texture& _Src);
```

### <a name="parameters"></a>Parameter

*_Acc_view*<br/>
Die ["accelerator_view"](accelerator-view-class.md) , der den Speicherort der Textur angibt.

*_Av*<br/>
Die ["accelerator_view"](accelerator-view-class.md) , der den Speicherort der Textur angibt.

*_Associated_av*<br/>
Ein accelerator_view-Objekt, das das bevorzugte Ziel für Kopien in oder aus dieser Textur angibt.

*_Bits_per_scalar_element*<br/>
Die Anzahl von Bits für jedes skalare Element im zugrunde liegenden skalaren Typ der Textur. Im Allgemeinen werden die Werte 8, 16, 32 und 64 unterstützt. Wenn 0 festgelegt ist, ist die Anzahl von Bits mit der des zugrunde liegende scalar_type-Objekts identisch. 64 ist nur für doppeltbasierte Texturen gültig.

*_Ext*<br/>
Der Wertebereich in jeder Dimension der Textur.

*_E0*<br/>
Die wichtigste Komponente der Texture.

*_E1*<br/>
Die zweitwichtigste Komponente der Textur.

*_E2*<br/>
Die unwichtigste Komponente des Wertebereichs der Textur.

*_Input_iterator*<br/>
Der Typ des Eingabeiterators.

*_Mipmap_levels*<br/>
Die Anzahl von MipMap-Ebenen in der zugrunde liegenden Textur. Wenn 0 angegeben ist, verfügt die Textur über den Bereich der MipMap-Ebenen bis hin zur kleinsten möglichen Größe für den angegebenen Wertebereich.

*_Rank*<br/>
Der Rang des Wertebereichs.

*_Quelle*<br/>
Ein Zeiger auf einen Hostpuffer.

*_Src*<br/>
Die zu kopierende Textur.

*_Src_byte_size*<br/>
Die Anzahl von Bytes im Quellpuffer.

*_Src_first*<br/>
Ein Anfangsiterator in den Quellcontainer.

*_Src_last*<br/>
Ein Endeiterator in den Quellcontainer.

*_Sonstige*<br/>
Andere Datenquelle.

*_Rank*<br/>
Der Rang des Abschnitts.

## <a name="see-also"></a>Siehe auch

[Concurrency::graphics Namespace](concurrency-graphics-namespace.md)
