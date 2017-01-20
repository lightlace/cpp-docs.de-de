---
title: "__super"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "__super_cpp"
  - "__super"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__super-Schlüsselwort [C++]"
ms.assetid: f0957c31-9256-405b-b402-cad182404b5f
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# __super
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Ermöglicht es Ihnen, explizit anzugeben, dass Sie eine Basisklassenimplementierung für eine Funktion aufrufen, die Sie überschreiben.  
  
## Syntax  
  
```  
  
__super::  
member_function  
();  
  
```  
  
## Hinweise  
 Alle verfügbaren Basisklassenmethoden werden während der Überladungsauflösungsphase berücksichtigt, und die Funktion, die die beste Übereinstimmung bereitstellt, ist die, die aufgerufen wird.  
  
 `__super` kann nur innerhalb des Texts einer Memberfunktion stehen.  
  
 `__super` kann nicht mit einer using\-Deklaration verwendet werden.  Weitere Informationen finden Sie unter [using\-Deklaration](../cpp/using-declaration.md).  
  
 Mit der Einführung von [Attributen](../windows/cpp-attributes-reference.md), die Code einfügen, kann Ihr Code eine oder mehrere Basisklassen enthalten, deren Namen Sie möglicherweise nicht kennen, die aber Methoden enthalten, die Sie aufrufen möchten.  
  
## Beispiel  
  
```  
// deriv_super.cpp  
// compile with: /c  
struct B1 {  
   void mf(int) {}  
};  
  
struct B2 {  
   void mf(short) {}  
  
   void mf(char) {}  
};  
  
struct D : B1, B2 {  
   void mf(short) {  
      __super::mf(1);   // Calls B1::mf(int)  
      __super::mf('s');   // Calls B2::mf(char)  
   }  
};  
```  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)