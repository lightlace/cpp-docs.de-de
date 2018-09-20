---
title: Sampler-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/28/2018
ms.technology:
- cpp-amp
ms.topic: reference
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
dev_langs:
- C++
ms.assetid: 9a6a9807-497d-402d-b092-8c4d86275b80
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ee5d50976b6d91bff6d84ec288560ff1348c73d9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46424689"
---
# <a name="sampler-class"></a>Samplerklasse

Die Samplerklasse aggregiert Informationen für die Samplingkonfiguration, die für das Textursampling verwendet werden sollen.

## <a name="syntax"></a>Syntax

```cpp
class sampler;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[Sampler-Konstruktor](#ctor)|Überladen. Erstellt eine Samplerinstanz.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[get_address_mode](#get_address_mode)|Gibt das `address_mode`-Objekt zurück, das mit dem Samplerobjekt verknüpft ist.|
|[get_border_color](#get_border_color)|Gibt die Rahmenfarbe zurück, die dem Samplerobjekt verknüpft ist.|
|[get_filter_mode](#get_filter_mode)|Gibt das `filter_mode`-Objekt zurück, das mit dem Samplerobjekt verknüpft ist.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[operator=](#operator_eq)|Überladen. Zuweisungsoperator.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[address_mode](#address_mode)|Ruft den Adressmodus des `sampler`-Objekts ab.|
|[border_color](#border_color)|Legt die Rahmenfarbe des `sampler`-Objekts fest.|
|[filter_mode](#filter_mode)|Ruft den Filtermodus des `sampler`-Objekts ab.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`sampler`

## <a name="requirements"></a>Anforderungen

**Header:** amp_graphics.h

**Namespace:** Concurrency:: Graphics

##  <a name="ctor"></a> Sampler

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
Die zu verwendenden Rahmenfarbe, wenn der Adressmodus address_border lautet. Der Standardwert ist `float_4(0.0f, 0.0f, 0.0f, 0.0f)`.

*_Sonstige*<br/>
[5]-Kopierkonstruktor der `sampler` zu kopierende in das neue Objekt `sampler` Instanz.

[6]-Bewegungskonstruktor die `sampler` Objekt, das Verschieben in das neue `sampler` Instanz.

##  <a name="address_mode"></a> address_mode

Ruft den Adressmodus des `sampler`-Objekts ab.

```cpp
__declspec(property(get= get_address_mode)) Concurrency::graphics::address_mode address_mode;
```

##  <a name="border_color"></a> border_color

Legt die Rahmenfarbe des `sampler`-Objekts fest.

```cpp
__declspec(property(get= get_border_color)) Concurrency::graphics::float_4 border_color;
```

##  <a name="filter_mode"></a> filter_mode

Ruft den Filtermodus des `sampler`-Objekts ab.

```cpp
__declspec(property(get= get_filter_mode)) Concurrency::graphics::filter_mode filter_mode;
```

##  <a name="get_address_mode"></a> get_address_mode

Gibt den Filtermodus zurück, der für dieses `sampler`-Objekt konfiguriert ist.

```cpp
Concurrency::graphics::address_mode get_address_mode() const __GPU;
```

### <a name="return-value"></a>Rückgabewert

Der Adressmodus, der für den Sampler konfiguriert ist.

##  <a name="get_border_color"></a> get_border_color

Gibt die Rahmenfarbe zurück, die für dieses `sampler`-Objekt konfiguriert ist.

```cpp
Concurrency::graphics::float_4 get_border_color() const restrict(amp, cpu);
```

### <a name="return-value"></a>Rückgabewert

Ein float_4-Objekt, das die Rahmenfarbe enthält.

##  <a name="get_filter_mode"></a> get_filter_mode

Gibt den Filtermodus zurück, der für dieses `sampler`-Objekt konfiguriert ist.

```cpp
Concurrency::graphics::filter_mode get_filter_mode() const restrict(amp, cpu);
```

### <a name="return-value"></a>Rückgabewert

Der Filtermodus, der für den Sampler konfiguriert ist.

##  <a name="operator_eq"></a> Operator =

Weist den Wert eines anderen Samplerobjekts einem vorhandenen Sampler zu.

```cpp
sampler& operator= (    // [1] copy assignment operator
    const sampler& _Other) restrict(amp, cpu);

sampler& operator= (    // [2] move assignment operator
    sampler&& _Other) restrict(amp, cpu);
```

### <a name="parameters"></a>Parameter

*_Sonstige*<br/>
[1]-Kopierzuweisungsoperator der `sampler` Objekt, das in diese kopiert `sampler`.

[2] Move-Zuweisungsoperator der `sampler` Objekt zum Umwandeln dieses `sampler`.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf diese Samplerinstanz.

## <a name="see-also"></a>Siehe auch

[Concurrency::graphics Namespace](concurrency-graphics-namespace.md)
