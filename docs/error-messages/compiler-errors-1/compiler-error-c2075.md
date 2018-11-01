---
title: Compilerfehler C2075
ms.date: 11/04/2016
f1_keywords:
- C2075
helpviewer_keywords:
- C2075
ms.assetid: 8b1865d2-540b-4117-b982-e7a58a0b6cf7
ms.openlocfilehash: d53ef6f34b061a04f2c136b4e349d4951529b94b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50436308"
---
# <a name="compiler-error-c2075"></a>Compilerfehler C2075

"Bezeichner": für die Initialisierung eines Arrays sind geschweifte Klammern erforderlich

Der angegebene Arrayinitialisierer war nicht in geschweifte Klammern eingeschlossen.

Im folgenden Beispiel wird C2075 generiert:

```
// C2075.c
int main() {
   int i[] = 1, 2, 3 };   // C2075
}
```

Mögliche Lösung:

```
// C2075b.c
int main() {
   int j[] = { 1, 2, 3 };
}
```