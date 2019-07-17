---
title: '&lt;limits&gt;-Enumerationen'
ms.date: 11/04/2016
f1_keywords:
- limits/std::float_denorm_style
- limits/std::float_round_style
ms.assetid: c86680a2-ba97-4ed9-8c20-a448857d7dc5
ms.openlocfilehash: 567e0538f59c40d57f85d652a8919be6e034cf0b
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68245354"
---
# <a name="ltlimitsgt-enums"></a>&lt;limits&gt;-Enumerationen

## <a name="float_denorm_style"></a> float_denorm_style

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

## <a name="float_round_style"></a> float_round_style

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
