---
title: "Compilerfehler C3365"
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
  - "C3365"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3365"
ms.assetid: 875ec3a4-522c-4e3d-9b67-48808b857f6d
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3365
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Operator\-Operator: Unterschiedliche Operanden vom Typ "Typ1" und "Typ2".  
  
 Es wurde versucht, Delegaten mit unterschiedlichen Typen zu erstellen.  Weitere Informationen zu Delegaten finden Sie unter [Gewusst wie: Erstellen von Delegaten](../../misc/how-to-compose-delegates.md).  
  
 Im folgenden Beispiel wird C3365 generiert:  
  
```  
// C3365.cpp // compile with: /clr delegate void D1(); delegate void D2(int); ref class R { public: void f(){} void g(int){} }; int main() { D1^ d1 = gcnew D1(gcnew R, &R::f); D2^ d2 = gcnew D2(gcnew R, &R::g); D1^ d3 = gcnew D1(gcnew R, &R::f); d1 += d2;   // C3365 d1 += d3;   // OK d1(); }  
```