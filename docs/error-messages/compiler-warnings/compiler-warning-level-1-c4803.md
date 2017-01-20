---
title: "Compilerwarnung (Stufe 1) C4803"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C4803"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4803"
ms.assetid: 2552f3a6-c418-49f4-98a2-a929857be658
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4803
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Methode': Die Raise\-Methode hat eine andere Speicherklasse als die des Ereignisses 'Ereignis'  
  
 Ereignismethoden müssen über dieselbe Speicherklasse wie die Ereignisdeklaration verfügen.  Die Ereignismethoden werden vom Compiler angepasst, sodass die Speicherklassen übereinstimmen.  
  
 Diese Warnung kann bei einer Klasse auftreten, die ein Ereignis über eine Schnittstelle implementiert.  Eine `Raise`\-Methode für ein Ereignis in einer Schnittstelle wird nicht implizit vom Compiler generiert.  Wenn Sie diese Schnittstelle in einer Klasse implementieren, generiert der Compiler jedoch implizit eine nicht virtuelle `Raise`\-Methode, was die Warnung zur Folge hat.  
  
 Informationen zum Deaktivieren einer Warnung finden Sie unter den Ausführungen zum Pragma [warning](../../preprocessor/warning.md).  
  
## Beispiel  
 C4803 kann mit **\/clr** generiert werden.  Weitere Informationen über die Verwendung von Ereignissen finden Sie unter [event](../../windows/event-cpp-component-extensions.md).  
  
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
  
## Beispiel  
 C4803 kann mit **\/clr:oldSyntax** generiert werden.  Im folgenden Beispiel wird C4803 generiert.  
  
```  
// C4803_b.cpp  
// compile with: /clr:oldSyntax /W1  
using namespace System;  
  
public __delegate void Del();  
  
__gc struct E {  
   Del* _pd1;  
   virtual __event void add_E1(Del* pd1) {  
      _pd1 = dynamic_cast<Del*> (Delegate::Combine(_pd1, pd1));  
   }  
  
   virtual __event void remove_E1(Del* pd1) {  
      _pd1 = dynamic_cast<Del*> (Delegate::Remove(_pd1, pd1));  
   }  
  
   __event void raise_E1 () {   // C4803, add virtual  
      if (_pd1)  
         _pd1->Invoke();  
   }  
  
   void func() {  
      Console::WriteLine("In E::func()");  
   }  
};  
  
int main() {  
   E* ep = new E;  
   ep->E1 += new Del(ep, &E::func);  
   ep->E1();  
   ep->E1 -= new Del(ep, &E::func);  
   ep->E1();  
}  
```