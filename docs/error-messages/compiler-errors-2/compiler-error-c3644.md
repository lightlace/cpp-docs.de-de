---
title: Compilerfehler C3644
ms.date: 11/04/2016
f1_keywords:
- C3644
helpviewer_keywords:
- C3644
ms.assetid: 2e3f6c41-3ec5-4a01-82bc-f11b61ebe68e
ms.openlocfilehash: b89ecc1e370edfb4d1365b3c7a7c42b29d5f1c6c
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757851"
---
# <a name="compiler-error-c3644"></a>Compilerfehler C3644

"Funktion": die Funktion kann nicht kompiliert werden, um verwalteten Code zu generieren.

Das vorhanden sein einiger Schlüsselwörter in einer Funktion bewirkt, dass die Funktion in System eigen kompiliert wird.

Im folgenden Beispiel wird C3644 generiert:

```cpp
// C3644.cpp
// compile with: /clr
// processor: x86

void __clrcall Func2(int i) {
   __asm {}   // C3644
}
```
