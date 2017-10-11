---
title: Compilerfehler C3918 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3918
dev_langs:
- C++
helpviewer_keywords:
- C3918
ms.assetid: a8b3a90a-3fe1-4244-a5ff-a31cdae97d98
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 1bf9cf676cf7435eaf1f0b924fbadcaddef842b4
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3918"></a>Compilerfehler C3918
Die Syntax muss "Member", um einen Datenmember werden  
  
 C3918 kann verschiedene Ursachen, die im Zusammenhang mit Ereignissen auftreten.  
  
## <a name="example"></a>Beispiel  
 C3918 kann auftreten, da ein Klassenmember im aktuellen Kontext erforderlich ist. Im folgenden Beispiel wird C3918 generiert.  
  
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
 C3918 wird auch verursacht, wenn Sie versuchen, ein triviales Ereignis für Null-Zeichen (der Namen des Ereignisses wird nicht mehr an den Delegaten der dahinter liegende Speicher für das Ereignis ermöglichen von direktem Zugriff).  
  
 Im folgenden Beispiel wird C3918 generiert.  
  
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
 C3918 kann auch auftreten, wenn Sie nicht ordnungsgemäß auf ein Ereignis abonnieren. Im folgenden Beispiel wird C3918 generiert.  
  
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
