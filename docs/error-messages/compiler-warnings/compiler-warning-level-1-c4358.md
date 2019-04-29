---
title: Compilerwarnung (Stufe 1) C4358
ms.date: 11/04/2016
f1_keywords:
- C4358
helpviewer_keywords:
- C4358
ms.assetid: a9848f84-14b3-405e-81bf-ee3e91a51511
ms.openlocfilehash: aebac17a343efedf678b55f8940004c85a2db708
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408380"
---
# <a name="compiler-warning-level-1-c4358"></a>Compilerwarnung (Stufe 1) C4358

'Operator': Rückgabetyp von kombinierten Delegaten ist nicht 'void'; Der zurückgegebene Wert ist nicht definiert

Zwei Delegaten kombiniert wurden, und der Rückgabewert ist nicht "void". Wenn zwei Delegaten mit nicht-Void-Rückgabe von Werten kombiniert werden, wird der Compiler nicht in der Lage, die richtige Zuweisung vornehmen, wenn der Rückgabewert des Delegaten verwendet wird.

Im folgende Beispiel wird die C4358 generiert:

```
// C4358.cpp
// compile with: /clr /W1
delegate int D();
delegate void E();

ref class X {
   int i;
public:
   X(int ii) : i(ii) {}
   int f() {
      return i;
   }
};

ref class Y {
   int i;
public:
   Y() {}
   void g() {}
};

int main() {
   D^ d = gcnew D(gcnew X(1), &X::f);
   D^ d2 = gcnew D(gcnew X(2), &X::f);

   d += d2;   // C4358
   int j = d();   // return value indeterminate

   E^ e = gcnew E(gcnew Y, &Y::g);
   E^ e2 = gcnew E(gcnew Y, &Y::g);
   e += e2;   // OK
}
```