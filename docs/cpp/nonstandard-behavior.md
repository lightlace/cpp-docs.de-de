---
title: "Nicht dem Standard entsprechendes Verhalten | Microsoft Docs"
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
helpviewer_keywords: 
  - "Kompatibilität und Compliance, Nicht dem Standard entsprechendes Verhalten"
  - "Microsoft-spezifisch, Compilerverhalten"
  - "Nicht dem Standard entsprechendes Verhalten, Compliance und Kompatibilität"
ms.assetid: a57dea27-dc79-4f64-8a83-017e84841773
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Nicht dem Standard entsprechendes Verhalten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die folgenden Abschnitte listen einige Bereiche auf, wo die Visual C\+\+\-Implementierung von C\+\+ nicht mit dem C\+\+\-Standard übereinstimmt.  Die unten angegebenen Abschnittszahlen beziehen sich auf die Abschnittszahlen im C\+\+ 11\-Standard \(ISO\/IEC 14882:2011\(E\)\).  
  
 Die Liste von Compilerlimits, die sich von denen unterscheiden, die im C\+\+\-Standard definiert wurden, wird in [Compiler Limits](../cpp/compiler-limits.md) angegeben.  
  
## Covariant\-Rückgabetypen  
 Virtuelle Basisklassen werden nicht als Covariant\-Rückgabetypen unterstützt, wenn die virtuelle Funktion eine variable Anzahl von Argumenten hat.  Dies entspricht nicht Abschnitt 10.3, Absatz 7 der C\+\+ ISO\-Spezifikation.  Das folgende Beispiel wird nicht kompiliert, es wird Compilerfehler [C2688](../error-messages/compiler-errors-2/compiler-error-c2688.md) ausgegeben  
  
```cpp  
// CovariantReturn.cpp  
class A   
{  
   virtual A* f(int c, ...);   // remove ...  
};  
  
class B : virtual A  
{  
   B* f(int c, ...);   // C2688 remove ...  
};  
```  
  
## Bindung von nicht abhängigen Namen in Vorlagen  
 Der Visual C\+\+\-Compiler unterstützt aktuell nicht die Bindung von nicht abhängigen Namen, wenn die Vorlage anfänglich analysiert wird.  Dies entspricht nicht Abschnitt 14.6.3, Absatz 7 der C\+\+ ISO\-Spezifikation.  Das kann zu Überladungen führen, die deklariert werden, nachdem die Vorlage \(aber bevor die Vorlage instanziiert wird\) angezeigt werden kann.  
  
```cpp  
#include <iostream>  
using namespace std;  
  
namespace N {  
   void f(int) { cout << "f(int)" << endl;}  
}  
  
template <class T> void g(T) {  
    N::f('a');   // calls f(char), should call f(int)  
}  
  
namespace N {  
    void f(char) { cout << "f(char)" << endl;}  
}  
  
int main() {  
    g('c');  
}  
// Output: f(char)  
  
```  
  
## Funktionsausnahmebezeichner  
 Funktionsausnahmebezeichner mit Ausnahme von `throw()` werden analysiert, aber nicht verwendet.  Dies entspricht nicht Abschnitt 15.4 der C\+\+ ISO C\+\+\-Spezifikation.  Beispiel:  
  
```cpp  
void f() throw(int); // parsed but not used  
void g() throw();    // parsed and used  
```  
  
 Weitere Informationen zu Ausnahmespezifikationen finden Sie unter [Aunahmespezifikationen](../cpp/exception-specifications-throw-cpp.md).  
  
## char\_traits::eof\(\)  
 Der C\+\+\-Standard gibt an, dass [char\_traits::eof](../Topic/char_traits::eof.md) nicht einem gültigen `char_type`\-Wert entsprechen darf.  Der Visual C\+\+\-Compiler erzwingt diese Einschränkung für Typ `char`, jedoch nicht für Typ `wchar_t`.  Dies entspricht nicht der Anforderung in Tabelle 62, in Abschnitt 12.1.1 der C\+\+ ISO\-Spezifikation.  Das unten gezeigte Beispiel veranschaulicht dies.  
  
```cpp  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
  
    char_traits<char>::int_type int2 = char_traits<char>::eof();  
    cout << "The eof marker for char_traits<char> is: " << int2 << endl;  
  
    char_traits<wchar_t>::int_type int3 = char_traits<wchar_t>::eof();  
    cout << "The eof marker for char_traits<wchar_t> is: " << int3 << endl;  
}  
```  
  
## Speicherort für Objekte  
 Der C\+\+\-Standard \(Abschnitt 1,8, Absatz 6\) erfordert vollständige C\+\+\-Objekte, um eindeutige Speicherpositionen zu haben.  Bei Visual C\+\+ gibt es jedoch Fälle, in denen Typen ohne Datenmember einen Speicherort während der Lebensdauer des Objekts für andere Typen freigeben.