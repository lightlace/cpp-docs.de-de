---
title: automatisch (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
f1_keywords:
- auto_CPP
- auto
helpviewer_keywords:
- auto keyword [C++]
ms.assetid: e9d495d7-601c-4547-b897-998389a311f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f38c4cdfcbb75cd4c2df4fadd10cfcaccda4540e
ms.sourcegitcommit: a88d228480d4bb5834e985d7b3ead2760be95572
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2018
ms.locfileid: "50203065"
---
# <a name="auto-c"></a>automatisch (C++)

Leitet den Typ einer deklarierten Variable vom entsprechenden Initialisierungsausdruck ab.

## <a name="syntax"></a>Syntax

```
auto declarator initializer;
```

```
[](auto param1, auto param2) {};
```

## <a name="remarks"></a>Hinweise

Die **automatisch** -Schlüsselwort weist den Compiler an den Initialisierungsausdruck einer deklarierten Variable oder einen lambdaausdrucksparameter zu verwenden, um den Typ herzuleiten.

Wir empfehlen die Verwendung der **automatisch** Schlüsselwort für die meisten Situationen – es sei denn, Sie wirklich eine Konvertierung möchten, da sie diese Vorteile bietet:

- **Stabilität:** , wenn der Typ des Ausdrucks geändert wird – dies schließt, wenn der Rückgabetyp einer Funktion geändert wird, dann funktioniert.

- **Leistung:** sind garantiert, dass es keine Konvertierung fallen.

- **Benutzerfreundlichkeit:** müssen Sie nicht über Typ Namen Rechtschreibung schwierigkeiten und Fehler machen.

- **Effizienz:** Ihre Codierung kann effizienter sein.

Fälle von Konvertierungen in der Sie möglicherweise nicht verwenden möchten **automatisch**:

- Wenn Sie einen ganz bestimmten Typ benötigen, und nichts anderes infrage kommt.

- Hilfetypen – z. B. `(valarray+valarray)`.

Verwenden der **automatisch** -Schlüsselwort, verwenden sie anstelle eines Typs zum Deklarieren einer Variablen, und geben Sie einen Initialisierungsausdruck. Darüber hinaus können Sie ändern die **automatisch** -Schlüsselwort mithilfe von Bezeichnern und Deklaratoren wie z. B. **const**, **flüchtige**, Zeiger (`*`), Referenz (`&`), und Rvalue-Verweis (`&&`). Der Compiler wertet den Initialisierungsausdruck aus und verwendet dann diese Informationen, um den Typ der Variable herzuleiten.

Der Initialisierungsausdruck kann eine Zuweisung (Gleichheitszeichensyntax), eine direkte Initialisierung (funktionsformatsyntax), werden ein [new-Operator](new-operator-cpp.md) möglich, Ausdruck oder der Initialisierungsausdruck der  *for-Range-Declaration* Parameter in einer [bereichsbasiert für Anweisung (C++)](../cpp/range-based-for-statement-cpp.md) Anweisung. Weitere Informationen finden Sie unter [Initialisierer](../cpp/initializers.md) und den Codebeispielen weiter unten in diesem Dokument.

Die **automatisch** -Schlüsselwort ist ein Platzhalter für einen Typ, aber es ist nicht selbst ein. Aus diesem Grund die **automatisch** -Schlüsselwort kann nicht in Umwandlungen und Operatoren wie z. B. verwendet werden ["sizeof"](../cpp/sizeof-operator.md) und [Typeid](../windows/typeid-cpp-component-extensions.md).

## <a name="usefulness"></a>Nützlichkeit

Die **automatisch** Schlüsselwort ist eine einfache Möglichkeit zum Deklarieren einer Variablen, die einen komplizierten Typ aufweist. Beispielsweise können Sie **automatisch** zum Deklarieren einer Variablen, in dem der Initialisierungsausdruck, Vorlagen, Zeiger auf Funktionen oder Zeiger auf Member umfasst.

Sie können auch **automatisch** zu deklarieren und initialisieren eine Variable, die einen Lambda-Ausdruck. Sie können den Typ der Variable nicht selbst deklarieren, da der Typ eines Lambdaausdrucks nur dem Compiler bekannt ist. Weitere Informationen finden Sie unter [Beispiele für Lambdaausdrücke](../cpp/examples-of-lambda-expressions.md).

## <a name="trailing-return-types"></a>Nachstehende Rückgabetypen

Sie können **automatisch**zusammen mit der **"decltype"** Typspezifizierer verwenden, um Hilfe Vorlagenbibliotheken zu schreiben. Verwendung **automatisch** und **"decltype"** um eine Vorlagenfunktion deklarieren, deren Rückgabetyp Typ hängt von den Typen seiner Vorlagenargumente. Oder verwenden Sie **automatisch** und **"decltype"** um eine Vorlagenfunktion zu deklarieren, die einen Aufruf einer anderen Funktion umschließt und gibt dann zurück, was der Rückgabetyp dieser anderen Funktion ist. Weitere Informationen finden Sie unter ["decltype"](../cpp/decltype-cpp.md).

## <a name="references-and-cv-qualifiers"></a>Verweise und CV-Qualifizierer

Beachten Sie, dass die Verwendung **automatisch** Löscht Verweise, const-Qualifizierer und flüchtige Qualifizierer. Betrachten Sie das folgende Beispiel:

```cpp
// cl.exe /analyze /EHsc /W4
#include <iostream>

using namespace std;

int main( )
{
    int count = 10;
    int& countRef = count;
    auto myAuto = countRef;

    countRef = 11;
    cout << count << " ";

    myAuto = 12;
    cout << count << endl;
}

```

Im vorherigen Beispiel ist der MyAuto eine ganze Zahl, ein Int-Verweis, damit die Ausgabe erfolgt `11 11`, nicht `11 12` wie der Fall wäre, wenn der Verweis-Qualifizierer nicht wäre, indem abgelegt worden **automatisch**.

## <a name="type-deduction-with-braced-initializers-c14"></a>Typableitung mit in Klammern gesetzte Initialisierern (C ++ 14)

Im folgenden Codebeispiel wird veranschaulicht, wie Sie eine automatische Variable, die mit geschweiften Klammern initialisiert werden. Beachten Sie den Unterschied zwischen B und C sowie zwischen A und E.

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

Die folgende Tabelle enthält die Einschränkungen für die Verwendung der **automatisch** -Schlüsselwort und die entsprechende diagnosefehlermeldung, die der Compiler gibt.

|Fehlernummer|Beschreibung|
|------------------|-----------------|
|[C3530](../error-messages/compiler-errors-2/compiler-error-c3530.md)|Die **automatisch** Schlüsselwort kann nicht mit einem anderen Typspezifizierer kombiniert werden.|
|[C3531](../error-messages/compiler-errors-2/compiler-error-c3531.md)|Ein Symbol, das mit deklariert wird die **automatisch** Schlüsselwort muss einen Initialisierer aufweisen.|
|[C3532](../error-messages/compiler-errors-2/compiler-error-c3532.md)|Sie falsch verwendet die **automatisch** Schlüsselwort, um einen Typ zu deklarieren. Sie haben zum Beispiel einen Methodenrückgabetyp oder ein Array deklariert.|
|[C3533](../error-messages/compiler-errors-2/compiler-error-c3533.md), [C3539](../error-messages/compiler-errors-2/compiler-error-c3539.md)|Ein Parameter oder ein Vorlagenargument kann nicht deklariert werden, mit der **automatisch** Schlüsselwort.|
|[C3535](../error-messages/compiler-errors-2/compiler-error-c3535.md)|Parameter-Methode oder die Vorlage kann nicht deklariert werden, mit der **automatisch** Schlüsselwort.|
|[C3536](../error-messages/compiler-errors-2/compiler-error-c3536.md)|Ein Symbol kann erst verwendet werden, wenn es initialisiert wurde. In der Praxis bedeutet dies, dass eine Variable nicht verwendet werden kann, um sich selbst zu initialisieren.|
|[C3537](../error-messages/compiler-errors-2/compiler-error-c3537.md)|Sie können nicht eine Umwandlung in einen Typ, der mit deklariert wird die **automatisch** Schlüsselwort.|
|[C3538](../error-messages/compiler-errors-2/compiler-error-c3538.md)|Alle Symbole in einer Deklaratorliste, die mit deklariert ist die **automatisch** Schlüsselwort muss in den gleichen Typ aufgelöst werden. Weitere Informationen finden Sie unter [Deklarationen und Definitionen](declarations-and-definitions-cpp.md).|
|[C3540](../error-messages/compiler-errors-2/compiler-error-c3540.md), [C3541](../error-messages/compiler-errors-2/compiler-error-c3541.md)|Die ["sizeof"](../cpp/sizeof-operator.md) und [Typeid](../windows/typeid-cpp-component-extensions.md) Operatoren nicht angewendet werden, um ein Symbol, das mit deklariert wird die **automatisch** Schlüsselwort.|

## <a name="examples"></a>Beispiele

Die Codefragmente veranschaulichen einige der Methoden in der die **automatisch** -Schlüsselwort kann verwendet werden.

Die folgenden Deklarationen sind gleichwertig. In der ersten Anweisung, die Variable `j` wird deklariert, um Typ **Int**. In der zweiten Anweisung, die Variable `k` abgeleitet wird, um Typ **Int** , da der Initialisierungsausdruck (0) eine ganze Zahl ist.

```cpp
int j = 0;  // Variable j is explicitly type int.
auto k = 0; // Variable k is implicitly type int because 0 is an integer.
```

Die folgenden Deklarationen sind gleichwertig, die zweite Deklaration ist jedoch einfacher als die erste. Eines der überzeugendsten Gründe für die Verwendung der **automatisch** -Schlüsselworts ist die Einfachheit.

```cpp
map<int,list<string>>::iterator i = m.begin();
auto i = m.begin();
```

Das folgende Codefragment deklariert den Typ der Variablen `iter` und `elem` bei der **für** und **für** Schleifen starten.

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

Das folgende Codefragment verwendet den **neue** Operator und die Zeigerdeklaration Deklaration Zeiger deklariert werden.

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

Das folgende Codefragment initialisiert Variablen `x` eingeben **Int**Variable `y` um einen Verweis auf Typ **const Int**, und die Variable `fp` in einen Zeiger auf eine Funktion Typ zurückgibt **Int**.

```cpp
int f(int x) { return x; }
int main()
{
    auto x = f(0);
    const auto & y = f(1);
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
[sizeof-Operator](../cpp/sizeof-operator.md)<br/>
[typeid](../windows/typeid-cpp-component-extensions.md)<br/>
[operator new](new-operator-cpp.md)<br/>
[Deklarationen und Definitionen](declarations-and-definitions-cpp.md)<br/>
[Beispiele für Lambdaausdrücke](../cpp/examples-of-lambda-expressions.md)<br/>
[Initialisierer](../cpp/initializers.md)<br/>
[decltype](../cpp/decltype-cpp.md)
