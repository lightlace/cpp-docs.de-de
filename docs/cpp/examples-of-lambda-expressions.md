---
title: "Beispiele für Lambdaausdrücke | Microsoft Docs"
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
- lambda expressions [C++], examples
ms.assetid: 52506b15-0771-4190-a966-2f302049ca86
caps.latest.revision: 22
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
ms.openlocfilehash: 29a2c80bbd586ecf495269dad84f2b42440c41cc
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="examples-of-lambda-expressions"></a>Beispiele für Lambdaausdrücke
Dieser Artikel zeigt, wie Lambdaausdrücke in Ihren Programmen zu verwenden sind. Einen Überblick über Lambda-Ausdrücken finden Sie unter [Lambda-Ausdrücke](../cpp/lambda-expressions-in-cpp.md). Weitere Informationen zur Struktur eines Lambda-Ausdrucks finden Sie unter [Lambda-Ausdruckssyntax](../cpp/lambda-expression-syntax.md).  
  
##  <a name="declaringLambdaExpressions"></a>Deklarieren von Lambdaausdrücken  
  
### <a name="example-1"></a>Beispiel 1  
 Da ein Lambda-Ausdruck typisiert ist, können Sie sie zum Zuweisen einer `auto` Variable oder ein [Funktion](../standard-library/function-class.md) -Objekts, wie hier gezeigt:  
  
### <a name="code"></a>Code  
  
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
  
### <a name="output"></a>Ausgabe  
  
```Output  
5  
7  
```  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [Auto](../cpp/auto-cpp.md), [Funktion Klasse](../standard-library/function-class.md), und [Funktionsaufruf](../cpp/function-call-cpp.md).  
  
 Obwohl Lambdaausdrücke am häufigsten im Text einer Funktion deklariert werden, können Sie sie überall da deklarieren, wo Sie eine Variable initialisieren können.  
  
### <a name="example-2"></a>Beispiel 2  
 Der Compiler für Visual C++ bindet einen Lambda-Ausdruck an die aufgezeichneten Variablen, wenn der Ausdruck deklariert wird, nicht wenn der Ausdruck aufgerufen wird. Das folgende Beispiel zeigt einen Lambda-Ausdruck, der die lokale Variable `i` nach Wert erfasst und die lokale Variable `j` nach Verweis. Da der Lambda-Ausdruck `i` als Wert erfasst, wirkt sich die Neuzuweisung von `i` später im Programm nicht auf das Ergebnis des Ausdrucks aus. Da der Lambda-Ausdruck `j` jedoch als Verweis erfasst, wirkt sich die erneute Zuweisung von `j` auf das Ergebnis des Ausdrucks aus.  
  
### <a name="code"></a>Code  
  
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
  
### <a name="output"></a>Ausgabe  
  
```Output  
47  
```  
  
 [[In diesem Artikel](#top)]  
  
##  <a name="callingLambdaExpressions"></a>Aufrufen von Lambdaausdrücken  
 Sie können einen Lambdaausdruck sofort aufrufen, wie im nächsten Codeausschnitt gezeigt wird. Der zweite Ausschnitt zeigt, wie einen Lambda als Argument für C++-Standardbibliothek Algorithmen wie z. B. übergeben `find_if`.  
  
### <a name="example-1"></a>Beispiel 1  
 Im folgenden Beispiel wird ein Lambda-Ausdruck deklariert, der die Summe von zwei ganze Zahlen zurückgibt und den Ausdruck sofort mit den Argumenten `5` und `4` aufruft:  
  
### <a name="code"></a>Code  
  
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
  
### <a name="output"></a>Ausgabe  
  
```Output  
9  
```  
  
### <a name="example-2"></a>Beispiel 2  
 Im folgenden Beispiel wird ein Lambda-Ausdruck als Argument an die `find_if`-Funktion übergeben. Der Lambda-Ausdruck gibt `true` zurück, wenn sein Parameter eine gerade Zahl ist.  
  
### <a name="code"></a>Code  
  
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
  
### <a name="output"></a>Ausgabe  
  
```Output  
The first even number in the list is 42.  
```  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu den `find_if` funktionieren, finden Sie unter [für "find_if"](../standard-library/algorithm-functions.md#find_if). Weitere Informationen zu den Funktionen von C++-Standardbibliothek, die allgemeine Algorithmen ausführen, finden Sie unter [ \<Algorithmus >](../standard-library/algorithm.md).  
  
 [[In diesem Artikel](#top)]  
  
##  <a name="nestingLambdaExpressions"></a>Schachteln von Lambdaausdrücken  
  
### <a name="example"></a>Beispiel  
 Sie können einen Lambda-Ausdruck innerhalb eines anderen schachteln, wie in diesem Beispiel gezeigt wird. Der innere Lambda-Ausdruck multipliziert sein Argument mit 2 und gibt das Ergebnis zurück. Der äußere Lambda-Ausdruck ruft den inneren Lambda-Ausdruck mit seinem Argument auf und fügt dem Ergebnis 3 hinzu.  
  
### <a name="code"></a>Code  
  
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
  
### <a name="output"></a>Ausgabe  
  
```Output  
13  
```  
  
### <a name="remarks"></a>Hinweise  
 In diesem Beispiel ist `[](int y) { return y * 2; }` der geschachtelte Lambda-Ausdruck.  
  
 [[In diesem Artikel](#top)]  
  
##  <a name="higherOrderLambdaExpressions"></a>Höherer Ordnung Lambda-Funktionen  
  
### <a name="example"></a>Beispiel  
 Viele Programmiersprachen unterstützen das Konzept einer *Funktion höherer Ordnung.* Eine Funktion höherer Ordnung ist ein Lambda-Ausdruck, der einen anderen Lambda-Ausdruck als Argument akzeptiert oder einen Lambda-Ausdruck zurückgibt. Sie können die [Funktion](../standard-library/function-class.md) -Klasse verwenden, um einen C++-Lambda-Ausdruck Verhalten zu aktivieren, wie eine Funktion höherer Ordnung. Das folgende Beispiel zeigt einen Lambda-Ausdruck, der ein `function`-Objekt zurückgibt, und einen Lambda-Ausdruck, der ein `function`-Objekt als sein Argument akzeptiert.  
  
### <a name="code"></a>Code  
  
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
  
### <a name="output"></a>Ausgabe  
  
```Output  
30  
```  
  
 [[In diesem Artikel](#top)]  
  
##  <a name="methodLambdaExpressions"></a>Verwenden eines Lambda-Ausdrucks in einer Funktion  
  
### <a name="example"></a>Beispiel  
 Sie können Lambda-Ausdrücke im Text einer Funktion verwenden. Der Lambda-Ausdruck kann auf alle Funktionen oder Datenmember zugreifen, auf die die einschließende Funktion zugreifen kann. Sie können den `this`-Zeiger explizit oder implizit erfassen, um den Zugriff auf die Funktionen und Datenmember der einschließenden Klasse bereitzustellen.  
**Visual Studio 2017 15,3 und höher** (verfügbar mit [/std:c ++ 17](../build/reference/std-specify-language-standard-version.md)): erfassen `this` nach Wert (`[*this]`) Wenn der Lambda-Ausdruck verwendet werden in asynchronen oder parallelen Vorgängen, in denen möglicherweise des Codes ausgeführt werden, nachdem das ursprüngliche Objekt den Gültigkeitsbereich verlässt.
  
 Sie können den `this`-Zeiger explizit in einer Funktion verwenden, wie hier gezeigt:  
  
```cpp  

// capture "this" by reference
void ApplyScale(const vector<int>& v) const  
{  
   for_each(v.begin(), v.end(),   
      [this](int n) { cout << n * _scale << endl; });  
}  

// capture "this" by value (Visual Studio 2017 version 15.3 and later)
void ApplyScale2(const vector<int>& v) const  
{  
   for_each(v.begin(), v.end(),   
      [*this](int n) { cout << n * _scale << endl; });  
}  

```  
  
 Sie können den `this`-Zeiger auch implizit erfassen:  
  
```  
void ApplyScale(const vector<int>& v) const  
{  
   for_each(v.begin(), v.end(),   
      [=](int n) { cout << n * _scale << endl; });  
}  
```  
  
 Das folgende Beispiel zeigt die `Scale`-Klasse, die einen Skalierungswert kapselt.  
  
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
  
### <a name="output"></a>Ausgabe  
  
```Output  
3  
6  
9  
12  
  
```  
  
### <a name="remarks"></a>Hinweise  
 Die `ApplyScale`-Funktion verwendet einen Lambda-Ausdruck, um das Produkt des Skalierungswerts und eines jeden Elements in einem `vector`-Objekt auszugeben. Der Lambda-Ausdruck erfasst implizit den `this`-Zeiger, sodass er auf den `_scale`-Member zugreifen kann.  
  
 [[In diesem Artikel](#top)]  
  
##  <a name="templateLambdaExpressions"></a>Verwenden von Lambdaausdrücken mit Vorlagen  
  
### <a name="example"></a>Beispiel  
 Da Lambda-Ausdrücke typisiert sind, können Sie sie mit C++-Vorlagen verwenden. Im folgenden Beispiel werden die Funktionen `negate_all` und `print_all` dargestellt. Die `negate_all`-Funktion wendet den unären `operator-` auf jedes Element im `vector`-Objekt an. Die `print_all`-Funktion gibt jedes Element im `vector`-Objekt auf der Konsole aus.  
  
### <a name="code"></a>Code  
  
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
  
### <a name="output"></a>Ausgabe  
  
```Output  
34  
-43  
56  
After negate_all():  
-34  
43  
-56  
  
```  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu C++-Vorlagen finden Sie unter [Vorlagen](../cpp/templates-cpp.md).  
  
 [[In diesem Artikel](#top)]  
  
##  <a name="ehLambdaExpressions"></a>Behandeln von Ausnahmen  
  
### <a name="example"></a>Beispiel  
 Der Text eines Lambda-Ausdrucks folgt den Regeln für die strukturierte Ausnahmebehandlung (SEH) und die C++-Ausnahmebehandlung. Sie können eine ausgelöste Ausnahme im Text eines Lambda-Ausdrucks behandeln oder die Ausnahmebehandlung auf den umschließenden Gültigkeitsbereich verzögern. Im folgenden Beispiel wird die `for_each`-Funktion und ein Lambda-Ausdruck verwendet, um ein `vector`-Objekt mit den Werten eines anderen Objekts zu füllen. Er verwendet ein `try` / `catch` Block, um ungültigen Zugriff auf den ersten Vektor zu behandeln.  
  
### <a name="code"></a>Code  
  
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
  
### <a name="output"></a>Ausgabe  
  
```Output  
Caught 'invalid vector<T> subscript'.  
```  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zur Behandlung von Ausnahmen finden Sie unter [Exception Handling](../cpp/exception-handling-in-visual-cpp.md).  
  
 [[In diesem Artikel](#top)]  
  
##  <a name="managedLambdaExpressions"></a>Verwenden von Lambda-Ausdrücken mit verwalteten Typen (C + c++ / CLI)  
  
### <a name="example"></a>Beispiel  
 Die Erfassungsklausel eines Lambda-Ausdrucks darf keine Variable mit einem verwalteten Typ enthalten. Sie können jedoch ein Argument mit einem verwalteten Typ an die Parameterliste eines Lambda-Ausdrucks übergeben. Das folgende Beispiel enthält einen Lambda-Ausdruck, der die lokale nicht verwaltete `ch`-Variable nach ihrem Wert erfasst und ein <xref:System.String?displayProperty=fullName>-Objekt als Parameter akzeptiert.  
  
### <a name="code"></a>Code  
  
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
  
### <a name="output"></a>Ausgabe  
  
```Output  
Hello!  
```  
  
### <a name="remarks"></a>Hinweise  
 Sie können Lambdaausdrücke auch mit der STL/CLR-Bibliothek verwenden. Weitere Informationen finden Sie unter [STL/CLR-Bibliotheksverweis](../dotnet/stl-clr-library-reference.md).  
  
> [!IMPORTANT]
>  Lambdas werden in diesen verwalteten Entitäten der Common Language Runtime (CLR) nicht unterstützt: `ref class`, `ref struct`, `value class` und `value struct`.  
  
 [[In diesem Artikel](#top)]  
  
## <a name="see-also"></a>Siehe auch  
 [Lambda-Ausdrücke](../cpp/lambda-expressions-in-cpp.md)   
 [Lambda-Ausdruckssyntax](../cpp/lambda-expression-syntax.md)   
 [Auto](../cpp/auto-cpp.md)   
 [Function-Klasse](../standard-library/function-class.md)   
 [für "find_if"](../standard-library/algorithm-functions.md#find_if)   
 [\<Algorithmus >](../standard-library/algorithm.md)   
 [Funktionsaufruf](../cpp/function-call-cpp.md)   
 [Vorlagen](../cpp/templates-cpp.md)   
 [Ausnahmebehandlung](../cpp/exception-handling-in-visual-cpp.md)   
 [Referenz zur STL/CLR-Bibliothek](../dotnet/stl-clr-library-reference.md)
