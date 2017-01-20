---
title: "auto_gcroot::attach"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "auto_gcroot.attach"
  - "auto_gcroot::attach"
  - "msclr::auto_gcroot::attach"
  - "msclr.auto_gcroot.attach"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "auto_gcroot::attach"
ms.assetid: 996ede65-bcb5-41f2-bfbf-507f8a578241
caps.latest.revision: 12
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# auto_gcroot::attach
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Anfügen `auto_gcroot` für ein Objekt.  
  
## Syntax  
  
```  
auto_gcroot<_element_type> & attach(  
   _element_type _right  
);  
auto_gcroot<_element_type> & attach(  
   auto_gcroot<_element_type> & _right  
);  
template<typename _other_type>  
auto_gcroot<_element_type> & attach(  
   auto_gcroot<_other_type> & _right  
);  
```  
  
#### Parameter  
 `_right`  
 Das Objekt der Anfügevorgang oder `auto_gcroot`, das das Objekt der Anfügevorgang enthält.  
  
## Rückgabewert  
 Der aktuelle `auto_gcroot`.  
  
## Hinweise  
 Wenn `_right``auto_gcroot` ist, wird der Besitz des Objekts freigegeben, bevor das Objekt zur aktuellen `auto_gcroot` angefügt wird.  
  
## Beispiel  
  
```  
// msl_auto_gcroot_attach.cpp  
// compile with: /clr  
#include <msclr\auto_gcroot.h>  
  
using namespace System;  
using namespace msclr;  
  
ref class ClassA {  
protected:     
   String^ m_s;  
public:  
   ClassA( String^ s ) : m_s( s ) {  
      Console::WriteLine( "in ClassA constructor:" + m_s );  
   }  
   ~ClassA() {  
      Console::WriteLine( "in ClassA destructor:" + m_s );  
   }  
  
   virtual void PrintHello() {  
      Console::WriteLine( "Hello from {0} A!", m_s );  
   }  
};  
  
ref class ClassB : ClassA {  
public:  
   ClassB( String ^ s) : ClassA( s ) {}  
   virtual void PrintHello() new {  
      Console::WriteLine( "Hello from {0} B!", m_s );  
   }  
};  
  
int main() {  
   auto_gcroot<ClassA^> a( gcnew ClassA( "first" ) );  
   a->PrintHello();  
   a.attach( gcnew ClassA( "second" ) ); // attach same type  
   a->PrintHello();  
   ClassA^ ha = gcnew ClassA( "third" );  
   a.attach( ha ); // attach raw handle  
   a->PrintHello();  
   auto_gcroot<ClassB^> b( gcnew ClassB("fourth") );  
   b->PrintHello();  
   a.attach( b ); // attach derived type  
   a->PrintHello();  
}  
```  
  
  **in ClassA\-Konstruktor: erstens**  
**Hello zuerst von A\!**  
**in ClassA\-Konstruktor: zweitens**  
**in ClassA\-Destruktor: erstens**  
**Hello von zweitem A\!**  
**in ClassA\-Konstruktor: drittens**  
**in ClassA\-Destruktor: zweitens**  
**Hello von drittem A\!**  
**in ClassA\-Konstruktor: viertes**  
**Hello von viertem B\!**  
**in ClassA\-Destruktor: drittens**  
**Hello von viertem A\!**  
**in ClassA\-Destruktor: viertes**   
## Anforderungen  
 **Headerdatei** \<msclr\\auto\_gcroot.h\>  
  
 **Namespace** msclr  
  
## Siehe auch  
 [auto\_gcroot Members](../dotnet/auto-gcroot-members.md)   
 [auto\_gcroot::operator\=](../dotnet/auto-gcroot-operator-assign.md)   
 [auto\_gcroot::release](../dotnet/auto-gcroot-release.md)