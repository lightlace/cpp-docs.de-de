---
title: Compilerfehler C3181
ms.date: 11/04/2016
f1_keywords:
- C3181
helpviewer_keywords:
- C3181
ms.assetid: 5d450f8b-6cef-4452-a0c4-2076e967451d
ms.openlocfilehash: e30ed7016ca3a4d4948a08c5c09268e52c9a407d
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761672"
---
# <a name="compiler-error-c3181"></a>Compilerfehler C3181

"Type": Ungültiger Operand für Operator.

An den [typeid](../../extensions/typeid-cpp-component-extensions.md) -Operator wurde ein ungültiger Parameter übergeben. Der-Parameter muss ein verwalteter Typ sein.

Beachten Sie, dass der Compiler Aliase für Native Typen verwendet, die Typen in der Common Language Runtime zugeordnet sind.

Im folgenden Beispiel wird C3181 generiert:

```cpp
// C3181a.cpp
// compile with: /clr
using namespace System;

int main() {
   Type ^pType1 = interior_ptr<int>::typeid;   // C3181
   Type ^pType2 = int::typeid;   // OK
}
```
