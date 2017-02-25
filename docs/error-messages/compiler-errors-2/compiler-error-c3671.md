---
title: "Compilerfehler C3671 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3671"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3671"
ms.assetid: d684e4ae-87e2-4424-80bb-6f346652c831
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerfehler C3671
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion\_1': Funktion überschreibt 'Funktion\_2' nicht  
  
 Beim Verwenden einer expliziten Überschreibungssyntax generiert der Compiler einen Fehler, wenn eine Funktion nicht überschrieben wird.  Weitere Informationen finden Sie unter [Explicit Overrides](../../windows/explicit-overrides-cpp-component-extensions.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C3671 generiert.  
  
```  
// C3671.cpp  
// compile with: /clr /c  
ref struct S {  
   virtual void f();  
};  
  
ref struct S1 : S {  
   virtual void f(int) new sealed = S::f;   // C3671  
   virtual void f() new sealed = S::f;  
};  
```