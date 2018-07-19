---
title: Compilerfehler C2247 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2247
dev_langs:
- C++
helpviewer_keywords:
- C2247
ms.assetid: 72efa03e-615e-4ef9-aede-0a98654b20fd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ed27398ea1f51ccc2ef0d3339446b422c7a503c0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33172312"
---
# <a name="compiler-error-c2247"></a>Compilerfehler C2247
'Bezeichner' nicht möglich, da 'Klasse' "Spezifizierer" verwendet, um von 'Klasse' erben.  
  
 `identifier` wird von einer Klasse deklariert mit privaten oder geschützten Zugriff geerbt.  
  
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
  
 Dieser Fehler kann außerdem infolge einer konformitätsverbesserung für Visual Studio .NET 2003 durchgeführt wurde, die generiert werden: Zugriffssteuerung mit geschützte Member. Ein geschützter Member (n) kann nur über eine Memberfunktion einer Klasse (B) zugegriffen werden, die von der Klasse (A) erbt der (n) angehört.  
  
 Deklarieren Sie für Code, der im Visual Studio .NET 2003 und Visual Studio .NET Versionen von Visual C++ gültig ist das Element einen "Friend" des Typs sein. Öffentliche Vererbung kann auch verwendet werden.  
  
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
  
 C2247 kann außerdem infolge einer konformitätsverbesserung für Visual Studio .NET 2003 durchgeführt wurde, die generiert werden: private Basisklassen nicht zugegriffen werden kann. Eine Klasse (A), die eine private Basisklasse in einen Typ ist (B) sollte nicht auf einen Typ zugegriffen werden (C), die B als Basisklasse verwendet.  
  
 Verwenden Sie für Code, der im Visual Studio .NET 2003 und Visual Studio .NET Versionen von Visual C++ gültig ist den Bereichsoperator.  
  
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