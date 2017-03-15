---
title: "Compilerfehler C2247 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2247"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2247"
ms.assetid: 72efa03e-615e-4ef9-aede-0a98654b20fd
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# Compilerfehler C2247
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Zugriff auf 'Bezeichner' nicht möglich, da 'Klasse' 'Spezifizierer' verwendet, um von 'Klasse' zu erben  
  
 `identifier` wurde von einer Klasse geerbt, die mit privatem oder geschütztem Zugriff deklariert wurde.  
  
 Im folgenden Beispiel wird C2247 generiert:  
  
```  
// C2247.cpp  
class A {  
public:  
   int i;  
};  
class B : private A {};    // B inherits a private A  
class C : public B {} c;   // so even though C's B is public  
int j = c.i;               // C2247, i not accessible  
```  
  
 Dieser Fehler kann auch aufgrund einer Verbesserung der Compilerkonformität in Visual Studio .NET 2003 ausgegeben werden: Zugriffssteuerung mit geschützten Membern.  Auf einen geschützten Member \(n\) kann nur über eine Memberfunktion einer Klasse \(B\) zugegriffen werden, die von der Klasse \(A\) erbt, der \(n\) als Member angehört.  
  
 In Code, der sowohl in der Visual Studio .NET 2003\-Version als auch in der Visual Studio .NET\-Version von Visual C\+\+ gültig ist, deklarieren Sie den Member als `friend` des Typs.  Darüber hinaus kann öffentliche Vererbung verwendet werden.  
  
```  
// C2247b.cpp  
// compile with: /c  
// C2247 expected  
class A {  
public:  
   void f();  
   int n;  
};  
  
class B: protected A {  
   // Uncomment the following line to resolve.  
   // friend void A::f();  
};  
  
void A::f() {  
   B b;  
   b.n;  
}  
```  
  
 C2247 kann auch aufgrund einer Verbesserung der Compilerkonformität in Visual Studio .NET 2003 ausgegeben werden: kein Zugriff auf private Basisklassen möglich.  Auf eine Klasse \(A\), die eine private Basisklasse für einen Typ \(B\) ist, sollte von einem Typ \(C\), der B als Basisklasse verwendet, kein Zugriff möglich sein.  
  
 Für Code, der sowohl in der Visual Studio .NET 2003\-Version als auch in der Visual Studio .NET\-Version von Visual C\+\+ gültig ist, verwenden Sie den Bereichsoperator.  
  
```  
// C2247c.cpp  
// compile with: /c  
struct A {};  
  
struct B: private A {};  
  
struct C : B {  
   void f() {  
      A *p1 = (A*) this;   // C2247  
      // try the following line instead  
      // ::A *p2 = (::A*) this;  
   }  
};  
```