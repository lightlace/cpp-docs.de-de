---
title: "Compilerfehler C2171"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "C2171"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2171"
ms.assetid: a80343b5-ab3f-4413-b6f1-3ce9d7e519e5
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2171
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

„operator“: für Operanden vom Typ „type“ nicht zulässig.  
  
 Ein unärer Operator wird zusammen mit einem ungültigen Operandentyp verwendet.  
  
## Beispiel  
 Im folgenden Beispiel wird C2171 generiert:  
  
```  
// C2171.cpp int main() { double d, d1; d = ~d1;   // C2171 // OK int d2 = 0, d3 = 0; d2 = ~d3; }  
```  
  
## Beispiel  
 Im folgenden Beispiel wird C2171 generiert:  
  
```  
// C2171_b.cpp // compile with: /c class A { public: A() { STF( &A::D ); } void D() {} void DTF() { (*TF)();   // C2171 (this->*TF)();   // OK } void STF(void (A::*fnc)()) { TF = fnc; } private: void (A::*TF)(); };  
```