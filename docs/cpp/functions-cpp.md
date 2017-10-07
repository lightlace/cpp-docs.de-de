---
title: Funktionen (C++) | Microsoft Docs
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
- defaults, arguments
- function definitions
- function definitions, about function definitions
- default arguments
- declarators, functions
ms.assetid: 33ba01d5-75b5-48d2-8eab-5483ac7d2274
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 4196abd9d33595c59ae291ea4eba9e8806cce984
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="functions-c"></a>Funktionen (C++)
Eine Funktion ist ein Codeblock, der einige Vorgänge ausführt. Eine Funktion kann optional Eingabeparameter definieren, die Aufrufern ermöglichen, Argumente in die Funktion weiterzugeben. Eine Funktion kann einen Wert optional als Ausgabe zurückgeben. Funktionen sind für das Kapseln allgemeiner Vorgänge in einem einzelnen wiederverwendbaren Block nützlich, und zwar ideal unter Verwendung eines Namens, der deutlich das beschreibt, was die Funktion vornimmt. Die folgende Funktion akzeptiert zwei Ganzzahlen von einem Aufrufer und gibt deren Summe zurück; `a` und `b` sind *Parameter* vom Typ `int`.  
  
```  
int sum(int a, int b)  
{  
    return a + b;  
}  
```  
  
 Kann die Funktion "aufgerufen wird, oder *aufgerufen*, von einer beliebigen Anzahl von Stellen in der Anwendung. Die Werte, die an die Funktion übergeben werden, sind die *Argumente*, deren Typen mit den Parametertypen in der Funktionsdefinition kompatibel sein müssen.  
  
```  
int main()  
{  
    int i = sum(10, 32);  
    int j = sum(i, 66);  
    cout << "The value of j is" << j << endl; // 108  
}  
```  
  
 Es gibt keine praktische Begrenzung für die Funktionslänge, jedoch angemessene Entwurfsziele für Funktionen, die eine einzelne klar definierte Aufgabe ausführen. Komplexe Algorithmen sollten möglichst in leicht verständliche einfachere Funktionen aufgeschlüsselt werden.  
  
 Im Klassenbereich definierte Funktionen werden als Memberfunktionen bezeichnet. In C++ kann eine Funktion im Gegensatz zu anderen Sprachen auch im Namespacebereich (einschließlich des impliziten globalen Namespace) definiert werden. Solche Funktionen heißen *freien Funktionen* oder *nicht-Memberfunktionen*; sie werden umfassend in der Standardbibliothek verwendet.  
  
## <a name="parts-of-a-function-declaration"></a>Bestandteile einer Funktionsdeklaration  
 Eine minimale Funktion *Deklaration* besteht aus den Rückgabetyp, den Funktionsnamen und die Parameterliste (die leer sein kann) sowie optionalen Schlüsselwörtern, die dem Compiler zusätzliche Anweisungen bereitstellen. Im folgende Beispiel wird die Deklaration einer Funktion:

 ```cpp
 int sum(int a, int b);
 ```

 Eine Funktionsdefinition besteht aus einer Deklaration plus dem *Text*, dem wird der gesamte Code zwischen den geschweiften Klammern:
 
 ```cpp
int sum(int a, int b)  
{  
    return a + b;  
}  
```
 Eine Funktionsdeklaration, auf die ein Semikolon folgt, wird möglicherweise an mehreren Stellen in einem Programm angezeigt. Sie muss vor dem Aufrufen dieser Funktion in jeder Übersetzungseinheit angezeigt werden. Die Funktionsdefinition darf gemäß der Regel mit einer Definition (One Definition Rule, ODR) nur einmal im Programm angezeigt werden.  
  
 Die erforderlichen Bestandteile einer Funktionsdeklaration lauten:  
  
1.  Der Rückgabetyp, der den Typ des Werts, den die Funktion zurückgibt, angibt, oder `void`, wenn kein Wert zurückgegeben wird. In C ++ 11 `auto` ist ein gültiger Rückgabetyp, die den Compiler anweist, den Typ aus der rückgabeanweisung abgeleitet werden. In C++14 ist „decltype(auto)“ ebenfalls zulässig. Weitere Informationen finden Sie unten unter „Typableitung in Rückgabetypen“.  
  
2.  Der Funktionsname, der mit einem Buchstaben oder Unterstrich beginnen muss, darf keine Leerzeichen enthalten. Im Allgemeinen weisen führende Unterstriche in Standardbibliothek-Funktionsnamen auf private Memberfunktionen oder Nicht-Memberfunktionen, die nicht für die Verwendung durch Ihren Code vorgesehen sind, hin. 
  
3.  Die Parameterliste, ein durch geschweifte Klammern getrennter, kommagetrennter Satz von mindestens null Parametern, die den Typ und optional einen lokalen Namen angeben, anhand dessen die Werte im Funktionsrumpf möglicherweise aufgerufen werden. 
  
 Optionale Bestandteile einer Funktionsdeklaration sind:  
  
1.  `constexpr`. Gibt an, dass es sich beim Rückgabewert der Funktion um einen konstanten Wert handelt, der zur Kompilierungszeit berechnet werden kann.  
  
    ```  
    constexpr float exp(float x, int n)  
    {  
        return n == 0 ? 1 :  
            n % 2 == 0 ? exp(x * x, n / 2) :  
            exp(x * x, (n - 1) / 2) * x;  
    };  
    ```  
  
2.  Es handelt sich um eine `linkage`-Spezifikation, `extern` oder `static`.  
  
    ```  
    Declare printf with C linkage.  
    extern "C" int printf( const char *fmt, ... );  
  
    ```  
  
     Weitere Informationen finden Sie unter [Programm und Verknüpfung](../cpp/program-and-linkage-cpp.md).  
  
3.  `inline`. Weist den Compiler an, jeden Funktionsaufruf durch den Funktionscode an sich zu ersetzen. Durch den Inlinevorgang kann die Leistung in Szenarien verbessert werden, in denen eine Funktion schnell ausgeführt und wiederholt in einem leistungskritischen Codeabschnitt aufgerufen wird.  
  
    ```  
    inline double Account::GetBalance()  
    {  
        return balance;  
    }  
    ```  
  
     Weitere Informationen finden Sie unter [Inlinefunktionen](../cpp/inline-functions-cpp.md).  
  
4.  Ein `noexcept` Ausdruck, der angibt, und zwar unabhängig davon, ob die Funktion eine Ausnahme auslösen kann. Im folgenden Beispiel löst die Funktion keine Ausnahme aus, wenn der Ausdruck `is_pod` als `true` ausgewertet wird.  
  
    ```  
    #include <type_traits>  
  
    template <typename T>  
    T copy_object(T& obj) noexcept(std::is_pod<T>) {...}  
    ```  
  
     Weitere Informationen finden Sie unter [Noexcept](../cpp/noexcept-cpp.md).  
  
5.  (nur Memberfunktionen) Die CV-Qualifizierer, die angeben, ob die Funktion `const` oder `volatile` ist.  
  
6.  (nur Memberfunktionen) `virtual`, `override` oder `final`. `virtual`. Gibt an, dass eine Funktion in einer abgeleiteten Klasse überschrieben werden kann. `override` bedeutet, dass eine Funktion in einer abgeleiteten Klasse eine virtuelle Funktion überschreibt. `final` bedeutet, dass eine Funktion in keiner weiteren abgeleiteten Klasse überschrieben werden kann. Weitere Informationen finden Sie unter [virtuelle Funktionen](../cpp/virtual-functions.md).  
  
7.  (nur Memberfunktionen) Wenn `static` auf eine Memberfunktion angewendet ist, bedeutet dies, dass die Funktion nicht mit Objektinstanzen der Klasse verknüpft ist.   
  
8.  (Gilt nur für nicht statische Memberfunktionen) Ref-Qualifizierer, der für den Compiler, welche Überladung einer Funktion angibt, um auszuwählen, wann der implizite Objektparameter (* dies) ein Rvalue-Verweis oder ein Lvalue-Verweis ist.  
  
 Die folgende Abbildung zeigt die Teile einer Funktionsdefinition. Der schattierte Bereich ist der Funktionsrumpf.  
  
 ![Teile einer Funktionsdefinition](../cpp/media/vc38ru1.gif "vc38RU1")  
Teile einer Funktionsdefinition  
  
## <a name="function-definitions"></a>Funktionsdefinitionen  
 Im Textteil deklarierte Variablen werden als lokale Variablen bezeichnet. Sie verlassen den Gültigkeitsbereich, wenn die Funktion beendet wird. Daher sollte eine Funktion niemals einen Verweis zu einer lokalen Variable zurückgeben!  
  
## <a name="function-templates"></a>Funktionsvorlagen  
 Eine Funktionsvorlage ähnelt einer Klassenvorlage. Sie generiert auf Grundlage der Vorlagenargumente konkrete Funktionen. In vielen Fällen kann die Vorlage die Typargumente ableiten. Daher ist es nicht erforderlich, sie explizit anzugeben.  
  
```  
template<typename Lhs, typename Rhs>  
auto Add2(const Lhs& lhs, const Rhs& rhs)  
{  
    return lhs + rhs;  
}  
  
auto a = Add2(3.13, 2.895); // a is a double  
auto b = Add2(string{ "Hello" }, string{ " World" }); // b is a std::string  
```  
  
 Weitere Informationen finden Sie unter [Funktionsvorlagen](../cpp/function-templates.md)  
  
## <a name="function-parameters-and-arguments"></a>Funktionsparameter und Argumente  
 Eine Funktion weist eine durch Kommas getrennte Liste von mindestens null Typen auf. Jede davon verfügt über einen Namen, unter dem es im Funktionsrumpf aufgerufen werden kann. Eine Funktionsvorlage kann den zusätzliche Typ- oder Wertparameter angeben. Der Aufrufer gibt Argumente weiter, bei denen es sich um konkrete Werte handelt, deren Typen mit der Parameterliste kompatibel sind.  
  
 Argumente werden standardmäßig zur Funktion nach Wert weitergegeben. Die Funktion empfängt demnach eine Kopie des weiterzugebenden Objekts. Für große Objekte kann das Erstellen einer Kopie aufwändig und nicht immer erforderlich sein. Fügen Sie dem Parameter einen Verweisqualifizierer hinzu, damit Argumente nach Verweis (insbesondere lvalue-Verweis) weitergegeben werden:  
  
```  
void DoSomething(std::string& input){...}  
```  
  
 Wenn eine Funktion ein Argument ändert, das nach Verweis weitergegeben wird, ändert sie das ursprüngliche Objekt und nicht eine lokale Kopie. Qualifizieren Sie den Parameter als „const&“, um zu verhindern, dass eine Funktion ein derartiges Argument ändert:  
  
```  
void DoSomething(const std::string& input){...}  
```  
  
 **C++ 11:** verwenden Sie zum expliziten Verarbeiten von Argumenten, die nach Rvalue-Verweis oder nach Lvalue-Verweis übergeben werden, ein doppeltes kaufmännisches und-Zeichen im Parameter um einen universellen Verweis anzugeben:  
  
```  
void DoSomething(const std::string&& input){...}  
```  
  
 Eine Funktion, die mit dem einzelnen Schlüsselwort `void` in der Parameterdeklarationsliste deklariert wird, akzeptiert keine Argumente, solange das Schlüsselwort `void` der erste und einzige Member der Argumentdeklarationsliste ist. Argumente des Typs `void` an anderer Stelle in der Liste erzeugen Fehler. Zum Beispiel:  
  
```  
  
// OK same as GetTickCount()  
long GetTickCount( void );   
```  
  
 Es ist zwar nicht zulässig, ein `void` Argument außer wie hier erläutert anzugeben. Aber Typen, die vom `void`-Typ abgeleitet werden (z. B. Zeiger auf `void` und Arrays von `void`), können an beliebiger Stelle in der Argumentdeklarationsliste vorkommen.  
  
### <a name="default-arguments"></a>Standardargumente  
 Der oder die letzten Parameter in einer Funktionssignatur werden möglicherweise einem Standardargument zugewiesen. Der Aufrufer kann demnach das Argument auslassen, wenn die Funktion aufgerufen wird, es sei denn, es soll ein anderer Wert angegeben werden.  
  
```  
int DoSomething(int num,   
    string str,   
    Allocator& alloc = defaultAllocator)  
{ ... }  
  
// OK both parameters are at end  
int DoSomethingElse(int num,   
    string str = string{ "Working" },   
    Allocator& alloc = defaultAllocator)  
{ ... }  
  
// C2548: 'DoMore': missing default parameter for parameter 2  
int DoMore(int num = 5, // Not a trailing parameter!  
    string str,  
    Allocator& = defaultAllocator)  
{...}  
```  
  
 Weitere Informationen finden Sie unter [Standardargumente](../cpp/default-arguments.md).  
  
## <a name="function-return-types"></a>Funktionsrückgabetypen  
 Eine Funktion kann nicht einer anderen Funktion oder ein integriertes Array zurückgeben; jedoch Zeiger auf diese Typen zurückgegeben werden kann oder ein *Lambda*, der ein Funktionsobjekt generiert. Mit Ausnahme dieser Fälle gibt eine Funktion möglicherweise einen Wert eines beliebigen Typs zurück, der sich im Bereich befindet, oder sie gibt keinen Wert zurück. In diesem Fall lautet der Rückgabetyp `void`.  
  
### <a name="trailing-return-types"></a>Nachstehende Rückgabetypen  
 Ein „gewöhnlicher“ Rückgabetyp befindet sich auf der linken Seite der Funktionssignatur. Ein *nachstehendem Rückgabetyp* befindet sich rechts von der Signatur und vorangestellt ist der Operator ->. Nachstehende Rückgabetypen sind insbesondere in Funktionsvorlagen nützlich, wenn der Typ des Rückgabewerts auf Vorlagenparametern beruht.  
  
```  
template<typename Lhs, typename Rhs>  
auto Add(const Lhs& lhs, const Rhs& rhs) -> decltype(lhs + rhs)  
{  
    return lhs + rhs;   
}  
```  
  
 Wenn `auto` zusammen mit einem nachstehenden Rückgabetyp verwendet wird, fungiert es als ein Platzhalter für das, was der decltype-Ausdruck generiert, und es führt keine eigene Typableitung aus.  

   
## <a name="function-local-variables"></a>Lokale Funktionsvariablen  
 Eine in einem Funktionsrumpf deklarierte Variable wird aufgerufen, eine *lokale Variable* oder einfach als *lokale*. Nicht statische lokale Variablen sind nur innerhalb des Funktionsrumpfs sichtbar, wenn sie auf dem Stapel deklariert werden, wenn den Bereich verlässt, wenn die Funktion vorhanden ist. Wenn Sie eine lokale Variable erstellen und nach Wert zurückgeben, kann der Compiler für gewöhnlich die Rückgabewertoptimierung vornehmen, um nicht erforderliche Kopiervorgänge zu vermeiden. Wenn Sie eine lokale Variable nach Verweis zurückgeben, stellt eine Compiler eine Warnung aus, da jeder Versuch durch den Aufrufer, diesen Verweis zu verwenden, erst nach der Zerstörung der lokalen Variablen auftritt.  
  
 Lokale statische Objekte werden während der Beendigung zerstört, die von `atexit` angegeben wird. Wenn kein statisches Objekt erstellt wurde, da die Ablaufsteuerung des Programms seine Deklaration umgangen ist, wird nicht versucht, das Objekt zu zerstören.  
  
### <a name="static-local-variables"></a>Statische lokale Variablen  
 In C++ kann eine lokale Variable als statisch deklariert werden. Die Variable ist nur innerhalb des Funktionsrumpfs sichtbar. Es ist jedoch eine einzelne Kopie der Variable für alle Instanzen der Funktion vorhanden.  
  
###  <a name="type_deduction"></a>Typableitung in Rückgabetypen (C ++ 14)  
 In C++14 können Sie `auto` verwenden, um den Compiler anzuweisen, den Rückgabetyp aus dem Funktionsrumpf abzuleiten, ohne einen nachstehenden Rückgabetyp anzugeben. Beachten Sie, dass `auto` immer eine Rückgabe per Wert ableitet. Verwenden Sie `auto&&` um den Compiler anzuweisen, einen Verweis abzuleiten.  
  
 In diesem Beispiel wird `auto` als eine nicht konstante Wertkopie der Summe von lhs und rhs abgeleitet.  
  
```  
template<typename Lhs, typename Rhs>  
auto Add2(const Lhs& lhs, const Rhs& rhs)  
{  
    return lhs + rhs; //returns a non-const object by value  
}  
```  
  
 Beachten Sie, dass `auto` nicht die Konstanz der abzuleitenden beibehalten. Bei Weiterleitungsfunktionen, deren Rückgabetyp die Konstanz oder Verweisbarkeit der entsprechenden Argumente beibehalten muss, können Sie das Schlüsselwort `decltype(auto)` verwenden. Dieses verwendet die `decltype`-Typrückschlussregeln und behält alle Typinformationen bei. `decltype(auto)` kann als ein gewöhnlicher Rückgabewert auf der linken Seite oder als ein nachstehender Rückgabewert verwendet werden.  
  
 Im folgenden Beispiel wird (basierend auf Code aus [N3493](http://www.open-std.org/JTC1/SC22/WG21/docs/papers/2013/n3493.html)), zeigt `decltype(auto)` verwendet wird, um die perfekten Weiterleitung von Funktionsargumenten in einem Rückgabetyp zu ermöglichen, bevor die Vorlage instanziiert wird.  
  
```  
template<typename F, typename Tuple = tuple<T...>, int... I>  
decltype(auto) apply_(F&& f, Tuple&& args, index_sequence<I...>)   
{  
    return std::forward<F>(f)(std::get<I>(std::forward<Tuple>(args))...);  
}  
  
template<typename F, typename Tuple = tuple<T...>,  
    typename Indices = make_index_sequence<tuple_size<Tuple>::value >>  
   decltype( auto)  
    apply(F&& f, Tuple&& args)      
{  
    return apply_(std::forward<F>(f), std::forward<Tuple>(args), Indices());  
}  
}  
```  
## <a name="returning-multiple-values-from-a-function"></a>Zurückgeben von mehreren Werten aus einer Funktion
Es gibt verschiedene Möglichkeiten, das mehr als einen Wert aus einer Funktion zurückgegeben:

1. Die Werte in ein benanntes Objekt der Klasse oder Struktur gekapselt werden. Erfordert die Definition Klasse oder Struktur an den Aufrufer sichtbar sein sollen:

```cpp
#include <string>
#include <iostream>

using namespace std;

struct S
{
    string name;
    int num;
};

S g()
{
    string t{ "hello" };
    int u{ 42 };
    return { t, u };
}

int main()
{
    S s = g();
    cout << s.name << " " << s.num << endl;
    return 0;
}
```

2. Geben Sie ein Std:: Tuple oder Std:: Pair-Objekt zurück:

```cpp
#include <tuple>
#include <string>
#include <iostream>

using namespace std;


tuple<int, string, double> f()
{
    int i{ 108 };
    string s{ "Some text" };
    double d{ .01 };
    return { i,s,d };
}

int main()
{
    auto t = f();
    cout << get<0>(t) << " " << get<1>(t) << " " << get<2>(t) << endl;
    
    // --or--

    int myval;
    string myname;
    double mydecimal;
    tie(myval, myname, mydecimal) = f();
    cout << myval << " " << myname << " " << mydecimal << endl;

    return 0;
}
```

3. **Visual Studio 2017 15,3 und höher** (verfügbar mit [/std:c ++ 17](../build/reference/std-specify-language-standard-version.md)): Verwenden Sie die strukturierte Bindungen. Der Vorteil der strukturierten Bindungen ist, dass die Variablen, die die Rückgabewerte speichern initialisiert werden zur gleichen Zeit, in die sie deklariert werden, die was in einigen Fällen kann deutlich effizienter sein. In dieser Anweisung--`auto[x, y, z] = f();`--die Klammern einführen und initialisieren Sie Namen, die im Bereich für die gesamte Funktionsblock befinden.  

```cpp
#include <tuple>
#include <string>
#include <iostream>

using namespace std;

tuple<int, string, double> f()
{
    int i{ 108 };
    string s{ "Some text" };
    double d{ .01 };
    return { i,s,d };
}
struct S
{
    string name;
    int num;
};

S g()
{
    string t{ "hello" };
    int u{ 42 };
    return { t, u };
}

int main()
{
    auto[x, y, z] = f(); // init from tuple
    cout << x << " " << y << " " << z << endl;

    auto[a, b] = g(); // init from POD struct
    cout << a << " " << b << endl;
    return 0;
}
```

4. Zusätzlich zur Verwendung des Rückgabewert selbst, können Sie "return" Werte definieren Sie eine beliebige Anzahl von Parametern zum Übergeben als Verweis verwendet werden, damit die Funktion zu ändern, oder initialisieren die Werte der Objekte, die der Aufrufer enthält. Weitere Informationen finden Sie unter [Verweistyp Funktionsargumente](reference-type-function-arguments.md).
  
## <a name="function-pointers"></a>Funktionszeiger  
 C++ unterstützt Funktionszeiger auf die gleiche Weise wie die C-Sprache. Eine typsichere Alternative besteht jedoch darin, ein Funktionsobjekt zu verwenden.  
  
 Es wird empfohlen, dass `typedef` verwendet wird, um einen Alias für den Funktionszeigertyp zu deklarieren, wenn eine Funktion deklariert wird, die einen Funktionszeigertyp zurückgibt.  Beispiel:  
  
```  
typedef int (*fp)(int);  
fp myFunction(char* s); // function returning function pointer  
```  
  
 Wenn dies nicht erfolgt, kann die korrekte Syntax für die Funktionsdeklaration aus der Deklaratorsyntax für den Funktionszeiger abgeleitet werden, und zwar wie folgt durch Ersetzen des Bezeichners (`fp` im obigen Beispiel) durch den Namen und die Argumentliste der Funktion:  
  
```  
int (*myFunction(char* s))(int);  
```  
  
 Die vorhergehende Deklaration gleicht der Deklaration oben, die "typedef" verwendet.  
  
## <a name="see-also"></a>Siehe auch  
 [Funktionsüberladung](../cpp/function-overloading.md)   
 [Funktionen mit Argumentlisten variabler Länge](../cpp/functions-with-variable-argument-lists-cpp.md)   
 [Explizit vorgegebene und gelöschte Funktionen](../cpp/explicitly-defaulted-and-deleted-functions.md)   
 [Argumentbezogene Namenssuche (Koenig) Lookup für Funktionen](../cpp/argument-dependent-name-koenig-lookup-on-functions.md)   
 [Standardargumente](../cpp/default-arguments.md)   
 [Inlinefunktionen](../cpp/inline-functions-cpp.md)
