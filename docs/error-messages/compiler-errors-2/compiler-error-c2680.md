---
title: "Compilerfehler C2680 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2680"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2680"
ms.assetid: d6f7129e-dd17-4661-b680-18d6b925b1cc
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Compilerfehler C2680
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Typ': Ungültiger Zieltyp für Name  
  
 Ein Umwandlungsoperator hat versucht, eine Typumwandlung in einen Typ durchzuführen, der kein Zeiger oder Verweis ist.  Der Operator [dynamic\_cast](../../cpp/dynamic-cast-operator.md) kann nur für Zeiger oder Verweise verwendet werden.  
  
 Im folgenden Beispiel wird C2680 generiert:  
  
```  
// C2680.cpp  
// compile with: /c  
class A { virtual void f(); };  
class B : public A {};  
  
void g(B b) {  
   A a;  
   a = dynamic_cast<A>(b);   // C2680  target not a reference type  
   a = dynamic_cast<A&>(b);   // OK  
}  
```  
  
 C2680 kann auch auftreten, wenn das Ziel nicht definiert ist:  
  
```  
// C2680b.cpp  
// compile with: /clr /c  
// C2680 expected  
using namespace System::Collections;  
  
// Delete the following line to resolve.  
ref class A;   // not defined  
  
// Uncomment the following line to resolve.  
// ref class A{};  
  
public ref class B : ArrayList {  
   property A^ C[int] {  
      A^ get(int index) {  
         return dynamic_cast<A^>(this->default::get(index));  
      }  
      void set(int index, A^ value) {  
         this->default::set(index, value);   
      }  
   }  
};  
```