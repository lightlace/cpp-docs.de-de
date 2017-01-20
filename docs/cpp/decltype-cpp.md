---
title: "decltype (C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "decltype"
  - "decltype_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "decltype-Operator"
  - "Operatoren [C++], decltype"
  - "Operatoren [C++], deduce expression type"
  - "Operatoren [C++], Typ eines Ausdrucks"
ms.assetid: 6dcf8888-8196-4f13-af50-51e3797255d4
caps.latest.revision: 14
caps.handback.revision: "14"
ms.author: "mblome"
manager: "ghogen"
---
# decltype (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der `decltype`\-Typspezifizierer ergibt den Typ eines angegebenen Ausdrucks.  `decltype` ist in Kombination mit dem [auto\-Schlüsselwort](../cpp/auto-cpp.md) vor allem für Entwickler nützlich, die Vorlagenbibliotheken schreiben.  Verwenden Sie `auto` und `decltype`, um eine Vorlagenfunktion zu deklarieren, deren Rückgabetyp von den Typen seiner Vorlagenargumente abhängt.  Oder Sie verwenden `auto` und `decltype`, um eine Vorlagenfunktion zu deklarieren, die einen Aufruf einer anderen Funktion umschließt und anschließend den Rückgabetyp der umschlossenen Funktion zurückgibt.  
  
## Syntax  
  
```  
decltype( expression )  
```  
  
#### Parameter  
  
|Parameter|Beschreibung|  
|---------------|------------------|  
|`expression`|Ein Ausdruck.  Weitere Informationen finden Sie unter [Ausdrücke](../cpp/expressions-cpp.md).|  
  
## Rückgabewert  
 Der Typ des `expression`\-Parameters.  
  
## Hinweise  
 Der Typspezifizierer `decltype` wird in Visual C\+\+ 2010 oder höher unterstützt und kann mit systemeigenem oder verwaltetem Code verwendet werden.  `decltype(auto)` \(C\+\+14\) wird in Visual Studio 2015 und höher unterstützt.  
  
 Der Compiler bestimmt mithilfe der folgenden Regeln den Typ des `expression`\-Parameters.  
  
-   Wenn der `expression`\-Parameter ein Bezeichner oder ein [Klassenmemberzugriff](../cpp/member-access-operators-dot-and.md) ist, ist `decltype(``expression``)` der Typ der durch `expression` benannten Entität.  Wenn keine solche Entität vorhanden ist oder der `expression`\-Parameter einen Satz überladener Funktionen bezeichnet, erzeugt der Compiler eine Fehlermeldung.  
  
-   Wenn der `expression`\-Parameter ein Aufruf einer Funktion oder überladenen Operatorfunktion ist, ist `decltype(``expression``)` der Rückgabetyp der Funktion.  Klammern um einen überladenen Operator werden ignoriert.  
  
-   Wenn der `expression`\-Parameter ein [rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md) ist, ist `decltype(``expression``)` der Typ von `expression`.  Wenn der `expression`\-Parameter ein [lvalue](../cpp/lvalues-and-rvalues-visual-cpp.md) ist, ist `decltype(``expression``)` ein [lvalue\-Verweis](../cpp/lvalue-reference-declarator-amp.md) auf den Typ von `expression`.  
  
 Im folgenden Codebeispiel werden einige Verwendungsmöglichkeiten des `decltype`\-Typspezifizierers veranschaulicht.  Angenommen, Sie haben die folgenden Anweisungen codiert.  
  
```  
int var;  
const int&& fx();   
struct A { double x; }  
const A* a = new A();  
```  
  
 Überprüfen Sie als Nächstes die Typen, die von den vier `decltype`\-Anweisungen in der folgenden Tabelle zurückgegeben werden.  
  
|Anweisung|Typ|Notizen|  
|---------------|---------|-------------|  
|`decltype(fx());`|`const int&&`|Ein [rvalue\-Verweis](../cpp/rvalue-reference-declarator-amp-amp.md) auf eine `const int`.|  
|`decltype(var);`|`int`|Der Typ der `var`\-Variablen.|  
|`decltype(a->x);`|`double`|Der Typ des Memberzugriffs.|  
|`decltype((a->x));`|`const double&`|Die innere Klammer bewirkt, dass die Anweisung als Ausdruck anstatt als Memberzugriff ausgewertet wird.  Und da `a` als `const`\-Zeiger deklariert ist, ist der Typ ein Verweis auf `const double`.|  
  
## "decltype" und "auto"  
 Sie können  `decltype(auto)` ohne nachstehenden Rückgabetyp in C\+\+14 verwenden, um eine Vorlagenfunktion zu deklarieren, deren Rückgabetyp von den Typen seiner Vorlagenargumente abhängt.  
  
 In C\+\+11 können Sie den `decltype`\-Typspezifizierer für einen nachstehenden Rückgabetyp in Kombination mit dem `auto`\-Schlüsselwort verwenden, um eine Vorlagenfunktion zu deklarieren, deren Rückgabetyp von den Typen der dazugehörigen Vorlagenargumente abhängt.  Betrachten Sie das folgende Codebeispiel, in dem der Rückgabetyp der Vorlagenfunktion von den Typen der Vorlagenargumente abhängt.  Im Codebeispiel zeigt der *UNKNOWN*\-Platzhalter an, dass der Rückgabetyp nicht angegeben werden kann.  
  
```  
template<typename T, typename U>  
UNKNOWN func(T&& t, U&& u){ return t + u; };   
```  
  
 Die Einführung des `decltype`\-Typspezifizierers ermöglicht es den Entwicklern, den Typ des Ausdrucks zu erhalten, den die Vorlagenfunktion zurückgibt.  Verwenden Sie die *alternative Funktionsdeklarationssyntax*, die später angezeigt wird, das `auto`\-Schlüsselwort und den `decltype`\-Typspezifizierer, um einen *spät angegebenen* Rückgabetyp zu deklarieren.  Der spät angegebene Rückgabetyp wird bestimmt, wenn die Deklaration kompiliert wird, anstatt wenn sie codiert wird.  
  
 Der folgende Prototyp veranschaulicht die Syntax einer alternativen Funktionsdeklaration.  Beachten Sie, dass die `const`\- und `volatile`\-Qualifizierer und die `throw`\-[Ausnahmespezifikation](../cpp/exception-specifications-throw-cpp.md) optional sind.  Der *function\_body*\-Platzhalter stellt eine Verbundanweisung dar, welche die Aufgabe der Funktion bezeichnet.  Als empfohlene Vorgehensweise bei der Codierung soll der *expression*\-Platzhalter in der `decltype`\-Anweisung mit dem Ausdruck übereinstimmen, der durch die `return`\-Anweisung \(sofern vorhanden\) in *function\_body* angegeben wird.  
  
 `auto` *function\_name*`(`*parameters*opt`)` `const`opt `volatile`opt `−>` `decltype(`*expression*`)` `throw`opt `{`*function\_body*`};`  
  
 Im folgenden Codebeispiel wird der spät angegebene Rückgabetyp der `myFunc`\-Vorlagenfunktion von den Typen der `t`\- und `u`\-Vorlagenargumente bestimmt.  Als empfohlene Vorgehensweise bei der Codierung verwendet das Codebeispiel auch rvalue\-Verweise und die `forward`\-Funktionsvorlage, die *perfekte Weiterleitung* unterstützen.  Weitere Informationen finden Sie unter [Rvalue\-Verweisdeklarator: &&](../cpp/rvalue-reference-declarator-amp-amp.md).  
  
```  
//C++11  
 template<typename T, typename U>  
auto myFunc(T&& t, U&& u) -> decltype (forward<T>(t) + forward<U>(u))   
        { return forward<T>(t) + forward<U>(u); };  
  
//C++14  
template<typename T, typename U>  
decltype(auto) myFunc(T&& t, U&& u)   
        { return forward<T>(t) + forward<U>(u); };  
  
```  
  
## „decltyp“ und Weiterleitungsfunktionen \(C\+\+11\)  
 Weiterleitungsfunktionen umschließen Aufrufe von anderen Funktionen.  Denken Sie an eine Funktionsvorlage, die ihre Argumente oder die Ergebnisse eines Ausdrucks, der diese Argumente beinhaltet, an eine andere Funktion weiterleitet.  Darüber hinaus gibt die Weiterleitungsfunktion das Ergebnis des Aufrufs der anderen Funktion zurück.  In diesem Szenario muss der Rückgabetyp der Weiterleitungsfunktion mit dem Rückgabetyp der umschlossenen Funktion identisch sein.  
  
 Sie können in diesem Szenario keinen geeigneten Typausdruck ohne den `decltype`\-Typspezifizierer schreiben.  Der `decltype`\-Typspezifizierer aktiviert generische Weiterleitungsfunktionen, denn er verliert keine erforderlichen Informationen darüber, ob eine Funktion einen Verweistyp zurückgibt.  Ein Codebeispiel für eine Weiterleitungsfunktion finden Sie im vorherigen `myFunc`\-Vorlagenfunktionsbeispiel.  
  
## Beispiel  
 Im folgenden Codebeispiel wird der spät angegebene Rückgabetyp der `Plus()`\-Vorlagenfunktion deklariert.  Die `Plus`\-Funktion verarbeitet ihre beiden Operanden mit der `operator+`\-Überladung.  Demzufolge hängen die Interpretation des Plus\-Operators \(\+\) und der Rückgabetyp der `Plus`\-Funktion von den Typen der Funktionsargumente ab.  
  
```  
// decltype_1.cpp  
// compile with: /EHsc  
//  
#include "stdafx.h"  
#include <iostream>  
#include <string>  
#include <utility>  
#include <iomanip>  
  
using namespace std;  
  
template<typename T1, typename T2>  
auto Plus(T1&& t1, T2&& t2) ->   
   decltype(forward<T1>(t1) + forward<T2>(t2))  
{  
   return forward<T1>(t1) + forward<T2>(t2);  
}  
  
class X  
{  
   friend X operator+(const X& x1, const X& x2)  
   {  
      return X(x1.m_data + x2.m_data);  
   }  
  
public:  
   X(int data) : m_data(data) {}  
   int Dump() const { return m_data;}  
private:  
   int m_data;  
};  
  
int main()  
{  
   // Integer   
   int i = 4;  
   cout <<   
      "Plus(i, 9) = " <<   
      Plus(i, 9) << endl;  
  
   // Floating point  
   float dx = 4.0;  
   float dy = 9.5;  
   cout <<     
      setprecision(3) <<   
      "Plus(dx, dy) = " <<  
      Plus(dx, dy) << endl;  
  
   // String        
   string hello = "Hello, ";  
   string world = "world!";  
   cout << Plus(hello, world) << endl;  
  
   // Custom type  
   X x1(20);  
   X x2(22);  
   X x3 = Plus(x1, x2);  
   cout <<   
      "x3.Dump() = " <<   
      x3.Dump() << endl;  
}  
```  
  
 **Ausgabe**  
  
 Dieses Codebeispiel führt zu folgenden Ergebnissen.  
  
 13  
  
 13.5  
  
 Hello, world\!  
  
 42  
  
## Anforderungen  
 Visual C\+\+ 2010 oder höhere Versionen  
  
 decltype\(auto\) erfordert Visual Studio 2015 oder höher  
  
## Siehe auch  
 [\(NOTINBUILD\)Simple Type Names](assetId:///333f45cb-2c72-4d81-8e59-e346b05f55e3)