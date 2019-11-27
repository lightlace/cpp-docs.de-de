---
title: Auto (C++)
ms.date: 11/04/2016
f1_keywords:
- auto_CPP
- auto
helpviewer_keywords:
- auto keyword [C++]
ms.assetid: e9d495d7-601c-4547-b897-998389a311f4
ms.openlocfilehash: 8af2aceb2964a5ec3adcbb0b0accab0b051ff48c
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74303382"
---
# <a name="auto-c"></a>Auto (C++)

Leitet den Typ einer deklarierten Variable vom entsprechenden Initialisierungsausdruck ab.

## <a name="syntax"></a>Syntax

```
auto declarator initializer;
```

```
[](auto param1, auto param2) {};
```

## <a name="remarks"></a>Hinweise

Das **Auto** -Schlüsselwort weist den Compiler an, den Initialisierungs Ausdruck einer deklarierten Variable oder eines Lambda-Ausdrucks Parameters zu verwenden, um den Typ abzuleiten.

Es wird empfohlen, das Schlüsselwort " **Auto** " für die meisten Situationen zu verwenden – es sei denn, Sie möchten eine Konvertierung –, weil es diese Vorteile bietet:

- **Stabilität:** , Wenn der Typ des Ausdrucks geändert wird – dies schließt ein, wenn ein Funktions Rückgabetyp geändert wird – er funktioniert einfach.

- **Leistung:** Sie sind sicher, dass keine Konvertierung erfolgt.

- **Benutzerfreundlichkeit:** Sie müssen sich keine Gedanken über Rechtschreib Probleme mit Typnamen und Typos machen.

- **Effizienz:** Ihre Codierung kann effizienter sein.

Konvertierungs Fälle, in denen Sie möglicherweise nicht **automatisch**verwenden möchten:

- Wenn Sie einen ganz bestimmten Typ benötigen, und nichts anderes infrage kommt.

- Hilfstypen für Ausdrucks Vorlagen – z. b. `(valarray+valarray)`.

Um das **Auto** -Schlüsselwort zu verwenden, verwenden Sie es anstelle eines Typs, um eine Variable zu deklarieren, und geben Sie einen Initialisierungs Ausdruck an. Außerdem können Sie das Schlüsselwort " **Auto** " mithilfe von Bezeichnern und Deklaratoren wie " **Konstanten**", " **volatile**", "Zeiger (`*`)", "Verweis (`&`)" und "rvalue reference" (`&&`) ändern. Der Compiler wertet den Initialisierungsausdruck aus und verwendet dann diese Informationen, um den Typ der Variable herzuleiten.

Der Initialisierungs Ausdruck kann eine Zuweisung (Gleichheitszeichen Syntax), eine direkte Initialisierung (Funktionsformat Syntax), ein [Operator new](new-operator-cpp.md) -Ausdruck oder der Initialisierungs Ausdruck sein, der für den Parameter " *for-Range-Declaration* " in einer [Bereichs basierten for-C++Anweisung ()](../cpp/range-based-for-statement-cpp.md) -Anweisung ist. Weitere Informationen finden Sie unter [Initialisierer](../cpp/initializers.md) und in den Codebeispielen weiter unten in diesem Dokument.

Das Schlüsselwort " **Auto** " ist ein Platzhalter für einen Typ, aber es ist nicht selbst ein Typ. Daher kann das **Auto** -Schlüsselwort nicht in Umwandlungen oder Operatoren wie [sizeof](../cpp/sizeof-operator.md) und ( C++for/CLI) [typeid](../extensions/typeid-cpp-component-extensions.md)verwendet werden.

## <a name="usefulness"></a>Nützlichkeit

Das Schlüsselwort " **Auto** " ist eine einfache Möglichkeit zum Deklarieren einer Variablen, die einen komplizierten Typ aufweist. Beispielsweise können Sie " **Auto** " verwenden, um eine Variable zu deklarieren, bei der der Initialisierungs Ausdruck Vorlagen, Zeiger auf Funktionen oder Zeiger auf Member umfasst.

Sie können auch " **Auto** " verwenden, um eine Variable in einem Lambda-Ausdruck zu deklarieren und zu initialisieren. Sie können den Typ der Variable nicht selbst deklarieren, da der Typ eines Lambdaausdrucks nur dem Compiler bekannt ist. Weitere Informationen finden Sie unter [Beispiele für Lambda-Ausdrücke](../cpp/examples-of-lambda-expressions.md).

## <a name="trailing-return-types"></a>Nachstehende Rückgabetypen

Sie können **Auto**und den **decltype** -Typspezifizierer verwenden, um Vorlagen Bibliotheken zu schreiben. Verwenden Sie **Auto** und **decltype** , um eine Vorlagen Funktion zu deklarieren, deren Rückgabetyp von den Typen seiner Vorlagen Argumente abhängt. Oder verwenden Sie **Auto** und **decltype** , um eine Vorlagen Funktion zu deklarieren, die einen Rückruf einer anderen Funktion umschließt und anschließend den Rückgabetyp dieser anderen Funktion zurückgibt. Weitere Informationen finden Sie unter [decltype](../cpp/decltype-cpp.md).

## <a name="references-and-cv-qualifiers"></a>Verweise und CV-Qualifizierer

Beachten Sie, dass mit **Auto** Drop Verweise, Konstanten Qualifizierern und volatile-Qualifizierer verwendet werden. Betrachten Sie das folgende Beispiel:

```cpp
// cl.exe /analyze /EHsc /W4
#include <iostream>

using namespace std;

int main( )
{
    int count = 10;
    int& countRef = count;
    auto myAuto = countRef;

    countRef = 11;
    cout << count << " ";

    myAuto = 12;
    cout << count << endl;
}
```

Im vorherigen Beispiel ist myauto ein int-und kein int-Verweis, sodass die Ausgabe `11 11`ist, nicht `11 12` wie es der Fall wäre, wenn der Verweis Qualifizierer nicht von **Auto**gelöscht wurde.

## <a name="type-deduction-with-braced-initializers-c14"></a>Typableitung mit geschweizten Initialisierern (c++ 14)

Im folgenden Codebeispiel wird veranschaulicht, wie Sie eine **auto** Variable, mit geschweiften Klammern initialisiert wird. Beachten Sie den Unterschied zwischen B und C sowie zwischen A und E.

```cpp
#include <initializer_list>

int main()
{
    // std::initializer_list<int>
    auto A = { 1, 2 };

    // std::initializer_list<int>
    auto B = { 3 };

    // int
    auto C{ 4 };

    // C3535: cannot deduce type for 'auto' from initializer list'
    auto D = { 5, 6.7 };

    // C3518 in a direct-list-initialization context the type for 'auto'
    // can only be deduced from a single initializer expression
    auto E{ 8, 9 };

    return 0;
}
```

## <a name="restrictions-and-error-messages"></a>Beschränkungen und Fehlermeldungen

In der folgenden Tabelle sind die Einschränkungen für die Verwendung des Schlüssel Worts " **Auto** " und die entsprechende Diagnose Fehlermeldung aufgeführt, die der Compiler ausgibt.

|Fehlernummer|Beschreibung|
|------------------|-----------------|
|[C3530](../error-messages/compiler-errors-2/compiler-error-c3530.md)|Das **Auto** -Schlüsselwort kann nicht mit einem anderen Typspezifizierer kombiniert werden.|
|[C3531](../error-messages/compiler-errors-2/compiler-error-c3531.md)|Ein Symbol, das mit dem **Auto** -Schlüsselwort deklariert wird, muss über einen Initialisierer verfügen.|
|[C3532](../error-messages/compiler-errors-2/compiler-error-c3532.md)|Sie haben das Schlüsselwort " **Auto** " fälschlicherweise zum Deklarieren eines Typs verwendet. Sie haben zum Beispiel einen Methodenrückgabetyp oder ein Array deklariert.|
|[C3533](../error-messages/compiler-errors-2/compiler-error-c3533.md), [C3539](../error-messages/compiler-errors-2/compiler-error-c3539.md)|Ein Parameter oder ein Vorlagen Argument kann nicht mit dem Schlüsselwort " **Auto** " deklariert werden.|
|[C3535](../error-messages/compiler-errors-2/compiler-error-c3535.md)|Eine Methode oder ein Vorlagen Parameter kann nicht mit dem Schlüsselwort " **Auto** " deklariert werden.|
|[C3536](../error-messages/compiler-errors-2/compiler-error-c3536.md)|Ein Symbol kann erst verwendet werden, wenn es initialisiert wurde. In der Praxis bedeutet dies, dass eine Variable nicht verwendet werden kann, um sich selbst zu initialisieren.|
|[C3537](../error-messages/compiler-errors-2/compiler-error-c3537.md)|Sie können nicht in einen Typ umwandeln, der mit dem Schlüsselwort " **Auto** " deklariert wird.|
|[C3538](../error-messages/compiler-errors-2/compiler-error-c3538.md)|Alle Symbole in einer Deklaratorliste, die mit dem Schlüsselwort " **Auto** " deklariert wird, müssen in denselben Typ aufgelöst werden. Weitere Informationen finden Sie unter [Deklarationen und Definitionen](declarations-and-definitions-cpp.md).|
|[C3540](../error-messages/compiler-errors-2/compiler-error-c3540.md), [C3541](../error-messages/compiler-errors-2/compiler-error-c3541.md)|Die Operatoren [sizeof](../cpp/sizeof-operator.md) und [typeid](../extensions/typeid-cpp-component-extensions.md) können nicht auf ein Symbol angewendet werden, das mit dem **Auto** -Schlüsselwort deklariert wird.|

## <a name="examples"></a>Beispiele

Diese Code Fragmente veranschaulichen einige der Methoden, mit denen das Schlüsselwort " **Auto** " verwendet werden kann.

Die folgenden Deklarationen sind gleichwertig. In der ersten Anweisung ist die Variable `j` als Typ " **int**" deklariert. In der zweiten Anweisung wird die Variable `k` in den Typ " **int** " abgeleitet, da der Initialisierungs Ausdruck (0) eine ganze Zahl ist.

```cpp
int j = 0;  // Variable j is explicitly type int.
auto k = 0; // Variable k is implicitly type int because 0 is an integer.
```

Die folgenden Deklarationen sind gleichwertig, die zweite Deklaration ist jedoch einfacher als die erste. Einer der überzeugendsten Gründe für die Verwendung des Schlüssel Worts " **Auto** " ist die Einfachheit.

```cpp
map<int,list<string>>::iterator i = m.begin();
auto i = m.begin();
```

Das folgende Code Fragment deklariert den Typ der Variablen `iter` und `elem`, wenn die **for** -und Range **for** -Schleifen gestartet werden.

```cpp
// cl /EHsc /nologo /W4
#include <deque>
using namespace std;

int main()
{
    deque<double> dqDoubleData(10, 0.1);

    for (auto iter = dqDoubleData.begin(); iter != dqDoubleData.end(); ++iter)
    { /* ... */ }

    // prefer range-for loops with the following information in mind
    // (this applies to any range-for with auto, not just deque)

    for (auto elem : dqDoubleData) // COPIES elements, not much better than the previous examples
    { /* ... */ }

    for (auto& elem : dqDoubleData) // observes and/or modifies elements IN-PLACE
    { /* ... */ }

    for (const auto& elem : dqDoubleData) // observes elements IN-PLACE
    { /* ... */ }
}
```

Das folgende Code Fragment verwendet den **New** -Operator und die Zeiger Deklaration, um Zeiger zu deklarieren.

```cpp
double x = 12.34;
auto *y = new auto(x), **z = new auto(&x);
```

Im folgenden Codefragment werden mehrere Symbole in jeder Deklarationsanweisung deklariert. Beachten Sie, dass alle Symbole in jeder Anweisung in den gleichen Typ aufgelöst werden.

```cpp
auto x = 1, *y = &x, **z = &y; // Resolves to int.
auto a(2.01), *b (&a);         // Resolves to double.
auto c = 'a', *d(&c);          // Resolves to char.
auto m = 1, &n = m;            // Resolves to int.
```

Dieses Codefragment verwendet den bedingten Operator (`?:`), um die `x`-Variable als ganze Zahl mit einem Wert von 200 zu deklarieren:

```cpp
int v1 = 100, v2 = 200;
auto x = v1 > v2 ? v1 : v2;
```

Das folgende Code Fragment initialisiert Variable `x` in den Typ " **int**", "Variable `y`" in einen Verweis auf den Typ "Konstante **int**" und die Variable `fp` einem Zeiger auf eine Funktion, die den Typ " **int**" zurückgibt.

```cpp
int f(int x) { return x; }
int main()
{
    auto x = f(0);
    const auto& y = f(1);
    int (*p)(int x);
    p = f;
    auto fp = p;
    //...
}
```

## <a name="see-also"></a>Siehe auch

[Auto-Schlüsselwort](../cpp/auto-keyword.md)<br/>
[Schlüsselwörter](../cpp/keywords-cpp.md)<br/>
[/Zc:auto (Variablentyp ableiten)](../build/reference/zc-auto-deduce-variable-type.md)<br/>
[sizeof Operator](../cpp/sizeof-operator.md)<br/>
[typeid](../extensions/typeid-cpp-component-extensions.md)<br/>
[operator new](new-operator-cpp.md)<br/>
[Deklarationen und Definitionen](declarations-and-definitions-cpp.md)<br/>
[Beispiele für Lambdaausdrücke](../cpp/examples-of-lambda-expressions.md)<br/>
[Initialisierer](../cpp/initializers.md)<br/>
[decltype](../cpp/decltype-cpp.md)
