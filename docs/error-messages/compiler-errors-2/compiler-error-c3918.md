---
title: "Compilerfehler C3918 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3918"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3918"
ms.assetid: a8b3a90a-3fe1-4244-a5ff-a31cdae97d98
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C3918
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Für die Syntax muss 'Member' ein Datenmember sein  
  
 C3918 kann aus mehreren Gründen in Bezug auf Ereignisse auftreten.  
  
## Beispiel  
 C3918 kann auftreten, weil ein Klassenmember im aktuellen Kontext erforderlich ist.  Im folgenden Beispiel wird C3918 generiert.  
  
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
  
## Beispiel  
 C3918 wird auch verursacht, wenn Sie ein triviales Ereignis auf NULL überprüfen \(der Ereignisname bietet keinen direkten Zugriff mehr auf zugrunde liegende Speicherdelegaten für das Ereignis\).  
  
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
  
## Beispiel  
 C3918 kann auch auftreten, wenn Sie ein Ereignis falsch abonnieren.  Im folgenden Beispiel wird C3918 generiert.  
  
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