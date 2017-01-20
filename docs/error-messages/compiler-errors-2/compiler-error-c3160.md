---
title: "Compilerfehler C3160"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C3160"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3160"
ms.assetid: a250c433-8adf-43b9-8dee-c3794e09b0a5
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3160
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

„Zeiger“: Ein Datenmember einer verwalteten oder WinRT\-Klasse kann nicht diesen Typ aufweisen.  
  
 Innere Garbage Collection\-Zeiger können auf das Innere einer verwalteten oder WinRT\-Klasse verweisen.  Da diese langsamer als Zeiger auf gesamte Objekte sind und eine besondere Behandlung durch den Garbage Collector erfordern, können innere verwaltete Zeiger nicht als Member einer Klasse deklariert werden.  
  
 Im folgenden Beispiel wird C3160 generiert:  
  
```  
// C3160.cpp  
// compile with: /clr  
ref struct A {  
   // cannot create interior pointers inside a class  
   interior_ptr<int> pg;   // C3160  
   int g;   // OK  
   int* pg2;   // OK  
};  
  
int main() {  
   interior_ptr<int> pg2;   // OK  
}  
```  
  
 **Verwaltete Erweiterungen für C\+\+**  
  
 Im folgenden Beispiel wird C3160 generiert:  
  
```  
// C3160b.cpp  
// compile with: /clr:oldSyntax  
  
__gc struct A {  
   // cannot create interior pointers inside a class  
   int __gc* pg; // C3160  
   int g;   // OK  
   int __nogc *pg2;   // OK  
};  
  
int main() {  
   int __gc* pg2;   // OK  
}  
```