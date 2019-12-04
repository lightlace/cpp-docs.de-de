---
title: Compilerfehler C2247
ms.date: 11/04/2016
f1_keywords:
- C2247
helpviewer_keywords:
- C2247
ms.assetid: 72efa03e-615e-4ef9-aede-0a98654b20fd
ms.openlocfilehash: e82b406b20d77a824b62207b1766fec55ac65c5c
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758904"
---
# <a name="compiler-error-c2247"></a>Compilerfehler C2247

auf ' Identifier ' kann nicht zugegriffen werden, da ' class ' ' Spezifizierer ' verwendet, um von ' class ' zu erben.

`identifier` wird von einer Klasse geerbt, die mit privatem oder geschütztem Zugriff deklariert wurde.

Im folgenden Beispiel wird C2247 generiert:

```cpp
// C2247.cpp
class A {
public:
   int i;
};
class B : private A {};    // B inherits a private A
class C : public B {} c;   // so even though C's B is public
int j = c.i;               // C2247, i not accessible
```

Dieser Fehler kann auch infolge einer compilerübereinstimmungs-Arbeit generiert werden, die für Visual Studio .NET 2003: Zugriffs Steuerung mit geschützten Membern durchgeführt wurde. Auf einen geschützten Member (n) kann nur über eine Member-Funktion einer Klasse (B) zugegriffen werden, die von der Klasse (a) erbt, von der er (n) ein Member ist.

Für Code, der in Visual Studio .NET 2003 und Visual Studio .NET-Versionen von Visual C++Studio gültig ist, deklarieren Sie den Member als Friend des Typs. Die öffentliche Vererbung könnte auch verwendet werden.

```cpp
// C2247b.cpp
// compile with: /c
// C2247 expected
class A {
public:
   void f();
   int n;
};

class B: protected A {
   // Uncomment the following line to resolve.
   // friend void A::f();
};

void A::f() {
   B b;
   b.n;
}
```

C2247 kann auch als Ergebnis einer compilerübereinstimmungs-Arbeit generiert werden, die für Visual Studio .NET 2003 ausgeführt wurde: private Basisklassen, auf die jetzt nicht mehr zugegriffen werden kann. Eine Klasse (a), bei der es sich um eine private Basisklasse für einen Typ (b) handelt, sollte nicht für einen Typ (C) zugänglich sein, der B als Basisklasse verwendet.

Verwenden Sie für Code, der in Visual Studio .NET 2003-und Visual Studio .NET-Versionen von C++Visual Studio gültig ist, den Scope-Operator.

```cpp
// C2247c.cpp
// compile with: /c
struct A {};

struct B: private A {};

struct C : B {
   void f() {
      A *p1 = (A*) this;   // C2247
      // try the following line instead
      // ::A *p2 = (::A*) this;
   }
};
```
