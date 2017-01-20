---
title: "Beispiele f&#252;r Lambda-Ausdr&#252;cke"
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
  - "lambda-Ausdrücke [C++], Beispiele"
ms.assetid: 52506b15-0771-4190-a966-2f302049ca86
caps.latest.revision: 22
caps.handback.revision: "20"
ms.author: "mblome"
manager: "ghogen"
---
# Beispiele f&#252;r Lambda-Ausdr&#252;cke
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel zeigt, wie Lambda\-Ausdrücke in Ihren Programmen zu verwenden sind.  Eine Übersicht über die Lambda\-Ausdrücke finden Sie unter [Lambda\-Ausdrücke](../cpp/lambda-expressions-in-cpp.md).  Weitere Informationen zur Struktur eines Lambda\-Ausdrucks finden Sie unter [Lambda\-Ausdruckssyntax](../cpp/lambda-expression-syntax.md).  
  
##  <a name="top"></a> In diesem Artikel  
 [Deklarieren von Lambda-Ausdrücken](#declaringLambdaExpressions)  
  
 [Aufrufen von Lambda-Ausdrücken](#callingLambdaExpressions)  
  
 [Schachteln von Lambda-Ausdrücken](#nestingLambdaExpressions)  
  
 [Lambda-Funktionen höherer Ordnung](#higherOrderLambdaExpressions)  
  
 [Verwenden eines Lambda-Ausdrucks in einer Funktion](#methodLambdaExpressions)  
  
 [Verwenden von Lambda-Ausdrücken mit Vorlagen](#templateLambdaExpressions)  
  
 [Behandeln von Ausnahmen](#ehLambdaExpressions)  
  
 [Verwenden von Lambda-Ausdrücken mit verwalteten Typen (C++/CLI)](#managedLambdaExpressions)  
  
##  <a name="declaringLambdaExpressions"></a> Deklarieren von Lambda\-Ausdrücken  
  
### Beispiel 1  
 Da ein Lambda\-Ausdruck typisiert ist, können Sie ihn einer `auto`\-Variablen oder einem [function](../standard-library/function-class.md)\-Objekt zuweisen, wie im folgenden Beispiel gezeigt:  
  
### Code  
  
```cpp  
// declaring_lambda_expressions1.cpp  
// compile with: /EHsc /W4  
#include <functional>  
#include <iostream>  
  
int main()  
{  
  
    using namespace std;  
  
    // Assign the lambda expression that adds two numbers to an auto variable.  
    auto f1 = [](int x, int y) { return x + y; };  
  
    cout << f1(2, 3) << endl;  
  
    // Assign the same lambda expression to a function object.  
    function<int(int, int)> f2 = [](int x, int y) { return x + y; };  
  
    cout << f2(3, 4) << endl;  
}  
```  
  
### Ausgabe  
  **5**  
**7**   
### Hinweise  
 Weitere Informationen finden Sie unter [auto](../cpp/auto-cpp.md), [function\-Klasse](../standard-library/function-class.md) und [Funktionsaufruf](../cpp/function-call-cpp.md).  
  
 Obwohl Lambda\-Ausdrücke am häufigsten im Text einer Funktion deklariert werden, können Sie sie überall da deklarieren, wo Sie eine Variable initialisieren können.  
  
### Beispiel 2  
 Der Compiler für Visual C\+\+ bindet einen Lambda\-Ausdruck an die aufgezeichneten Variablen, wenn der Ausdruck deklariert wird, nicht wenn der Ausdruck aufgerufen wird.  Das folgende Beispiel zeigt einen Lambda\-Ausdruck, der die lokale Variable `i` nach Wert erfasst und die lokale Variable `j` nach Verweis.  Da der Lambda\-Ausdruck `i` als Wert erfasst, wirkt sich die Neuzuweisung von `i` später im Programm nicht auf das Ergebnis des Ausdrucks aus.  Da der Lambda\-Ausdruck `j` jedoch als Verweis erfasst, wirkt sich die erneute Zuweisung von `j` auf das Ergebnis des Ausdrucks aus.  
  
### Code  
  
```cpp  
// declaring_lambda_expressions2.cpp  
// compile with: /EHsc /W4  
#include <functional>  
#include <iostream>  
  
int main()  
{  
   using namespace std;  
  
   int i = 3;  
   int j = 5;  
  
   // The following lambda expression captures i by value and  
   // j by reference.  
   function<int (void)> f = [i, &j] { return i + j; };  
  
   // Change the values of i and j.  
   i = 22;  
   j = 44;  
  
   // Call f and print its result.  
   cout << f() << endl;  
}  
```  
  
### Ausgabe  
  **47** \[[In diesem Artikel](#top)\]  
  
##  <a name="callingLambdaExpressions"></a> Aufrufen von Lambda\-Ausdrücken  
 Sie können einen Lambda\-Ausdruck sofort aufrufen, wie im nächsten Codeausschnitt gezeigt wird.  Der zweite Ausschnitt zeigt, wie ein Lambda als Argument an Standardvorlagenbibliotheks\-Algorithmen \(Standard Template Library, STL\) übergeben wird, wie z. B. `find_if`.  
  
### Beispiel 1  
 Im folgenden Beispiel wird ein Lambda\-Ausdruck deklariert, der die Summe von zwei ganze Zahlen zurückgibt und den Ausdruck sofort mit den Argumenten `5` und `4` aufruft:  
  
### Code  
  
```cpp  
// calling_lambda_expressions1.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main()  
{  
   using namespace std;  
   int n = [] (int x, int y) { return x + y; }(5, 4);  
   cout << n << endl;  
}  
```  
  
### Ausgabe  
  **9**   
### Beispiel 2  
 Im folgenden Beispiel wird ein Lambda\-Ausdruck als Argument an die `find_if`\-Funktion übergeben.  Der Lambda\-Ausdruck gibt `true` zurück, wenn sein Parameter eine gerade Zahl ist.  
  
### Code  
  
```cpp  
// calling_lambda_expressions2.cpp  
// compile with: /EHsc /W4  
#include <list>  
#include <algorithm>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
  
    // Create a list of integers with a few initial elements.  
    list<int> numbers;  
    numbers.push_back(13);  
    numbers.push_back(17);  
    numbers.push_back(42);  
    numbers.push_back(46);  
    numbers.push_back(99);  
  
    // Use the find_if function and a lambda expression to find the   
    // first even number in the list.  
    const list<int>::const_iterator result =   
        find_if(numbers.begin(), numbers.end(),[](int n) { return (n % 2) == 0; });  
  
    // Print the result.  
    if (result != numbers.end()) {  
        cout << "The first even number in the list is " << *result << "." << endl;  
    } else {  
        cout << "The list contains no even numbers." << endl;  
    }  
}  
```  
  
### Ausgabe  
  **Die erste gerade Zahl in der Liste ist 42.**   
### Hinweise  
 Weitere Informationen zur `find_if`\-Funktion finden Sie unter [find\_if](../Topic/find_if.md).  Weitere Informationen zu den STL\-Funktionen, die allgemeine Algorithmen ausführen, finden Sie unter [\<algorithm\>](../standard-library/algorithm.md).  
  
 \[[In diesem Artikel](#top)\]  
  
##  <a name="nestingLambdaExpressions"></a> Schachteln von Lambda\-Ausdrücken  
  
### Beispiel  
 Sie können einen Lambda\-Ausdruck innerhalb eines anderen schachteln, wie in diesem Beispiel gezeigt wird.  Der innere Lambda\-Ausdruck multipliziert sein Argument mit 2 und gibt das Ergebnis zurück.  Der äußere Lambda\-Ausdruck ruft den inneren Lambda\-Ausdruck mit seinem Argument auf und fügt dem Ergebnis 3 hinzu.  
  
### Code  
  
```cpp  
// nesting_lambda_expressions.cpp  
// compile with: /EHsc /W4  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
  
    // The following lambda expression contains a nested lambda  
    // expression.  
    int timestwoplusthree = [](int x) { return [](int y) { return y * 2; }(x) + 3; }(5);  
  
    // Print the result.  
    cout << timestwoplusthree << endl;  
}  
  
```  
  
### Ausgabe  
  **13**   
### Hinweise  
 In diesem Beispiel ist `[](int y) { return y * 2; }` der geschachtelte Lambda\-Ausdruck.  
  
 \[[In diesem Artikel](#top)\]  
  
##  <a name="higherOrderLambdaExpressions"></a> Lambda\-Funktionen höherer Ordnung  
  
### Beispiel  
 Viele Programmiersprachen unterstützen das Konzept einer *Funktion höherer Ordnung*. Eine Funktion höherer Ordnung ist ein Lambda\-Ausdruck, der einen anderen Lambda\-Ausdruck als Argument akzeptiert oder einen Lambda\-Ausdruck zurückgibt.  Sie können die [function](../standard-library/function-class.md)\-Klasse verwenden, um zu ermöglichen, dass sich ein C\+\+\-Lambda\-Ausdruck wie eine Funktion höherer Ordnung verhält.  Das folgende Beispiel zeigt einen Lambda\-Ausdruck, der ein `function`\-Objekt zurückgibt, und einen Lambda\-Ausdruck, der ein `function`\-Objekt als sein Argument akzeptiert.  
  
### Code  
  
```cpp  
// higher_order_lambda_expression.cpp  
// compile with: /EHsc /W4  
#include <iostream>  
#include <functional>  
  
int main()  
{  
    using namespace std;  
  
    // The following code declares a lambda expression that returns   
    // another lambda expression that adds two numbers.   
    // The returned lambda expression captures parameter x by value.  
    auto addtwointegers = [](int x) -> function<int(int)> {   
        return [=](int y) { return x + y; };   
    };  
  
    // The following code declares a lambda expression that takes another  
    // lambda expression as its argument.  
    // The lambda expression applies the argument z to the function f  
    // and multiplies by 2.  
    auto higherorder = [](const function<int(int)>& f, int z) {   
        return f(z) * 2;   
    };  
  
    // Call the lambda expression that is bound to higherorder.   
    auto answer = higherorder(addtwointegers(7), 8);  
  
    // Print the result, which is (7+8)*2.  
    cout << answer << endl;  
}  
  
```  
  
### Ausgabe  
  **30** \[[In diesem Artikel](#top)\]  
  
##  <a name="methodLambdaExpressions"></a> Verwenden eines Lambda\-Ausdrucks in einer Funktion  
  
### Beispiel  
 Sie können Lambda\-Ausdrücke im Text einer Funktion verwenden.  Der Lambda\-Ausdruck kann auf alle Funktionen oder Datenmember zugreifen, auf die die einschließende Funktion zugreifen kann.  Sie können den `this`\-Zeiger explizit oder implizit erfassen, um den Zugriff auf die Funktionen und Datenmember der einschließenden Klasse bereitzustellen.  
  
 Sie können den `this`\-Zeiger explizit in einer Funktion verwenden, wie hier gezeigt:  
  
```cpp  
void ApplyScale(const vector<int>& v) const  
{  
   for_each(v.begin(), v.end(),   
      [this](int n) { cout << n * _scale << endl; });  
}  
```  
  
 Sie können den `this`\-Zeiger auch implizit erfassen:  
  
```  
void ApplyScale(const vector<int>& v) const  
{  
   for_each(v.begin(), v.end(),   
      [=](int n) { cout << n * _scale << endl; });  
}  
```  
  
 Das folgende Beispiel zeigt die `Scale`\-Klasse, die einen Skalierungswert kapselt.  
  
```cpp  
// function_lambda_expression.cpp  
// compile with: /EHsc /W4  
#include <algorithm>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
class Scale  
{  
public:  
    // The constructor.  
    explicit Scale(int scale) : _scale(scale) {}  
  
    // Prints the product of each element in a vector object   
    // and the scale value to the console.  
    void ApplyScale(const vector<int>& v) const  
    {  
        for_each(v.begin(), v.end(), [=](int n) { cout << n * _scale << endl; });  
    }  
  
private:  
    int _scale;  
};  
  
int main()  
{  
    vector<int> values;  
    values.push_back(1);  
    values.push_back(2);  
    values.push_back(3);  
    values.push_back(4);  
  
    // Create a Scale object that scales elements by 3 and apply  
    // it to the vector object. Does not modify the vector.  
    Scale s(3);  
    s.ApplyScale(values);  
}  
  
```  
  
### Ausgabe  
  **3**  
**6**  
**9**  
**12**   
### Hinweise  
 Die `ApplyScale`\-Funktion verwendet einen Lambda\-Ausdruck, um das Produkt des Skalierungswerts und eines jeden Elements in einem `vector`\-Objekt auszugeben.  Der Lambda\-Ausdruck erfasst implizit den `this`\-Zeiger, sodass er auf den `_scale`\-Member zugreifen kann.  
  
 \[[In diesem Artikel](#top)\]  
  
##  <a name="templateLambdaExpressions"></a> Verwenden von Lambda\-Ausdrücken mit Vorlagen  
  
### Beispiel  
 Da Lambda\-Ausdrücke typisiert sind, können Sie sie mit C\+\+\-Vorlagen verwenden.  Im folgenden Beispiel werden die Funktionen `negate_all` und `print_all` dargestellt.  Die `negate_all`\-Funktion wendet den unären `operator-` auf jedes Element im `vector`\-Objekt an.  Die `print_all`\-Funktion gibt jedes Element im `vector`\-Objekt auf der Konsole aus.  
  
### Code  
  
```cpp  
// template_lambda_expression.cpp  
// compile with: /EHsc  
#include <vector>  
#include <algorithm>  
#include <iostream>  
  
using namespace std;  
  
// Negates each element in the vector object. Assumes signed data type.  
template <typename T>  
void negate_all(vector<T>& v)  
{  
    for_each(v.begin(), v.end(), [](T& n) { n = -n; });  
}  
  
// Prints to the console each element in the vector object.  
template <typename T>  
void print_all(const vector<T>& v)  
{  
    for_each(v.begin(), v.end(), [](const T& n) { cout << n << endl; });  
}  
  
int main()  
{  
    // Create a vector of signed integers with a few elements.  
    vector<int> v;  
    v.push_back(34);  
    v.push_back(-43);  
    v.push_back(56);  
  
    print_all(v);  
    negate_all(v);  
    cout << "After negate_all():" << endl;  
    print_all(v);  
}  
  
```  
  
### Ausgabe  
  **34**  
**\-43**  
**56**  
**Nach negate\_all\(\):**  
**\-34**  
**43**  
**\-56**   
### Hinweise  
 Weitere Informationen zu C\+\+\-Vorlagen finden Sie unter [Vorlagen](../cpp/templates-cpp.md).  
  
 \[[In diesem Artikel](#top)\]  
  
##  <a name="ehLambdaExpressions"></a> Behandeln von Ausnahmen  
  
### Beispiel  
 Der Text eines Lambda\-Ausdrucks folgt den Regeln für die strukturierte Ausnahmebehandlung \(SEH\) und die C\+\+\-Ausnahmebehandlung.  Sie können eine ausgelöste Ausnahme im Text eines Lambda\-Ausdrucks behandeln oder die Ausnahmebehandlung auf den umschließenden Gültigkeitsbereich verzögern.  Im folgenden Beispiel wird die `for_each`\-Funktion und ein Lambda\-Ausdruck verwendet, um ein `vector`\-Objekt mit den Werten eines anderen Objekts zu füllen.  Es wird ein `try`\/`catch`\-Block verwendet, um ungültigen Zugriff auf den ersten Vektor zu behandeln.  
  
### Code  
  
```cpp  
// eh_lambda_expression.cpp  
// compile with: /EHsc /W4  
#include <vector>  
#include <algorithm>  
#include <iostream>  
using namespace std;  
  
int main()  
{  
    // Create a vector that contains 3 elements.  
    vector<int> elements(3);  
  
    // Create another vector that contains index values.  
    vector<int> indices(3);  
    indices[0] = 0;  
    indices[1] = -1; // This is not a valid subscript. It will trigger an exception.  
    indices[2] = 2;  
  
    // Use the values from the vector of index values to   
    // fill the elements vector. This example uses a   
    // try/catch block to handle invalid access to the   
    // elements vector.  
    try  
    {  
        for_each(indices.begin(), indices.end(), [&](int index) {   
            elements.at(index) = index;   
        });  
    }  
    catch (const out_of_range& e)  
    {  
        cerr << "Caught '" << e.what() << "'." << endl;  
    };  
}  
```  
  
### Ausgabe  
  **'invalid vector\<T\> subscript' abgefangen.**   
### Hinweise  
 Weitere Informationen zur Behandlung von Ausnahmen finden Sie unter [Ausnahmebehandlung](../cpp/exception-handling-in-visual-cpp.md).  
  
 \[[In diesem Artikel](#top)\]  
  
##  <a name="managedLambdaExpressions"></a> Verwenden von Lambda\-Ausdrücken mit verwalteten Typen \(C\+\+\/CLI\)  
  
### Beispiel  
 Die Erfassungsklausel eines Lambda\-Ausdrucks darf keine Variable mit einem verwalteten Typ enthalten.  Sie können jedoch ein Argument mit einem verwalteten Typ an die Parameterliste eines Lambda\-Ausdrucks übergeben.  Das folgende Beispiel enthält einen Lambda\-Ausdruck, der die lokale nicht verwaltete `ch`\-Variable nach ihrem Wert erfasst und ein <xref:System.String?displayProperty=fullName>\-Objekt als Parameter akzeptiert.  
  
### Code  
  
```cpp  
// managed_lambda_expression.cpp  
// compile with: /clr  
using namespace System;  
  
int main()  
{  
    char ch = '!'; // a local unmanaged variable  
  
    // The following lambda expression captures local variables  
    // by value and takes a managed String object as its parameter.  
    [=](String ^s) {   
        Console::WriteLine(s + Convert::ToChar(ch));   
    }("Hello");  
}  
  
```  
  
### Ausgabe  
  **Hallo\!**   
### Hinweise  
 Sie können Lambda\-Ausdrücke auch mit der STL\/CLR\-Bibliothek verwenden.  Weitere Informationen finden Sie unter [STL\/CLR\-Bibliothek](../dotnet/stl-clr-library-reference.md).  
  
> [!IMPORTANT]
>  Lambdas werden in diesen verwalteten Entitäten der Common Language Runtime \(CLR\) nicht unterstützt: `ref class`, `ref struct`, `value class` und `value struct`.  
  
 \[[In diesem Artikel](#top)\]  
  
## Siehe auch  
 [Lambda\-Ausdrücke](../cpp/lambda-expressions-in-cpp.md)   
 [Lambda\-Ausdruckssyntax](../cpp/lambda-expression-syntax.md)   
 [auto](../cpp/auto-cpp.md)   
 [function\-Klasse](../standard-library/function-class.md)   
 [find\_if](../Topic/find_if.md)   
 [\<algorithm\>](../standard-library/algorithm.md)   
 [Funktionsaufruf](../cpp/function-call-cpp.md)   
 [Vorlagen](../cpp/templates-cpp.md)   
 [Ausnahmebehandlung](../cpp/exception-handling-in-visual-cpp.md)   
 [STL\/CLR\-Bibliothek](../dotnet/stl-clr-library-reference.md)