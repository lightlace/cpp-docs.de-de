---
title: "Compilerwarnung (Stufe 4) C4913 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4913"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4913"
ms.assetid: b94aa52e-6029-4170-9134-017714931546
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# Compilerwarnung (Stufe 4) C4913
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**Benutzerdefinierter binärer Operator "," ist vorhanden, die Überladung konnte aber alle Operanden nicht konvertieren. Es wurde der standardmäßig enthaltene binäre Operator "," verwendet.**  
  
 Ein Aufruf des integrierten Kommaoperators ist in einem Programm aufgetreten, das ebenfalls einen überladenen Kommaoperator aufweist. Eine erwartete Konvertierung ist nicht erfolgt.  
  
 Im folgenden Codebeispiel wird C4913 generiert:  
  
```  
// C4913.cpp // compile with: /W4 struct A { }; struct S { }; struct B { // B() { } // B(S &s) { s; } }; B operator , (A a, B b) { a; return b; } int main() { A a; B b; S s; a, b;   // OK calls user defined operator a, s;   // C4913 uses builtin comma operator // uncomment the conversion code in B to resolve. }  
```