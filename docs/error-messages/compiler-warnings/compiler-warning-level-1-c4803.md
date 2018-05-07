---
title: Compilerwarnung (Stufe 1) C4803 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4803
dev_langs:
- C++
helpviewer_keywords:
- C4803
ms.assetid: 2552f3a6-c418-49f4-98a2-a929857be658
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c574b51fc13f9224d48495f8b591a56abdc74966
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4803"></a>Compilerwarnung (Stufe 1) C4803
'Methode': Die Raise-Methode wurde eine anderen Speicherklasse aus, der das Ereignis 'Ereignis'  
  
Ereignismethoden müssen die gleiche Speicherklasse als die Ereignisdeklaration haben. Der Compiler passt das Ereignis Methoden, sodass die Speicherklassen identisch sind.  
  
Diese Warnung kann auftreten, wenn Sie eine Klasse haben, die ein Ereignis über eine Schnittstelle implementiert. Der Compiler generiert eine Raise-Methode für ein Ereignis nicht implizit in einer Schnittstelle. Wenn Sie diese Schnittstelle in einer Klasse implementieren, generiert der Compiler implizit eine Raise-Methode, und diese Methode ist nicht virtuell sein, daher die Warnung. Weitere Informationen zu Ereignissen finden Sie unter [Ereignis](../../windows/event-cpp-component-extensions.md).  
  
Finden Sie unter [Warnung](../../preprocessor/warning.md) Pragma Informationen zum Deaktivieren einer Warnung.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C4803 generiert.  
  
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
