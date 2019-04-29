---
title: Compilerfehler C3644
ms.date: 11/04/2016
f1_keywords:
- C3644
helpviewer_keywords:
- C3644
ms.assetid: 2e3f6c41-3ec5-4a01-82bc-f11b61ebe68e
ms.openlocfilehash: 6d147d6a5955208bbca1ccf9a2f2bcfe3f485b4f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385622"
---
# <a name="compiler-error-c3644"></a>Compilerfehler C3644

'Funktion': die Funktion zum Generieren von verwalteten Codes kann nicht kompiliert werden.

Das Vorhandensein von Schlüsselwörtern in einer Funktion bewirkt, dass die Funktion in systemeigenem Code kompiliert werden.

Im folgende Beispiel wird die C3644 generiert:

```
// C3644.cpp
// compile with: /clr
// processor: x86

void __clrcall Func2(int i) {
   __asm {}   // C3644
}
```