---
title: Compilerfehler C2524
ms.date: 11/04/2016
f1_keywords:
- C2524
helpviewer_keywords:
- C2524
ms.assetid: e71d17f5-2fc2-416b-8dbd-e9bed85eb33a
ms.openlocfilehash: 369aa5f21c072472808ffba06c3bc5c5e608ac22
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50640114"
---
# <a name="compiler-error-c2524"></a>Compilerfehler C2524

'Destruktor': ein Destruktor/Finalizer muss eine "void"-Parameterliste haben

Der Destruktor oder Finalizer hatte eine Parameterliste, die nicht ["void"](../../cpp/void-cpp.md). Andere Parametertypen sind nicht zulässig.

## <a name="example"></a>Beispiel

Der folgende Code wird C2524 generiert.

```
// C2524.cpp
// compile with: /c
class A {
   A() {}
   ~A(int i) {}    // C2524
   // try the following line instead
   // ~A() {}
};
```

## <a name="example"></a>Beispiel

Der folgende Code wird C2524 generiert.

```
// C2524_b.cpp
// compile with: /clr /c
ref struct I1 {
protected:
   !I1(int i);   // C2524
   // try the following line instead
   // !I1();
};
```