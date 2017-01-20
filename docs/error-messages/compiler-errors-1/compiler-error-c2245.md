---
title: "Compilerfehler C2245"
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
  - "C2245"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2245"
ms.assetid: 08aaeadf-10ec-485a-b2a6-6e775289082b
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2245
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Nicht vorhandene Memberfunktion "Funktion" wurde als Friend angegeben \(Memberfunktionssignatur stimmt nicht mit Überladungen überein\)  
  
 Eine als Friend angegebene Funktion wurde vom Compiler nicht gefunden.  
  
 Im folgenden Beispiel wird C2245 generiert:  
  
```  
// C2245.cpp // compile with: /c class B { void f(int i); }; class A { int m_i; friend void B::f(char);   // C2245 // try the following line instead // friend void B::f(int); }; void B::f(int i) { A a; a.m_i = 0; }  
```