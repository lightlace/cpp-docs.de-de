---
title: Compilerfehler C3656
ms.date: 11/04/2016
f1_keywords:
- C3656
helpviewer_keywords:
- C3656
ms.assetid: 88965d85-73b0-4b35-8020-0650c9c94cd8
ms.openlocfilehash: 312fc4311120819fe6621d03e5ab6f7cab13cac9
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758280"
---
# <a name="compiler-error-c3656"></a>Compilerfehler C3656

"override": Überschreibungsspezifizierer kann nicht wiederholt werden

Ein explizites Überschreibungs Schlüsselwort kann nur einmal angegeben werden. Weitere Informationen finden Sie unter [explizite über](../../extensions/explicit-overrides-cpp-component-extensions.md)schreibungen.

Im folgenden Beispiel wird C3656 generiert:

```cpp
// C3656.cpp
// compile with: /clr /c
public interface struct O {
   int f();
};

public ref struct V : O {
   int f() override override { return 0; }   // C3656
   // try the following line instead
   // int f() override { return 0; }
};
```
