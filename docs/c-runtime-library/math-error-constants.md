---
title: Mathematische Fehlerkonstanten
ms.date: 11/04/2016
f1_keywords:
- _PLOSS
- _UNDERFLOW
- _TLOSS
- _SING
- _DOMAIN
- _OVERFLOW
helpviewer_keywords:
- _TLOSS constant
- _SING constant
- PLOSS constant
- UNDERFLOW constant
- _UNDERFLOW constant
- _OVERFLOW constant
- DOMAIN constant
- OVERFLOW constant
- TLOSS constant
- SING constant
- _DOMAIN constant
- _PLOSS constant
- math error constants
ms.assetid: 4be933a6-674e-45a5-8ac9-090023542f5b
ms.openlocfilehash: f51d9a3a28118d922f81a44e31c9abc610645f13
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2018
ms.locfileid: "51524989"
---
# <a name="math-error-constants"></a>Mathematische Fehlerkonstanten

## <a name="syntax"></a>Syntax

```

#include <math.h>
```

## <a name="remarks"></a>Hinweise

Die mathematischen Routinen der Laufzeitbibliothek können mathematische Fehlerkonstanten generieren.

Die im Folgenden beschriebenen Fehler entsprechen den Ausnahmetypen, die in MATH.H definiert sind, und werden von der `_matherr`-Funktion zurückgegeben, wenn ein mathematischer Fehler auftritt.

|Konstante|Bedeutung|
|--------------|-------------|
|`_DOMAIN`|Das Argument für die Funktion befindet sich außerhalb der Domäne der Funktion.|
|`_OVERFLOW`|Das Ergebnis ist zu groß, um im Rückgabetyp der Funktion dargestellt werden zu können.|
|`_PLOSS`|Ein teilweiser Signifikanzverlust ist aufgetreten.|
|`_SING`|Argumentsingularität: Das Argument für die Funktion enthält einen ungültigen Wert. (Beispiel: Es wird ein Wert von 0 an eine Funktion übergeben, die einen Wert ungleich null erfordert.)|
|`_TLOSS`|Ein Verlust der gesamten Signifikanz ist aufgetreten.|
|`_UNDERFLOW`|Das Ergebnis ist zu klein, um dargestellt werden zu können.|

## <a name="see-also"></a>Siehe auch

[_matherr](../c-runtime-library/reference/matherr.md)<br/>
[Globale Konstanten](../c-runtime-library/global-constants.md)