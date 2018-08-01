---
title: 'Funktionsaufrufoperator: () | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- ( ) function call operator
- function calls, C++ functions
- () function call operator
- postfix operators [C++]
- function calls, operator
- functions [C++], function-call operator
- function call operator ()
ms.assetid: 50c92e59-a4bf-415a-a6ab-d66c679ee80a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1b0c4cde0c50064c5a88469e8f9061a0321902e4
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39408995"
---
# <a name="function-call-operator-"></a>Funktionsaufrufoperator: ()
Ein postfixausdruck, gefolgt von den Funktionsaufrufoperator **()**, gibt einen Funktionsaufruf.  
  
## <a name="syntax"></a>Syntax  
  
```  
postfix-expression   
( [argument-expression-list ] )  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Argumente für den Funktionsaufrufoperator sind null oder mehr Ausdrücke, die durch Trennzeichen getrennt sind – die tatsächlichen Argumente der Funktion.  
  
 Die *Postfix-Expression* muss zu einer Funktionsadresse (z. B. einen Funktionsbezeichner oder den Wert eines Funktionszeigers) ausgewertet und *Argument-Expression-List* ist eine Liste von Ausdrücken (getrennt durch Kommas), deren Werte (die Argumente) an die Funktion übergeben werden. Das *argument-expression-list*-Argument kann leer sein.  
  
 Die *Postfix-Expression* muss eines der folgenden Typen sein:  
  
-   Funktion, die den Typ `T` zurückgibt. Eine Beispieldeklaration ist  
  
    ```cpp 
    T func( int i )  
    ```  
  
-   Zeiger auf eine Funktion, die den Typ `T` zurückgibt. Eine Beispieldeklaration ist  
  
    ```cpp 
    T (*func)( int i )  
    ```  
  
-   Verweis auf eine Funktion, die den Typ `T` zurückgibt. Eine Beispieldeklaration ist  
  
    ```cpp 
    T (&func)(int i)  
    ```  
  
-   Zeiger auf eine Memberfunktion dereferenziert die Rückgabe des Typs `T`. Beispiele für Funktionsaufrufe sind  
  
    ```cpp 
    (pObject->*pmf)();  
    (Object.*pmf)();  
    ```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Standardbibliotheksfunktion `strcat_s` mit drei Argumenten aufgerufen:  
  
```cpp 
// expre_Function_Call_Operator.cpp  
// compile with: /EHsc  
  
#include <iostream>  
#include <string>  
  
// C++ Standard Library name space  
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
  
```Output  
Welcome to C++  
```  
  
## <a name="function-call-results"></a>Ergebnisse des Funktionsaufrufs  
 Ein Funktionsaufruf wird zu einem r-value ausgewertet, es sei denn, die Funktion ist als Referenztyp deklariert. Funktionen mit dem Verweisrückgabetyp werden zu L-Werten ausgewertet und können wie folgt auf der linken Seite einer Zuweisungsanweisung verwendet werden:  
  
```cpp 
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
  
 Der vorhergehende Code definiert eine Klasse namens `Point`, enthält private Objekte, die darstellen, *x* und *y* Koordinaten. Diese Datenobjekte müssen geändert und ihre Werte abgerufen werden. Dieses Programm ist nur einer von mehreren Entwürfen für eine solche Klasse. Eine Verwendung der Funktionen `GetX` und `SetX` oder `GetY` und `SetY` ist ein anderer möglicher Entwurf.  
  
 Funktionen, die Klassentypen, Zeiger auf Klassentypen oder Verweise auf Klassentypen zurückgeben, können als linker Operand für Memberauswahloperatoren verwendet werden. Daher ist der folgende Code gültig:  
  
```cpp 
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
  
 Funktionen können rekursiv aufgerufen werden. Weitere Informationen über Funktionsdeklarationen finden Sie unter [Funktionen](functions-cpp.md). Verwandtes Material finden Sie [Programm und Verknüpfung](../cpp/program-and-linkage-cpp.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Postfixausdrücke](../cpp/postfix-expressions.md)   
 [C++-Built-Operatoren, Rangfolge und Assoziativität](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Funktionsaufruf](../c-language/function-call-c.md)   