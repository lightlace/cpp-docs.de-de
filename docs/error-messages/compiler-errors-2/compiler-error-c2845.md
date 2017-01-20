---
title: "Compilerfehler C2845"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C2845"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2845"
ms.assetid: 31b28ee9-978f-403b-94d8-dbaacd24cce0
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2845
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Operator': Zeigerarithmetik ist für diesen Typ nicht zulässig  
  
 Der Zeiger kann nicht auf eine verwaltete Klasse erhöht werden.  
  
 **Managed Extensions for C\+\+**  
  
 Der Zeiger kann nicht auf eine [\_\_gc](../../misc/gc.md)\-Klasse erhöht werden.  Zeichenfolgenoperatoren sind außerdem nur mit **\/clr** gültig \(nicht mit **\/clr:oldSyntax**\).  
  
 Im folgenden Beispiel wird C2845 generiert:  
  
```  
// C2845b.cpp  
// compile with: /clr:oldSyntax  
using namespace System;  
__gc class X {};  
  
int main() {  
   X *pX = new X;  
   pX++;   // C2845  
  
   String * a = new String("abc");  
   String * b = new String("def");  
   Console::WriteLine(a + b);   // C2845 not with /clr:oldSyntax  
}  
```