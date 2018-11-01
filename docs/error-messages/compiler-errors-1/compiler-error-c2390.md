---
title: Compilerfehler C2390
ms.date: 11/04/2016
f1_keywords:
- C2390
helpviewer_keywords:
- C2390
ms.assetid: 06b749ee-d072-4db1-b229-715f2c0728b5
ms.openlocfilehash: 89f6ebb02326413e8dca67d333e555321da4e645
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50595871"
---
# <a name="compiler-error-c2390"></a>Compilerfehler C2390

'Bezeichner': 'Spezifizierer' ist eine inkorrekte Speicherklasse

Die Speicherklasse gilt nicht für die Bezeichner im globalen Gültigkeitsbereich. Anstelle der ungültige Klasse ist die Standardspeicherklasse dient.

Mögliche Lösungen:

- Wenn der Bezeichner einer Funktion ist, deklarieren Sie ihn mit `extern` Speicher.

- Wenn der Bezeichner ein formaler Parameter oder lokale Variable ist, deklarieren Sie es mit automatischem Speicher ein.

- Wenn der Bezeichner eine globale Variable ist, deklarieren Sie ihn mit keine Speicherklasse (Auto-Speicher) ein.

## <a name="example"></a>Beispiel

- Im folgende Beispiel wird die C2390 generiert:

```
// C2390.cpp
register int i;   // C2390

int main() {
   register int j;   // OK
}
```