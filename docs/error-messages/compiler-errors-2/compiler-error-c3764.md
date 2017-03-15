---
title: "Compilerfehler C3764 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3764"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3764"
ms.assetid: af5d254c-8d4a-4dda-aad9-3c5c1257c868
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerfehler C3764
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'override\_function': Basisklassenmethode 'base\_class\_function' kann nicht überschrieben werden  
  
 Der Compiler hat eine falsch formatierte Überschreibung entdeckt.  Die Basisklassenfunktion war beispielsweise nicht `virtual`.  Weitere Informationen finden Sie unter [override](../../windows/override-cpp-component-extensions.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C3764 generiert.  
  
```  
// C3764.cpp  
// compile with: /clr /c  
public ref struct A {  
   void g(int);  
   virtual void h(int);  
};  
  
public ref struct B : A {  
   virtual void g(int) override {}   // C3764  
   virtual void h(int) override {}   // OK  
};  
```  
  
## Beispiel  
 C3764 kann auch auftreten, wenn eine Basisklassenmethode explizit und benannt überschrieben ist.  Im folgenden Beispiel wird C3764 generiert.  
  
```  
// C3764_b.cpp  
// compile with: /clr /c  
ref struct A {  
   virtual void Test() {}  
};  
  
ref struct B : public A {  
   virtual void Test() override {}  
   virtual void Test2() = A::Test {}   // C3764  
};  
```