---
title: Compilerfehler C2327
ms.date: 11/04/2016
f1_keywords:
- C2327
helpviewer_keywords:
- C2327
ms.assetid: 95278c95-d1f9-4487-ad27-53311f5e8112
ms.openlocfilehash: abc9aa92c41947a2536e53108c1fb646792a8202
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50652308"
---
# <a name="compiler-error-c2327"></a>Compilerfehler C2327

'Symbol': ist kein, ein Typname, Static oder Enumerator

Code innerhalb einer geschachtelten Klasse versucht, die Zugriff auf einen Member der einschließenden Klasse, die einen Typnamen, einen statischen Member oder einen Enumerator nicht ist.

Beim Kompilieren mit **"/ CLR"**, eine häufige Ursache für Fehler C2327 ist eine Eigenschaft mit dem gleichen Namen wie der Eigenschaftentyp.

Im folgende Beispiel wird die C2327 generiert:

```
// C2327.cpp
int x;
class enclose {
public:
   int x;
   static int s;
   class inner {
      void f() {
         x = 1;   // C2327; enclose::x is not static
         s = 1;   // ok; enclose::s is static
         ::x = 1;   // ok; ::x refers to global
      }
   };
};
```

Fehler C2327 kann auch auftreten, wenn der Name eines Typs durch den Namen eines Members ausgeblendet wird:

```
// C2327b.cpp
class X {};

class S {
   X X;
   // try the following line instead
   // X MyX;
   X other;   // C2327, rename member X
};
```

In diesem Fall können auch Fehler C2327 ausgelöst, in dem Sie den Datentyp des Parameters vollständig angeben müssen:

```
// C2327c.cpp
// compile with: /c
struct A {};

struct B {
   int A;
   void f(A a) {   // C2327
   void f2(struct A a) {}   // OK
   }
};
```

Im folgende Beispiel wird die C2327 generiert:

```
// C2327d.cpp
// compile with: /clr /c
using namespace System;

namespace NA {
   public enum class E : Int32 {
      one = 1,
      two = 2,
      three = 3
   };

   public ref class A {
   private:
      E m_e;
   public:
      property E E {
         NA::E get() {
            return m_e;
         }
         // At set, compiler doesn't know whether E is get_E or
         // Enum E, therefore fully qualifying Enum E is necessary
         void set( E e ) {   // C2327
            // try the following line instead
            // void set(NA::E e) {
            m_e = e;
         }
      }
   };
}
```

Das folgende Beispiel zeigt Fehler C2327 auf, wenn eine Eigenschaft mit den gleichen Namen wie der Eigenschaftstyp hat:

```
// C2327f.cpp
// compile with: /clr /c
public value class Address {};

public ref class Person {
public:
   property Address Address {
      ::Address get() {
         return address;
      }
      void set(Address addr) {   // C2327
      // try the following line instead
      // set(::Address addr) {
         address = addr;
      }
   }
private:
   Address address;   // C2327
   // try the following line instead
   // ::Address address;
};
```
