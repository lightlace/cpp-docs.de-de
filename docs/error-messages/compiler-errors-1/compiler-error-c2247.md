---
title: Compilerfehler C2247
ms.date: 11/04/2016
f1_keywords:
- C2247
helpviewer_keywords:
- C2247
ms.assetid: 72efa03e-615e-4ef9-aede-0a98654b20fd
ms.openlocfilehash: ab1f83e2075128441cbffd2d939e3b99b45be4c3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50596430"
---
# <a name="compiler-error-c2247"></a>Compilerfehler C2247

'Bezeichner' nicht zugegriffen werden kann, da 'Klasse' "Spezifizierer" verwendet, um "Klasse" erben

`identifier` wird von einer Klasse deklariert wird, mit dem privaten oder geschützten Zugriff geerbt.

Im folgende Beispiel wird die C2247 generiert:

```
// C2247.cpp
class A {
public:
   int i;
};
class B : private A {};    // B inherits a private A
class C : public B {} c;   // so even though C's B is public
int j = c.i;               // C2247, i not accessible
```

Dieser Fehler kann außerdem infolge einer konformitätsverbesserung für Compiler, die für Visual Studio .NET 2003 durchgeführt wurde, generiert werden: Zugriffssteuerung mit geschützten Elementen. Ein geschützter Member (n) kann nur über eine Memberfunktion einer Klasse (B) zugegriffen werden, die von der Klasse (A) erbt der (n) Mitglied ist.

Deklarieren Sie für Code, der in der Visual Studio .NET 2003 und Visual Studio .NET der Versionen von Visual C++ gültig ist das Element einen Freund des Typs sein. Öffentliche Vererbung kann auch verwendet werden.

```
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

C2247 kann außerdem infolge einer konformitätsverbesserung für Compiler, die für Visual Studio .NET 2003 durchgeführt wurde, generiert werden: private Basisklassen nicht zugegriffen werden kann. Eine Klasse (A), eine private Basisklasse in einen Typ (B) sollte nicht auf einen Typ zugegriffen werden (C), die B als Basisklasse verwendet.

Verwenden Sie für Code, der in der Visual Studio .NET 2003 und Visual Studio .NET der Versionen von Visual C++ gültig ist den Bereichsoperator.

```
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