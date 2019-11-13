---
title: Compilerwarnung (Stufe 1) C4552
ms.date: 11/04/2016
f1_keywords:
- C4552
helpviewer_keywords:
- C4552
ms.assetid: ebbbb5ee-1c19-45bd-b386-41a19630fc76
ms.openlocfilehash: b9f7fcd5a1949082aad75407f230db2e32dddd67
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966358"
---
# <a name="compiler-warning-level-1-c4552"></a>Compilerwarnung (Stufe 1) C4552

"Operator": Operator hat keine Auswirkung; Operator mit Nebeneffekt erwartet

Wenn eine Expression-Anweisung einen Operator ohne Nebeneffekte als Anfang des Ausdrucks aufweist, ist dies wahrscheinlich ein Fehler.

Fügen Sie den Ausdruck in Klammern ein, um diese Warnung zu überschreiben.

Im folgenden Beispiel wird C4552 generiert:

```cpp
// C4552.cpp
// compile with: /W1
int main() {
   int i, j;
   i + j;   // C4552
   // try the following line instead
   // (i + j);
}
```