---
title: "swap-Funktion (auto_handle)"
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
  - "msclr::swap"
  - "msclr.swap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "swap-Funktion"
ms.assetid: 7dd91b5c-f0de-4634-a2e2-642626706e27
caps.latest.revision: 8
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# swap-Funktion (auto_handle)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Austauschobjekte zwischen einem `auto_handle` und andere.  
  
## Syntax  
  
```  
template<typename _element_type>  
void swap(  
   auto_handle<_element_type> % _left,  
   auto_handle<_element_type> % _right  
);  
```  
  
#### Parameter  
 `_left`  
 Ein `auto_handle`.  
  
 `_right`  
 Eine andere `auto_handle`.  
  
## Beispiel  
  
```  
// msl_swap_auto_handle.cpp  
// compile with: /clr  
#include <msclr\auto_handle.h>  
  
using namespace System;  
using namespace msclr;  
  
int main() {  
   auto_handle<String> s1 = "string one";  
   auto_handle<String> s2 = "string two";  
  
   Console::WriteLine( "s1 = '{0}', s2 = '{1}'",  
      s1->ToString(), s2->ToString() );  
   swap( s1, s2 );  
   Console::WriteLine( "s1 = '{0}', s2 = '{1}'",  
      s1->ToString(), s2->ToString() );  
}  
```  
  
  **s1 \= "Zeichenfolge eine", s2 \= Zeichenfolge "zwei"**  
**s1 \= Zeichenfolge "zwei", s2 \= eine "Zeichenfolge"**   
## Anforderungen  
 **Headerdatei** \<msclr\\auto\_handle.h\>  
  
 **Namespace** msclr  
  
## Siehe auch  
 [auto\_handle](../dotnet/auto-handle.md)   
 [auto\_handle::swap](../dotnet/auto-handle-swap.md)