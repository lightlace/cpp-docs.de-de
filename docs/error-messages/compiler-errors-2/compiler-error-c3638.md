---
title: Compilerfehler C3638
ms.date: 11/04/2016
f1_keywords:
- C3638
helpviewer_keywords:
- C3638
ms.assetid: 8d8bc5ca-75aa-480e-b6b6-3178fab51b1d
ms.openlocfilehash: 8b1ef7f4cb38653f0ccdfae5684eb2907a735af7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50486890"
---
# <a name="compiler-error-c3638"></a>Compilerfehler C3638

'Operator': die Boxing- und unboxing Konvertierungsoperatoren nicht neu definiert werden

Der Compiler definiert einen Konvertierungsoperator für jede verwaltete Klasse zur Unterstützung von impliziten Boxing. Dieser Operator kann nicht neu definiert werden.

Weitere Informationen finden Sie unter [implizites Boxing](../../windows/boxing-cpp-component-extensions.md).

Im folgende Beispiel wird die C3638 generiert:

```
// C3638.cpp
// compile with: /clr
value struct V {
   V(){}
   static operator V^(V);   // C3638
};

int main() {
   V myV;
   V ^ pmyV = myV;   // operator supports implicit boxing
}
```