---
title: "Operator f&#252;r die explizite Typkonvertierung: ()"
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
  - "Konvertierungen [C++], Explizit"
  - "Datentypkonvertierung [C++], Explizit"
  - "Operator für die explizite Konvertierung von Datentypen"
  - "Operatoren [C++], Explizite Typkonvertierung"
  - "Typkonvertierung [C++], Explizite Konvertierungen"
ms.assetid: 54272006-5ffb-45ed-8283-27152ab97529
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Operator f&#252;r die explizite Typkonvertierung: ()
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\+\+ lässt die explizite Typkonvertierung mithilfe der Syntax ähnlich der Syntax des Funktionsaufrufs zu.  
  
## Syntax  
  
```  
  
simple-type-name ( expression-list )  
```  
  
## Hinweise  
 *simple\-type\-name* gefolgt von *expression\-list* in Klammern erstellt ein Objekt des angegebenen Typs mithilfe der angegebenen Ausdrücke.  Das folgende Beispiel zeigt eine explizite Typkonvertierung in den Typ "int":  
  
```  
int i = int( d );  
```  
  
 Im folgenden Beispiel wird eine modifizierte Version der Klasse `Point` verwendet, die in [Funktionsaufrufergebnisse](../misc/function-call-results.md) definiert wird.  
  
## Beispiel  
  
```  
// expre_Explicit_Type_Conversion_Operator.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
class Point  
{  
public:  
    // Define default constructor.  
    Point() { _x = _y = 0; }  
    // Define another constructor.  
    Point( int X, int Y ) { _x = X; _y = Y; }  
  
    // Define "accessor" functions as  
    // reference types.  
    unsigned& x() { return _x; }  
    unsigned& y() { return _y; }  
    void Show()   { cout << "x = " << _x << ", "  
                         << "y = " << _y << "\n"; }  
private:  
    unsigned _x;  
    unsigned _y;  
};  
  
int main()  
{  
    Point Point1, Point2;  
  
    // Assign Point1 the explicit conversion  
    //  of ( 10, 10 ).  
    Point1 = Point( 10, 10 );  
  
    // Use x() as an l-value by assigning an explicit  
    //  conversion of 20 to type unsigned.  
    Point1.x() = unsigned( 20 );  
    Point1.Show();  
  
    // Assign Point2 the default Point object.  
    Point2 = Point();  
    Point2.Show();  
}  
```  
  
## Ausgabe  
  
```  
x = 20, y = 10  
x = 0, y = 0  
```  
  
 Obwohl das obige Beispiel die explizite Typkonvertierung mithilfe von Konstanten demonstriert, funktioniert das gleiche Verfahren, um diese Konvertierungen für Objekte auszuführen.  Der folgende Codeausschnitt stellt dies dar:  
  
```  
int i = 7;  
float d;  
  
d = float( i );  
```  
  
 Explizite Typkonvertierungen können mithilfe der "cast"\-Syntax ebenfalls angegeben werden.  Das vorherige Beispiel, das mithilfe der Umwandlungssyntax neu geschrieben wird, lautet:  
  
```  
d = (float)i;  
```  
  
 Umwandlungs\- und Funktionskonvertierungen haben dieselben Ergebnisse beim Konvertieren von Einzelwerten.  In der Funktionsformatsyntax können Sie mehr als ein Argument für die Konvertierung angeben.  Dieser Unterschied ist für benutzerdefinierte Typen wichtig.  Betrachten Sie eine `Point`\-Klasse und ihre Konvertierungen:  
  
```  
struct Point  
{  
    Point( short x, short y ) { _x = x; _y = y; }  
    ...  
    short _x, _y;  
};  
...  
Point pt = Point( 3, 10 );  
```  
  
 Das vorhergehende Beispiel, in die Funktionskonvertierung verwendet wird, zeigt, wie zwei Werte \(einer für *x* und einer für *y*\) in den benutzerdefinierten Typ `Point` konvertiert werden.  
  
> [!CAUTION]
>  Verwenden Sie die expliziten Typkonvertierungen mit Bedacht, da sie die integrierte Typüberprüfung des C\+\+\-Compilers überschreiben.  
  
 Die [cast](../cpp/cast-operator-parens.md)\-Schreibweise muss für Konvertierungen in Typen verwendet werden, die keinen *simple\-type\-name* \(z. B. Zeiger oder Referenztypen\) haben.  Konvertierung in Typen, die mit einem *simple\-type\-name* ausgedrückt werden kann, kann in jeder Form geschrieben werden.  Weitere Informationen zu den Bedingungen für *simple\-type\-name* finden Sie unter [Typbezeichner](assetId:///34b6c737-0ef1-4470-9b77-b26e46c0bbd4).  
  
 Eine Typdefinition innerhalb von Umwandlungen ist unzulässig.  
  
## Siehe auch  
 [Postfixausdrücke](../cpp/postfix-expressions.md)   
 [C\+\+\-Operatoren](../misc/cpp-operators.md)   
 [C\+\+\-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)