---
title: "Compilerwarnung (Stufe 2) C4356 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4356"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4356"
ms.assetid: 3af3defe-de33-43b6-bd6c-2c2e09e34f3f
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Compilerwarnung (Stufe 2) C4356
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Member': Statischer Datenmember darf nicht über eine abgeleitete Klasse initialisiert werden  
  
 Die Initialisierung eines statischen Datenmembers wurde nicht ordnungsgemäß formatiert.  Die Initialisierung wurde vom Compiler akzeptiert.  
  
 Hierbei handelt es sich um eine wichtige Änderung im Visual C\+\+ .NET 2003\-Compiler.  
  
 Bei Code, der in allen Versionen von Visual C\+\+ die gleiche Funktionsweise hat, initialisieren Sie den Member durch die Basisklasse.  
  
 Verwenden Sie das [warning](../../preprocessor/warning.md)\-Pragma, um diese Warnung zu unterdrücken.  
  
 Im folgenden Beispiel wird C4356 generiert:  
  
```  
// C4356.cpp  
// compile with: /W2 /EHsc  
#include <iostream>  
  
template <class T>  
class C {  
   static int n;  
};  
  
class D : C<int> {};  
  
int D::n = 0; // C4356  
// try the following line instead  
// int C<int>::n = 0;  
  
class A {  
public:  
   static int n;  
};  
  
class B : public A {};  
  
int B::n = 10;   // C4356  
// try the following line instead  
// int A::n = 99;  
  
int main() {  
   using namespace std;  
   cout << B::n << endl;  
}  
```