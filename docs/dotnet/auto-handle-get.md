---
title: "auto_handle::get"
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
  - "auto_handle::get"
  - "msclr::auto_handle::get"
  - "auto_handle.get"
  - "msclr.auto_handle.get"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "auto_handle::get"
ms.assetid: 8c75727b-8f21-44b3-be3e-7eb8858da4f7
caps.latest.revision: 10
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# auto_handle::get
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ruft das übergeordnete Objekt ab.  
  
## Syntax  
  
```  
_element_type ^ get();  
```  
  
## Rückgabewert  
 Das enthaltende Objekt.  
  
## Beispiel  
  
```  
// msl_auto_handle_get.cpp  
// compile with: /clr  
#include "msclr\auto_handle.h"  
  
using namespace System;  
using namespace msclr;  
  
ref class ClassA {  
   String^ m_s;  
public:  
   ClassA( String^ s ) : m_s( s ){  
      Console::WriteLine( "in ClassA constructor:" + m_s );  
   }  
   ~ClassA() {  
      Console::WriteLine( "in ClassA destructor:" + m_s );  
   }  
  
   void PrintHello() {  
      Console::WriteLine( "Hello from {0} A!", m_s );  
   }  
};  
  
void PrintA( ClassA^ a ) {  
   a->PrintHello();  
}  
  
int main() {  
   auto_handle<ClassA> a = gcnew ClassA( "first" );  
   a->PrintHello();  
  
   ClassA^ a2 = a.get();  
   a2->PrintHello();  
  
   PrintA( a.get() );  
}  
```  
  
  **in ClassA\-Konstruktor: erstens**  
**Hello zuerst von A\!**  
**Hello zuerst von A\!**  
**Hello zuerst von A\!**  
**in ClassA\-Destruktor: erstens**   
## Anforderungen  
 **Headerdatei** \<msclr\\auto\_handle.h\>  
  
 **Namespace** msclr  
  
## Siehe auch  
 [auto\_handle\-Member](../dotnet/auto-handle-members.md)