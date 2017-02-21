---
title: "Compilerfehler C2316 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2316"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2316"
ms.assetid: 9ad08eb5-060b-4eb0-8d66-0dc134f7bf67
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Compilerfehler C2316
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Ausnahme": Kann nicht aufgefangen werden, da auf den Destruktor und\/oder den copy\-Konstruktor nicht zugegriffen werden kann.  
  
 Eine Ausnahme wurde durch einen Wert oder Verweis abgefangen, aber auf den copy\-Konstruktor und\/oder den Zuweisungsoperator konnte nicht zugegriffen werden.  
  
 Dieser Code wurde vom Compiler der Vorgängerversion akzeptiert, verursacht jetzt jedoch einen Fehler.  
  
## Beispiel  
 Im folgenden Beispiel wird C2316 generiert:  
  
```  
// C2316.cpp // compile with: /EHsc #include <stdio.h> extern "C" int printf_s(const char*, ...); struct B { public: B() {} // Delete the following line to resolve. private: // copy constructor B(const B&) { } }; void f(const B&) { } int main() { try { B aB; f(aB); } catch (B b) {   // C2316 printf_s("Caught an exception!\n"); } }  
```