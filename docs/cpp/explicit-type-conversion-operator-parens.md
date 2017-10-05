---
title: "Operator für explizite Typkonvertierung: () | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- explicit data type conversion operator
- conversions [C++], explicit
- operators [C++], explicit type conversion
- data type conversion [C++], explicit
- type conversion [C++], explicit conversions
ms.assetid: 54272006-5ffb-45ed-8283-27152ab97529
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 09afbed7f5a399b9ca192ff57be1c866baf59626
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="explicit-type-conversion-operator-"></a>Operator für die explizite Typkonvertierung: ()
C++ lässt die explizite Typkonvertierung mithilfe der Syntax ähnlich der Syntax des Funktionsaufrufs zu.  
  
## <a name="syntax"></a>Syntax  
  
```  
simple-type-name ( expression-list )  
```  
  
## <a name="remarks"></a>Hinweise  
 Ein *Simple-Type-Name* gefolgt von einem *Expression-List* eingeschlossen in Klammern erstellt ein Objekt des angegebenen Typs unter Verwendung der angegebenen Ausdrücke. Das folgende Beispiel zeigt eine explizite Typkonvertierung in den Typ "int":  
  
```  
int i = int( d );  
```  
  
 Das folgende Beispiel zeigt eine `Point` Klasse.  
  
## <a name="example"></a>Beispiel  
  
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
  
## <a name="output"></a>Ausgabe  
  
```  
x = 20, y = 10  
x = 0, y = 0  
```  
  
 Obwohl das obige Beispiel die explizite Typkonvertierung mithilfe von Konstanten demonstriert, funktioniert das gleiche Verfahren, um diese Konvertierungen für Objekte auszuführen. Der folgende Codeausschnitt stellt dies dar:  
  
```  
int i = 7;  
float d;  
  
d = float( i );  
```  
  
 Explizite Typkonvertierungen können mithilfe der "cast"-Syntax ebenfalls angegeben werden. Das vorherige Beispiel, das mithilfe der Umwandlungssyntax neu geschrieben wird, lautet:  
  
```  
d = (float)i;  
```  
  
 Umwandlungs- und Funktionskonvertierungen haben dieselben Ergebnisse beim Konvertieren von Einzelwerten. In der Funktionsformatsyntax können Sie mehr als ein Argument für die Konvertierung angeben. Dieser Unterschied ist für benutzerdefinierte Typen wichtig. Betrachten Sie eine `Point`-Klasse und ihre Konvertierungen:  
  
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
  
 Im vorhergehende Beispiel, das funktionskonvertierung verwendet wird, wird gezeigt, wie zwei Werte zu konvertieren (eine für *x* und eine für *y*) in den benutzerdefinierten Typ `Point`.  
  
> [!CAUTION]
>  Verwenden Sie die expliziten Typkonvertierungen mit Bedacht, da sie die integrierte Typüberprüfung des C++-Compilers überschreiben.  
  
 Die [Umwandlung](../cpp/cast-operator-parens.md) -Schreibweise muss verwendet werden, für die Konvertierung in Typen, die keine *Simple-Type-Name* (Zeiger- oder Verweistyp Typen, z. B.). Konvertierung in Typen, die mit ausgedrückt werden, kann eine *Simple-Type-Name* können in jeder Form geschrieben werden. Finden Sie unter [Typspezifizierer](http://msdn.microsoft.com/en-us/34b6c737-0ef1-4470-9b77-b26e46c0bbd4) Weitere Informationen darüber, worin eine *Simple-Type-Name*.  
  
 Eine Typdefinition innerhalb von Umwandlungen ist unzulässig.  
  
## <a name="see-also"></a>Siehe auch  
 [Postfixausdrücke](../cpp/postfix-expressions.md)   
 [C++-Built-in-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)
