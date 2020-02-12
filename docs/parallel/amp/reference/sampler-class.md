---
title: Samplerklasse
ms.date: 06/28/2018
f1_keywords:
- sampler
- AMP_GRAPHICS/sampler
- AMP_GRAPHICS/concurrency::sampler::graphics::sampler
- AMP_GRAPHICS/concurrency::sampler::graphics::get_address_mode
- AMP_GRAPHICS/concurrency::sampler::graphics::get_border_color
- AMP_GRAPHICS/concurrency::sampler::graphics::get_filter_mode
- AMP_GRAPHICS/concurrency::sampler::graphics::address_mode
- AMP_GRAPHICS/concurrency::sampler::graphics::border_color
- AMP_GRAPHICS/concurrency::sampler::graphics::filter_mode
ms.assetid: 9a6a9807-497d-402d-b092-8c4d86275b80
ms.openlocfilehash: 8f47bf6e9b88dba1e94e9e2ed2b93c8d2d3f9b8c
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77126351"
---
# <a name="sampler-class"></a>Samplerklasse

Die Samplerklasse aggregiert Informationen für die Samplingkonfiguration, die für das Textursampling verwendet werden sollen.

## <a name="syntax"></a>Syntax

```cpp
class sampler;
```

## <a name="members"></a>Members

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[Sampler-Konstruktor](#ctor)|Ist überladen. Erstellt eine Samplerinstanz.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|BESCHREIBUNG|
|----------|-----------------|
|[get_address_mode](#get_address_mode)|Gibt das `address_mode`-Objekt zurück, das mit dem Samplerobjekt verknüpft ist.|
|[get_border_color](#get_border_color)|Gibt die Rahmenfarbe zurück, die dem Samplerobjekt verknüpft ist.|
|[get_filter_mode](#get_filter_mode)|Gibt das `filter_mode`-Objekt zurück, das mit dem Samplerobjekt verknüpft ist.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[operator=](#operator_eq)|Ist überladen. Zuweisungsoperator.|

### <a name="public-data-members"></a>Öffentliche Datenelemente

|Name|BESCHREIBUNG|
|----------|-----------------|
|[address_mode](#address_mode)|Ruft den Adressmodus des `sampler`-Objekts ab.|
|[border_color](#border_color)|Legt die Rahmenfarbe des `sampler`-Objekts fest.|
|[filter_mode](#filter_mode)|Ruft den Filtermodus des `sampler`-Objekts ab.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`sampler`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** amp_graphics. h

**Namespace:** Parallelität:: graphics

## <a name="ctor"></a>Sammel

Erstellt eine Instanz der [samplerklasse](sampler-class.md).

```cpp
sampler() restrict(cpu);    // [1] default constructor

sampler(                    // [2] constructor
    filter_mode _Filter_mode) restrict(cpu);

sampler(                    // [3] constructor
    address_mode _Address_mode,
    float_4 _Border_color = float_4(0.0f,
    0.0f,
    0.0f,
    0.0f)) restrict(cpu);

sampler(                    // [4] constructor
    filter_mode _Filter_mode,
    address_mode _Address_mode,
    float_4 _Border_color = float_4(0.0f,
    0.0f,
    0.0f,
    0.0f)) restrict(cpu);

sampler(                    // [5] copy constructor
    const sampler& _Other) restrict(amp,
    cpu);

sampler(                    // [6] move constructor
    sampler&& _Other) restrict(amp,
    cpu);
```

### <a name="parameters"></a>Parameter

*_Filter_mode*<br/>
Der im Sampling verwendete Filtermodus.

*_Address_mode*<br/>
Die im Sampling für alle Dimensionen zu verwendenden Adressierung.

*_Border_color*<br/>
Die zu verwendenden Rahmenfarbe, wenn der Adressmodus address_border lautet. Standardwert: `float_4(0.0f, 0.0f, 0.0f, 0.0f)`.

*_Other*<br/>
[5] kopieren Sie den Konstruktor des `sampler` Objekts, das in die neue `sampler` Instanz kopiert werden soll.

[6] bewegungskonstruktor das `sampler` Objekt, das in die neue `sampler` Instanz verschoben werden soll.

## <a name="address_mode"></a>address_mode

Ruft den Adressmodus des `sampler`-Objekts ab.

```cpp
__declspec(property(get= get_address_mode)) Concurrency::graphics::address_mode address_mode;
```

## <a name="border_color"></a>border_color

Legt die Rahmenfarbe des `sampler`-Objekts fest.

```cpp
__declspec(property(get= get_border_color)) Concurrency::graphics::float_4 border_color;
```

## <a name="filter_mode"></a>filter_mode

Ruft den Filtermodus des `sampler`-Objekts ab.

```cpp
__declspec(property(get= get_filter_mode)) Concurrency::graphics::filter_mode filter_mode;
```

## <a name="get_address_mode"></a>get_address_mode

Gibt den Filtermodus zurück, der für dieses `sampler`-Objekt konfiguriert ist.

```cpp
Concurrency::graphics::address_mode get_address_mode() const __GPU;
```

### <a name="return-value"></a>Rückgabewert

Der Adressmodus, der für den Sampler konfiguriert ist.

## <a name="get_border_color"></a>get_border_color

Gibt die Rahmenfarbe zurück, die für dieses `sampler`-Objekt konfiguriert ist.

```cpp
Concurrency::graphics::float_4 get_border_color() const restrict(amp, cpu);
```

### <a name="return-value"></a>Rückgabewert

Ein float_4-Objekt, das die Rahmenfarbe enthält.

## <a name="get_filter_mode"></a>get_filter_mode

Gibt den Filtermodus zurück, der für dieses `sampler`-Objekt konfiguriert ist.

```cpp
Concurrency::graphics::filter_mode get_filter_mode() const restrict(amp, cpu);
```

### <a name="return-value"></a>Rückgabewert

Der Filtermodus, der für den Sampler konfiguriert ist.

## <a name="operator_eq"></a>Operator =

Weist den Wert eines anderen Samplerobjekts einem vorhandenen Sampler zu.

```cpp
sampler& operator= (    // [1] copy assignment operator
    const sampler& _Other) restrict(amp, cpu);

sampler& operator= (    // [2] move assignment operator
    sampler&& _Other) restrict(amp, cpu);
```

### <a name="parameters"></a>Parameter

*_Other*<br/>
[1] Kopier Zuweisungs Operator das `sampler` Objekt, das in diese `sampler`kopiert werden soll.

[2] Bewegungs Zuweisungs Operator das `sampler` Objekt, das in diesen `sampler`verschoben werden soll.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf diese Samplerinstanz.

## <a name="see-also"></a>Weitere Informationen

[Concurrency::graphics Namespace](concurrency-graphics-namespace.md)
