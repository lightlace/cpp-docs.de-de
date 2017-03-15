---
title: "Compilerfehler C2512 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2512"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2512"
ms.assetid: 15206da9-1164-451a-b869-280e00711aad
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C2512
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier': Kein geeigneter Standardkonstruktor verfügbar  
  
 Für die angegebene Klasse, Struktur oder Union steht kein standardmäßiger Konstruktor zur Verfügung.  Der Compiler stellt nur dann einen standardmäßigen Konstruktor bereit, wenn keine benutzerdefinierten Konstruktoren bereitgestellt werden.  
  
 Wenn Sie einen Konstruktor bereitstellen, der einen Nicht\-„void“\-Parameter verwendet und Sie ermöglichen möchten, dass Ihre Klasse ohne Parameter erstellt wird \(beispielsweise wie die Elemente eines Arrays\), müssen Sie zudem einen standardmäßigen Konstruktor bereitstellen.  Beim standardmäßigen Konstruktor kann es sich um einen Konstruktor mit standardmäßigen Werten für alle Parameter handeln.  
  
 Im folgenden Beispiel wird C2512 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C2512.cpp  
// C2512 expected  
struct B {  
   B (char *);  
   // Uncomment the following line to fix.  
   // B() {};  
};  
  
int main() {  
   B b;   
}  
```  
  
 Das folgende Beispiel zeigt ein dezenteres C2512.  Ordnen Sie den zum Beheben dieses Fehlers den Code neu an, um die Klasse zu definieren, bevor ihr Konstruktor referenziert wird.  
  
```  
// C2512b.cpp  
// compile with: /c  
struct S {  
   struct X;  
  
   void f() {  
      X *x = new X();   // C2512 X not defined yet  
   }  
  
};  
  
struct S::X {};  
  
struct T {  
   struct X;  
   void f();  
};  
  
struct T::X {};  
  
void T::f() {  
   X *x = new X();  
}  
```  
  
 C2512 kann auch durch einen Aufruf für die standardmäßige Erstellung einer Klasse, die ein „const“\- oder Verweisdatenmember aufweist, verursacht werden.  Diese Member müssen in einer Konstruktorinitialisiererliste initialisiert werden. Diese verhindert, dass der Compiler einen Standardkonstruktor generiert.  
  
 Im folgenden Beispiel wird C2512 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C2512c.cpp  
// Compile by using: cl /c /W3 C2512c.cpp  
struct S {  
   const int i_;  
   int &r_;   
};   
  
int SumS() {  
   const int ci = 7;  
   int ir = 42;  
  
   S s1; // C2512 - no default constructor available  
   S s2{ci, ir};  // Fix - initialize const and reference members   
   return s2.i_ + s2.r_;  
}  
```