---
title: Compiler (Stufe 1) C4803 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4803
dev_langs:
- C++
helpviewer_keywords:
- C4803
ms.assetid: 2552f3a6-c418-49f4-98a2-a929857be658
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: 2581d4240306e88d75fe5fcc0249371005853b7e
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4803"></a>Compilerwarnung (Stufe 1) C4803
"Methode": Die Raise-Methode hat eine andere Speicherklasse aus, der das Ereignis "Ereignis"  
  
Ereignismethoden müssen über dieselbe Speicherklasse wie die Ereignisdeklaration verfügen. Der Compiler passt Ereignismethoden, sodass die Speicherklassen identisch sind.  
  
Diese Warnung kann auftreten, wenn Sie eine Klasse verfügen, die ein Ereignis von einer Schnittstelle implementiert. Raise-Methode für ein Ereignis wird in einer Schnittstelle nicht implizit vom Compiler generiert. Wenn Sie diese Schnittstelle in einer Klasse implementieren, generiert der Compiler implizit Raise-Methode, und diese Methode nicht virtuell ist, daher die Warnung. Weitere Informationen zu Ereignissen finden Sie unter [Ereignis](../../windows/event-cpp-component-extensions.md).  
  
Finden Sie unter [Warnung](../../preprocessor/warning.md) Pragma Informationen um eine Warnung zu deaktivieren.  
  
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

