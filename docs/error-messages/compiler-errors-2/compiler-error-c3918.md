---
title: Compilerfehler C3918 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3918
dev_langs:
- C++
helpviewer_keywords:
- C3918
ms.assetid: a8b3a90a-3fe1-4244-a5ff-a31cdae97d98
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8d7111c2c34b4fb367af906156cc1e8b6dd496bb
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46019106"
---
# <a name="compiler-error-c3918"></a>Compilerfehler C3918

Die Syntax muss "Member", um ein Datenmember sein.

C3918 kann verschiedene Ursachen, die im Zusammenhang mit Ereignissen auftreten.

## <a name="example"></a>Beispiel

C3918 kann auftreten, da ein Klassenmember im aktuellen Kontext erforderlich ist. Im folgende Beispiel wird die C3918 generiert.

```
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

C3918 wird auch verursacht werden, wenn Sie versuchen, ein triviales Ereignis auf Null überprüfen (der Ereignisname wird nicht mehr direkten Zugriff auf das dahinter liegende Store Delegat für das Ereignis ermöglichen).

Im folgende Beispiel wird die C3918 generiert.

```
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

C3918 kann auch auftreten, wenn Sie nicht ordnungsgemäß auf ein Ereignis abonnieren. Im folgende Beispiel wird die C3918 generiert.

```
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