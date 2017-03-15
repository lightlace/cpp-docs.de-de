---
title: "Compilerwarnung (Stufe 2) C4250 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4250"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4250"
ms.assetid: d47f7249-6b5a-414b-b2d4-56e5d246a782
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Compilerwarnung (Stufe 2) C4250
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Klasse1': Erbt 'Klasse2::Member' via Dominanz  
  
 Zwei oder mehr Member haben denselben Namen.  Der Member in `class2` wird geerbt, da es eine Basisklasse für die anderen Klassen ist, in denen dieser Member enthalten war.  
  
 Um C4250 zu unterdrücken, verwenden Sie das [warning](../../preprocessor/warning.md)\-Pragma.  
  
 Da eine virtuelle Basisklasse von mehreren abgeleiteten Klassen gemeinsam verwendet wird, dominiert ein Name in einer abgeleiteten Klasse einen Namen in einer Basisklasse.  Beispielsweise gibt es bei der folgenden Klassenhierarchie zwei Definitionen für func, die innerhalb einer diamond\-Anweisung geerbt werden: Die vbc::func\(\)\-Instanz durch die schwache Klasse und die dominant::func\(\)\-Instanz durch die dominante Klasse.  Ein nicht qualifizierter Aufruf von func\(\) durch ein diamond\-Klassenobjekt führt stets zum Aufruf der dominate::func\(\)\-Instanz.  Wenn durch die schwache Klasse eine Instanz von func\(\) eingeführt wird, dominiert keine der Definitionen, und der Aufruf wird als mehrdeutig gekennzeichnet.  
  
```  
// C4250.cpp  
// compile with: /c /W2  
#include <stdio.h>  
struct vbc {  
   virtual void func() { printf("vbc::func\n"); }  
};  
  
struct weak : public virtual vbc {};  
  
struct dominant : public virtual vbc {  
   void func() { printf("dominant::func\n"); }  
};  
  
struct diamond : public weak, public dominant {};  
  
int main() {  
   diamond d;  
   d.func();   // C4250  
}  
```  
  
## Beispiel  
 Im folgenden Beispiel wird C4250 generiert.  
  
```  
// C4250_b.cpp  
// compile with: /W2 /EHsc  
#include <iostream>  
using namespace std;  
class A {  
public:  
   virtual operator int () {  
      return 2;  
   }  
};  
  
class B : virtual public A {  
public:  
   virtual operator int () {  
      return 3;  
   }  
};  
  
class C : virtual public A {};  
  
class E : public B, public C {};   // C4250  
  
int main() {  
   E eObject;  
   cout << eObject.operator int() << endl;  
}  
```  
  
## Beispiel  
 In diesem Beispiel wird eine komplexere Situation dargestellt.  Im folgenden Beispiel wird C4250 generiert.  
  
```  
// C4250_c.cpp  
// compile with: /W2 /EHsc  
#include <iostream>  
using namespace std;  
  
class V {  
public:  
   virtual int f() {  
      return 1024;  
   }  
};  
  
class B : virtual public V {  
public:  
   int b() {  
      return f(); // B::b() calls V::f()  
   }  
};  
  
class M : virtual public V {  
public:  
   int f() {  
      return 7;  
   }  
};  
  
// because of dominance, f() is M::f() inside D,  
// changing the meaning of B::b's f() call inside a D  
class D : public B, public M {};   // C4250  
  
int main() {  
   D d;  
   cout << "value is: " << d.b();   // invokes M::f()  
}  
```