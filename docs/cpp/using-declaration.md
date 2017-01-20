---
title: "using-Deklaration"
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
helpviewer_keywords: 
  - "using-Deklaration"
  - "Deklarieren von Namespaces, nicht qualifizierte Namen in Namespaces"
  - "Deklarationen [C++], using-Deklaration"
  - "Namespaces [C++], nicht qualifizierte Namen in"
  - "using-Schlüsselwort [C++]"
  - "Deklarationen [C++], Namespaces"
ms.assetid: 4184e2b1-3adc-408e-b5f3-0b3f8b554723
caps.latest.revision: 12
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# using-Deklaration
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die `using`\-Deklaration erstellt einen Namen im deklarativen Bereich, in dem die `using`\-Deklaration angezeigt wird.  
  
## Syntax  
  
```  
  
      using [typename][::] nested-name-specifier unqualified-id  
using :: unqualified-id  
```  
  
## Hinweise  
 Der Name wird zum Synonym für eine Entität, die an anderer Stelle deklariert wurde.  Sie können einen *individuellen* Namen von einem bestimmten Namespace ohne [explizite Qualifizierung](../misc/explicit-qualification.md) verwenden.  Dies steht im Gegensatz zur `using`\-Direktive, mit der *alle* Namen in einem Namespace ohne Qualifikation verwendet werden können.  Weitere Information finden Sie im Artikel zu [using\-Direktive](../misc/using-directive-cpp.md).  Dieses Schlüsselwort wird auch für [Typaliase](../cpp/aliases-and-typedefs-cpp.md) verwendet.  
  
## Beispiel  
 Eine using\-Deklaration kann in einer Klassendefinition verwendet werden.  
  
```cpp  
// using_declaration1.cpp  
#include <stdio.h>  
class B {  
public:  
   void f(char) {  
      printf_s("In B::f()\n");  
   }  
  
   void g(char) {  
      printf_s("In B::g()\n");  
   }  
};  
  
class D : B {  
public:  
   using B::f;  
   using B::g;  
   void f(int) {  
      printf_s("In D::f()\n");  
      f('c');  
   }  
  
   void g(int) {  
      printf_s("In D::g()\n");  
      g('c');  
   }  
};  
  
int main() {  
   D myD;  
   myD.f(1);  
   myD.g('a');  
}  
```  
  
  **In D::f\(\)**  
**In B::f\(\)**  
**In B::g\(\)**   
## Beispiel  
 Bei Verwendung zum Deklarieren eines Members muss eine using\-Deklaration auf den Member einer Basisklasse verweisen.  
  
```cpp  
// using_declaration2.cpp  
#include <stdio.h>  
  
class B {  
public:  
   void f(char) {  
      printf_s("In B::f()\n");  
   }  
  
   void g(char) {  
      printf_s("In B::g()\n");  
   }  
};  
  
class C {  
public:  
   int g();  
};  
  
class D2 : public B {  
public:  
   using B::f;   // ok: B is a base of D2  
   // using C::g;   // error: C isn't a base of D2  
};  
  
int main() {  
   D2 MyD2;  
   MyD2.f('a');  
}  
```  
  
  **In B::f\(\)**   
## Beispiel  
 Member, die mit einer using\-Deklaration deklariert werden, können mithilfe der expliziten Qualifikation referenziert werden.  Das Präfix `::` verweist auf den globalen Namespace.  
  
```cpp  
// using_declaration3.cpp  
#include <stdio.h>  
  
void f() {  
   printf_s("In f\n");  
}  
  
namespace A {  
   void g() {  
      printf_s("In A::g\n");  
   }  
}  
  
namespace X {  
   using ::f;   // global f  
   using A::g;   // A's g  
}  
  
void h() {  
   printf_s("In h\n");  
   X::f();   // calls ::f  
   X::g();   // calls A::g  
}  
  
int main() {  
   h();  
}  
```  
  
  **In h**  
**In f**  
**In A::g**   
## Beispiel  
 Wenn eine using\-Deklaration erfolgt, verweist das von der Deklaration erstellte Synonym nur auf Definitionen, die zum Zeitpunkt der using\-Deklaration gültig waren.  Definitionen, die nach der using\-Deklaration einem Namespace hinzugefügt werden, sind ungültige Synonyme.  
  
 Ein Name, der durch eine using\-Deklaration definiert wird, ist ein Alias für den ursprünglichen Namen.  Er wirkt sich nicht auf den Typ, die Verknüpfung oder andere Attribute der ursprünglichen Deklaration aus.  
  
```cpp  
// post_declaration_namespace_additions.cpp  
// compile with: /c  
namespace A {  
   void f(int) {}  
}  
  
using A::f;   // f is a synonym for A::f(int) only  
  
namespace A {  
   void f(char) {}  
}  
  
void f() {  
   f('a');   // refers to A::f(int), even though A::f(char) exists  
}  
  
void b() {  
   using A::f;   // refers to A::f(int) AND A::f(char)  
   f('a');   // calls A::f(char);  
}  
```  
  
## Beispiel  
 In Bezug auf Funktionen in Namespaces gilt Folgendes: Wenn eine Reihe von lokalen Deklarationen und using\-Deklarationen in einem deklarativen Gültigkeitsbereich für einen einzelnen Namen angegeben werden, müssen alle auf dieselbe Entität verweisen, oder sie müssen alle auf Funktionen verweisen.  
  
```cpp  
// functions_in_namespaces1.cpp  
// C2874 expected  
namespace B {  
    int i;  
    void f(int);  
    void f(double);  
}  
  
void g() {  
    int i;  
    using B::i;   // error: i declared twice  
    void f(char);  
    using B::f;   // ok: each f is a function  
}  
```  
  
 Im Beispiel oben veranlasst die `using B::i`\-Anweisung, dass eine zweite `int i` in der `g()`\-Funktion deklariert wird.  Die `using B::f`\-Anweisung steht nicht mit der `f(char)`\-Funktion in Konflikt, da die Funktionsnamen, die von `B::f` eingeführt werden, über verschiedene Parametertypen verfügen.  
  
## Beispiel  
 Eine lokale Funktionsdeklaration kann nicht den gleichen Namen und Typ wie eine Funktion haben, die von einer using\-Deklaration eingeführt wird.  Beispiel:  
  
```cpp  
// functions_in_namespaces2.cpp  
// C2668 expected  
namespace B {  
    void f(int);  
    void f(double);  
}  
  
namespace C {  
    void f(int);  
    void f(double);  
    void f(char);  
}  
  
void h() {  
    using B::f;          // introduces B::f(int) and B::f(double)  
    using C::f;          // C::f(int), C::f(double), and C::f(char)  
    f('h');              // calls C::f(char)  
    f(1);                // C2668 ambiguous: B::f(int) or C::f(int)?  
    void f(int);         // C2883 conflicts with B::f(int) and C::f(int)  
}  
```  
  
## Beispiel  
 In Bezug auf Vererbung gilt Folgendes: Wenn eine using\-Deklaration einen Namen aus einer Basisklasse in den Gültigkeitsbereich einer abgeleiteten Klasse einführt, überschreiben Memberfunktionen in der abgeleiteten Klasse virtuelle Memberfunktionen in der Basisklasse, die denselben Namen und dieselben Argumenttypen aufweisen.  
  
```cpp  
// using_declaration_inheritance1.cpp  
#include <stdio.h>  
struct B {  
   virtual void f(int) {  
      printf_s("In B::f(int)\n");  
   }  
  
   virtual void f(char) {  
      printf_s("In B::f(char)\n");  
   }  
  
   void g(int) {  
      printf_s("In B::g\n");  
   }  
  
   void h(int);  
};  
  
struct D : B {  
   using B::f;  
   void f(int) {   // ok: D::f(int) overrides B::f(int)  
      printf_s("In D::f(int)\n");  
   }  
  
   using B::g;  
   void g(char) {   // ok: there is no B::g(char)  
      printf_s("In D::g(char)\n");  
   }  
  
   using B::h;  
   void h(int) {}   // Note: D::h(int) hides non-virtual B::h(int)  
};  
  
void f(D* pd) {  
   pd->f(1);   // calls D::f(int)  
   pd->f('a');   // calls B::f(char)  
   pd->g(1);   // calls B::g(int)  
   pd->g('a');   // calls D::g(char)  
}  
  
int main() {  
   D * myd = new D();  
   f(myd);  
}  
```  
  
  **In D::f\(int\)**  
**In B::f\(char\)**  
**In B::g**  
**In D::g\(char\)**   
## Beispiel  
 Alle in einer using\-Deklaration erwähnten Instanzen eines Namens müssen verfügbar sein.  Insbesondere muss der Membername zugänglich sein, wenn eine abgeleitete Klasse eine using\-Deklaration verwendet, um auf einen Member einer Basisklasse zuzugreifen.  Wenn der Name der einer überladenen Memberfunktion ist, muss auf alle genannten Funktionen zugegriffen werden können.  
  
 Weitere Informationen über den Zugriff von Membern erhalten Sie im Artikel über [Memberzugriffssteuerung](../cpp/member-access-control-cpp.md).  
  
```cpp  
// using_declaration_inheritance2.cpp  
// C2876 expected  
class A {  
private:  
   void f(char);  
public:  
   void f(int);  
protected:  
   void g();  
};  
  
class B : public A {  
   using A::f;   // C2876: A::f(char) is inaccessible  
public:  
   using A::g;   // B::g is a public synonym for A::g  
};  
```  
  
## Siehe auch  
 [Namespaces](../cpp/namespaces-cpp.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)