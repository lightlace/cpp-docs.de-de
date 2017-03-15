---
title: "auto_gcroot::auto_gcroot | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "msclr::auto_gcroot::auto_gcroot"
  - "auto_gcroot::auto_gcroot"
  - "auto_gcroot.auto_gcroot"
  - "msclr.auto_gcroot.auto_gcroot"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "auto_gcroot::auto_gcroot"
ms.assetid: 27faa42a-64ea-4d31-836f-073a55145735
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# auto_gcroot::auto_gcroot
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der `auto_gcroot`\-Konstruktor.  
  
## Syntax  
  
```  
auto_gcroot(  
   _element_type _ptr = nullptr  
);  
auto_gcroot(  
   auto_gcroot<_element_type> & _right  
);  
template<typename _other_type>  
auto_gcroot(  
   auto_gcroot<_other_type> & _right  
);  
```  
  
#### Parameter  
 `_ptr`  
 Das Objekt in eigenem.  
  
 `_right`  
 Eine vorhandene `auto_gcroot`.  
  
## Hinweise  
 Wenn `auto_gcroot` von vorhandenen `auto_gcroot` erstellt, gibt vorhandene `auto_gcroot` sein Objekt frei, bevor der Besitz des Objekts zu neuen `auto_gcroot` überträgt.  
  
## Beispiel  
  
```  
// msl_auto_gcroot_auto_gcroot.cpp  
// compile with: /clr  
#include <msclr\auto_gcroot.h>  
  
using namespace System;  
using namespace msclr;  
  
ref class RefClassA {  
protected:  
   String^ m_s;     
public:  
   RefClassA(String^ s) : m_s(s) {  
      Console::WriteLine( "in RefClassA constructor: " + m_s );  
   }  
   ~RefClassA() {  
      Console::WriteLine( "in RefClassA destructor: " + m_s );  
   }  
  
   virtual void PrintHello() {  
      Console::WriteLine( "Hello from {0} A!", m_s );  
   }  
};  
  
ref class RefClassB : RefClassA {  
public:     
   RefClassB( String^ s ) : RefClassA( s ) {}  
   virtual void PrintHello() new {  
      Console::WriteLine( "Hello from {0} B!", m_s );  
   }  
};  
  
class ClassA { //unmanaged class  
private:     
   auto_gcroot<RefClassA^> m_a;  
  
public:  
   ClassA() : m_a( gcnew RefClassA( "unmanaged" ) ) {}  
   ~ClassA() {} //no need to delete m_a  
  
   void DoSomething() {  
      m_a->PrintHello();  
   }  
};  
  
int main()  
{  
   {  
      ClassA a;  
      a.DoSomething();  
   } // a.m_a is automatically destroyed as a goes out of scope  
  
   {  
      auto_gcroot<RefClassA^> a(gcnew RefClassA( "first" ) );  
      a->PrintHello();  
   }  
  
   {  
      auto_gcroot<RefClassB^> b(gcnew RefClassB( "second" ) );  
      b->PrintHello();  
      auto_gcroot<RefClassA^> a(b); //construct from derived type  
      a->PrintHello();  
      auto_gcroot<RefClassA^> a2(a); //construct from same type  
      a2->PrintHello();  
   }  
  
   Console::WriteLine("done");  
}  
```  
  
  **in RefClassA\-Konstruktor: nicht verwaltet**  
**Hello von nicht verwaltetem A\!**  
**in RefClassA\-Destruktor: nicht verwaltet**  
**in RefClassA\-Konstruktor: erstens**  
**Hello zuerst von A\!**  
**in RefClassA\-Destruktor: erstens**  
**in RefClassA\-Konstruktor: zweitens**  
**Hello von zweitem B\!**  
**Hello von zweitem A\!**  
**Hello von zweitem A\!**  
**in RefClassA\-Destruktor: zweitens**  
**dein**   
## Anforderungen  
 **Headerdatei** \<msclr\\auto\_gcroot.h\>  
  
 **Namespace** msclr  
  
## Siehe auch  
 [auto\_gcroot Members](../dotnet/auto-gcroot-members.md)   
 [auto\_gcroot::attach](../dotnet/auto-gcroot-attach.md)   
 [auto\_gcroot::operator\=](../dotnet/auto-gcroot-operator-assign.md)   
 [auto\_gcroot::~auto\_gcroot](../dotnet/auto-gcroot-tilde-auto-gcroot.md)