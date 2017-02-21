---
title: "auto_handle::reset | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "auto_handle.reset"
  - "msclr::auto_handle::reset"
  - "auto_handle::reset"
  - "msclr.auto_handle.reset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "auto_handle::reset"
ms.assetid: 32dc3a83-80fd-45c9-8f79-8c4096c30f57
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# auto_handle::reset
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Zerstören Sie das aktuelle besessene Objekt und nehmen Sie optional ein neues Objekt in Besitz.  
  
## Syntax  
  
```  
void reset(  
   _element_type ^ _new_ptr  
);  
void reset();  
```  
  
#### Parameter  
 `_new_ptr`  
 \(Optional\) Das neue Objekt.  
  
## Beispiel  
  
```  
// msl_auto_handle_reset.cpp  
// compile with: /clr  
#include <msclr\auto_handle.h>  
  
using namespace System;  
using namespace msclr;  
  
ref class ClassA {  
   String^ m_s;  
public:  
   ClassA( String^ s ) : m_s( s ) {  
      Console::WriteLine( "ClassA constructor: " + m_s );  
   }  
   ~ClassA() {  
      Console::WriteLine( "ClassA destructor: " + m_s );  
   }  
  
   void PrintHello() {  
      Console::WriteLine( "Hello from {0} A!", m_s );  
   }  
};  
  
int main()  
{  
   auto_handle<ClassA> agc1 = gcnew ClassA( "first" );  
   agc1->PrintHello();  
  
   ClassA^ ha = gcnew ClassA( "second" );  
   agc1.reset( ha ); // release first object, reference second  
   agc1->PrintHello();  
  
   agc1.reset(); // release second object, set to nullptr  
  
   Console::WriteLine( "done" );  
}  
```  
  
  **ClassA\-Konstruktor: erstens**  
**Hello zuerst von A\!**  
**ClassA\-Konstruktor: zweitens**  
**ClassA\-Destruktor: erstens**  
**Hello von zweitem A\!**  
**ClassA\-Destruktor: zweitens**  
**dein**   
## Anforderungen  
 **Headerdatei** \<msclr\\auto\_handle.h\>  
  
 **Namespace** msclr  
  
## Siehe auch  
 [auto\_handle\-Member](../dotnet/auto-handle-members.md)   
 [auto\_handle::release](../dotnet/auto-handle-release.md)