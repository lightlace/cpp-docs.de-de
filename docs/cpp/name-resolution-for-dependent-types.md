---
title: "Namensaufl&#246;sung f&#252;r abh&#228;ngige Typen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
ms.assetid: 34066bb4-0c79-4fd8-bda7-539a60a277ab
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Namensaufl&#246;sung f&#252;r abh&#228;ngige Typen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Verwenden Sie **typename** für qualifizierte Namen in Vorlagendefinitionen, um dem Compiler mitzuteilen, dass der angegebene qualifizierte Typ einen Namen identifiziert.  Weitere Informationen finden Sie unter [Typname](../cpp/typename.md).  
  
```cpp  
// template_name_resolution1.cpp  
#include <stdio.h>  
template <class T> class X  
{  
public:  
   void f(typename T::myType* mt) {}  
};  
  
class Yarg  
{  
public:  
   struct myType { };  
};  
  
int main()  
{  
   X<Yarg> x;  
   x.f(new Yarg::myType());  
   printf("Name resolved by using typename keyword.");  
}  
```  
  
### Ausgabe  
  
```  
Name resolved by using typename keyword.  
```  
  
 Die Namenssuche nach abhängigen Namen überprüft sowohl Namen aus Kontext der Vorlagendefinition \(im folgenden Beispiel würde dieser Kontext `myFunction(char)` suchen\) als auch aus dem Kontext der Vorlageninstanziierung.  Im folgenden Beispiel wird die Vorlage in "main" instanziiert. Daher ist `MyNamespace::myFunction` vom Zeitpunkt der Instanziierung sichtbar und wird als bessere Übereinstimmung ausgewählt.  Wenn `MyNamespace::myFunction` umbenannt wurde, wird stattdessen `myFunction(char)` aufgerufen.  
  
 Alle Namen werden aufgelöst, als ob sie abhängige Namen wären.  Dennoch wird empfohlen, vollqualifizierte Namen zu verwenden, wenn ein möglicher Konflikte besteht.  
  
```cpp  
//template_name_resolution2.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
void myFunction(char)  
{  
   cout << "Char myFunction" << endl;  
}  
  
template <class T> class Class1  
{  
public:  
   Class1(T i)  
   {  
      // If replaced with myFunction(1), myFunction(char)  
      // will be called  
      myFunction(i);  
}  
};  
  
namespace MyNamespace  
{  
   void myFunction(int)  
   {  
      cout << "Int MyNamespace::myFunction" << endl;  
   }  
};  
  
using namespace MyNamespace;  
  
int main()  
{  
   Class1<int>* c1 = new Class1<int>(100);  
}  
```  
  
### Ausgabe  
  
```  
Int MyNamespace::myFunction  
```  
  
### Vorlagenmehrdeutigkeit  
 [!INCLUDE[cpp_dev11_long](../build/includes/cpp_dev11_long_md.md)] erzwingt die Standardregeln für C\+\+98\/03\/11 für Mehrdeutigkeit mit dem "template"\-Schlüsselwort.  Im folgenden Beispiel würde [!INCLUDE[cpp_dev10_long](../build/includes/cpp_dev10_long_md.md)] sowohl die nicht konformen Zeilen als auch die konformen Zeilen akzeptieren. [!INCLUDE[cpp_dev11_long](../build/includes/cpp_dev11_long_md.md)] akzeptiert nur die konformen Zeilen.  
  
```cpp  
#include <iostream>  
#include <ostream>  
#include <typeinfo>  
using namespace std;  
  
template <typename T> struct Allocator {  
    template <typename U> struct Rebind {  
        typedef Allocator<U> Other;  
    };  
};  
  
template <typename X, typename AY> struct Container {  
    #if defined(NONCONFORMANT)  
        typedef typename AY::Rebind<X>::Other AX; // nonconformant  
    #elif defined(CONFORMANT)  
        typedef typename AY::template Rebind<X>::Other AX; // conformant  
    #else  
        #error Define NONCONFORMANT or CONFORMANT.  
    #endif  
};  
  
int main() {  
    cout << typeid(Container<int, Allocator<float>>::AX).name() << endl;  
}  
```  
  
 Eine Übereinstimmung mit den Mehrdeutigkeitsregeln ist erforderlich, da C\+\+ standardmäßig annimmt, dass `AY::Rebind` keine Vorlage ist, und der Compiler deshalb folgenden "`<`"\-Code als "less\-than" interpretiert.  Er muss wissen, dass `Rebind` eine Vorlage darstellt, sodass er "`<`" ordnungsgemäß als spitze Klammer analysieren kann.  
  
## Siehe auch  
 [Namensauflösung](../cpp/templates-and-name-resolution.md)