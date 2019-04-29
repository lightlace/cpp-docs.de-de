---
title: Compilerwarnung (Stufe 1) C4319
ms.date: 1/18/2018
f1_keywords:
- C4319
helpviewer_keywords:
- C4319
ms.assetid: 1fac8048-9bd6-4552-a21c-192c67772bb9
ms.openlocfilehash: 20b268bacd6e7e259e9b4fa1c9e98fa6fd353718
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385471"
---
# <a name="compiler-warning-level-1-c4319"></a>Compilerwarnung (Stufe 1) C4319

> "~": Null erweitert "*type1*'to'*Typ2*" größeren

Das Ergebnis der **~** (bitweiser Komplementoperator) ist nicht signiert und anschließend mit 0 erweitert, wenn es in einen größeren Typ konvertiert wird.

## <a name="example"></a>Beispiel

Im folgenden Beispiel `~(a - 1)` als ein 32-Bit-unsigned long-Ausdruck ausgewertet, und klicken Sie dann in 64 Bits konvertiert, von NULL-Erweiterung. Dies kann zu unerwarteten Vorgangsergebnisse führen.

```cpp
// C4319.cpp
// compile with: cl /W4 C4319.cpp
int main() {
   unsigned long a = 0;
   unsigned long long q = 42;
   q = q & ~(a - 1);    // C4319 expected
}
```
