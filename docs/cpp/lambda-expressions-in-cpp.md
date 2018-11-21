---
title: Lambdaausdrücke in C++
ms.date: 11/19/2018
helpviewer_keywords:
- lambda expressions [C++]
- lambda expressions [C++], overview
- lambda expressions [C++], vs. function objects
ms.assetid: 713c7638-92be-4ade-ab22-fa33417073bf
ms.openlocfilehash: 1b8568d69fea002e59925e1e9354407457954e42
ms.sourcegitcommit: 9e891eb17b73d98f9086d9d4bfe9ca50415d9a37
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2018
ms.locfileid: "52176262"
---
# <a name="lambda-expressions-in-c"></a>Lambdaausdrücke in C++

In C ++ 11 und höher ein Lambda-Ausdruck – häufig bezeichnet ein *Lambda*– ist eine bequeme Möglichkeit, ein anonymes Funktionsobjekt zu definieren (einen *Closure*) direkt an der Position, in dem es aufgerufen oder als Argument übergeben, Um eine Funktion. Lambda-Ausdrücke werden in der Regel verwendet, um ein paar Codezeilen zu kapseln, die an Algorithmen oder asynchrone Methoden übergeben werden. Dieser Artikel definiert, was Lambdas sind, vergleicht sie mit anderen Programmierverfahren, beschreibt ihre Vorteile und bietet ein grundlegendes Beispiel.

## <a name="related-topics"></a>Verwandte Themen

- [Lambda-Ausdrücke im Vergleich zu Funktionsobjekten](lambda-expression-syntax.md)
- [Arbeiten mit Lambda-Ausdrücke](examples-of-lambda-expressions.md)
- ["constexpr" Lambda-Ausdrücke](lambda-expressions-constexpr.md)

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

![Strukturelle Elemente eines Lambda-Ausdrucks](../cpp/media/lambdaexpsyntax.png "strukturellen Elemente eines Lambda-Ausdrucks")

1. *Erfassungsklausel* (auch bekannt als die *Lambda-Introducer* in der C++-Spezifikation.)

1. *Parameterliste* Optional. (Auch bekannt als die *Lambda Declarator*)

1. *änderbare Spezifikation* Optional.

1. *Ausnahmespezifikation* Optional.

1. *Trailing-Return-Type* Optional.

1. *Lambda-Text*)

### <a name="capture-clause"></a>Erfassungsklausel

Ein Lambda-Ausdruck kann neue Variablen im Text einführen (in **C ++ 14**), und es können auch Zugriff auf oder *erfassen*, Variablen, aus dem umgebenden Bereich. Ein Lambda-Ausdruck beginnt mit der Erfassungsklausel (*Lambda-Introducer* in der Standardsyntax), der angibt, welche Variablen erfasst werden, und gibt an, ob die Erfassung nach Wert oder Verweis erfolgt. Auf Variablen mit dem kaufmännischen Und-Zeichen (`&`) als Präfix erfolgt der Zugriff nach Verweis, und auf Variablen ohne dieses Präfix wird nach Wert zugegriffen.

Eine leere Erfassungsklausel (`[ ]`) gibt an, dass der Lambda-Text auf keine Variablen im einschließenden Bereich zugreift.

Können Sie den standarderfassungsmodus ein Modus (*Capture standardmäßige* in der Standardsyntax), die angeben, wie externe Variablen erfasst, die im Lambda-Ausdruck verwiesen wird: `[&]` bedeutet, dass alle Variablen, die Sie verweisen, werden vom erfasst Referenz und `[=]` bedeutet, dass sie nach Wert erfasst werden. Sie können einen Standarderfassungsmodus verwenden, und dann den entgegengesetzten Modus explizit für bestimmte Variablen angeben. Wenn beispielsweise der Lambda-Text auf die externe Variable `total` nach Wert zugreift und auf die externe Variable `factor` nach Wert, dann sind die folgenden Erfassungsklauseln gleichwertig:

```cpp
[&total, factor]
[factor, &total]
[&, factor]
[factor, &]
[=, &total]
[&total, =]
```

Wenn eine standardmäßige Capture verwendet wird, werden nur die im Lambda erwähnten Variablen erfasst.

Wenn Erfassungsklausel einen standardmäßigen Erfassung enthält `&`, kein `identifier` in einem `capture` Klausel haben dieser Erfassungsklausel die Form `& identifier`. Auch wenn die Erfassungsklausel einen standardmäßigen Erfassung enthält `=`, kein `capture` Klausel haben dieser Erfassungsklausel die Form `= identifier`. Ein Bezeichner oder **dies** kann nicht mehr als einmal in einer Erfassungsklausel angezeigt. Der folgende Codeausschnitt veranschaulicht einige Beispiele.

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

Eine Erfassung, die von einem Auslassungszeichen gefolgt wird eine paketerweiterung, wie in diesem Beispiel [Variadic-Vorlage](../cpp/ellipses-and-variadic-templates.md) Beispiel:

```cpp
template<class... Args>
void f(Args... args) {
    auto x = [args...] { return g(args...); };
    x();
}
```

Um Lambda-Ausdrücke im Text einer Klassenmethode verwenden möchten, übergeben die **dies** Zeiger an die Erfassungsklausel, um Zugriff auf die Methoden und Datenmember der einschließenden Klasse bereitzustellen.

**Visual Studio 2017 Version 15.3 und höher** (verfügbar mit [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): die **dies** Zeiger kann nach Wert erfasst werden, indem Sie angeben `*this` in der Erfassungsklausel. Erfassung nach Wert bedeutet, dass die gesamte *Closure*, ist die anonymes Funktionsobjekt, Encapulates Lambda-Ausdrucks und wird in jeder Aufrufposition, an dem der Lambda-Ausdruck aufgerufen wird, kopiert. Erfassung nach Wert ist nützlich, wenn das Lambda in parallelen oder asynchrone Vorgänge, insbesondere auf bestimmter Hardwarearchitekturen wie NUMA ausgeführt wird.

Ein Beispiel, das zeigt, wie Sie das Verwenden von Lambdaausdrücken mit Klassenmethoden finden Sie unter "Beispiel: Verwenden eines Lambda-Ausdruck in eine Methode" in [Beispiele für Lambdaausdrücke](../cpp/examples-of-lambda-expressions.md).

Wenn Sie die Erfassungsklausel verwenden, sollten Sie diese wichtigen Punkte beachten, insbesondere wenn Sie Lambdas mit Multithreading verwenden:

- Verweiserfassungen können im Gegensatz zu Werterfassungen dazu verwendet werden, um Variablen outside zu ändern. (**änderbare** ermöglicht Kopien geändert werden, jedoch nicht am Original.)

- Verweiserfassungen können im Gegensatz zu Werterfassungen Änderungen von Variablen outside wiederspiegeln.

- Verweiserfassungen führen eine Lebenszeitabhängigkeit ein, während Werterfassungen keine Lebenszeitabhängigkeiten haben. Dies ist besonders beim asynchronen Ausführen von Lambda-Ausdrücken von Bedeutung. Beim Erfassen einer lokalen Variablen in einem asynchronem Lambda-Ausdruck ist die Variable höchstwahrscheinlich beim Ausführen des Lambdas nicht verfügbar und es tritt eine Zugriffsverletzung zur Laufzeit auf.

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

Neben dem Erfassen von Variablen werden in einem Lambda-Ausdruck Eingabeparameter akzeptiert. Eine Parameterliste (*Lambda Declarator* in der Standardsyntax) ist optional und in den meisten Aspekten ähnelt die Parameterliste für eine Funktion.

```cpp
auto y = [] (int first, int second)
{
    return first + second;
};
```

In **C++ 14**, wenn der Typ generisch ist, können Sie das Schlüsselwort "Auto" verwenden, als Typspezifizierer. Das weist den Compiler an, den Funktionsaufrufoperator als Vorlage zu erstellen. Jede Instanz des auto-Schlüsselworts in einer Parameterliste entspricht einem Typparameter.

```cpp
auto y = [] (auto first, auto second)
{
    return first + second;
};
```

Ein Lambdaausdruck kann einen anderen Lambdaausdruck als Argument übernehmen. Weitere Informationen finden Sie unter "Lambdaausdrücke höherer Ordnung" im Thema [Beispiele für Lambdaausdrücke](../cpp/examples-of-lambda-expressions.md).

Da eine Parameterliste optional ist, können Sie die leeren Klammern weglassen, wenn Sie Argumente nicht an den Lambda-Ausdruck übergeben, und der Lambda-Declarator keine enthält *Ausnahmespezifikation*,  *Trailing-Return-Type*, oder **änderbare**.

### <a name="mutable-specification"></a>Änderbare Spezifikation

In der Regel ist ein Aufrufoperator einer Lambda Funktion Const-by-Value, aber verwenden, der die **änderbare** Schlüsselwort hebt dies auf. Er erstellt keine änderbaren Datenmember. Die änderbare Spezifikation aktiviert den Text eines Lambdaausdrucks, um Variablen zu ändern, die als Wert erfasst werden. Einige der Beispiele später in diesem Artikel veranschaulichen, wie **änderbare**.

### <a name="exception-specification"></a>Ausnahmespezifikation

Sie können die `noexcept`-Ausnahmespezifikation verwenden, um anzugeben, dass der Lambdaausdruck keine Ausnahmen auslöst. Wie bei normalen Funktionen generiert der Visual C++-Compiler die Warnung [C4297](../error-messages/compiler-warnings/compiler-warning-level-1-c4297.md) Wenn ein Lambda-Ausdruck deklariert die `noexcept` Ausnahmespezifikation und der Lambda-Text eine Ausnahme auslöst, wie hier gezeigt:

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

Der Rückgabetyp von Lambdaausdrücken wird automatisch hergeleitet. Müssen Sie nicht mit der [automatisch](../cpp/auto-cpp.md) Schlüsselwort, außer Sie geben eine *trailing-Return-Type*. Die *trailing-Return-Type* ähnelt den Rückgabetyp Teil einer normalen Methode oder Funktion. Der Rückgabetyp folgt jedoch auf die Parameterliste, und das Schlüsselwort „trailing-return-type `->`“ muss vor dem Rückgabetyp angegeben werden.

Sie können den Rückgabetyp eines Lambda-Ausdrucks weglassen, wenn der Lambda-Text nur eine einzelne Return-Anweisung enthält oder der Lambda-Ausdruck keinen Wert zurückgibt. Wenn der Lambda-Text aus einer einzelnen Rückgabeanweisung besteht, leitet der Compiler den Rückgabetyp vom Typ des Rückgabeausdrucks ab. Andernfalls leitet der Compiler den Rückgabetyp **"void"**. Betrachten Sie die folgenden Beispiele von Codeausschnitten, die dieses Prinzip veranschaulichen.

```cpp
auto x1 = [](int i){ return i; }; // OK: return type is int
auto x2 = []{ return{ 1, 2 }; };  // ERROR: return type is void, deducing
                                  // return type from braced-init-list is not valid
```

Ein Lambdaausdruck kann einen anderen Lambdaausdruck als Rückgabewert erzeugen. Weitere Informationen finden Sie unter "Lambdaausdrücke höherer Ordnung" im [Beispiele für Lambdaausdrücke](../cpp/examples-of-lambda-expressions.md).

### <a name="lambda-body"></a>Lambda-Text

Der Lambda-Text (*Compound-Statement* in der Standardsyntax) eines Lambda-Ausdrucks kann alles enthalten, die der Text einer gewöhnlichen Methode oder Funktion enthalten kann. Der Text einer gewöhnlichen Funktion und eines Lambdaausdrucks kann auf die folgenden Variablenarten zugreifen:

- Aus dem einschließenden Bereich erfasste Variablen, wie zuvor beschrieben.

- Parameter

- Lokal deklarierte Variablen

- Klassendatenmember, wenn innerhalb einer Klasse deklariert und **dies** erfasst wird

- Jede beliebige Variable mit statischer Speicherdauer (z. B. globale Variablen)

Das folgende Beispiel enthält einen Lambdaausdruck, welcher explizit die Variable `n` nach ihrem Wert erfasst und implizit die Variable `m` als Verweis erfasst:

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

Da die Variable `n` als Wert erfasst wird, bleibt der Wert `0` nach dem Aufruf des Lambdaausdrucks erhalten. Die **änderbare** -Spezifikation ermöglicht `n` innerhalb des Lambda geändert werden.

Obwohl ein Lambdaausdruck nur Variablen mit automatischer Speicherdauer aufzeichnen kann, können Sie Variablen verwenden, die eine statische Speicherdauer im Text eines Lambdaausdrucks aufweisen. Im folgenden Beispiel wird die Funktion `generate` und ein Lambda-Ausdruck verwendet, um jedem Element in einem `vector`-Objekt einen Wert zuzuweisen. Der Lambdaausdruck ändert die statische Variable, um den Wert des nächsten Elements zu generieren.

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

Das folgende Codebeispiel verwendet die Funktion aus dem vorherigen Beispiel und fügt Sie ein Beispiel für einen Lambda-Ausdruck, den C++-Standardbibliothek-Algorithmus verwendet `generate_n`. Dieser Lambdaausdruck weist ein Element eines `vector`-Objekts der Summe der vorangehenden zwei Elemente zu. Die **änderbare** -Schlüsselwort wird verwendet, sodass der Text des Lambda-Ausdrucks seine Kopien der externen Variablen ändern kann `x` und `y`, die der Lambda-Ausdruck als Wert erfasst. Da der Lambdaausdruck die originalen Variablen `x` und `y` als Wert erfasst, bleiben die Werte `1`, nachdem das Lambda ausgeführt wird.

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

## <a name="constexpr-lambda-expressions"></a>"constexpr" Lambda-Ausdrücke

**Visual Studio 2017 Version 15.3 und höher** (zur Verfügung, mit [/Std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): kann ein Lambda-Ausdruck deklariert werden, als `constexpr` oder in einem konstanten Ausdruck verwendet, wenn die Initialisierung der einzelnen Datenmember, dass die It erfasst oder einführt, die in einem konstanten Ausdruck zulässig ist.

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

Ein Lambda-Ausdruck ist implizit `constexpr` Wenn das Ergebnis die Anforderungen erfüllt, eine `constexpr` Funktion:

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

Lambdas werden in der folgenden Entitäten der common Language Runtime (CLR) verwaltet werden nicht unterstützt: **Verweisklasse**, **Referenzstruktur**, **Wertklasse**, oder **wertstruktur** .

Wenn Sie einen Microsoft-spezifische Modifizierer wie z. B. verwenden [__declspec](../cpp/declspec.md), fügen Sie ihn in einen Lambdaausdruck sofort nach der `parameter-declaration-clause`– z. B.:

```cpp
auto Sqr = [](int t) __declspec(code_seg("PagedMem")) -> int { return t*t; };
```

Um zu bestimmen, ob ein Modifizierer von Lambdas unterstützt wird, finden Sie unter im Artikel über das sie in der [Microsoft-spezifische Modifizierer](../cpp/microsoft-specific-modifiers.md) Abschnitt der Dokumentation.

Zusätzlich zu C ++ 11-Standard Lambda-Funktionalität unterstützt Visual Studio zustandslose Lambdas sind unbegrenzt konvertierbar zu Funktionszeigern, die willkürliche Aufrufkonventionen verwenden.

## <a name="see-also"></a>Siehe auch

[C++-Programmiersprachenreferenz](../cpp/cpp-language-reference.md)<br/>
[Funktionsobjekte in der C++-Standardbibliothek](../standard-library/function-objects-in-the-stl.md)<br/>
[Funktionsaufruf](../cpp/function-call-cpp.md)<br/>
[for_each](../standard-library/algorithm-functions.md#for_each)