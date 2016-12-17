---
title: "Compilerfehler C3166"
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
  - "C3166"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3166"
ms.assetid: ec3e330d-c15d-4158-8268-09101486c566
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3166
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Zeiger' : Ein Zeiger auf einen internen \_\_gc\-Zeiger kann nicht als Member von 'Typ' deklariert werden  
  
 Der Compiler hat eine ungültige Zeigerdeklaration gefunden \(ein [\_\_nogc](../../misc/nogc.md)\-Pointer auf einen [\_\_gc](../../misc/gc.md)\-Pointer.\).  Diese Syntax wird in zukünftigen Versionen u. U. unterstützt.  
  
 C3166 ist nur mit **\/clr:oldSyntax** erreichbar.  
  
 Im folgenden Beispiel wird C3166 generiert:  
  
```  
// C3166.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
using namespace System;  
  
__gc struct G {  
   int __gc* __nogc* p;   // C3166  
};  
  
public __gc class H {  
public:  
   Int32 __gc* __nogc* p;   // C3166  
};  
  
public __value struct I {  
   int __gc* __nogc* p;   // C3166  
};  
  
public __value class J {  
public:  
   int __gc* __nogc* p;   // C3166  
};  
  
int main() {  
   G* pG = new G;  
   H* pH = new H;  
}  
```