---
title: 'Concurrency:: Graphics-Namespace | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
f1_keywords:
- AMP_GRAPHICS/Concurrency
dev_langs:
- C++
ms.assetid: 4529d3b1-d7da-4ffb-82bf-080915e0f23e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 31abd263f2536d0f2e73a3dfb35cad0eaa29e818
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46387197"
---
# <a name="concurrencygraphics-namespace"></a>Concurrency::graphics-Namespace

Der Grafiknamespace stellt Typen und Funktionen bereit, die für die Grafikprogrammierung vorgesehen sind.

## <a name="syntax"></a>Syntax

```
namespace graphics;
```

## <a name="members"></a>Member

### <a name="namespaces"></a>Namespaces

|Name|Beschreibung|
|----------|-----------------|
|[Concurrency::graphics::direct3d Namespace](concurrency-graphics-direct3d-namespace.md)|Stellt Funktionen für Direct3D-Interop bereit.|

### <a name="typedefs"></a>Typedefs

|Name|Beschreibung|
|----------|-----------------|
|`uint`|Der Elementtyp für [uint_2-Klasse](uint-2-class.md), [uint_3-Klasse](uint-3-class.md), und [uint_4-Klasse](uint-4-class.md). Definiert als `typedef unsigned int uint;`.|

### <a name="enumerations"></a>Enumerationen

|name|Beschreibung|
|----------|-----------------|
|[Address_mode-Enumeration](concurrency-graphics-namespace-enums.md#address_mode).|Gibt die unterstützten Adressmodi für das Textursampling an.|
|[Filter_mode-Enumeration](concurrency-graphics-namespace-enums.md#filter_mode)|Gibt die unterstützten Filtermodi für das Textursampling an.|

### <a name="classes"></a>Klassen

|Name|Beschreibung|
|----------|-----------------|
|[texture-Klasse](texture-class.md)|Eine Textur ist ein Datenaggregat in einer "accelerator_view" in der extent-Domäne. Es ist eine Auflistung von Variablen, eine für jedes Element in einer extent-Domäne. Jede Variable enthält einen Wert gemäß primitivem C++-Typ ohne Vorzeichen (int, int, Float, Double) oder skalarer Typnorm bzw. unorm (definiert in concurrency::graphics) oder zulässige kurze Vektortypen, die in concurrency::graphics definiert werden.|
|[writeonly_texture_view-Klasse](writeonly-texture-view-class.md)|Eine "writeonly_texture_view" bietet Nur-Schreib-Zugriff auf eine Textur.|
|[double_2-Klasse](double-2-class.md)|Stellt einen kurzen Vektor von 2 `double`-Werten dar.|
|[double_3-Klasse](double-3-class.md)|Stellt einen kurzen Vektor von 3 `double` Werte.|
|[double_4-Klasse](double-4-class.md)|Stellt einen kurzen Vektor von 4 `double` Werte.|
|[float_2-Klasse](float-2-class.md)|Stellt einen kurzen Vektor von 2 `float`-Werten dar.|
|[float_3-Klasse](float-3-class.md)|Stellt einen kurzen Vektor von 3 `float` Werte.|
|[float_4-Klasse](float-4-class.md)|Stellt einen kurzen Vektor von 4 `float` Werte.|
|[int_2-Klasse](int-2-class.md)|Stellt einen kurzen Vektor von 2 `int`-Werten dar.|
|[int_3-Klasse](int-3-class.md)|Stellt einen kurzen Vektor von 3 `int` Werte.|
|[int_4-Klasse](int-4-class.md)|Stellt einen kurzen Vektor von 4 `int` Werte.|
|[norm_2-Klasse](norm-2-class.md)|Stellt einen kurzen Vektor von 2 `norm`-Werten dar.|
|[norm_3-Klasse](norm-3-class.md)|Stellt einen kurzen Vektor von 3 `norm` Werte.|
|[norm_4-Klasse](norm-4-class.md)|Stellt einen kurzen Vektor von 4 `norm` Werte.|
|[uint_2-Klasse](uint-2-class.md)|Stellt einen kurzen Vektor von 2 `uint`-Werten dar.|
|[uint_3-Klasse](uint-3-class.md)|Stellt einen kurzen Vektor von 3 `uint` Werte.|
|[uint_4-Klasse](uint-4-class.md)|Stellt einen kurzen Vektor von 4 `uint` Werte.|
|[unorm_2-Klasse](unorm-2-class.md)|Stellt einen kurzen Vektor von 2 `unorm`-Werten dar.|
|[unorm_3-Klasse](unorm-3-class.md)|Stellt einen kurzen Vektor von 3 `unorm` Werte.|
|[unorm_4-Klasse](unorm-4-class.md)|Stellt einen kurzen Vektor von 4 `unorm` Werte.|
|[sampler-Klasse](sampler-class.md)|Stellt die Samplerkonfiguration dar, die für Textursampling verwendet wird.|
|[short_vector-Struktur](short-vector-structure.md)|Stellt eine grundlegende Implementierung eines kurzen Vektors von Werten.|
|[short_vector_traits-Struktur](short-vector-traits-structure.md)|Stellt das Abrufen der Länge und des Typs eines kurzen Vektors bereit.|
|[texture_view-Klasse](texture-view-class.md)|Stellt einer Textur Lese- und Schreibzugriff zur Verfügung.|

### <a name="functions"></a>Funktionen

|Name|Beschreibung|
|----------|-----------------|
|[copy](concurrency-graphics-namespace-functions.md#copy)|Überladen. Kopiert den Inhalt der Quelltextur in den Zielhostpuffer.|
|[copy_async](concurrency-graphics-namespace-functions.md#copy_async)|Überladen. Kopiert den Inhalt der Quelltextur asynchron in den Zielhostpuffer.|

## <a name="requirements"></a>Anforderungen

**Header:** amp_graphics.h

**Namespace:** Parallelität

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)
