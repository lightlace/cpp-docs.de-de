---
title: Compilerfehler C2711
ms.date: 11/04/2016
f1_keywords:
- C2711
helpviewer_keywords:
- C2711
ms.assetid: 9df9f808-7419-4e63-abdd-e6538ff0871f
ms.openlocfilehash: 65612e4a7d19295a8fa49576fb1d72c852a76b82
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757435"
---
# <a name="compiler-error-c2711"></a>Compilerfehler C2711

"Function": Diese Funktion kann nicht als verwaltet kompiliert werden. verwenden Sie #pragma nicht verwaltete

Einige Anweisungen verhindern, dass der Compiler MSIL für die einschließende Funktion erzeugt.

Im folgenden Beispiel wird C2711 generiert:

```cpp
// C2711.cpp
// compile with: /clr
// processor: x86
using namespace System;
value struct V {
   static const t = 10;
};

void bar() {
   V::t;
   __asm int 3   // C2711 inline asm can't be compiled managed
}
```
