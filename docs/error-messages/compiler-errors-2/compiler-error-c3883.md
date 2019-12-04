---
title: Compilerfehler C3883
ms.date: 11/04/2016
f1_keywords:
- C3883
helpviewer_keywords:
- C3883
ms.assetid: cdd1c1f4-f268-4469-9c62-d52303114b0c
ms.openlocfilehash: 9dbb0328aa1810d55f2d974aed822992b53101b5
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74736658"
---
# <a name="compiler-error-c3883"></a>Compilerfehler C3883

"var": ein statischer initonly-Datenmember muss initialisiert werden.

Eine mit [initonly](../../dotnet/initonly-cpp-cli.md) markierte Variable wurde nicht ordnungsgemäß initialisiert.

Im folgenden Beispiel wird C3883 generiert:

```cpp
// C3883.cpp
// compile with: /clr
ref struct Y1 {
   initonly
   static int staticConst1;   // C3883
};
```

Das folgende Beispiel zeigt eine mögliche Lösung:

```cpp
// C3883b.cpp
// compile with: /clr /c
ref struct Y1 {
   initonly
   static int staticConst2 = 0;
};
```

Im folgenden Beispiel wird gezeigt, wie in einem statischen Konstruktor initialisiert wird:

```cpp
// C3883c.cpp
// compile with: /clr /LD
ref struct Y1 {
   initonly
   static int staticConst1;

   static Y1() {
      staticConst1 = 0;
   }
};
```
