---
title: "Compilerfehler C2875"
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
  - "C2875"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2875"
ms.assetid: d589fc0c-08b2-4a79-bc0e-dca5eb80bdd5
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2875
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

using\-Deklaration verursacht eine mehrfache Deklaration von 'class::identifier'  
  
 Die Deklaration bewirkt, dass dasselbe Element zweimal definiert wird.  
  
 Im folgenden Beispiel wird C2875 generiert:  
  
```  
// C2875.cpp  
struct A {  
   void f(int*);  
};  
  
struct B {  
   void f(double*);  
};  
  
struct AB : A, B {  
   using A::f;  
   using A::f;   // C2875  
   using B::f;  
};  
```