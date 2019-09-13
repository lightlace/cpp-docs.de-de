---
title: Compilerwarnung (Stufe 1) C4319
ms.date: 01/18/2018
f1_keywords:
- C4319
helpviewer_keywords:
- C4319
ms.assetid: 1fac8048-9bd6-4552-a21c-192c67772bb9
ms.openlocfilehash: 2d5ae8fcf5a527031c3a974b227f713675f31ffa
ms.sourcegitcommit: effb516760c0f956c6308eeded48851accc96b92
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70926103"
---
# <a name="compiler-warning-level-1-c4319"></a>Compilerwarnung (Stufe 1) C4319

> "~": keine Erweiterung von "*Typ1*" auf "*Typ2*" mit größerer Größe

Das Ergebnis des **~** (bitweisen Komplement)-Operators ist nicht signiert und dann mit 0 (null) erweitert, wenn es in einen größeren Typ konvertiert wird.

## <a name="example"></a>Beispiel

Im folgenden Beispiel `~(a - 1)` wird als ein 32-Bit-Long-Ausdruck ohne Vorzeichen ausgewertet und dann in 64 Bits durch die Erweiterung 0 konvertiert. Dies kann zu unerwarteten Vorgangsergebnisse führen.

```cpp
// C4319.cpp
// compile with: cl /W4 C4319.cpp
int main() {
   unsigned long a = 0;
   unsigned long long q = 42;
   q = q & ~(a - 1);    // C4319 expected
}
```
