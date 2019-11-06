---
title: Compilerwarnung C4484
ms.date: 11/04/2016
f1_keywords:
- C4484
helpviewer_keywords:
- C4484
ms.assetid: 3d30e5b3-2297-45b7-a37a-1360056fdd0e
ms.openlocfilehash: 4d3f72ddf7675ea7ad73022dc55a60fdc74d4390
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2019
ms.locfileid: "73623631"
---
# <a name="compiler-warning-c4484"></a>Compilerwarnung C4484

"override_function": stimmt mit der "base_class_function"-Basis Methode der Verweis Klasse überein, ist jedoch nicht als "Virtual", "New" oder "override" markiert. "New" (und nicht "Virtual") wird angenommen.

Beim Kompilieren mit **/CLR**überschreibt der Compiler eine Basisklassen Funktion nicht implizit, was bedeutet, dass die Funktion einen neuen Slot in der vtable erhält. Um aufzulösen, geben Sie explizit an, ob eine Funktion eine außer Kraft Setzung ist.

Weitere Informationen finden Sie unter:

- [/clr (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md)

- [override](../../extensions/override-cpp-component-extensions.md)

- [new (neuer Slot in vtable)](../../extensions/new-new-slot-in-vtable-cpp-component-extensions.md)

C4484 wird immer als Fehler ausgegeben. Verwenden Sie das [Warning](../../preprocessor/warning.md) -Pragma, um C4484 zu unterdrücken.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4484 generiert.

```cpp
// C4484.cpp
// compile with: /clr
ref struct A {
   virtual void Test() {}
};

ref struct B : A {
   void Test() {}   // C4484
};

// OK
ref struct C {
   virtual void Test() {}
   virtual void Test2() {}
};

ref struct D : C {
   virtual void Test() new {}
   virtual void Test2() override {}
};
```