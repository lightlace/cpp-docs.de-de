---
title: Compilerfehler C3638
ms.date: 11/04/2016
f1_keywords:
- C3638
helpviewer_keywords:
- C3638
ms.assetid: 8d8bc5ca-75aa-480e-b6b6-3178fab51b1d
ms.openlocfilehash: 33bb248faf946c39543de4a14a44e2ebbda49880
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385887"
---
# <a name="compiler-error-c3638"></a>Compilerfehler C3638

'Operator': die Boxing- und unboxing Konvertierungsoperatoren nicht neu definiert werden

Der Compiler definiert einen Konvertierungsoperator für jede verwaltete Klasse zur Unterstützung von impliziten Boxing. Dieser Operator kann nicht neu definiert werden.

Weitere Informationen finden Sie unter [implizites Boxing](../../extensions/boxing-cpp-component-extensions.md).

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