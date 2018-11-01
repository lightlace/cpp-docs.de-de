---
title: Compilerwarnung (Stufe 1) C4630
ms.date: 11/04/2016
f1_keywords:
- C4630
helpviewer_keywords:
- C4630
ms.assetid: d8926376-7acc-4fc7-8438-6f0de3468870
ms.openlocfilehash: 98ea72bef0cb95163604144c1069a13c3b27d81c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50616254"
---
# <a name="compiler-warning-level-1-c4630"></a>Compilerwarnung (Stufe 1) C4630

'Symbol': Speicherklassenspezifizierer "Extern" nicht für Elementdefinition

Ein Datenmember oder eine Memberfunktion ist definiert als `extern`. Member können nicht extern und sein, jedoch können komplette Objekte. Der Compiler ignoriert die `extern` Schlüsselwort. Im folgende Beispiel wird die C4630 generiert:

```
// C4630.cpp
// compile with: /W1 /LD
class A {
   void func();
};

extern void A::func() {   // C4630, remove 'extern' to resolve
}
```