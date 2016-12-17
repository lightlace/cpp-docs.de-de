---
title: "Lambda-Ausdr&#252;cke in C++"
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
  - "lambda-Ausdrücke [C++]"
  - "lambda-Ausdrücke [C++], Übersicht"
  - "lambda-Ausdrücke [C++], Im Vergleich zu Funktionsobjekten"
ms.assetid: 713c7638-92be-4ade-ab22-fa33417073bf
caps.latest.revision: 36
caps.handback.revision: "34"
ms.author: "mblome"
manager: "ghogen"
---
# Lambda-Ausdr&#252;cke in C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Mit einem Lambda\-Ausdruck, häufig *Lambda* genannt, kann in C\+\+11 bequem ein anonymes Funktionsobjekt direkt an der Position definiert werden, an der es aufgerufen oder als Argument an eine Funktion übergeben wird.  Lambda\-Ausdrücke werden in der Regel verwendet, um ein paar Codezeilen zu kapseln, die an Algorithmen oder asynchrone Methoden übergeben werden.  Dieser Artikel definiert, was Lambdas sind, vergleicht sie mit anderen Programmierverfahren, beschreibt ihre Vorteile und bietet ein grundlegendes Beispiel.  
  
## Bestandteile eines Lambda\-Ausdrucks  
 Der ISO C\+\+\-Standard zeigt einen einfachen Lambda\-Ausdruck, der als drittes Argument an die `std::sort()`\-Funktion übergeben wird:  
  
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
  
 In dieser Abbildung werden die Bestandteile eines Lambda\-Ausdrucks dargestellt:  
  
 ![Strukturelle Elemente eines Lambda&#45;Ausdrucks](../cpp/media/lambdaexpsyntax.png "LambdaExpSyntax")  
  
1.  *capture clause* \(auch bekannt als *lambda\-introducer* in der C\+\+\-Spezifikation.\)  
  
2.  *parameter list* Optional.  \(auch bekannt als *lambda declarator*\)  
  
3.  *mutable specification* Optional.  
  
4.  *exception\-specification* Optional.  
  
5.  *trailing\-return\-type* Optional.  
  
6.  *lambda body*\)  
  
### Erfassungsklausel  
 Ein Lambda\-Ausdruck kann neue Variablen im Text einführen \(in **C \+\+ 14**\) und auf diese oder auf *capture*\-Variablen aus dem umgebenden Bereich zugreifen.  Ein Lambda\-Ausdruck beginnt mit der Erfassungsklausel \(*lambda\-introducer* in der Standardsyntax\), die angibt, welche Variablen erfasst werden, und ob diese Erfassung nach Wert oder Verweis erfolgt.  Auf Variablen mit dem kaufmännischen Und\-Zeichen \(`&`\) als Präfix erfolgt der Zugriff nach Verweis, und auf Variablen ohne dieses Präfix wird nach Wert zugegriffen.  
  
 Eine leere Erfassungsklausel \(`[ ]`\) gibt an, dass der Lambda\-Text auf keine Variablen im einschließenden Bereich zugreift.  
  
 Mit dem Standarderfassungsmodus \(`capture-default` in der Standardsyntax\) können Sie angeben, wie externe Variablen erfasst werden sollen, auf die mit dem Lambda\-Ausdruck verwiesen wird: \[&\] bedeutet, dass alle Variablen, auf die verwiesen wird, nach Verweis erfasst werden, und \[\=\] bedeutet, dass sie nach Wert erfasst werden.  Sie können einen Standarderfassungsmodus verwenden, und dann den entgegengesetzten Modus explizit für bestimmte Variablen angeben.  Wenn beispielsweise der Lambda\-Text auf die externe Variable `total` nach Wert zugreift und auf die externe Variable `factor` nach Wert, dann sind die folgenden Erfassungsklauseln gleichwertig:  
  
```cpp  
  
[&total, factor]  
[factor, &total]  
[&, factor]  
[factor, &]  
[=, &total]  
[&total, =]  
```  
  
 Bei Verwendung eines `capture-default` werden nur die im Lambda\-Ausdruck erwähnten Variablen erfasst.  
  
 Wenn Ihre Erfassungsklausel ein `capture-default` `&` umfasst, kann kein `identifier` in einer `capture` dieser Erfassungsklausel die Form `& identifier` haben.  Wenn Ihre Erfassungsklausel ein `capture-default` `=` umfasst, kann analog dazu kein `capture` in dieser Erfassungsklausel die Form `= identifier` haben.  Ein Bezeichner oder `this` kann nicht mehr als einmal in einer Erfassungsklausel angezeigt werden.  Der folgende Codeausschnitt veranschaulicht einige Beispiele.  
  
```cpp  
struct S { void f(int i); };  
  
void S::f(int i) {  
    [&, i]{};    // OK  
    [&, &i]{};   // ERROR: i preceded by & when & is the default  
    [=, this]{}; // ERROR: this when = is the default  
    [i, i]{};    // ERROR: i repeated  
}  
```  
  
 Eine `capture`, die von einem Auslassungszeichen gefolgt wird, ist eine Paketerweiterung, wie in diesem Beispiel für eine [variadic\-Vorlage](../cpp/ellipses-and-variadic-templates.md) gezeigt wird:  
  
```cpp  
template<class... Args>  
void f(Args... args) {  
    auto x = [args...] { return g(args...); };  
    x();  
}  
```  
  
 Übergeben Sie zum Verwenden von Lambda\-Ausdrücken in einer Klassenmethode den `this`\-Zeiger auf die Erfassungsklausel, um den Zugriff auf die Methoden und Datenmember der einschließenden Klasse bereitzustellen.  Ein Beispiel für die Verwendung von Lambda\-Ausdrücken mit Klassenmethoden finden Sie unter „Beispiel: Verwenden eines Lambda\-Ausdrucks in einer Methode“ unter [Beispiele für Lambda\-Ausdrücke](../cpp/examples-of-lambda-expressions.md).  
  
 Wenn Sie die Erfassungsklausel verwenden, sollten Sie diese wichtigen Punkte beachten, insbesondere wenn Sie Lambdas mit Multithreading verwenden:  
  
-   Verweiserfassungen können im Gegensatz zu Werterfassungen dazu verwendet werden, um Variablen outside zu ändern.  \(`mutable` ermöglicht Änderungen an Kopien, jedoch nicht am Original.\)  
  
-   Verweiserfassungen können im Gegensatz zu Werterfassungen Änderungen von Variablen outside wiederspiegeln.  
  
-   Verweiserfassungen führen eine Lebenszeitabhängigkeit ein, während Werterfassungen keine Lebenszeitabhängigkeiten haben.  Dies ist besonders beim asynchronen Ausführen von Lambda\-Ausdrücken von Bedeutung.  Beim Erfassen einer lokalen Variablen in einem asynchronem Lambda\-Ausdruck ist die Variable höchstwahrscheinlich beim Ausführen des Lambdas nicht verfügbar und es tritt eine Zugriffsverletzung zur Laufzeit auf.  
  
 **Generalisierte Erfassung \(C\+\+14\)**  
  
 Neue Variablen können in C\+\+14 in der Erfassungsklausel eingeführt und initialisiert werden, ohne dass diese Variablen im Bereich der Lambdafunktion vorhanden sein müssen.  Die Initialisierung kann mit einem beliebigen Ausdruck ausgedrückt werden; der Typ der neuen Variablen wird von dem durch den Ausdruck genierten Typ abgeleitet.  Ein Vorteil dieser Funktion ist, dass Sie Variablen, die nur verschoben werden können, \(z. B. std::unique\_ptr\) aus dem umgebenden Bereich erfassen und in einem Lambda\-Ausdruck verwenden können.  
  
```  
pNums = make_unique<vector<int>>(nums);  
//...  
      auto a = [ptr = move(pNums)]()  
        {  
           // use ptr  
        };  
```  
  
### Parameterliste  
 Neben dem Erfassen von Variablen werden in einem Lambda\-Ausdruck Eingabeparameter akzeptiert.  Eine Parameterliste \(*lambda declarator* in der Standardsyntax\) ist optional und ähnelt in den meisten Aspekten der Parameterliste für eine Funktion.  
  
```  
int y = [] (int first, int second)  
{  
    return first + second;  
};  
  
```  
  
 Bei einem generischen Parametertyp kann in **C\+\+ 14** das auto\-Schlüsselwort als Typspezifizierer verwendet werden.  Das weist den Compiler an, den Funktionsaufrufoperator als Vorlage zu erstellen.  Jede Instanz des auto\-Schlüsselworts in einer Parameterliste entspricht einem Typparameter.  
  
```  
auto y = [] (auto first, auto second)  
{  
    return first + second;  
};  
```  
  
 Ein Lambda\-Ausdruck kann einen anderen Lambda\-Ausdruck als Argument übernehmen.  Weitere Informationen finden Sie unter „Lambda\-Ausdrücke höherer Ordnung“ im Thema [Beispiele für Lambda\-Ausdrücke](../cpp/examples-of-lambda-expressions.md).  
  
 Da die Parameterliste optional ist, können Sie die leeren Klammern weglassen, wenn Sie keine Argumente an den Lambda\-Ausdruck übergeben und deren `lambda-declarator:` keine *exception\-specification*, *trailing\-return\-type* oder `mutable` enthält.  
  
### Änderbare Spezifikation  
 Normalerweise ist ein Aufrufoperator einer Lambda\-Funktion "const\-by\-value", aber das Schlüsselwort `mutable` hebt dies auf.  Er erstellt keine änderbaren Datenmember.  Die änderbare Spezifikation aktiviert den Text eines Lambda\-Ausdrucks, um Variablen zu ändern, die als Wert erfasst werden.  Einige der späteren Beispiele in diesem Artikel veranschaulichen die Verwendung von `mutable`.  
  
### Ausnahmespezifikation  
 Sie können die `throw()`\-Ausnahmespezifikation verwenden, um anzugeben, dass der Lambda\-Ausdruck keine Ausnahmen auslöst.  Wie bei normalen Funktionen generiert der Visual C\+\+\-Compiler die Warnung [C4297](../error-messages/compiler-warnings/compiler-warning-level-1-c4297.md), wenn ein Lambda\-Ausdruck die `throw()`\-Ausnahmespezifikation deklariert und der Lambda\-Text eine Ausnahme auslöst, wie hier gezeigt:  
  
```cpp  
// throw_lambda_expression.cpp  
// compile with: /W4 /EHsc   
int main() // C4297 expected  
{  
   []() throw() { throw 5; }();  
}  
```  
  
 Weitere Informationen finden Sie unter [Ausnahmespezifikationen \(throw\)](../cpp/exception-specifications-throw-cpp.md).  
  
### Rückgabetyp  
 Der Rückgabetyp von Lambda\-Ausdrücken wird automatisch hergeleitet.  Sie müssen das [auto](../cpp/auto-cpp.md)\-Schlüsselwort nur verwenden, wenn Sie einen *trailing\-return\-type* angeben.  *trailing\-return\-type* ähnelt dem Rückgabetyp\-Ausschnitt einer normalen Methode oder Funktion.  Der Rückgabetyp folgt jedoch auf die Parameterliste, und das Schlüsselwort trailing\-return\-type `->` muss vor dem Rückgabetyp angegeben werden.  
  
 Sie können den Rückgabetyp eines Lambda\-Ausdrucks weglassen, wenn der Lambda\-Text nur eine einzelne Return\-Anweisung enthält oder der Lambda\-Ausdruck keinen Wert zurückgibt.  Wenn der Lambda\-Text aus einer einzelnen Return\-Anweisung besteht, leitet der Compiler den Rückgabetyp vom Typ des Return\-Ausdrucks ab.  Andernfalls geht der Compiler davon aus, dass der Rückgabetyp `void` ist.  Betrachten Sie die folgenden Beispiele von Codeausschnitten, die dieses Prinzip veranschaulichen.  
  
```cpp  
auto x1 = [](int i){ return i; }; // OK: return type is int  
auto x2 = []{ return{ 1, 2 }; };  // ERROR: return type is void, deducing   
                                  // return type from braced-init-list is not valid  
  
```  
  
 Ein Lambda\-Ausdruck kann einen anderen Lambda\-Ausdruck als Rückgabewert erzeugen.  Weitere Informationen finden Sie unter „Lambda\-Ausdrücke höherer Ordnung“ unter [Beispiele für Lambda\-Ausdrücke](../cpp/examples-of-lambda-expressions.md).  
  
### Lambda\-Text  
 Der Lambda\-Textteil \(*compound\-statement* in der Standardsyntax\) eines Lambda\-Ausdrucks kann alles enthalten, was der Text einer gewöhnlichen Methode oder Funktion enthalten kann.  Der Text einer gewöhnlichen Funktion und eines Lambda\-Ausdrucks kann auf die folgenden Variablenarten zugreifen:  
  
-   Aus dem einschließenden Bereich erfasste Variablen, wie zuvor beschrieben.  
  
-   Parameter  
  
-   Lokal deklarierte Variablen  
  
-   Klassendatenmember, wenn diese innerhalb einer Klasse deklariert sind und `this` erfasst wird  
  
-   Jede beliebige Variable mit statischer Speicherdauer \(z. B. globale Variablen\)  
  
 Das folgende Beispiel enthält einen Lambda\-Ausdruck, welcher explizit die Variable `n` nach ihrem Wert erfasst und implizit die Variable `m` als Verweis erfasst:  
  
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
  
 **Ausgabe:**  
  
  **5**  
**0** Da die Variable `n` als Wert erfasst wird, bleibt der Wert `0` nach dem Aufruf des Lambda\-Ausdrucks erhalten.  Die `mutable`\-Spezifikation ermöglicht es, dass `n` innerhalb des Lambda geändert wird.  
  
 Obwohl ein Lambda\-Ausdruck nur Variablen mit automatischer Speicherdauer aufzeichnen kann, können Sie Variablen verwenden, die eine statische Speicherdauer im Text eines Lambda\-Ausdrucks aufweisen.  Im folgenden Beispiel wird die Funktion `generate` und ein Lambda\-Ausdruck verwendet, um jedem Element in einem `vector`\-Objekt einen Wert zuzuweisen.  Der Lambda\-Ausdruck ändert die statische Variable, um den Wert des nächsten Elements zu generieren.  
  
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
  
 Weitere Informationen finden Sie unter [Generieren](../Topic/generate.md).  
  
 Im folgenden Codebeispiel wird die Funktion aus dem vorherigen Beispiel verwendet, und es wird ein Beispiel eines Lambda\-Ausdrucks mit dem STL\-Algorithmus `generate_n` hinzugefügt.  Dieser lambda\-Ausdruck weist ein Element eines `vector`\-Objekts der Summe der vorangehenden zwei Elemente zu.  Das `mutable`\-Schlüsselwort wird verwendet, sodass der Text des Lambda\-Ausdrucks seine Kopien der externen Variablen `x` und `y` ändern kann, die vom Lambda\-Ausdruck als Wert erfasst werden.  Da der Lambda\-Ausdruck die originalen Variablen `x` und `y` als Wert erfasst, bleiben die Werte `1`, nachdem das Lambda ausgeführt wird.  
  
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
  
 **Ausgabe:**  
  
  **Vektor v nach Aufruf von generate\_n\(\) mit Lambda: 1 1 2 3 5 8 13 21 34**  
**x: 1 y: 1**  
**Vektor v nach 1. Aufruf von fillVector\(\): 1 2 3 4 5 6 7 8 9**  
**Vektor v nach 2. Aufruf von fillVector\(\): 10 11 12 13 14 15 16 17 18** Weitere Informationen finden Sie unter [generate\_n](../Topic/generate_n.md).  
  
## Microsoft\-spezifisch  
 Lambdas werden in den folgenden verwalteten Entitäten der Common Language Runtime \(CLR\) nicht unterstützt: `ref class`, `ref struct`, `value class` bzw. `value struct`.  
  
 Wenn Sie einen Microsoft\-spezifischen Modifizierer wie z. B. [\_\_declspec](../cpp/declspec.md) verwenden, können Sie diesen direkt nach `parameter-declaration-clause` in einen Lambda\-Ausdruck einfügen—zum Beispiel:  
  
```cpp  
auto Sqr = [](int t) __declspec(code_seg("PagedMem")) -> int { return t*t; };  
  
```  
  
 Um herauszufinden, ob ein Modifizierer von Lambdas unterstützt wird, lesen Sie den entsprechenden Artikel im Abschnitt [Microsoft\-spezifische Modifizierer](../cpp/microsoft-specific-modifiers.md) in der Dokumentation.  
  
 Visual Studio unterstützt die standardmäßige C\+\+11\-Lambda\-Ausdruckssyntax und \-Funktionalität mit den folgenden Ausnahmen:  
  
-   Wie alle anderen Klassen rufen Lambdas nicht automatisch generierte Bewegungskonstruktoren und Bewegungszuweisungsoperatoren ab.  Weitere Informationen über Unterstützung für rvalue\-Verweisverhalten finden Sie im Abschnitt „Rvalue\-Referenzen“ unter [Unterstützung für C\+\+11\/14\/17\-Funktionen](../cpp/support-for-cpp11-14-17-features-modern-cpp.md).  
  
-   Das optionale *attribute\-specifier\-seq* wird in dieser Version nicht unterstützt.  
  
 Visual Studio enthält die folgenden Features zusätzlich zur standardmäßigen C\+\+11\-Lambda\-Funktionalität:  
  
-   Statusfreie Lambdas sind unbegrenzt konvertierbar zu Funktionszeigern, die willkürliche Aufrufkonventionen verwenden.  
  
-   Automatisch hergeleitete Rückgabetypen für Lambda\-Texte, die komplizierter als `{ return expression; }` sind, sofern alle Return\-Anweisungen denselben Typ haben.  \(Diese Funktion ist Teil des vorgeschlagenen C\+\+14\-Standards.\)  
  
## Siehe auch  
 [C\+\+\-Sprachreferenz](../cpp/cpp-language-reference.md)   
 [Funktionsobjekte in der STL](../standard-library/function-objects-in-the-stl.md)   
 [Funktionsaufruf](../cpp/function-call-cpp.md)   
 [for\_each](../Topic/for_each.md)