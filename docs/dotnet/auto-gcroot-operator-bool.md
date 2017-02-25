---
title: "auto_gcroot::operator bool | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "auto_gcroot.operator bool"
  - "auto_gcroot::operator bool"
  - "msclr.auto_gcroot.operator bool"
  - "msclr::auto_gcroot::operator bool"
  - "operator bool"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bool-Operator"
ms.assetid: 87d38498-4221-4de8-8d02-c2dd2e6274ec
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# auto_gcroot::operator bool
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Operator für die Anwendung von `auto_gcroot` in einem Bedingungsausdruck.  
  
## Syntax  
  
```  
operator bool() const;  
```  
  
## Rückgabewert  
 `true`, wenn das umschlossene Objekt gültig ist; andernfalls `false`.  
  
## Hinweise  
 Dieser Operator konvertiert tatsächlich an eine `_detail_class::_safe_bool`, die sicherer als `bool` ist, da es nicht zu einem ganzzahligen Typ konvertiert werden kann.  
  
## Beispiel  
  
```  
// msl_auto_gcroot_operator_bool.cpp  
// compile with: /clr  
#include <msclr\auto_gcroot.h>  
  
using namespace System;  
using namespace msclr;  
  
int main() {  
   auto_gcroot<String^> s;  
   if ( s ) Console::WriteLine( "s is valid" );  
   if ( !s ) Console::WriteLine( "s is invalid" );  
   s = "something";  
   if ( s ) Console::WriteLine( "now s is valid" );  
   if ( !s ) Console::WriteLine( "now s is invalid" );  
   s.reset();  
   if ( s ) Console::WriteLine( "now s is valid" );  
   if ( !s ) Console::WriteLine( "now s is invalid" );  
}  
```  
  
  **s ist ungültig**  
**jetzt s ist gültig**  
**jetzt s ist ungültig**   
## Anforderungen  
 **Headerdatei** \<msclr\\auto\_gcroot.h\>  
  
 **Namespace** msclr  
  
## Siehe auch  
 [auto\_gcroot Members](../dotnet/auto-gcroot-members.md)   
 [auto\_gcroot::operator\!](../dotnet/auto-gcroot-operator-logical-not.md)