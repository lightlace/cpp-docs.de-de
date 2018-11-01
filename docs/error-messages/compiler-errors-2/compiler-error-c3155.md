---
title: Compilerfehler C3155
ms.date: 11/04/2016
f1_keywords:
- C3155
helpviewer_keywords:
- C3155
ms.assetid: b04a42e1-64e7-40f8-81fe-c7945348b2cf
ms.openlocfilehash: 85ee53dff7ae50717eabfd1ac6504ebb74deaa2d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50644359"
---
# <a name="compiler-error-c3155"></a>Compilerfehler C3155

in einem Eigenschaftenindexer sind keine Attribute zulässig.

Eine indizierte Eigenschaft wurde falsch deklariert. Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden von Eigenschaften in C++ / CLI](../../dotnet/how-to-use-properties-in-cpp-cli.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3155 generiert.

```
// C3155.cpp
// compile with: /clr /c
using namespace System;
ref struct R {
   property int F[[ParamArray] int] {   // C3155
   // try the following line instead
   // property int F[ int] {   // OK
      int get(int i) {
         return 0;
      }
   }
};
```