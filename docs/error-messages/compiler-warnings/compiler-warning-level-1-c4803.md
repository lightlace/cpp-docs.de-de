---
title: Compilerwarnung (Stufe 1) C4803
ms.date: 11/04/2016
f1_keywords:
- C4803
helpviewer_keywords:
- C4803
ms.assetid: 2552f3a6-c418-49f4-98a2-a929857be658
ms.openlocfilehash: ebf7b3baec3519a142c7a1835aa15a980974bb48
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052347"
---
# <a name="compiler-warning-level-1-c4803"></a>Compilerwarnung (Stufe 1) C4803

' Methode ': die Raise-Methode hat eine andere Speicher Klasse als die des Ereignisses ' Event '.

Ereignis Methoden müssen dieselbe Speicher Klasse wie die Ereignis Deklaration aufweisen. Der Compiler passt die Methoden des Ereignisses so an, dass die Speicher Klassen identisch sind.

Diese Warnung kann auftreten, wenn Sie über eine Klasse verfügen, die ein Ereignis von einer Schnittstelle implementiert. Der Compiler generiert nicht implizit eine Raise-Methode für ein Ereignis in einer Schnittstelle. Wenn Sie diese Schnittstelle in einer Klasse implementieren, generiert der Compiler implizit eine Raise-Methode, und diese Methode ist nicht virtuell, daher wird die Warnung verwendet. Weitere Informationen zu Ereignissen finden Sie unter [Event](../../extensions/event-cpp-component-extensions.md).

Weitere Informationen zum Deaktivieren einer Warnung finden Sie unter [Warning](../../preprocessor/warning.md) -Pragma.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4803 generiert.

```cpp
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
