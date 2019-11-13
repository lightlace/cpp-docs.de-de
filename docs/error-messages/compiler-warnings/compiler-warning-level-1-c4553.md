---
title: Compilerwarnung (Stufe 1) C4553
ms.date: 11/04/2016
f1_keywords:
- C4553
helpviewer_keywords:
- C4553
ms.assetid: d8aacbe0-3cb5-4367-a6e5-fd7e28f0ff9d
ms.openlocfilehash: a2d5e52e565878011b2439792c721eeb57cdd20a
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966323"
---
# <a name="compiler-warning-level-1-c4553"></a>Compilerwarnung (Stufe 1) C4553

"Operator": Operator hat keine Auswirkung; haben Sie ' Operator ' beabsichtigt?

Wenn eine Expression-Anweisung einen Operator ohne Nebeneffekte als Anfang des Ausdrucks aufweist, ist dies wahrscheinlich ein Fehler.

Im folgenden Beispiel wird C4553 generiert:

```cpp
// C4553.cpp
// compile with: /W1
int func()
{
   return 0;
}

int main()
{
   int i;
   i == func();   // C4553
   // try the following line instead
   // i = func();
}
```