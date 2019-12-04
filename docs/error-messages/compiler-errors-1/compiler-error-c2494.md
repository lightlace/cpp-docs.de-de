---
title: Compilerfehler C2494
ms.date: 11/04/2016
f1_keywords:
- C2494
helpviewer_keywords:
- C2494
ms.assetid: 5dfd07ab-351d-49c9-b54e-f0a104776ab8
ms.openlocfilehash: e46eff4ec2b1afdb309b3c4db89c9283e2fc8971
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757032"
---
# <a name="compiler-error-c2494"></a>Compilerfehler C2494

' Keywords ' kann nicht innerhalb eines Filter Ausdrucks oder __finally/finally-Blocks aufgerufen werden.

`keyword` können nicht in einem `__finally` oder schließlich Block verwendet werden.

Im folgenden Beispiel wird C2494 generiert:

```cpp
// C2494.cpp
#include <malloc.h>

int main() {
   __try {}
   __except ( _alloca(100), 1 ) {}   // C2494
   __try {}
   __finally {
      _alloca(100);   // C2494
   }
}
```

C2494 kann auch auftreten, wenn **/CLR**verwendet wird.

```cpp
// C2494b.cpp
// compile with: /clr
#include <malloc.h>

int main() {
   char * buf;
   try {}
   catch (char * buf2) {}
   finally {
      _alloca(100);   // C2494
   }
}
```
