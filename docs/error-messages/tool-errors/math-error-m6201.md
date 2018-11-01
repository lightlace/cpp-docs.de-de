---
title: Mathematischer Fehler M6201
ms.date: 11/04/2016
f1_keywords:
- M6201
helpviewer_keywords:
- M6201
ms.assetid: 4041c331-d9aa-4dd4-b565-7dbe0218538c
ms.openlocfilehash: 6d3f107de7e45653374036ecafaa864cb3eff5b0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50622104"
---
# <a name="math-error-m6201"></a>Mathematischer Fehler M6201

'Funktion': _DOMAIN-Fehler

Ein Argument für die angegebene Funktion war außerhalb der Domäne des zulässige Eingabewerte für diese Funktion.

## <a name="example"></a>Beispiel

```
result = sqrt(-1.0)   // C statement
result = SQRT(-1.0)   !  FORTRAN statement
```

Dieser Fehler führt zum Aufruf der `_matherr` -Funktion mit den Namen der Funktion, die Argumente und den Fehlertyp. Sie können Umschreiben der `_matherr` Funktion, um die Behandlung bestimmter Gleitkommaoperationen Laufzeit anpassen.