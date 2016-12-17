---
title: "Namensaufl&#246;sung f&#252;r lokal deklarierte Namen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
ms.assetid: 743b88f3-de11-48f4-ae83-931449ea3886
caps.latest.revision: 11
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Namensaufl&#246;sung f&#252;r lokal deklarierte Namen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der Name der Vorlage selbst kann mit oder ohne Vorlagenargumente angegeben werden.  Im Bereich einer Klassenvorlage bezieht sich der Name selbst auf die Vorlage.  Im Bereich einer Vorlagenspezialisierung oder Teilspezialisierung bezieht sich der Name allein auf die Spezialisierung oder Teilspezialisierung.  Andere Spezialisierungen oder Teilspezialisierungen der Vorlage können mit den entsprechenden Vorlagenargumenten ebenfalls referenziert werden.  
  
## Beispiel  
 Der folgende Code zeigt, dass der Name der Klassenvorlage A im Bereich einer Spezialisierung oder einer teilweisen Spezialisierung unterschiedlich interpretiert wird.  
  
```  
// template_name_resolution3.cpp  
// compile with: /c  
template <class T> class A {  
   A* a1;   // A refers to A<T>  
   A<int>* a2;  // A<int> refers to a specialization of A.  
   A<T*>* a3;   // A<T*> refers to the partial specialization A<T*>.  
};  
  
template <class T> class A<T*> {  
   A* a4; // A refers to A<T*>.  
};  
  
template<> class A<int> {  
   A* a5; // A refers to A<int>.  
};  
```  
  
## Beispiel  
 Im Falle eines Namenskonflikts zwischen einem Vorlagenparameter und einem anderen Objekt kann der Vorlagenparameter ausgeblendet oder nicht ausgeblendet werden.  Die folgenden Regeln bestimmen die Vorrangigkeit.  
  
 Der Vorlagenparameter befindet sich ab seinem ersten Auftreten bis zum Ende der Klasse oder Funktionsvorlage im Gültigkeitsbereich.  Wenn der Name erneut in der Vorlagenargumentliste oder in der Liste der Basisklassen vorkommt, bezieht er sich auf denselben Typ.  In Standard\-C\+\+ kann kein anderer Name, der mit dem Vorlagenparameter identisch ist, im selben Gültigkeitsbereich deklariert werden.  Mit einer Microsoft\-Erweiterung kann der Vorlagenparameter im Gültigkeitsbereich der Vorlage neu definiert werden.  Das folgende Beispiel zeigt die Verwendung des Vorlagenparameters in der Basisspezifizierung einer Klassenvorlage.  
  
```  
// template_name_resolution4.cpp  
// compile with: /EHsc  
template <class T>  
class Base1 {};  
  
template <class T>  
class Derived1 : Base1<T> {};  
  
int main() {  
   // Derived1<int> d;  
}  
```  
  
## Beispiel  
 Wenn Sie die Memberfunktionen einer Vorlage außerhalb der Klassenvorlage definieren, kann ein anderer Vorlagenparametername verwendet werden.  Wenn die Definition für die Vorlagenmemberfunktion einen anderen Namen für den Vorlagenparameter verwendet als die Deklaration, und der Name in der Definition mit einem anderen Member der Deklaration in Konflikt steht, hat der Member in der Vorlagendeklaration Vorrang.  
  
```  
// template_name_resolution5.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
template <class T> class C {  
public:  
   struct Z {  
      Z() { cout << "Z::Z()" << endl; }  
   };  
   void f();  
};  
  
template <class Z>  
void C<Z>::f() {  
   // Z refers to the struct Z, not to the template arg;  
   // Therefore, the constructor for struct Z will be called.  
   Z z;  
}  
  
int main() {  
   C<int> c;  
   c.f();  
}  
```  
  
  **Z::Z\(\)**   
## Beispiel  
 Wenn eine Vorlagenfunktion oder Memberfunktion außerhalb des Namespaces definiert wird, in dem die Vorlage deklariert wurde, hat das Vorlagenargument Vorrang vor den Namen anderer Member des Namespaces.  
  
```  
// template_name_resolution6.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
namespace NS {  
   void g() { cout << "NS::g" << endl; }  
  
   template <class T> struct C {  
      void f();  
      void g() { cout << "C<T>::g" << endl; }  
   };  
};  
  
template <class T>  
void NS::C<T>::f() {  
   g(); // C<T>::g, not NS::g  
};  
  
int main() {  
   NS::C<int> c;  
   c.f();  
}  
```  
  
  **C\<T\>::g**   
## Beispiel  
 In Definitionen, die sich außerhalb der Deklaration der Vorlagenklassen befinden, gilt: Wenn eine Vorlagenklasse über eine Basisklasse verfügt, die nicht von einem Vorlagenargument abhängig ist, und wenn die Basisklasse oder einer ihrer Member über denselben Namen wie ein Vorlagenargument verfügt, blendet die Basisklasse oder der Membername das Vorlagenargument aus.  
  
```  
// template_name_resolution7.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
struct B {  
   int i;  
   void print() { cout << "Base" << endl; }  
};  
  
template <class T, int i> struct C : public B {  
   void f();  
};  
  
template <class B, int i>  
void C<B, i>::f() {  
   B b;   // Base class b, not template argument.  
   b.print();  
   i = 1; // Set base class's i to 1.  
}  
  
int main() {  
   C<int, 1> c;  
   c.f();  
   cout << c.i << endl;  
}  
```  
  
  **Base**  
**1**   
## Siehe auch  
 [Namensauflösung](../cpp/templates-and-name-resolution.md)