---
title: Compilerfehler C3181
ms.date: 11/04/2016
f1_keywords:
- C3181
helpviewer_keywords:
- C3181
ms.assetid: 5d450f8b-6cef-4452-a0c4-2076e967451d
ms.openlocfilehash: dc848d4108ed4a1a7b6646647a1bbb1ec8dcadf7
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58781808"
---
# <a name="compiler-error-c3181"></a>Compilerfehler C3181

'Typ': Ungültiger Operand für den Operator

Ein ungültiger Parameter wurde übergeben, um die [Typeid](../../extensions/typeid-cpp-component-extensions.md) Operator. Der Parameter muss es sich um einen verwalteten Typ sein.

Beachten Sie, dass der Compiler Aliase für systemeigene Typen verwendet werden, die Typen in der common Language Runtime zugeordnet.

Im folgende Beispiel wird die C3181 generiert:

```
// C3181a.cpp
// compile with: /clr
using namespace System;

int main() {
   Type ^pType1 = interior_ptr<int>::typeid;   // C3181
   Type ^pType2 = int::typeid;   // OK
}
```
