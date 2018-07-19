---
title: '&lt;limits&gt;-Enumerationen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- limits/std::float_denorm_style
- limits/std::float_round_style
ms.assetid: c86680a2-ba97-4ed9-8c20-a448857d7dc5
ms.openlocfilehash: 5795d146714c6eb00902518347138a98574679a8
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38960647"
---
# <a name="ltlimitsgt-enums"></a>&lt;limits&gt;-Enumerationen

|||
|-|-|
|[float_denorm_style](#float_denorm_style)|[float_round_style](#float_round_style)|

## <a name="float_denorm_style"></a> float_denorm_style Enumeration

Die Enumeration beschreibt die verschiedenen Methoden, die eine Implementierung für die Darstellung eines denormalisierten Gleitkommawerts auswählen kann – für Werte, die zu klein sind, um als normalisierte Werte dargestellt zu werden:

```cpp
enum float_denorm_style {
    denorm_indeterminate = -1,
    denorm_absent = 0,
    denorm_present = 1    };
```

### <a name="return-value"></a>Rückgabewert

Die Enumeration gibt Folgendes zurück:

- `denorm_indeterminate` Wenn das Vorhandensein oder fehlen von denormalisierten Formularen bei der Übersetzung nicht bestimmt werden kann.

- `denorm_absent` Wenn denormalisierte Formulare fehlen.

- `denorm_present` Wenn denormalisierte Formulare vorhanden sind.

### <a name="example"></a>Beispiel

Unter [numeric_limits::has_denorm](../standard-library/numeric-limits-class.md#has_denorm) finden Sie ein Beispiel, in dem auf die Werte dieser Enumeration zugegriffen werden kann.

## <a name="float_round_style"></a> float_round_style Enumeration

Die Enumeration beschreibt die verschiedenen Methoden, die eine Implementierung für die Rundung eines Gleitkommawerts auf einen ganzzahligen Wert auswählen kann.

```cpp
enum float_round_style {
    round_indeterminate = -1,
    round_toward_zero = 0,
    round_to_nearest = 1,
    round_toward_infinity = 2,
    round_toward_neg_infinity = 3    };
```

### <a name="return-value"></a>Rückgabewert

Die Enumeration gibt Folgendes zurück:

- `round_indeterminate` Wenn die Rundungsmethode nicht bestimmt werden kann.

- `round_toward_zero` Wenn in Richtung 0 (null).

- `round_to_nearest` Wenn die Rundung auf nächste ganze Zahl.

- `round_toward_infinity` Wenn die Runde von Null weg.

- `round_toward_neg_infinity` Wenn die Runde negativerer ganzer.

### <a name="example"></a>Beispiel

Unter [numeric_limits::round_style](../standard-library/numeric-limits-class.md#round_style) finden Sie ein Beispiel, in dem auf die Werte dieser Enumeration zugegriffen werden kann.

## <a name="see-also"></a>Siehe auch

[\<limits>](../standard-library/limits.md)<br/>
