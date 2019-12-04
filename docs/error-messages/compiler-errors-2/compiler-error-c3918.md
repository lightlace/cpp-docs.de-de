---
title: Compilerfehler C3918
ms.date: 11/04/2016
f1_keywords:
- C3918
helpviewer_keywords:
- C3918
ms.assetid: a8b3a90a-3fe1-4244-a5ff-a31cdae97d98
ms.openlocfilehash: ff2b59338c707767fa1d3c382feaa1bfcdf29ce2
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758488"
---
# <a name="compiler-error-c3918"></a>Compilerfehler C3918

die Verwendung erfordert, dass "Member" ein Datenmember ist.

C3918 kann aus verschiedenen Gründen im Zusammenhang mit Ereignissen auftreten.

## <a name="example"></a>Beispiel

C3918 kann auftreten, wenn ein Klassenmember im aktuellen Kontext erforderlich ist. Im folgenden Beispiel wird C3918 generiert.

```cpp
// C3918.cpp
// compile with: /clr /c
public ref class C {
public:
   System::Object ^ o;
   delegate void Del();

   event Del^ MyEvent {
      void add(Del^ev) {
         if ( MyEvent != nullptr) {}   // C3918
         if ( o != nullptr) {}   // OK
   }
   void remove(Del^){}
   }
};
```

## <a name="example"></a>Beispiel

C3918 wird auch ausgelöst, wenn Sie versuchen, ein triviales Ereignis auf NULL zu überprüfen (der Ereignis Name stellt keinen direkten Zugriff auf den Sicherungs Speicher Delegaten für das Ereignis bereit).

Im folgenden Beispiel wird C3918 generiert.

```cpp
// C3918_2.cpp
// compile with: /clr /c
using namespace System;
public delegate int MyDel(int);

interface struct IEFace {
   event MyDel ^ E;
};

ref struct EventSource : public IEFace {
   virtual event MyDel ^ E;
   void Fire_E(int i) {
      if (E)   // C3918
         E(i);
   }
};
```

## <a name="example"></a>Beispiel

C3918 kann auch auftreten, wenn Sie fälschlicherweise ein Ereignis abonnieren. Im folgenden Beispiel wird C3918 generiert.

```cpp
// C3918_3.cpp
// compile with: /clr /c
using namespace System;

public delegate void del();

public ref class A {
public:
   event del^ e {
      void add(del ^handler ) {
         d += handler;
      }

      void remove(del ^handler) {
         d -= handler;
      }

      void raise() {
         d();
      }
   }

   del^ d;
   void f() {}

   A() {
      e = gcnew del(this, &A::f);   // C3918
      // try the following line instead
      // e += gcnew del(this, &A::f);
      e();
   }
};

int main() {
   A a;
}
```
