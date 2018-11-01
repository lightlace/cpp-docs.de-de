---
title: 'NMAKE: Schwerwiegender Fehler U1070'
ms.date: 11/04/2016
f1_keywords:
- U1070
helpviewer_keywords:
- U1070
ms.assetid: 8639fc39-b4b1-48f5-ac91-0e9fb61680fd
ms.openlocfilehash: 35bea47f6626dfe283a537d3d96340921c37f3f6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50484213"
---
# <a name="nmake-fatal-error-u1070"></a>NMAKE: Schwerwiegender Fehler U1070

Schleife in Makrodefinition "Makroname"

Die angegebene Makrodefinition enthalten ein Makro, deren Definition über das angegebene Makro enthalten. Zirkuläre Makrodefinitionen sind ungültig.

## <a name="example"></a>Beispiel

Die folgenden Makrodefinitionen

```
ONE=$(TWO)
TWO=$(ONE)
```

Führen Sie den folgenden Fehler:

```
cycle in macro definition 'TWO'
```