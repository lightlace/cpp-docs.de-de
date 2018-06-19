---
title: Auto (C++) | Microsoft Docs
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
ms.openlocfilehash: 14ad8e7cb81df62156d35809853e1060107d7c90
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32418223"
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
 Das `auto`-Schlüsselwort weist den Compiler an, den Initialisierungsausdruck einer deklarierten Variable oder einen Lambda-Ausdrucksparameter zu verwenden, um den Typ herzuleiten.  
  
 Es wird empfohlen, in den meisten Fällen das `auto`-Schlüsselwort zu verwenden (es sei denn, Sie möchten wirklich eine Konvertierung durchführen), denn diese Vorgehensweise bietet folgende Vorteile:  
  
-   **Stabilität:** , wenn der Typ des Ausdrucks geändert wird – dies schließt, wenn der Rückgabetyp einer Funktion geändert wird – es genauso funktioniert.  
  
-   **Leistung:** haben Sie die Sicherheit, dass sich keine Konvertierung.  
  
-   **Benutzerfreundlichkeit:** Sie keine Gedanken Typ Name Rechtschreibung schwierigkeiten und Fehler.  
  
-   **Effizienz:** die Codierung kann effizienter sein.  
  
 Fälle von Konvertierungen, bei denen Sie `auto` möglicherweise nicht verwenden sollten:  
  
-   Wenn Sie einen ganz bestimmten Typ benötigen, und nichts anderes infrage kommt.  
  
-   Hilfetypen – z. B. `(valarray+valarray)`.  
  
 Wenn Sie das `auto`-Schlüsselwort verwenden, verwenden Sie es anstelle eines Typs, um eine Variable zu deklarieren, und geben Sie einen Initialisierungsausdruck an. Darüber hinaus können Sie das `auto`-Schlüsselwort mithilfe von Bezeichnern und Deklaratoren wie `const`, `volatile`, Zeigern (`*`), Verweisen (`&`) und rvalue-Verweisen (`(&&`) ändern. Der Compiler wertet den Initialisierungsausdruck aus und verwendet dann diese Informationen, um den Typ der Variable herzuleiten.  
  
 Der Initialisierungsausdruck kann eine Zuweisung (Gleichheitszeichensyntax), eine direkte Initialisierung (funktionsformatsyntax), ein [new-Operator](new-operator-cpp.md) Ausdruck oder der Initialisierungsausdruck kann der  *für-Range-Declaration* Parameter in einem [bereichsbasiert für Anweisung (C++)](../cpp/range-based-for-statement-cpp.md) Anweisung. Weitere Informationen finden Sie unter [Initialisierer](../cpp/initializers.md) und den Codebeispielen weiter unten in diesem Dokument.  
  
 Das `auto`-Schlüsselwort ist ein Platzhalter für einen Typ, ist jedoch selbst kein Typ. Aus diesem Grund die `auto` Schlüsselwort kann nicht in Umwandlungen und Operatoren wie z. B. verwendet werden ["sizeof"](../cpp/sizeof-operator.md) und [Typeid](../windows/typeid-cpp-component-extensions.md).  
  
## <a name="usefulness"></a>Nützlichkeit  
 Das `auto`-Schlüsselwort ist eine einfache Möglichkeit, eine Variable zu deklarieren, die einen komplizierten Typ aufweist. Sie können beispielsweise `auto` verwenden, um eine Variable zu deklarieren, in der der Initialisierungsausdruck Vorlagen, Zeiger auf Funktionen oder Zeiger auf Member umfasst.  
  
 Sie können `auto` außerdem verwenden, um eine Variable zu deklarieren und auf einen Lambda-Ausdruck zu initialisieren. Sie können den Typ der Variable nicht selbst deklarieren, da der Typ eines Lambdaausdrucks nur dem Compiler bekannt ist. Weitere Informationen finden Sie unter [Beispiele für Lambdaausdrücke](../cpp/examples-of-lambda-expressions.md).  
  
## <a name="trailing-return-types"></a>Nachstehende Rückgabetypen  
 Sie können `auto` zusammen mit dem `decltype`-Typspezifizierer verwenden, um Vorlagenbibliotheken zu schreiben. Verwenden Sie `auto` und `decltype`, um eine Vorlagenfunktion zu deklarieren, deren Rückgabetyp von den Typen seiner Vorlagenargumente abhängt. Oder verwenden Sie `auto` und `decltype`, um eine Vorlagenfunktion zu deklarieren, die einen Aufruf einer anderen Funktion umschließt und anschließend das zurückgibt, was der Rückgabetyp dieser anderen Funktion ist. Weitere Informationen finden Sie unter ["decltype"](../cpp/decltype-cpp.md).  
  
## <a name="references-and-cv-qualifiers"></a>Verweise und CV-Qualifizierer  
 Beachten Sie, dass durch die Verwendung von `auto` Verweise, const-Qualifizierer und flüchtige Qualifizierer abgelegt werden. Betrachten Sie das folgende Beispiel:  
  
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
  
 Im vorherigen Beispiel ist MyAuto ein "Int", ein Int-Verweis, sodass die Ausgabe `11 11`, nicht `11 12` wie der Fall wäre, wenn der Verweis-Qualifizierer nicht wäre, indem abgelegt worden `auto`.  
  
## <a name="type-deduction-with-braced-initializers-c14"></a>Typableitung mit in Klammern gesetzte Initialisierer (C ++ 14)  
 Der folgende Code Exmample zeigt, wie eine automatische Variable mit geschweiften Klammern initialisiert werden soll. Beachten Sie den Unterschied zwischen B und C und A und E.  
  
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
 Die folgende Tabelle zeigt die Einschränkungen bei der Nutzung des `auto`-Schlüsselworts und die entsprechende Diagnosefehlermeldung, die der Compiler ausgibt.  
  
|Fehlernummer|Beschreibung|  
|------------------|-----------------|  
|[C3530](../error-messages/compiler-errors-2/compiler-error-c3530.md)|Das `auto`-Schlüsselwort kann nicht mit einem anderen Typspezifizierer kombiniert werden.|  
|[C3531](../error-messages/compiler-errors-2/compiler-error-c3531.md)|Ein Symbol, das mit dem `auto`-Schlüsselwort deklariert wird, muss einen Initialisierer aufweisen.|  
|[C3532](../error-messages/compiler-errors-2/compiler-error-c3532.md)|Sie haben fälschlicherweise das `auto`-Schlüsselwort verwendet, um einen Typ zu deklarieren. Sie haben zum Beispiel einen Methodenrückgabetyp oder ein Array deklariert.|  
|[C3533](../error-messages/compiler-errors-2/compiler-error-c3533.md), [C3539](../error-messages/compiler-errors-2/compiler-error-c3539.md)|Ein Parameter oder ein Vorlagenargument kann nicht mit dem `auto`-Schlüsselwort deklariert werden.|  
|[C3535](../error-messages/compiler-errors-2/compiler-error-c3535.md)|Eine Methode oder ein Vorlagenparameter kann nicht mit dem `auto`-Schlüsselwort deklariert werden.|  
|[C3536](../error-messages/compiler-errors-2/compiler-error-c3536.md)|Ein Symbol kann erst verwendet werden, wenn es initialisiert wurde. In der Praxis bedeutet dies, dass eine Variable nicht verwendet werden kann, um sich selbst zu initialisieren.|  
|[C3537](../error-messages/compiler-errors-2/compiler-error-c3537.md)|Sie können nicht in einen Typ umwandeln, der mit dem `auto`-Schlüsselwort deklariert wird.|  
|[C3538](../error-messages/compiler-errors-2/compiler-error-c3538.md)|Alle Symbole in einer Deklaratorliste, die mit dem `auto`-Schlüsselwort deklariert wird, müssen in den gleichen Typ aufgelöst werden. Weitere Informationen finden Sie unter [Deklarationen und Definitionen](declarations-and-definitions-cpp.md).|  
|[C3540](../error-messages/compiler-errors-2/compiler-error-c3540.md), [C3541](../error-messages/compiler-errors-2/compiler-error-c3541.md)|Die ["sizeof"](../cpp/sizeof-operator.md) und [Typeid](../windows/typeid-cpp-component-extensions.md) Operatoren nicht angewendet werden, um ein Symbol, das mit deklariert wird die `auto` Schlüsselwort.|  
  
## <a name="examples"></a>Beispiele  
 Die Codefragmente veranschaulichen einige Verwendungsmöglichkeiten des `auto`-Schlüsselworts.  
  
 Die folgenden Deklarationen sind gleichwertig. In der ersten Anweisung wird die `j`-Variable als Typ `int` deklariert. In der zweiten Anweisung wird die `k`-Variable hergeleitet, um Typ `int` zu entsprechen, da der Initialisierungsausdruck (0) eine ganze Zahl ist.  
  
```cpp  
int j = 0;  // Variable j is explicitly type int.  
auto k = 0; // Variable k is implicitly type int because 0 is an integer.  
```  
  
 Die folgenden Deklarationen sind gleichwertig, die zweite Deklaration ist jedoch einfacher als die erste. Einer der überzeugendsten Gründe für die Verwendung des `auto`-Schlüsselworts ist die Einfachheit.  
  
```cpp  
map<int,list<string>>::iterator i = m.begin();   
auto i = m.begin();   
```  
  
 Das folgende Codefragment deklariert den Typ der Variablen `iter` und `elem`, wenn die Schleifen `for` und range-`for` beginnen.  
  
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
  
 Das folgende Codefragment verwendet den Operator und die Zeigerdeklaration `new`, um Zeiger zu deklarieren.  
  
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
  
 Das folgende Codefragment initialisiert die Variable `x` Eingabe `int`variabler `y` auf einen Verweis auf den Typ `const int`, und die Variable `fp` in einen Zeiger auf eine Funktion, die Typ zurückgibt `int`.  
  
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
 [Auto-Schlüsselwort](../cpp/auto-keyword.md)   
 [Stichwörter](../cpp/keywords-cpp.md)   
 [/ Zc: Auto (Variablentyp ableiten)](../build/reference/zc-auto-deduce-variable-type.md)   
 [Sizeof-Operator](../cpp/sizeof-operator.md)   
 [typeid](../windows/typeid-cpp-component-extensions.md)   
 [new-Operator](new-operator-cpp.md)   
 [Deklarationen und Definitionen](declarations-and-definitions-cpp.md)   
 [Beispiele für Lambda-Ausdrücke](../cpp/examples-of-lambda-expressions.md)   
 [Initialisierer](../cpp/initializers.md)   
 [decltype](../cpp/decltype-cpp.md)