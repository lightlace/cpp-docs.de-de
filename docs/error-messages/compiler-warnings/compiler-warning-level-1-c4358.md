---
title: Compilerwarnung (Stufe 1) C4358
ms.date: 11/04/2016
f1_keywords:
- C4358
helpviewer_keywords:
- C4358
ms.assetid: a9848f84-14b3-405e-81bf-ee3e91a51511
ms.openlocfilehash: 7fd3109df3ecd32933b5fc217dfc02181f43d97c
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966537"
---
# <a name="compiler-warning-level-1-c4358"></a>Compilerwarnung (Stufe 1) C4358

"Operator": der Rückgabetyp von kombinierten Delegaten ist nicht "void". der zurückgegebene Wert ist nicht definiert

Zwei Delegaten wurden kombiniert, und der Rückgabewert ist nicht "void". Wenn zwei Delegaten mit nicht leeren Rückgabe Werten kombiniert werden, kann der Compiler keine ordnungsgemäße Zuweisung durchführen, wenn der Rückgabewert des Delegaten verwendet wird.

Im folgenden Beispiel wird C4358 generiert:

```cpp
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