---
title: "Compilerfehler C3421"
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
  - "C3421"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3421"
ms.assetid: b52050c6-17a4-424a-8894-337b0cec7010
caps.latest.revision: 3
caps.handback.revision: "3"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3421
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Typ': Sie können den Finalizer für diese Klasse nicht aufrufen, da er nicht zugreifbar oder nicht vorhanden ist.  
  
 Ein Finalizer ist implizit privat, sodass er von außerhalb des einschließenden Typs nicht aufgerufen werden kann.  
  
 Weitere Informationen finden Sie unter [Destruktoren und Finalizer in Visual C\+\+](../../misc/destructors-and-finalizers-in-visual-cpp.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C3421 generiert:  
  
```  
// C3421.cpp // compile with: /clr ref class A {}; ref class B { !B() {} public: ~B() {} }; int main() { A a; a.!A();   // C3421 B b; b.!B();   // C3421 }  
```