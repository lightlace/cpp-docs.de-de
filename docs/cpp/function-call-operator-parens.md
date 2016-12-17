---
title: "Funktionsaufrufoperator: ()"
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
  - "( )-Funktionsaufrufoperator"
  - "()-Funktionsaufrufoperator"
  - "Funktionsaufrufoperator ( )"
  - "Funktionsaufrufe, C++-Funktionen"
  - "Funktionsaufrufe, Operator"
  - "Funktionen [C++], function-call-Operator"
  - "Postfixoperatoren"
ms.assetid: 50c92e59-a4bf-415a-a6ab-d66c679ee80a
caps.latest.revision: 14
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# Funktionsaufrufoperator: ()
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein vom Funktionsaufrufoperator **\( \)** gefolgter Postfixausdruck gibt einen Funktionsaufruf an.  
  
## Syntax  
  
```  
  
postfix-expression   
( [argument-expression-list ] )  
```  
  
## Hinweise  
 Die Argumente für den Funktionsaufrufoperator sind null oder mehr Ausdrücke, die durch Trennzeichen getrennt sind – die tatsächlichen Argumente der Funktion.  
  
 Der *Postfixausdruck* muss zu einer Funktionsadresse in Beziehung gesetzt werden \(z. B. zu einem Funktionsbezeichner oder zum Funktionszeigewert\), und die *Argumentausdrucksliste* ist eine Ausdrucksliste \(durch Kommas getrennt\), deren Werte \(Argumente\) an die Funktion übergeben werden.  Das *argument\-expression\-list*\-Argument kann leer sein.  
  
 Der *Postfixausdruck* muss einen dieser Typen aufweisen:  
  
-   Funktion, die den Typ `T` zurückgibt.  Eine Beispieldeklaration ist  
  
    ```  
    T func( int i )  
    ```  
  
-   Zeiger auf eine Funktion, die den Typ `T` zurückgibt.  Eine Beispieldeklaration ist  
  
    ```  
    T (*func)( int i )  
    ```  
  
-   Verweis auf eine Funktion, die den Typ `T` zurückgibt.  Eine Beispieldeklaration ist  
  
    ```  
    T (&func)(int i)  
    ```  
  
-   Zeiger auf eine Memberfunktion dereferenziert die Rückgabe des Typs `T`.  Beispiele für Funktionsaufrufe sind  
  
    ```  
    (pObject->*pmf)();  
    (Object.*pmf)();  
    ```  
  
## Beispiel  
 Im folgenden Beispiel wird die Standardbibliotheksfunktion `strcat_s` mit drei Argumenten aufgerufen:  
  
```  
// expre_Function_Call_Operator.cpp  
// compile with: /EHsc  
  
#include <iostream>  
#include <string>  
  
// STL name space  
using namespace std;  
  
int main()  
{  
    enum  
    {  
        sizeOfBuffer = 20  
    };  
  
    char s1[ sizeOfBuffer ] = "Welcome to ";  
    char s2[ ] = "C++";  
  
    strcat_s( s1, sizeOfBuffer, s2 );  
  
    cout << s1 << endl;  
}  
```  
  
  **Willkommen bei C\+\+**   
## Ergebnisse des Funktionsaufrufs  
 Ein Funktionsaufruf wird zu einem r\-value ausgewertet, es sei denn, die Funktion ist als Referenztyp deklariert.  Funktionen mit dem Verweisrückgabetyp werden zu L\-Werten ausgewertet und können wie folgt auf der linken Seite einer Zuweisungsanweisung verwendet werden:  
  
```  
// expre_Function_Call_Results.cpp  
// compile with: /EHsc  
#include <iostream>  
class Point  
{  
public:  
    // Define "accessor" functions as  
    // reference types.  
    unsigned& x() { return _x; }  
    unsigned& y() { return _y; }  
private:  
    unsigned _x;  
    unsigned _y;  
};  
  
using namespace std;  
int main()  
{  
    Point ThePoint;  
  
    ThePoint.x() = 7;           // Use x() as an l-value.  
    unsigned y = ThePoint.y();  // Use y() as an r-value.  
  
    // Use x() and y() as r-values.  
    cout << "x = " << ThePoint.x() << "\n"  
         << "y = " << ThePoint.y() << "\n";  
}  
```  
  
 Dieser vorhergehende Code definiert eine Klasse namens `Point`. Sie enthält private Datenobjekte, die die Koordinaten *x* und *y* darstellen.  Diese Datenobjekte müssen geändert und ihre Werte abgerufen werden.  Dieses Programm ist nur einer von mehreren Entwürfen für eine solche Klasse. Eine Verwendung der Funktionen `GetX` und `SetX` oder `GetY` und `SetY` ist ein anderer möglicher Entwurf.  
  
 Funktionen, die Klassentypen, Zeiger auf Klassentypen oder Verweise auf Klassentypen zurückgeben, können als linker Operand für Memberauswahloperatoren verwendet werden.  Daher ist der folgende Code gültig:  
  
```  
// expre_Function_Results2.cpp  
class A {  
public:  
   A() {}  
   A(int i) {}  
   int SetA( int i ) {  
      return (I = i);  
   }  
  
   int GetA() {  
      return I;  
   }  
  
private:  
   int I;  
};  
  
A func1() {  
   A a = 0;  
   return a;  
}  
  
A* func2() {  
   A *a = new A();  
   return a;  
}  
  
A& func3() {  
   A *a = new A();  
   A &b = *a;  
   return b;  
}  
  
int main() {  
   int iResult = func1().GetA();  
   func2()->SetA( 3 );  
   func3().SetA( 7 );  
}  
```  
  
 Funktionen können rekursiv aufgerufen werden.  Weitere Informationen über Funktionsdeklarationen finden Sie unter [Funktions\-Spezifizierer](../misc/function-specifiers.md) und [Memberfunktion](../misc/member-functions-cpp.md).  Verwandtes Material finden Sie in [Programm und Verknüpfung](../cpp/program-and-linkage-cpp.md).  
  
## Siehe auch  
 [Postfixausdrücke](../cpp/postfix-expressions.md)   
 [C\+\+\-Operatoren](../misc/cpp-operators.md)   
 [C\+\+\-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Funktionsaufruf](../c-language/function-call-c.md)   
 [\(NOTINBUILD\) Function Declarations](assetId:///3f9b4e14-60d2-47c1-acd8-4fa8fc988be7)