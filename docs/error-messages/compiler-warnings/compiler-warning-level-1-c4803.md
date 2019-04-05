---
title: Compilerwarnung (Stufe 1) C4803
ms.date: 11/04/2016
f1_keywords:
- C4803
helpviewer_keywords:
- C4803
ms.assetid: 2552f3a6-c418-49f4-98a2-a929857be658
ms.openlocfilehash: bb8f5fe9d55a44193325a2fcfe9ef7675a2b3b89
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "58774879"
---
# <a name="compiler-warning-level-1-c4803"></a>Compilerwarnung (Stufe 1) C4803

"Method": Die Raise-Methode verfügt über eine andere Speicherklasse aus, der das Ereignis 'Ereignis'

Ereignismethoden müssen dieselbe Speicherklasse wie die Deklaration des Ereignisses. Der Compiler passt Ereignismethoden, sodass die Speicherklassen identisch sind.

Diese Warnung kann auftreten, wenn Sie eine Klasse verfügen, die ein Ereignis von einer Schnittstelle implementiert. Raise-Methode für ein Ereignis wird in einer Schnittstelle nicht implizit vom Compiler generiert. Wenn Sie diese Schnittstelle in einer Klasse implementieren, generiert der Compiler implizit eine Raise-Methode, und diese Methode nicht virtuell, daher die Warnung. Weitere Informationen zu Ereignissen finden Sie unter [Ereignis](../../extensions/event-cpp-component-extensions.md).

Finden Sie unter [Warnung](../../preprocessor/warning.md) Pragma Informationen dazu, wie eine Warnung zu deaktivieren.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird C4803 generiert.

```
// C4803.cpp
// compile with: /clr /W1
using namespace System;

public delegate void Del();

ref struct E {
   Del ^ _pd1;
   event Del ^ E1 {
      void add (Del ^ pd1) {
         _pd1 = dynamic_cast<Del ^>(Delegate::Combine(_pd1, pd1));
      }

      void remove(Del^ pd1) {
         _pd1 = dynamic_cast<Del^> (Delegate::Remove(_pd1, pd1));
      }

      virtual void raise() {   // C4803 warning (remove virtual)
         if (_pd1)
            _pd1();
      }
   }

   void func() {
      Console::WriteLine("In E::func()");
   }
};

int main() {
   E ^ ep = gcnew E;
   ep->E1 += gcnew Del(ep, &E::func);
   ep->E1();
   ep->E1 -= gcnew Del(ep, &E::func);
   ep->E1();
}
```
