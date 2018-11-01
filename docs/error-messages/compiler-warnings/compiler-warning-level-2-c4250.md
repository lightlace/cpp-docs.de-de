---
title: Compilerwarnung (Stufe 2) C4250
ms.date: 11/04/2016
f1_keywords:
- C4250
helpviewer_keywords:
- C4250
ms.assetid: d47f7249-6b5a-414b-b2d4-56e5d246a782
ms.openlocfilehash: 8baf3c03c87dc70a80b785d7f81cbee4e1d828f0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50454859"
---
# <a name="compiler-warning-level-2-c4250"></a>Compilerwarnung (Stufe 2) C4250

'Klasse1': 'Klasse2:: Member"via Dominanz erbt

Zwei oder mehr Elemente haben den gleichen Namen. In `class2` geerbt wird, da es sich um eine Basisklasse für die anderen Klassen handelt, die dieses Element enthalten.

Um C4250 zu unterdrücken, verwenden die [Warnung](../../preprocessor/warning.md) Pragma.

Da eine virtuelle Basisklasse für mehrere abgeleitete Klassen freigegeben werden, dominiert ein Namen in einer abgeleiteten Klasse einen Namen in einer Basisklasse. Z. B. wenn die folgende Hierarchie von Klassen, werden zwei Definitionen von Func in Raute geerbt: die vbc::Func()-Instanz durch die schwachen-Klasse und den dominanten:: func() über die vorherrschende-Klasse. Ein nicht qualifizierter Aufruf von func() über ein Klassenobjekt Raute, und ruft immer die dominate::Func()-Instanz aus.  Würde die schwache Klasse eine Instanz von func() einführen, weder Definition der Definitionen, und der Aufruf als mehrdeutig markiert.

```
// C4250.cpp
// compile with: /c /W2
#include <stdio.h>
struct vbc {
   virtual void func() { printf("vbc::func\n"); }
};

struct weak : public virtual vbc {};

struct dominant : public virtual vbc {
   void func() { printf("dominant::func\n"); }
};

struct diamond : public weak, public dominant {};

int main() {
   diamond d;
   d.func();   // C4250
}
```

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4250 generiert.

```
// C4250_b.cpp
// compile with: /W2 /EHsc
#include <iostream>
using namespace std;
class A {
public:
   virtual operator int () {
      return 2;
   }
};

class B : virtual public A {
public:
   virtual operator int () {
      return 3;
   }
};

class C : virtual public A {};

class E : public B, public C {};   // C4250

int main() {
   E eObject;
   cout << eObject.operator int() << endl;
}
```

## <a name="example"></a>Beispiel

Dieses Beispiel zeigt eine komplexere Situation. Im folgende Beispiel wird die C4250 generiert.

```
// C4250_c.cpp
// compile with: /W2 /EHsc
#include <iostream>
using namespace std;

class V {
public:
   virtual int f() {
      return 1024;
   }
};

class B : virtual public V {
public:
   int b() {
      return f(); // B::b() calls V::f()
   }
};

class M : virtual public V {
public:
   int f() {
      return 7;
   }
};

// because of dominance, f() is M::f() inside D,
// changing the meaning of B::b's f() call inside a D
class D : public B, public M {};   // C4250

int main() {
   D d;
   cout << "value is: " << d.b();   // invokes M::f()
}
```