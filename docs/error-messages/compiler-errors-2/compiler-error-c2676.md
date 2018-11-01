---
title: Compilerfehler C2676
ms.date: 11/04/2016
f1_keywords:
- C2676
helpviewer_keywords:
- C2676
ms.assetid: 838a5e34-c92f-4f65-a597-e150bf8cf737
ms.openlocfilehash: 1a3eab8d1df7534f2bfbed42db5c1a660942eacc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50608068"
---
# <a name="compiler-error-c2676"></a>Compilerfehler C2676

Binärer 'Operator': 'Typ' definiert diesen Operator oder eine Konvertierung in einen für den vordefinierten Operator geeigneten Typ nicht

Um den Operator zu verwenden, müssen Sie ihn für den angegebenen Typ überladen oder eine Konvertierung in einen Typ definieren, für den der Operator definiert ist.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C2676 generiert.

```
// C2676.cpp
// C2676 expected
struct C {
   C();
} c;

struct D {
   D();
   D operator >>( C& ){return * new D;}
   D operator <<( C& ){return * new D;}
} d;

struct E {
   // operator int();
};

int main() {
   d >> c;
   d << c;
   E e1, e2;
   e1 == e2;   // uncomment operator int in class E, then
               // it is OK even though neither E::operator==(E) nor
               // operator==(E, E) defined. Uses the conversion to int
               // and then the builtin-operator==(int, int)
}
```

## <a name="example"></a>Beispiel

C2676 kann auch bei dem Versuch auftreten, im `this`-Zeiger eines Referenztyps eine Zeigerarithmetik auszuführen.

Der `this`-Zeiger tritt in einem Referenztyp als Handletyp auf. Weitere Informationen finden Sie unter [Semantik dieses Zeigers](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Semantics_of_the_this_pointer).

Im folgende Beispiel wird die C2676 generiert.

```
// C2676_a.cpp
// compile with: /clr
using namespace System;

ref struct A {
   property Double default[Double] {
      Double get(Double data) {
         return data*data;
      }
   }

   A() {
      Console::WriteLine("{0}", this + 3.3);   // C2676
      Console::WriteLine("{0}", this[3.3]);   // OK
   }
};

int main() {
   A ^ mya = gcnew A();
}
```