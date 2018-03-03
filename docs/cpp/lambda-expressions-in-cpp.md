---
title: "Lambda-Ausdrücke in C++ | Microsoft Docs"
ms.custom: 
ms.date: 07/19/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- lambda expressions [C++]
- lambda expressions [C++], overview
- lambda expressions [C++], vs. function objects
ms.assetid: 713c7638-92be-4ade-ab22-fa33417073bf
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 035fe5c222f6de5b3f0d71c0ce9133c1101f2993
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="lambda-expressions-in-c"></a>Lambdaausdrücke in C++
In C ++ 11 und höher, ein Lambda-Ausdruck – wird häufig aufgerufen, eine *Lambda*– bequem ein anonymes Funktionsobjekt definiert ist (eine *Closure*) direkt an der Position, wo es aufgerufen oder als Argument übergeben, Um eine Funktion. Lambda-Ausdrücke werden in der Regel verwendet, um ein paar Codezeilen zu kapseln, die an Algorithmen oder asynchrone Methoden übergeben werden. Dieser Artikel definiert, was Lambdas sind, vergleicht sie mit anderen Programmierverfahren, beschreibt ihre Vorteile und bietet ein grundlegendes Beispiel.  

## <a name="related-topics"></a>Verwandte Themen
- [Lambda-Ausdrücke im Vergleich zu Funktionsobjekten](lambda-expression-syntax.md)
- [Arbeiten mit Lambda-Ausdrücke](examples-of-lambda-expressions.md)
- [Constexpr-Lambda-Ausdrücke](lambda-expressions-constexpr.md)

## <a name="parts-of-a-lambda-expression"></a>Bestandteile eines Lambdaausdrucks  
 Der ISO C++-Standard zeigt einen einfachen Lambda-Ausdruck, der als drittes Argument an die `std::sort()`-Funktion übergeben wird:  
  
```cpp  
#include <algorithm>  
#include <cmath>  
  
void abssort(float* x, unsigned n) {  
    std::sort(x, x + n,  
        // Lambda expression begins  
        [](float a, float b) {  
            return (std::abs(a) < std::abs(b));  
        } // end of lambda expression  
    );  
}  
  
```  
  
 In dieser Abbildung werden die Bestandteile eines Lambda-Ausdrucks dargestellt:  
  
 ![Strukturelle Elemente eines Lambda-Ausdrucks](../cpp/media/lambdaexpsyntax.png "LambdaExpSyntax")  
  
1.  *Erfassungsklausel* (auch bekannt als die *Lambda-Introducer* in der C++-Spezifikation.)  
  
2.  *Parameterliste* Optional. (Auch bekannt als die *Lambda Declarator*)  
  
3.  *änderbare Spezifikation* Optional.  
  
4.  *Ausnahmespezifikation* Optional.  
  
5.  *Trailing-Return-Type* Optional.  
  
6.  *Lambda-Text*)  
  
### <a name="capture-clause"></a>Erfassungsklausel  
 Ein Lambda-Ausdruck kann neue Variablen im Text einführen (in **C ++ 14**), und er kann auch den Zugriff auf oder *erfassen*, Variablen, aus dem umgebenden Bereich. Ein Lambda-Ausdruck beginnt mit der Erfassungsklausel (*Lambda-Introducer* in der Standardsyntax), die angibt, welche Variablen erfasst werden, und gibt an, ob die Erfassung nach Wert oder nach Verweis ist. Auf Variablen mit dem kaufmännischen Und-Zeichen (`&`) als Präfix erfolgt der Zugriff nach Verweis, und auf Variablen ohne dieses Präfix wird nach Wert zugegriffen.  
  
 Eine leere Erfassungsklausel (`[ ]`) gibt an, dass der Lambda-Text auf keine Variablen im einschließenden Bereich zugreift.  
  
 Können Sie den standarderfassungsmodus ein Modus (*Capture standardmäßiger* in der Standardsyntax) an, wie externe Variablen erfasst, die in der Lambda-Ausdruck verwiesen wird: `[&]` bedeutet, dass alle Variablen, auf die verwiesen erfasst werden, Referenz zu und `[=]` bedeutet, dass sie nach Wert erfasst werden. Sie können einen Standarderfassungsmodus verwenden, und dann den entgegengesetzten Modus explizit für bestimmte Variablen angeben. Wenn beispielsweise der Lambda-Text auf die externe Variable `total` nach Wert zugreift und auf die externe Variable `factor` nach Wert, dann sind die folgenden Erfassungsklauseln gleichwertig:  
  
```cpp  
[&total, factor]  
[factor, &total]  
[&, factor]  
[factor, &]  
[=, &total]  
[&total, =]  
```  
  
 Nur Variablen, die in der Lambda-Ausdruck erwähnten werden erfasst, wenn ein Capture-Standard verwendet wird.  
  
 Wenn Ihre Erfassungsklausel ein standardmäßiger Capture enthält `&`, wird keine `identifier` in einem `capture` -Klausel kann dieser Erfassungsklausel die Form aufweisen `& identifier`. Ebenso, wenn die Erfassungsklausel ein standardmäßigen Capture enthält `=`, wird keine `capture` -Klausel kann dieser Erfassungsklausel die Form aufweisen `= identifier`. Ein Bezeichner oder `this` kann nicht mehr als einmal in einer Erfassungsklausel angezeigt werden. Der folgende Codeausschnitt veranschaulicht einige Beispiele.  
  
```cpp  
struct S { void f(int i); };  
  
void S::f(int i) {  
    [&, i]{};      // OK  
    [&, &i]{};     // ERROR: i preceded by & when & is the default  
    [=, this]{};   // ERROR: this when = is the default  
    [=, *this]{ }; // OK: captures this by value. See below.
    [i, i]{};      // ERROR: i repeated  
}  
```  
  
 Eine Erfassung, gefolgt von einem Auslassungszeichen ist eine paketerweiterung, wie in diesem Beispiel [Variadic-Vorlage](../cpp/ellipses-and-variadic-templates.md) Beispiel:  
  
```cpp  
template<class... Args>  
void f(Args... args) {  
    auto x = [args...] { return g(args...); };  
    x();  
}  
```  
  
 Übergeben Sie zum Verwenden von Lambda-Ausdrücken in einer Klassenmethode den `this`-Zeiger auf die Erfassungsklausel, um den Zugriff auf die Methoden und Datenmember der einschließenden Klasse bereitzustellen. 
 
**Visual Studio 2017 15,3 und höher** (verfügbar mit [/std:c ++ 17](../build/reference/std-specify-language-standard-version.md)): der `this` Zeiger als Wert erfasst werden kann, durch Angabe `*this` in der Erfassungsklausel. Erfassung nach Wert bedeutet, dass die gesamte *Closure*, ist die anonymes Funktionsobjekt dieses Encapulates der Lambda-Ausdruck und in jeder Aufrufsite, wo der Lambda-Ausdruck aufgerufen wird, kopiert. Erfassung nach Wert ist hilfreich, wenn der Lambda-Ausdruck in parallelen oder asynchrone Vorgänge, insbesondere auf bestimmte Hardware-Architekturen, z. B. NUMA ausgeführt wird. 

Ein Beispiel zur Verwendung von Lambda-Ausdrücken mit Klassenmethoden finden Sie unter "Beispiel: Verwenden eines Lambda-Ausdruck in einer Methode" in [Beispiele für Lambdaausdrücke](../cpp/examples-of-lambda-expressions.md).  
  
 Wenn Sie die Erfassungsklausel verwenden, sollten Sie diese wichtigen Punkte beachten, insbesondere wenn Sie Lambdas mit Multithreading verwenden:  
  
-   Verweiserfassungen können im Gegensatz zu Werterfassungen dazu verwendet werden, um Variablen outside zu ändern. (`mutable` ermöglicht Änderungen an Kopien, jedoch nicht am Original.)  
  
-   Verweiserfassungen können im Gegensatz zu Werterfassungen Änderungen von Variablen outside wiederspiegeln.  
  
-   Verweiserfassungen führen eine Lebenszeitabhängigkeit ein, während Werterfassungen keine Lebenszeitabhängigkeiten haben. Dies ist besonders beim asynchronen Ausführen von Lambda-Ausdrücken von Bedeutung. Beim Erfassen einer lokalen Variablen in einem asynchronem Lambda-Ausdruck ist die Variable höchstwahrscheinlich beim Ausführen des Lambdas nicht verfügbar und es tritt eine Zugriffsverletzung zur Laufzeit auf.  
  
### <a name="generalized-capture-c-14"></a>Generalisierte Erfassung (C++14)  
  
 Neue Variablen können in C++14 in der Erfassungsklausel eingeführt und initialisiert werden, ohne dass diese Variablen im Bereich der Lambdafunktion vorhanden sein müssen. Die Initialisierung kann mit einem beliebigen Ausdruck ausgedrückt werden; der Typ der neuen Variablen wird von dem durch den Ausdruck genierten Typ abgeleitet. Ein Vorteil dieser Funktion ist, dass Sie Variablen, die nur verschoben werden können, (z. B. std::unique_ptr) aus dem umgebenden Bereich erfassen und in einem Lambda-Ausdruck verwenden können.  
  
```cpp  
pNums = make_unique<vector<int>>(nums);  
//...  
      auto a = [ptr = move(pNums)]()  
        {  
           // use ptr  
        };  
```  
  
### <a name="parameter-list"></a>Parameterliste  
 Neben dem Erfassen von Variablen werden in einem Lambda-Ausdruck Eingabeparameter akzeptiert. Eine Parameterliste (*Lambda Declarator* in der Standardsyntax) ist optional und ähnelt Sie in den meisten Aspekten die Parameterliste für eine Funktion.  
  
```cpp  
auto y = [] (int first, int second)  
{  
    return first + second;  
};  
  
```  
  
 In **C++ 14**, wenn der Typ generisch ist, können Sie den Auto-Schlüsselwort als Typspezifizierer. Das weist den Compiler an, den Funktionsaufrufoperator als Vorlage zu erstellen. Jede Instanz des auto-Schlüsselworts in einer Parameterliste entspricht einem Typparameter.  
  
```cpp  
auto y = [] (auto first, auto second)  
{  
    return first + second;  
};  
```  
  
 Ein Lambdaausdruck kann einen anderen Lambdaausdruck als Argument übernehmen. Weitere Informationen finden Sie unter "Lambdaausdrücke höherer Ordnung" im Thema [Beispiele für Lambdaausdrücke](../cpp/examples-of-lambda-expressions.md).  
  
 Da die Parameterliste optional ist, können Sie die leeren Klammern weglassen, wenn führen Sie nicht das Übergeben von Argumenten an den Lambda-Ausdruck und dessen Lambda-Declarator keine enthält *Ausnahmespezifikation*,  *Trailing-Return-Type*, oder `mutable`.  
  
### <a name="mutable-specification"></a>Änderbare Spezifikation  
 Normalerweise ist ein Aufrufoperator einer Lambda-Funktion "const-by-value", aber das Schlüsselwort `mutable` hebt dies auf. Er erstellt keine änderbaren Datenmember. Die änderbare Spezifikation aktiviert den Text eines Lambda-Ausdrucks, um Variablen zu ändern, die als Wert erfasst werden. Einige der späteren Beispiele in diesem Artikel veranschaulichen die Verwendung von `mutable`.  
  
### <a name="exception-specification"></a>Ausnahmespezifikation  
 Sie können die `noexcept`-Ausnahmespezifikation verwenden, um anzugeben, dass der Lambda-Ausdruck keine Ausnahmen auslöst. Wie bei normalen Funktionen generiert der Visual C++-Compiler die Warnung [C4297](../error-messages/compiler-warnings/compiler-warning-level-1-c4297.md) , wenn ein Lambda-Ausdruck deklariert die `noexcept` Ausnahmespezifikation und der Lambda-Text eine Ausnahme auslöst, wie hier gezeigt:  
  
```cpp  
// throw_lambda_expression.cpp  
// compile with: /W4 /EHsc   
int main() // C4297 expected  
{  
   []() noexcept { throw 5; }();  
}  
```  
  
 Weitere Informationen finden Sie unter [Ausnahmespezifikationen (Throw)](../cpp/exception-specifications-throw-cpp.md).  
  
### <a name="return-type"></a>Rückgabetyp  
 Der Rückgabetyp von Lambdaausdrücken wird automatisch hergeleitet. Sie müssen nicht verwenden die [automatisch](../cpp/auto-cpp.md) Schlüsselwort, außer Sie geben eine *trailing-Return-Type*. Die *trailing-Return-Type* ähnelt dem Rückgabetyp einer gewöhnlichen Methode oder Funktion. Der Rückgabetyp folgt jedoch auf die Parameterliste, und das Schlüsselwort trailing-return-type `->` muss vor dem Rückgabetyp angegeben werden.  
  
 Sie können den Rückgabetyp eines Lambda-Ausdrucks weglassen, wenn der Lambda-Text nur eine einzelne Return-Anweisung enthält oder der Lambda-Ausdruck keinen Wert zurückgibt. Wenn der Lambda-Text aus einer einzelnen Return-Anweisung besteht, leitet der Compiler den Rückgabetyp vom Typ des Return-Ausdrucks ab. Andernfalls geht der Compiler davon aus, dass der Rückgabetyp `void` ist. Betrachten Sie die folgenden Beispiele von Codeausschnitten, die dieses Prinzip veranschaulichen.  
  
```cpp  
auto x1 = [](int i){ return i; }; // OK: return type is int  
auto x2 = []{ return{ 1, 2 }; };  // ERROR: return type is void, deducing   
                                  // return type from braced-init-list is not valid  
```  
  
 Ein Lambdaausdruck kann einen anderen Lambdaausdruck als Rückgabewert erzeugen. Weitere Informationen finden Sie unter "Lambdaausdrücke höherer Ordnung" im [Beispiele für Lambdaausdrücke](../cpp/examples-of-lambda-expressions.md).  
  
### <a name="lambda-body"></a>Lambda-Text  
 Der Lambda-Text (*Compound-Statement* in der Standardsyntax) eines Lambda-Ausdrucks kann alles enthalten, die den Text einer gewöhnlichen Methode oder Funktion enthalten kann. Der Text einer gewöhnlichen Funktion und eines Lambdaausdrucks kann auf die folgenden Variablenarten zugreifen:  
  
-   Aus dem einschließenden Bereich erfasste Variablen, wie zuvor beschrieben.  
  
-   Parameter  
  
-   Lokal deklarierte Variablen  
  
-   Klassendatenmember, wenn diese innerhalb einer Klasse deklariert sind und `this` erfasst wird  
  
-   Jede beliebige Variable mit statischer Speicherdauer (z. B. globale Variablen)  
  
 Das folgende Beispiel enthält einen Lambda-Ausdruck, welcher explizit die Variable `n` nach ihrem Wert erfasst und implizit die Variable `m` als Verweis erfasst:  
  
```cpp  
// captures_lambda_expression.cpp  
// compile with: /W4 /EHsc   
#include <iostream>  
using namespace std;  
  
int main()  
{  
   int m = 0;  
   int n = 0;  
   [&, n] (int a) mutable { m = ++n + a; }(4);  
   cout << m << endl << n << endl;  
}  
```  
  
```Output  
5  
0  
```  
  
 Da die Variable `n` als Wert erfasst wird, bleibt der Wert `0` nach dem Aufruf des Lambda-Ausdrucks erhalten. Die `mutable`-Spezifikation ermöglicht es, dass `n` innerhalb des Lambda geändert wird.  
  
 Obwohl ein Lambda-Ausdruck nur Variablen mit automatischer Speicherdauer aufzeichnen kann, können Sie Variablen verwenden, die eine statische Speicherdauer im Text eines Lambda-Ausdrucks aufweisen. Im folgenden Beispiel wird die Funktion `generate` und ein Lambda-Ausdruck verwendet, um jedem Element in einem `vector`-Objekt einen Wert zuzuweisen. Der Lambdaausdruck ändert die statische Variable, um den Wert des nächsten Elements zu generieren.  
  
```cpp  
void fillVector(vector<int>& v)  
{  
    // A local static variable.  
    static int nextValue = 1;  
  
    // The lambda expression that appears in the following call to  
    // the generate function modifies and uses the local static   
    // variable nextValue.  
    generate(v.begin(), v.end(), [] { return nextValue++; });   
    //WARNING: this is not thread-safe and is shown for illustration only  
}  
```  
  
 Weitere Informationen finden Sie unter [generieren](../standard-library/algorithm-functions.md#generate).  
  
 Im folgenden Codebeispiel wird die Funktion aus dem vorherigen Beispiel und fügt ein Beispiel für einen Lambda-Ausdruck, den Algorithmus für die C++-Standardbibliothek verwendet `generate_n`. Dieser lambda-Ausdruck weist ein Element eines `vector`-Objekts der Summe der vorangehenden zwei Elemente zu. Das `mutable`-Schlüsselwort wird verwendet, sodass der Text des Lambda-Ausdrucks seine Kopien der externen Variablen `x` und `y` ändern kann, die vom Lambda-Ausdruck als Wert erfasst werden. Da der Lambda-Ausdruck die originalen Variablen `x` und `y` als Wert erfasst, bleiben die Werte `1`, nachdem das Lambda ausgeführt wird.  
  
```cpp  
// compile with: /W4 /EHsc  
#include <algorithm>  
#include <iostream>  
#include <vector>  
#include <string>  
  
using namespace std;  
  
template <typename C> void print(const string& s, const C& c) {  
    cout << s;  
  
    for (const auto& e : c) {  
        cout << e << " ";  
    }  
  
    cout << endl;  
}  
  
void fillVector(vector<int>& v)  
{  
    // A local static variable.  
    static int nextValue = 1;  
  
    // The lambda expression that appears in the following call to  
    // the generate function modifies and uses the local static   
    // variable nextValue.  
    generate(v.begin(), v.end(), [] { return nextValue++; });  
    //WARNING: this is not thread-safe and is shown for illustration only  
}  
  
int main()  
{  
    // The number of elements in the vector.  
    const int elementCount = 9;  
  
    // Create a vector object with each element set to 1.  
    vector<int> v(elementCount, 1);  
  
    // These variables hold the previous two elements of the vector.  
    int x = 1;  
    int y = 1;  
  
    // Sets each element in the vector to the sum of the   
    // previous two elements.  
    generate_n(v.begin() + 2,  
        elementCount - 2,  
        [=]() mutable throw() -> int { // lambda is the 3rd parameter  
        // Generate current value.  
        int n = x + y;  
        // Update previous two values.  
        x = y;  
        y = n;  
        return n;  
    });  
    print("vector v after call to generate_n() with lambda: ", v);  
  
    // Print the local variables x and y.  
    // The values of x and y hold their initial values because   
    // they are captured by value.  
    cout << "x: " << x << " y: " << y << endl;  
  
    // Fill the vector with a sequence of numbers  
    fillVector(v);  
    print("vector v after 1st call to fillVector(): ", v);  
    // Fill the vector with the next sequence of numbers  
    fillVector(v);  
    print("vector v after 2nd call to fillVector(): ", v);  
}  
```  
  
```Output  
vector v after call to generate_n() with lambda: 1 1 2 3 5 8 13 21 34  
x: 1 y: 1  
vector v after 1st call to fillVector(): 1 2 3 4 5 6 7 8 9  
vector v after 2nd call to fillVector(): 10 11 12 13 14 15 16 17 18  
```  
  
 Weitere Informationen finden Sie unter [Generate_n](../standard-library/algorithm-functions.md#generate_n).  

## <a name="constexpr-lambda-expressions"></a>Constexpr-Lambda-Ausdrücke
**Visual Studio 2017 15,3 und höher** (verfügbar mit [/std:c ++ 17](../build/reference/std-specify-language-standard-version.md)): ein Lambda-Ausdruck kann als deklariert werden `constexpr` oder in einem konstanten Ausdruck verwendet beim die Initialisierung der einzelnen Datenmember, dass die It erfasst oder führt in einem konstanten Ausdruck zulässig ist.  

```cpp
    int y = 32;
    auto answer = [y]() constexpr 
    {
        int x = 10;
        return y + x; 
    };

    constexpr int Increment(int n) 
    {
        return [n] { return n + 1; }();
    }

``` 
Ein Lambda-Ausdruck ist implizit `constexpr` das Ergebnis der Anforderungen erfüllt eine `constexpr` Funktion:
```cpp
    auto answer = [](int n) 
    {
        return 32 + n; 
    };

    constexpr int response = answer(10);
``` 
Wenn ein Lambda-Ausdruck implizit oder explizit ist `constexpr`, Konvertierung in einen Funktionszeiger erzeugt eine `constexpr` Funktion:

```cpp
    auto Increment = [](int n)
    {
        return n + 1;
    };

    constexpr int(*inc)(int) = Increment;
```
  
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
 Lambdas werden in den folgenden verwalteten Entitäten der Common Language Runtime (CLR) nicht unterstützt: `ref class`, `ref struct`, `value class` bzw. `value struct`.  
  
 Wenn Sie einen Microsoft-spezifischen Modifizierer wie z. B. verwenden [__declspec](../cpp/declspec.md), können Sie es in einem Lambda-Ausdruck einfügen unmittelbar nach der `parameter-declaration-clause`– zum Beispiel:  
  
```cpp  
auto Sqr = [](int t) __declspec(code_seg("PagedMem")) -> int { return t*t; };  
```  
  
 Um zu bestimmen, ob ein Modifizierer von Lambdas unterstützt wird, finden Sie unter den entsprechenden Artikel in der [Microsoft-spezifische Modifizierer](../cpp/microsoft-specific-modifiers.md) Abschnitt der Dokumentation.  
  
 Visual Studio unterstützt zusätzlich zu C ++ 11-Standard-Lambda-Funktionalität zustandslose Lambdas, d. h. Omni-konvertierbar zu Funktionszeigern, die willkürliche Aufrufkonventionen verwenden.  
  
## <a name="see-also"></a>Siehe auch  
 [C++-Sprachreferenz](../cpp/cpp-language-reference.md)   
 [Function-Objekte in der C++-Standardbibliothek](../standard-library/function-objects-in-the-stl.md)   
 [Funktionsaufruf](../cpp/function-call-cpp.md)   
 [for_each](../standard-library/algorithm-functions.md#for_each)
