---
title: "Compilerfehler C3243"
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
  - "C3243"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3243"
ms.assetid: 35d8ad1a-377d-47df-be9d-c55eea23340f
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3243
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Keine der überladenen Funktionen wurde von "Schnittstelle" eingeführt  
  
 Sie haben versucht, einen Member, der in der angegebenen Schnittstelle nicht nicht vorhanden ist, [explizit zu überschreiben](../../cpp/explicit-overrides-cpp.md).  
  
 Im folgenden Beispiel wird C3243 generiert:  
  
```  
// C3243.cpp #pragma warning(disable:4199) __interface IX14A { void g(); }; __interface IX14B { void f(); void f(int); }; class CX14 : public IX14A, public IX14B { public: void IX14A::g(); void IX14B::f(); void IX14B::f(int); }; void CX14::IX14A::f()   // C3243 occurs here { }  
```