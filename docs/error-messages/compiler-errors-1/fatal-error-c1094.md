---
title: Schwerwiegender Fehler C1094
ms.date: 11/04/2016
f1_keywords:
- C1094
helpviewer_keywords:
- C1094
ms.assetid: 9e1193b2-cb95-44f9-bf6f-019e0d41dd97
ms.openlocfilehash: 23891a783a018f6d84ea820af98992f61632984c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50469653"
---
# <a name="fatal-error-c1094"></a>Schwerwiegender Fehler C1094

"-Zmval1': Befehlszeilenoption ist nicht mit dem Wert, der zum Erstellen des vorkompilierten Headers verwendet ("-Zmval2 ")

Der Wert, der an übergebene ["/ Yc"](../../build/reference/yc-create-precompiled-header-file.md) muss der gleiche Wert, der an übergebene ["/ Yu"](../../build/reference/yu-use-precompiled-header-file.md) (**/Zm** Werte müssen in allen Kompilierungen, die verwenden, oder erstellen die gleiche vorkompilierte identisch sein Headerdatei).

Im folgende Beispiel wird die C1094 generiert:

```
// C1094.h
int func1();
```

und anschließend

```
// C1094.cpp
// compile with: /Yc"C1094.h" /Zm200
int u;
int main() {
   int sd = 32;
}
#include "C1094.h"
```

und anschließend

```
// C1094b.cpp
// compile with: /Yu"C1094.h" /Zm300 /c
#include "C1094.h"   // C1094 compile with /Zm200
void Test() {}
```