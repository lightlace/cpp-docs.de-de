---
title: Compilerfehler C3648
ms.date: 11/04/2016
f1_keywords:
- C3648
helpviewer_keywords:
- C3648
ms.assetid: 5d042989-41cb-4cd0-aa50-976b70146aaf
ms.openlocfilehash: 3b26be9890bbbdf6276c61023e6867160528e236
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74751832"
---
# <a name="compiler-error-c3648"></a>Compilerfehler C3648

Diese explizite Überschreibungs Syntax erfordert/clr: oldSyntax.

Beim Kompilieren für die neueste verwaltete Syntax fand der Compiler eine explizite Überschreibungs Syntax für frühere Versionen, die nicht mehr unterstützt wird.

Weitere Informationen finden Sie unter [explizite über](../../extensions/explicit-overrides-cpp-component-extensions.md)schreibungen.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3648 generiert:

```cpp
// C3648.cpp
// compile with: /clr
public interface struct I {
   void f();
};

public ref struct R : I {
   virtual void I::f() {}   // C3648
   // try the following line instead
   // virtual void f() = I::f{}
};
```
