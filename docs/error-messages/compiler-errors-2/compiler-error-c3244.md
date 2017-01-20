---
title: "Compilerfehler C3244"
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
  - "C3244"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3244"
ms.assetid: dae6c49b-5212-4206-8f61-d4010c0b9969
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3244
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'methode': Diese Methode wurde von 'schnittstelle' eingeführt, nicht von 'schnittstelle'  
  
 Versuch zum [expliziten Überschreiben](../../cpp/explicit-overrides-cpp.md) eines Members, der in der angegebenen Schnittstelle nicht vorhanden ist, wohl aber in einer anderen Basisklasse.  
  
 Im folgenden Beispiel wird C3244 generiert:  
  
```  
// C3244.cpp #pragma warning(disable:4199) __interface IX15A { void f(); }; __interface IX15B { void g(); }; class CX15 : public IX15A, public IX15B { public: void IX15A::f(); void IX15B::g(); }; void CX15::IX15A::g()   // C3244 occurs here { }  
```