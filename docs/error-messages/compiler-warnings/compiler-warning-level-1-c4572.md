---
title: Compilerwarnung (Stufe 1) C4572
ms.date: 11/04/2016
f1_keywords:
- C4572
helpviewer_keywords:
- C4572
ms.assetid: 482dee5a-29bd-4fc3-b769-9dfd4cd2a964
ms.openlocfilehash: e32509e4d32eef4f53b8d43a7db769844f1182c7
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "58781548"
---
# <a name="compiler-warning-level-1-c4572"></a>Compilerwarnung (Stufe 1) C4572

[ParamArray]-Attribut ist unter "/ CLR", und verwenden als veraltet markiert "..." Stattdessen

Es wurde ein veraltetes Format zum Angeben einer Liste variabler Argumente verwendet. Verwenden Sie beim Kompilieren für die CLR auslassungszeichensyntax anstelle von <xref:System.ParamArrayAttribute>. Weitere Informationen finden Sie unter [Variablenargumentlisten (...) (C++ / CLI) ](../../extensions/variable-argument-lists-dot-dot-dot-cpp-cli.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4572 generiert.

```
// C4572.cpp
// compile with: /clr /W1
void Func([System::ParamArray] array<int> ^);   // C4572
void Func2(... array<int> ^){}   // OK

int main() {
   Func2(1, 2, 3);
}
```