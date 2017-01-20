---
title: "auto_gcroot::swap"
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
  - "msclr.auto_gcroot.swap"
  - "msclr::auto_gcroot::swap"
  - "auto_gcroot::swap"
  - "auto_gcroot.swap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "auto_gcroot::swap"
ms.assetid: 4915c629-6a53-432c-8155-3a7511dc70cb
caps.latest.revision: 12
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# auto_gcroot::swap
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Austauschobjekte mit einem anderen `auto_gcroot`.  
  
## Syntax  
  
```  
void swap(  
   auto_gcroot<_element_type> & _right  
);  
```  
  
#### Parameter  
 `_right`  
 Die `auto_gcroot`, der von Objekten auszutauschen.  
  
## Beispiel  
  
```  
// msl_auto_gcroot_swap.cpp  
// compile with: /clr  
#include <msclr\auto_gcroot.h>  
  
using namespace System;  
using namespace msclr;  
  
int main() {  
   auto_gcroot<String^> s1 = "string one";  
   auto_gcroot<String^> s2 = "string two";  
  
   Console::WriteLine( "s1 = '{0}', s2 = '{1}'",  
      s1->ToString(), s2->ToString() );  
   s1.swap( s2 );  
   Console::WriteLine( "s1 = '{0}', s2 = '{1}'",  
      s1->ToString(), s2->ToString() );  
}  
```  
  
  **s1 \= "Zeichenfolge eine", s2 \= Zeichenfolge "zwei"**  
**s1 \= Zeichenfolge "zwei", s2 \= eine "Zeichenfolge"**   
## Anforderungen  
 **Headerdatei** \<msclr\\auto\_gcroot.h\>  
  
 **Namespace** msclr  
  
## Siehe auch  
 [auto\_gcroot Members](../dotnet/auto-gcroot-members.md)   
 [swap\-Funktion \(auto\_gcroot\)](../dotnet/swap-function-auto-gcroot.md)