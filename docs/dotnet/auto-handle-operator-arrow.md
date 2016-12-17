---
title: "auto_handle::operator-&gt;"
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
  - "msclr::auto_handle::operator->"
  - "auto_handle.operator->"
  - "auto_handle::operator->"
  - "msclr.auto_handle.operator->"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "auto_handle::operator->"
ms.assetid: c8c7a771-ea15-41fa-981a-065b8d1162b4
caps.latest.revision: 10
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# auto_handle::operator-&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der Memberzugriffsoperator.  
  
## Syntax  
  
```  
_element_type ^ operator->();  
```  
  
## Rückgabewert  
 Das Objekt, das von `auto_handle` umschlossen wird.  
  
## Beispiel  
  
```  
// msl_auto_handle_op_arrow.cpp  
// compile with: /clr  
#include <msclr\auto_handle.h>  
  
using namespace System;  
using namespace msclr;  
  
ref class ClassA {  
protected:     
   String^ m_s;  
public:  
   ClassA( String^ s ) : m_s( s ) {}  
  
   virtual void PrintHello() {  
      Console::WriteLine( "Hello from {0} A!", m_s );  
   }  
  
   int m_i;  
};  
  
int main() {  
   auto_handle<ClassA> a( gcnew ClassA( "first" ) );  
   a->PrintHello();  
  
   a->m_i = 5;  
   Console::WriteLine( "a->m_i = {0}", a->m_i );  
}  
```  
  
  **Hello zuerst von A\!**  
**Uhr \>\_I \= 5**   
## Anforderungen  
 **Headerdatei** \<msclr\\auto\_handle.h\>  
  
 **Namespace** msclr  
  
## Siehe auch  
 [auto\_handle\-Member](../dotnet/auto-handle-members.md)   
 [auto\_handle::get](../dotnet/auto-handle-get.md)