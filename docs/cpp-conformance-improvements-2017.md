---
title: "C++-Konformitätsverbesserungen | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8801dbdb-ca0b-491f-9e33-01618bff5ae9
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 45f22597944084ecd2d30fe29bf4e8ab3ef80201
ms.sourcegitcommit: 30ab99c775d99371ed22d1a46598e542012ed8c6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2018
---
# <a name="c-conformance-improvements-in-visual-studio-2017-versions-150-153improvements153-and-155improvements155"></a>C++-Konformitätsverbesserungen in Visual Studio 2017, Versionen 15.0, [15.3](#improvements_153) und [15.5](#improvements_155)

Der Microsoft Visual C++-Compiler ist jetzt vollständig mit Unterstützung für generalisierte contextpr und NSDMI für Aggregate für Funktionen, die im C++14-Standard hinzugefügt wurden. Beachten Sie, dass dem Compiler noch einige Funktionen der C++11- und C++98-Standards fehlen. Eine Tabelle mit dem aktuellen Compilerstatus finden Sie unter [Visual C++-Sprachkonformität](visual-cpp-language-conformance.md).

## <a name="c11"></a>C++11

**Unterstützung für SFINAE für Ausdrücke in mehr Bibliotheken**  
Der Visual C++-Compiler verbessert weiterhin die Unterstützung der SFINAE für Ausdrücke, die für die Vorlagenargumentableitung und -ersetzung erforderlich ist, wobei die Ausdrücke „decltype“ und „constexpr“ möglicherweise als Vorlagenparameter angezeigt werden. Weitere Informationen finden Sie unter [Expression SFINAE improvements in Visual Studio 2017 RC (Verbesserungen der SFINAE für Ausdrücke in Visual Studio 2017)](https://blogs.msdn.microsoft.com/vcblog/2016/06/07/expression-sfinae-improvements-in-vs-2015-update-3).

## <a name="c-14"></a>C++ 14

**NSDMI für Aggregate**  
Ein Aggregat ist ein Array oder eine Klasse ohne einen vom Benutzer bereitgestellten Konstruktor, ohne privaten oder geschützten nicht statische Datenmember, ohne Basisklassen und ohne virtuelle Funktionen. Ab C++ 14 können Aggregate Memberinitialisierer enthalten. Weitere Informationen finden Sie unter [Member initializers and aggregates (Memberinitialisierer und Aggregate)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3605.html).

**Erweiterte constexpr**  
Ausdrücke, die als „constexpr“ deklariert sind, dürfen jetzt bestimmte Arten von Deklarationen, if- und switch-Anweisungen, Schleifenanweisungen und Mutationen der Objekte enthalten, deren Lebensdauer in der Auswertung von constexpr-Ausdrücken begonnen hat. Darüber hinaus ist es nicht mehr erforderlich, dass eine nicht statische Memberfunktion von constexpr implizit const ist. Weitere Informationen finden Sie unter [Relaxing constraints on constexpr functions (Lockerung der Einschränkungen auf constexpr-Funktionen)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3652.html).

## <a name="c17"></a>C++17

**Knappes static-assert** (verfügbar mit **/std:c++17**)  
In C++17 ist der Meldungsparameter für static_assert optional. Weitere Informationen finden Sie unter [Extending static_assert, v2 (Erweitern des static_assert, v2)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3928.pdf).

**[[fallthrough]] attribute** (verfügbar mit **/std:c++17**)  
Das [[fallthrough]]-Attribut kann im Kontext von switch-Anweisungen als Hinweis für den Compiler verwendet werden, dass das Fall-Through-Verhalten vorgesehen ist. Dadurch wird verhindert, dass der Compiler in solchen Fällen Warnungen ausgeben kann. Weitere Informationen finden Sie unter [Wording for [[fallthrough]] attribute (Worlaut für [[fallthrough]]-Attribut)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0188r0.pdf).

**Allgemeine bereichsbezogene for-Schleifen** (kein Compilerparameter erforderlich)  
Bereichsbezogene for-Schleifen erfordern nicht mehr, dass „begin()“ und „end()“ Objekte des gleichen Typs zurückgeben. Dies ermöglicht end() die Rückgabe eines Sentinels wie von Bereichen in [range-v3](https://github.com/ericniebler/range-v3) verwendet und die Einhaltung der abgeschlossenen, jedoch noch nicht ganz veröffentlichten technische Spezifikation zu Bereichen. Weitere Informationen finden Sie unter [Generalizing the Range-Based For Loop (Generalisieren einer bereichsbasierten for-Schleife)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0184r0.html).

## <a name="improvements_153"></a> Verbesserungen in Visual Studio 2017 Version 15.3

**constexpr-Lambdas**  
Lambdaausdrücke können jetzt in konstanten Ausdrücken verwendet werden. Weitere Informationen finden Sie unter [Constexpr Lambda](http://open-std.org/JTC1/SC22/WG21/docs/papers/2015/n4487.pdf).

**„if constexpr“ in Funktionsvorlagen**  
Eine Funktionsvorlage kann `if constexpr`-Anweisungen zum Branchen zur Kompilierzeit enthalten. Weitere Informationen finden Sie unter [if constexpr](http://open-std.org/JTC1/SC22/WG21/docs/papers/2016/p0128r1.html).

**Auswahlanweisungen mit Initialisierern**  
Eine `if`-Anweisung kann einen Initialisierer enthalten, der im Blockbereich innerhalb der Anweisung selbst eine Variable einführt. Weitere Informationen finden Sie unter [Selection statements with initializer](http://www.open-std.org/JTC1/SC22/WG21/docs/papers/2016/p0305r1.html) (Auswahlanweisungen mit Initialisierer).

**Die Attribute [[maybe_unused]] und [[nodiscard]]**  
Neue Attribute zum Unterdrücken von Warnungen, wenn eine Entität nicht verwendet wird, oder zum Erstellen einer Warnung, wenn der Rückgabewert eines Funktionsaufrufs verworfen wird. Weitere Informationen finden Sie unter [Wording for maybe_unused attribute](http://open-std.org/JTC1/SC22/WG21/docs/papers/2016/p0212r0.pdf) (Formulierungen für maybe_unused-Attribut) und [Proposal of unused, nodiscard and fallthrough attributes](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0068r0.pdf) (Vorschlag der Attribute „unused“, „nodiscard“ und „fallthrough“).

**Verwenden von Attributnamespaces ohne Wiederholung**  
Neue Syntax, um nur einen einzigen Namespacebezeichner in einer Attributliste zu erlauben. Weitere Informationen finden Sie unter [Attribute in C++](cpp/attributes2.md).

**Strukturierte Bindungen**  
Es ist jetzt möglich, einen Wert mit individuellen Namen für die verschiedenen Komponenten in einer einzigen Anweisung zu speichern. Dies gilt, wenn der Wert ein Array, „std::tuple“ oder „std::pair“ ist oder nur öffentliche, nicht statische Datenmembers enthält. Weitere Informationen finden Sie unter [Structured Bindings](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0144r0.pdf) (Strukturierte Bindungen).

**Erstellungsregeln für enum-Klassenwerte**  
Es gibt jetzt eine implizite/nicht einschränkende Umwandlung des zugrunde liegenden Typs einer bereichsbezogenen Enumeration in die Enumeration selbst, wenn deren Definition keinen Enumerator einführt und die Quelle eine list-initialization-Syntax verwendet. Weitere Informationen finden Sie unter [Construction Rules for enum class Values ](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0138r2.pdf) (Erstellungsregeln für enum-Klassenwerte).

**Erfassen von „*this“ anhand des Werts**  
Das `*this`-Objekt in einem Lambdaausdruck kann jetzt anhand des Werts erfasst werden. Das ermöglicht Szenarios in denen der Lambdaausdruck in parallelen und asynchronen Vorgängen aufgerufen wird, insbesondere in neueren Computerarchitekturen. Weitere Informationen finden Sie unter [Lambda Capture of \*this by Value as [=,\*this]](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0018r3.html) (Lambdaerfassung von „*this“ anhand des Werts als [=,*this]).

**Entfernen von „operator++“ für „bool“**  
`operator++` wird nicht mehr in `bool`-Typen unterstützt. Weitere Informationen finden Sie unter [Remove Deprecated operator++(bool)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0002r1.html) (Veralteten „operator++(bool)“ entfernen).

**Entfernen des veralteten Schlüsselworts „register“**  
Das Schlüsselwort `register`, das als veraltet gekennzeichnet wurde (und vom Visual C++-Compiler ignoriert wurde), wurde jetzt aus der Sprache entfernt. Weitere Informationen finden Sie unter [Remove Deprecated Use of the register Keyword](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0001r1.html) (Entfernen der Verwendung des veralteten register-Schlüsselworts).

Eine vollständige Liste der Konformitätsverbesserungen bis zum Visual Studio 2015 Update 3 finden Sie unter [Visual C++ What's New 2003 through 2015 (Visual C++ – Neues von 2003 bis 2015)](https://msdn.microsoft.com/en-us/library/mt723604.aspx).

## <a name="improvements_155"></a> Verbesserungen in Visual Studio 2017 Version 15.5

Features, die mit [14] markiert sind, stehen bedingungslos auch im /std:c++14-Modus zur Verfügung.

**Neuer Compilerparameter für externe constexpr**  
In früheren Versionen von Visual Studio hat der Compiler immer eine interne `constexpr`-Variablenverknüpfung ausgegeben, selbst wenn die Variable als `extern` markiert wurde. In Visual Studio 2017 Version 15.5 ermöglicht ein neuer Compilerschalter [/Zc:externConstexpr](build/reference/zc-externconstexpr.md) das richtige standardkonforme Verhalten. Weitere Informationen finden Sie unter [Externe constexpr-Verknüpfung](#extern_linkage).

**Entfernen dynamischer Ausnahmespezifikationen**  
[P0003R5](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0003r5.html) Dynamische Ausnahmespezifikationen sind in C++11 veraltet. Das Feature wird aus C ++ 17 entfernt, aber die (immer noch) veraltete `throw()`-Spezifikation wird strikt als Alias für `noexcept(true)` beibehalten. Weitere Informationen dazu finden Sie unter [Entfernen der dynamischen Ausnahmespezifikation und noexcept](#noexcept_removal). 

**not_fn()**  
[P0005R4](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0005r4.html) `not_fn` ersetzt `not1` und `not2`.

**Umformulieren von „enable_shared_from_this“**  
[P0033R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0033r1.html) `enable_shared_from_this` wurde in C++11 hinzugefügt. Der C++17-Standard aktualisiert die Spezifikation, um bestimmte Ausnahmefälle besser zu verarbeiten. [14]

**Anwenden von Splice-Vorgängen auf Zuordnungen und Sätze**  
[P0083R3](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0083r3.pdf) Dieses Feature ermöglicht das Extrahieren von Knoten aus assoziativen Containern (z.B. map, set, unordered\_map, unordered\_set), die dann geändert und wieder in den gleichen Container oder einen anderen Container eingefügt werden können, der den gleichen Knotentyp verwendet. (Ein häufiger Anwendungsfall besteht darin, einen Knoten aus einer `std::map` zu extrahieren, den Schlüssel zu ändern und ihn dann erneut einzufügen.)

**Veraltete rudimentäre Bibliotheksteile**  
[P0174R2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0174r2.html) Einige Features der C++ Standardbibliothek wurden im Laufe der Jahre durch neuere Features ersetzt, oder es hat sich herausgestellt, dass sie nicht sehr nützlich oder sogar problematisch sind. Diese Funktionen werden sind in C++17 offiziell als veraltet eingestuft. 

**Entfernen der Unterstützung für Zuweisung in std::function**  
[P0302R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0302r1.html) Vor C++17 besaß die Klassenvorlage `std::function` mehrere Konstruktoren, die ein Zuweisungsargument angenommen haben. Allerdings war die Verwendung von Zuweisungen in diesem Kontext problematisch, und die Semantik war unklar. Aus diesem Grund wurden diese Konstruktoren entfernt.

**Korrekturen für not_fn()**  
[P0358R1](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0358r1.html) Neue Formulierungen für `std::not_fn` bieten Unterstützung für die Weitergabe der Wertkategorie bei einem Wrapperaufruf.

**shared_ptr\<T[]>, shared_ptr\<T[N]>**  
[P0414R2](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0414r2.html) Zusammenführen von `shared_ptr`-Änderungen aus Library Fundamentals in C++17. [14]

**Korrektur von „shared_ptr“ für Arrays**  
[P0497R0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0497r0.html) Korrekturen an der shared_ptr-Unterstützung für Arrays. [14]

**Erklärung zu „insert_return_type“**  
[P0508R0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0508r0.html) Die assoziativen Container mit eindeutigen Schlüsseln und die ungeordneten Container mit eindeutigen Schlüsseln besitzen die Memberfunktion `insert`, die einen geschachtelten `insert_return_type`-Typ zurückgibt. Dieser Rückgabetyp ist nun als Spezialisierung eines Typs definiert, der für den Iterator und NodeType des Containers parametrisiert ist.

**Inlinevariablen für die Standardvorlagenbibliothek**  
[P0607R0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0607r0.html)

**Features aus Anhang D als veraltet markiert**  
Anhang D des C++-Standards enthält alle Features, die veraltet sind. Dazu gehören auch `shared_ptr::unique()`, `<codecvt>` und `namespace std::tr1`. Wenn der Compilerparameter **/std:c++17** festgelegt wird, werden fast alle Features der Standardbibliothek in Anhang D als veraltet markiert. Weitere Informationen finden Sie unter [Features der Standardbibliothek in Anhang D sind als veraltet markiert](#annex_d).

Der `std::tr2::sys`-Namespace in `<experimental/filesystem>` gibt jetzt standardmäßig eine Warnung zu veralteten Features unter „/std:c++14“ aus und wird jetzt unter **/std:c++17** standardmäßig entfernt.

Verbesserte Konformität in iostreams durch Vermeidung einer nicht standardmäßigen Erweiterung (explizite Spezialisierungen in der Klasse).

Die Standardbibliothek verwendet jetzt intern Variablenvorlagen.

Die Standardbibliothek wurde als Reaktion auf C++17-Compileränderungen aktualisiert, einschließlich der Hinzufügung von noexcept im Typsystem und der Entfernung von dynamic-exception-Spezifikationen.

## <a name="bug-fixes-in-visual-studio-versions-150-153update153-and-155update155"></a>Fehlerbehebungen in Visual Studio, Versionen 15.0, [15.3](#update_153) und [15.5](#update_155)

### <a name="copy-list-initialization"></a>copy-list-Initialisierung

Visual Studio 2017 löst ordnungsgemäß Compilerfehler im Zusammenhang mit der Erstellung von Objekten mithilfe von Initialisiererlisten aus, die nicht in Visual Studio 2015 abgefangen wurden und die zu Abstürzen oder einem nicht definierten Laufzeitverhalten führen können. Laut N4594 13.3.1.7p1 in der copy-list-Initialisierung, muss der Compiler einen expliziten Konstruktor für die Überladungsauflösung berücksichtigen, aber er muss einen Fehler auslösen, wenn diese Überladung tatsächlich ausgewählt wird.

Die folgenden beiden Beispiele kompilieren in Visual Studio 2015, aber nicht in Visual Studio 2017.

```cpp
struct A
{
    explicit A(int) {}
    A(double) {}
};

int main()
{
    A a1 = { 1 }; // error C3445: copy-list-initialization of 'A' cannot use an explicit constructor
    const A& a2 = { 1 }; // error C2440: 'initializing': cannot convert from 'int' to 'const A &'

}
```

Verwenden Sie direkte Initialisierung, um den Fehler zu korrigieren:

```cpp
A a1{ 1 };
const A& a2{ 1 };
```

In Visual Studio 2015 behandelt der Compiler fälschlicherweise eine copy-list-Initialisierung auf die gleiche Weise wie eine Kopierinitialisierung. Er konvertiert nur die Konstruktoren für die Überladungsauflösung. Im folgenden Beispiel wählt Visual Studio 2015 MyInt(23), aber Visual Studio 2017 löst den Fehler ordnungsgemäß aus.

```cpp
// From http://www.open-std.org/jtc1/sc22/wg21/docs/cwg_closed.html#1228
struct MyStore {
    explicit MyStore(int initialCapacity);
};

struct MyInt {
    MyInt(int i);
};

struct Printer {
    void operator()(MyStore const& s);
    void operator()(MyInt const& i);
};

void f() {
    Printer p;
    p({ 23 }); // C3066: there are multiple ways that an object of this type can be called with these arguments
}
```

Dieses Beispiel ähnelt dem vorherigen Beispiel, löst jedoch einen anderen Fehler aus. Es ist in Visual Studio 2015 erfolgreich, und in Visual Studio 2017 mit C2668 schlägt es fehl.

```cpp
struct A {
    explicit A(int) {}
};

struct B {
    B(int) {}
};

void f(const A&) {}
void f(const B&) {}

int main()
{
    f({ 1 }); // error C2668: 'f': ambiguous call to overloaded function
}
```

### <a name="deprecated-typedefs"></a>Veraltete TypeDefs

Visual Studio 2017 gibt jetzt die richtige Warnung für veraltete TypeDefs aus, die in einer Klasse oder Struktur deklariert werden. Das folgende Beispiel wird ohne Warnung in Visual Studio 2015 kompiliert, erstellt jedoch C4996 in Visual Studio 2017.

```cpp
struct A
{
    // also for __declspec(deprecated)
    [[deprecated]] typedef int inttype;
};

int main()
{
    A::inttype a = 0; // C4996 'A::inttype': was declared deprecated
}
```

### <a name="constexpr"></a>constexpr

Visual Studio 2017 löst ordnungsgemäß einen Fehler aus, wenn der linke Operand eines bedingten Auswertungsvorgangs in einem constexpr-Kontext ungültig ist. Der folgende Code kompiliert in Visual Studio 2015, jedoch nicht in Visual Studio 2017 (C3615: Die constexpr-Funktion „f“ darf keinen konstanten Ausdruck ergeben):

```cpp
template<int N>
struct array
{
    int size() const { return N; }
};

constexpr bool f(const array<1> &arr)
{
    return arr.size() == 10 || arr.size() == 11; // C3615
}
```
Deklarieren Sie die Funktion `array::size()` als `constexpr`, oder entfernen Sie den Qualifizierer `constexpr` aus `f`, um den Fehler zu beheben.

### <a name="class-types-passed-to-variadic-functions"></a>Klassentypen, die an variadic-Funktionen übergeben werden

In Visual Studio 2017 müssen Klassen oder Strukturen, die an eine variadic-Funktion wie printf übergeben werden, einfach kopierbar sein. Wenn solche Objekte übergeben werden, macht der Compiler einfach eine bitweise Kopie und ruft keinen Konstruktor oder Destruktor auf.

```cpp
#include <atomic>
#include <memory>
#include <stdio.h>

int main()
{
    std::atomic<int> i(0);
    printf("%i\n", i); // error C4839: non-standard use of class 'std::atomic<int>'
                        // as an argument to a variadic function.
                        // note: the constructor and destructor will not be called;
                        // a bitwise copy of the class will be passed as the argument
                        // error C2280: 'std::atomic<int>::atomic(const std::atomic<int> &)':
                        // attempting to reference a deleted function

    struct S {
        S(int i) : i(i) {}
        S(const S& other) : i(other.i) {}
        operator int() { return i; }
    private:
        int i;
    } s(0);
    printf("%i\n", s); // warning C4840 : non-portable use of class 'main::S'
                      // as an argument to a variadic function
}
```

Sie können eine Memberfunktion aufrufen, die einen einfachen kopierbaren Typ zurückgibt, um den Fehler zu beheben, 

```cpp
    std::atomic<int> i(0);
    printf("%i\n", i.load());
```

oder Sie führen eine statische Umwandlung aus, um das Objekt zu konvertieren, bevor es übergeben wird:

```cpp
    struct S {/* as before */} s(0);
    printf("%i\n", static_cast<int>(s))
```

Für mit CStringW erstellte und verwaltete Zeichenfolgen sollte der bereitgestellte `operator LPCWSTR()` verwendet werden, um ein CStringW-Objekt in einen C-Zeiger umzuwandeln, der von der Formatzeichenfolge erwartet wird.

```cpp
CStringW str1;
CStringW str2;
str1.Format(L"%s", static_cast<LPCWSTR>(str2));
```

### <a name="cv-qualifiers-in-class-construction"></a>CV-Qualifizierer in der Klassenkonstruktion

In Visual Studio 2015 ignoriert der Compiler beim Generieren eines Klassenobjekts über einen Konstruktoraufruf manchmal fälschlicherweise die CV-Qualifizierer. Dies kann potenziell zu einem Absturz oder zu unerwartetem Laufzeitverhalten führen. Das folgende Beispiel kompiliert in Visual Studio 2015, aber löst einen Compilerfehler in Visual Studio 2017 aus:

```cpp
struct S
{
    S(int);
    operator int();
};

int i = (const S)0; // error C2440
```

Deklarieren Sie `operator int()` als `const`, um den Fehler zu beheben.

### <a name="access-checking-on-qualified-names-in-templates"></a>Zugriff auf qualifizierte Namen in Vorlagen überprüfen

Frühere Versionen des Compilers haben den Zugriff auf qualifizierte Namen in bestimmten Kontexten von Vorlagen nicht überprüft. Das erwartete SFINAE-Verhalten kann behindert werden, in dem die Ersetzung aufgrund der Nichterreichbarkeit des Namens erwartungsgemäß fehlschlägt. Dies kann potenziell einen Absturz oder unerwartetes Verhalten zur Laufzeit auslösen, da der Compiler fälschlicherweise die falsche Überladung des Operators aufgerufen hat. In Visual Studio 2017 wird ein Compilerfehler ausgelöst. Der Fehlercode kann variieren, aber normalerweise ist es „C2672 keine entsprechende überladene Funktion gefunden“. Der folgende Code kompiliert in Visual Studio 2015, aber löst in Visual Studio 2017 einen Fehler aus:

```cpp
#include <type_traits>

template <class T> class S {
    typedef typename T type;
};

template <class T, std::enable_if<std::is_integral<typename S<T>::type>::value, T> * = 0>
bool f(T x);

int main()
{
    f(10); // C2672: No matching overloaded function found.
}
```

### <a name="missing-template-argument-lists"></a>Fehlende Vorlagenargumentlisten

In Visual Studio 2015 und früheren Versionen diagnostizierte der Compiler keine fehlenden Vorlagenargumentlisten, wenn die Vorlage in einer Vorlagenparameterliste (z.B. als Teil eines Standardvorlagenarguments oder Nichttyp-Vorlagenparameter) angezeigt wurde. Dies kann zu unvorhersehbarem Verhalten führen, einschließlich des Absturzes des Compilers oder unerwartetem Laufzeitverhalten. Der folgende Code kompiliert in Visual Studio 2015, aber erzeugt in Visual Studio 2017 einen Fehler.

```cpp
template <class T> class ListNode;
template <class T> using ListNodeMember = ListNode<T> T::*;
template <class T, ListNodeMember M> class ListHead; // C2955: 'ListNodeMember': use of alias 
                                                     // template requires template argument list

// correct:  template <class T, ListNodeMember<T> M> class ListHead;
```

### <a name="expression-sfinae"></a>SFINAE für Ausdrücke

Um SFINAE für Ausdrücke zu unterstützen, analysiert der Compiler jetzt decltype-Argumente, wenn die Vorlagen deklariert, aber nicht instanziiert sind. Wenn eine unabhängige Spezialisierung im decltype-Argument gefunden wird, wird sie nicht zum Zeitpunkt der Instanziierung zurückgestellt. Sie wird sofort verarbeitet, und alle resultierenden Fehler werden zu diesem Zeitpunkt untersucht.

Das folgende Beispiel zeigt einen solchen Compilerfehler, der zum Zeitpunkt der Deklaration ausgelöst wird:

```cpp
#include <utility>
template <class T, class ReturnT, class... ArgsT>
class IsCallable
{
public:
    struct BadType {};

    template <class U>
    static decltype(std::declval<T>()(std::declval<ArgsT>()...)) Test(int); //C2064. Should be declval<U>

    template <class U>
    static BadType Test(...);

    static constexpr bool value = std::is_convertible<decltype(Test<T>(0)), ReturnT>::value;
};

constexpr bool test1 = IsCallable<int(), int>::value;
static_assert(test1, "PASS1");
constexpr bool test2 = !IsCallable<int*, int>::value;
static_assert(test2, "PASS2");
```

### <a name="classes-declared-in-anonymous-namespaces"></a>In anonymen Namespaces deklarierte Klassen

Entsprechend dem C++-Standard verfügt eine Klasse, die innerhalb eines anonymen Namespace deklariert wird, über interne Verknüpfungen und kann daher nicht exportiert werden. In Visual Studio 2015 und früheren Versionen wurde diese Regel nicht durchgesetzt. In Visual Studio 2017 wird die Regel teilweise durchgesetzt. Das folgende Beispiel löst in Visual Studio 2017 diesen Fehler aus: Fehler C2201: "const anonymous namespace::S1::vftable:" Externe Bindung erforderlich, um Export/Import zu ermöglichen.

```cpp
struct __declspec(dllexport) S1 { virtual void f() {} }; //C2201
```

### <a name="default-initializers-for-value-class-members-ccli"></a>Standardinitialisierer für Wertklassenmember (C++/CLI)

In Visual Studio 2015 und früher, ließ der Compiler einen Standardmember-Initialisierer für einen Member einer Wertklasse zu, ignorierte diesen aber. Standardinitialisierung einer Wertklasse initialisiert die Elemente immer auf null; ein Standardkonstruktor ist nicht zulässig. In Visual Studio 2017 lösen Standardmember-Initialisierer einen Compilerfehler aus, wie im folgenden Beispiel gezeigt:

```cpp
value struct V
{
    int i = 0; // error C3446: 'V::i': a default member initializer
               // is not allowed for a member of a value class
};
```

### <a name="default-indexers-ccli"></a>Standardindexer (C++/CLI)

In Visual Studio 2015 und früher hat der Compiler in einigen Fällen fälschlicherweise eine Standardeigenschaft als einen Standardindexer kategorisiert. Es war möglich das Problem zu umzugehen, indem mithilfe des Bezeichners `default` auf die Eigenschaft zugegriffen wurde. Diese Lösung wurde problematisch, nachdem `default` als Schlüsselwort in C++11 eingeführt wurde. Aus diesem Grund wurden in Visual Studio 2017 Fehler behoben, die die Problemumgehung erforderten, und der Compiler löst jetzt einen Fehler aus, wenn `default` verwendet wird, um auf die Standardeigenschaft für eine Klasse zuzugreifen.

```cpp
//class1.cs

using System.Reflection;
using System.Runtime.InteropServices;

namespace ClassLibrary1
{
    [DefaultMember("Value")]
    public class Class1
    {
        public int Value
        {
            // using attribute on the return type triggers the compiler bug
            [return: MarshalAs(UnmanagedType.I4)]
            get;
        }
    }
    [DefaultMember("Value")]
    public class Class2
    {
        public int Value
        {
            get;
        }
    }
}

// code.cpp
#using "class1.dll"

void f(ClassLibrary1::Class1 ^r1, ClassLibrary1::Class2 ^r2)
{
       r1->Value; // error
       r1->default;
       r2->Value;
       r2->default; // error
}
```

In Visual Studio 2017 können Sie anhand ihres Namens auf beide Eigenschaften zugreifen:

```cpp
#using "class1.dll"

void f(ClassLibrary1::Class1 ^r1, ClassLibrary1::Class2 ^r2)
{
       r1->Value;
       r2->Value;
}
```

## <a name="update_153"></a> Fehlerbehebungen in Visual Studio 2017 Version 15.3

### <a name="calls-to-deleted-member-templates"></a>Aufrufe gelöschter Membervorlagen

In früheren Versionen von Visual Studio gab der Compiler mitunter keine Fehlermeldung bei falsch formatierten Aufrufen einer gelöschten Membervorlage zurück, wodurch zur Laufzeit möglicherweise Abstürze verursacht wurden. Mit dem folgenden Code wird nun C2280 generiert: „int S\<int>::f\<int>(void)': Es wurde versucht, auf eine gelöschte Funktion zu verweisen“:

```cpp
template<typename T>
struct S {
   template<typename U> static int f() = delete;
};

void g()
{
   decltype(S<int>::f<int>()) i; // this should fail
}
```

Um den Fehler zu beheben, deklarieren Sie „i“ als `int`.

### <a name="pre-condition-checks-for-type-traits"></a>Voraussetzungsprüfungen für Typmerkmale

Visual Studio 2017 Version 15.3 verbessert Voraussetzungsprüfungen für Typmerkmale so, dass der Standard strenger befolgt wird. Eine solche Prüfung erfolgt für „assignable“. Mit dem folgenden Code wird C2139 in Visual Studio 2017 Version 15.3 generiert:

```cpp
struct S;
enum E;

static_assert(!__is_assignable(S, S), "fail"); // C2139 in 15.3
static_assert(__is_convertible_to(E, E), "fail"); // C2139 in 15.3
```

### <a name="new-compiler-warning-and-runtime-checks-on-native-to-managed-marshaling"></a>Neue Compilerwarnung und CLR-Prüfungen für Marshalling von nativ zu verwaltet

Aufrufe nativer Funktionen aus verwalteten Funktionen erfordern Marshalling. Die CLR führt das Marshalling aus, versteht aber nicht die C++-Semantik. Wenn Sie ein natives Objekt nach Wert übergeben, ruft die CLR entweder den Kopierkonstruktor des Objekts auf oder verwendet BitBlt, was zu einem nicht definiertem Verhalten zur Laufzeit führt.

Nun gibt der Compiler eine Warnung aus, wenn er zur Kompilierzeit erkennt, dass ein natives Objekt mit gelöschtem Kopierkonstruktor zwischen der nativen und verwalteten Grenze nach Wert übergeben wird. In den Fällen, in denen dem Compiler zur Kompilierzeit keine Informationen vorliegen, fügt er eine Laufzeitprüfung hinzu, sodass das Programm sofort `std::terminate` aufruft, sobald ein falsch formatiertes Marshalling erfolgt. In Visual Studio 2017 Version 15.3 generiert der folgende Code die Warnung C4606 „'A': Die Übergabe eines Arguments nach Wert zwischen einer nativen und verwalteten Grenze erfordert einen gültigen Kopierkonstruktor. Andernfalls ist das Laufzeitverhalten nicht definiert“.

```cpp
class A
{
public:
   A() : p_(new int) {}
   ~A() { delete p_; }

   A(A const &) = delete;
   A(A &&rhs) {
   p_ = rhs.p_;
}

private:
   int *p_;
};

#pragma unmanaged

void f(A a)
{
}

#pragma managed

int main()
{
    f(A()); // This call from managed to native requires marshalling. The CLR doesn't understand C++ and uses BitBlt, which results in a double-free later.
}
```

Um den Fehler zu beheben, entfernen Sie die Direktive `#pragma managed`, um den Aufrufer als nativ zu markieren und Marshalling zu vermeiden.

### <a name="experimental-api-warning-for-winrt"></a>Warnung zu experimenteller API für WinRT

WinRT-APIs, die zu Experimentier- und Feedbackzwecken veröffentlicht werden, werden mit `Windows.Foundation.Metadata.ExperimentalAttribute` versehen. In Visual Studio 2017 Version 15.3 generiert der Compiler die Warnung C4698, wenn er auf dieses Attribut trifft. Einige APIs in früheren Versionen des Windows SDK wurden bereits mit dem Attribut markiert, sodass Aufrufe dieser APIs jetzt diese Compilerwarnung auslösen. Bei neueren Windows SDKs wurde das Attribut aus allen ausgelieferten Typen entfernt. Doch wenn Sie ein älteres SDK verwenden, müssen Sie diese Warnungen für alle Aufrufe ausgelieferter Typen unterdrücken.

Der folgende Code erzeugt die Warnung C4698: „‘Windows::Storage::IApplicationDataStatics2::GetForUserAsync‘ ist nur für Evaluierungszwecke gedacht und kann in künftigen Updates geändert oder entfernt werden“:

```cpp
Windows::Storage::IApplicationDataStatics2::GetForUserAsync(); //C4698
```

Fügen Sie #pragma hinzu, um die Warnung zu deaktivieren:

```cpp
#pragma warning(push)
#pragma warning(disable:4698)

Windows::Storage::IApplicationDataStatics2::GetForUserAsync();

#pragma warning(pop)
```

### <a name="out-of-line-definition-of-a-template-member-function"></a>Out-of-Line-Definition einer Vorlagenmemberfunktion

Visual Studio 2017 Version 15.3 generiert einen Fehler, wenn eine Out-of-Line-Definition einer Vorlagenmemberfunktion gefunden wird, die in der Klasse nicht deklariert wurde. Mit dem folgenden Code wird nun der Fehler C2039 generiert: „f“ ist kein Member von „S“:

```cpp
struct S {};

template <typename T>
void S::f(T t) {} //C2039: 'f': is not a member of 'S'
```

Um den Fehler zu beheben, fügen Sie der Klasse eine Deklaration hinzu:

```cpp
struct S {
    template <typename T>
    void f(T t);
};
template <typename T>
void S::f(T t) {}
```

### <a name="attempting-to-take-the-address-of-this-pointer"></a>Es wird versucht, die Adresse eines „this“-Zeigers zu verwenden

In C++ ist `this` ein prvalue des Typzeigers auf X. Sie können nicht die Adresse von `this` verwenden oder sie an einen lvalue-Verweis binden. In früheren Versionen von Visual Studio konnte es Ihnen der Compiler ermöglichen, diese Einschränkung mithilfe einer Umwandlung zu umgehen. In Visual Studio 2017 Version 15.3 generiert der Compiler Fehler C2664.

### <a name="conversion-to-an-inaccessible-base-class"></a>Konvertierung in eine Basisklasse, auf die nicht zugegriffen werden kann

Visual Studio 2017 Version 15.3 generiert einen Fehler, wenn Sie versuchen, einen Typ in eine Basisklasse zu konvertieren, auf die nicht zugegriffen werden kann. Der Compiler löst jetzt folgenden Fehler aus: Fehler C2243: "type-cast": Konvertierung von "D *" zu "B *" ist bereits vorhanden, aber es kann nicht darauf zugegriffen werden. Der folgende Code ist falsch formatiert und kann möglicherweise einen Absturz während der Laufzeit verursachen. Der Compiler generiert nun C2243, wenn er auf Code wie diesen trifft:

```cpp
#include <memory>

class B { };
class D : B { }; // C2243. should be public B { };

void f()
{
   std::unique_ptr<B>(new D());
}
```

### <a name="default-arguments-are-not-allowed-on-out-of-line-definitions-of-member-functions"></a>Standardargumente sind in Out-of-Line-Definitionen von Memberfunktionen nicht zulässig

Standardargumente sind in Out-of-Line-Definitionen von Memberfunktionen in Vorlagenklassen nicht zulässig. Der Compiler gibt unter **/permissive** eine Warnung und unter **/permissive-** einen harten Fehler aus.

In früheren Versionen von Visual Studio konnte der folgende falsch formatierte Code einen Absturz zur Laufzeit verursachen. Visual Studio 2017 Version 15.3 generiert die Warnung C5034: „'A\<T>::f': Eine Out-of-Line-Definition eines Members einer Klassenvorlage kann keine Standardargumente haben:

```cpp
template <typename T>
struct A {
    T f(T t, bool b = false);
};

template <typename T>
T A<T>::f(T t, bool b = false) // C5034
{
    // ...
}
```

Entfernen Sie das Standardargument `= false`, um den Fehler zu beheben.

### <a name="use-of-offsetof-with-compound-member-designator"></a>Verwendung von „offsetof“ mit zusammengesetztem Memberkennzeichner

In Visual Studio 2017 Version 15.3 führt das Verwenden von `offsetof(T, m)`, wobei *m* ein zusammengesetzter Memberkennzeichner ist, zu einer Warnung, wenn die Kompilierung mit der Option **/Wall** erfolgt. Der folgende Code ist falsch formatiert und kann möglicherweise zur Laufzeit einen Absturz verursachen. Visual Studio 2017 Version 15.3 generiert die Warnung C4841: „non-standard extension used: compound member designator in offsetof“ (Erweiterung, die nicht dem Standard entspricht, verwendet: In offsetof verwendeter Bezeichner für Verbundmitglied):

```cpp
struct A {
   int arr[10];
};

// warning C4841: non-standard extension used: compound member designator in offsetof
constexpr auto off = offsetof(A, arr[2]);
```

Um den Code zu korrigieren, deaktivieren Sie die Warnung mit einem Pragma, oder ändern Sie den Code so, dass `offsetof` nicht verwendet wird:

```cpp
#pragma warning(push)
#pragma warning(disable: 4841)
constexpr auto off = offsetof(A, arr[2]);
#pragma warning(pop)
```

### <a name="using-offsetof-with-static-data-member-or-member-function"></a>Verwenden von „offsetof“ mit statischem Datenmember oder mit Memberfunktion

In Visual Studio 2017 Version 15.3 führt das Verwenden von `offsetof(T, m)` zu einem Fehler, wenn *m* ein statischer Datenmember oder eine Memberfunktion ist. Mit dem folgenden Code wird der Fehler C4597: „Nicht definiertes Verhalten: offsetof auf Memberfunktion ‚foo‘ angewendet“ und der Fehler C4597: „Nicht definiertes Verhalten: offsetof auf statischen Datenmember ‚bar‘ angewendet" generiert:

```cpp
#include <cstddef>

struct A {
   int foo() { return 10; }
   static constexpr int bar = 0;
};

constexpr auto off = offsetof(A, foo);
constexpr auto off2 = offsetof(A, bar);
```

Dieser Code ist falsch formatiert und kann möglicherweise zur Laufzeit einen Absturz verursachen. Um den Fehler zu beheben, ändern Sie den Code so, dass das nicht definierte Verhalten nicht mehr aufgerufen wird. Dies ist nicht portierbarer Code, der vom C++-Standard nicht zugelassen ist.

### <a name="declspec"></a> Neue Warnung zu declspec-Attributen

In Visual Studio 2017 Version 15.3 ignoriert der Compiler Attribute nicht mehr, wenn `__declspec(...)` vor der externen Verknüpfungsspezifikation `extern "C"` angewendet wird. Zuvor hat der Compiler das Attribut ignoriert, was zu Problemen zur Laufzeit führen konnte. Wenn die Optionen **/Wall** und **/WX** festgelegt werden, generiert der folgende Code die Warnung C4768: „__declspec attributes before linkage specification are ignored“ (declspec-Attribute vor Verknüpfungsspezifikation werden ignoriert):

```cpp
__declspec(noinline) extern "C" HRESULT __stdcall //C4768
```

Um die Warnung zu korrigieren, fügen Sie zuerst externes „C“ hinzu:

```cpp
extern "C" __declspec(noinline) HRESULT __stdcall
```

Diese Warnung ist standardmäßig in 15.3 deaktiviert (standardmäßig aktiviert in Version 15.5) und wirkt sich nur auf den mit **/Wall** und **/WX** kompilierten Code aus.

### <a name="decltype-and-calls-to-deleted-destructors"></a>decltype und Aufrufe gelöschter Destruktoren

In früheren Versionen von Visual Studio erkannte der Compiler nicht, wenn ein Aufruf eines gelöschten Destruktors im Kontext des Ausdrucks erfolgte, der „decltype“ zugeordnet war. In Visual Studio 2017 Version 15.3 erzeugt der folgende Code Fehler C2280: "'A\<T>::~A(void)': Es wurde versucht, auf eine gelöschte Funktion zu verweisen“:

```cpp
template<typename T>
struct A
{
   ~A() = delete;
};

template<typename T>
auto f() -> A<T>;

template<typename T>
auto g(T) -> decltype((f<T>()));

void h()
{
   g(42);
}
```

### <a name="uninitialized-const-variables"></a>Nicht initialisierte „const“-Variablen

Die Visual Studio 2017 RTW-Version wies eine Regression auf, bei der der C++-Compiler keine Diagnose ausgab, wenn eine „const“-Variable nicht initialisiert war. Diese Regression wurde in Visual Studio 2017 Version 15.3 behoben. Der folgende Code erzeugt nun die "Warnung C4132: 'Value': const-Objekt sollte initialisiert werden":

```cpp
const int Value; //C4132
```

Um den Fehler zu beheben, weisen Sie `Value` einen Wert zu.

### <a name="empty-declarations"></a>Leere Deklarationen

Visual Studio 2017 Version 15.3 warnt bei leeren Deklarationen jetzt für alle Typen und nicht nur für integrierte Typen. Der folgende Code führt jetzt zur Warnung C4091, Stufe 2 für alle vier Deklarationen:

```cpp
struct A {};
template <typename> struct B {};
enum C { c1, c2, c3 };

int;    // warning C4091 : '' : ignored on left of 'int' when no variable is declared
A;      // warning C4091 : '' : ignored on left of 'main::A' when no variable is declared
B<int>; // warning C4091 : '' : ignored on left of 'B<int>' when no variable is declared
C;      // warning C4091 : '' : ignored on left of 'C' when no variable is declared
```

Um die Warnungen zu entfernen, können Sie die leeren Deklarationen einfach auskommentieren oder entfernen. In Fällen, in denen das nicht benannte Objekt einen Nebeneffekt haben soll (z. B. RAII), sollte es mit einem Namen versehen werden.

Die Warnung wird unter **/Wv:18** ausgeschlossen und ist auf der Warnstufe W2 standardmäßig aktiviert.

### <a name="stdisconvertible-for-array-types"></a>std::is_convertible für Arraytypen

Frühere Versionen des Compilers haben zu falschen Ergebnissen für [std::is_convertible](standard-library/is-convertible-class.md) für Arraytypen geführt. Dadurch mussten Bibliotheksautoren bei der Verwendung der Typeigenschaft `std::is_convertible<...>` besondere Schreibweisen für den Microsoft Visual C++-Compiler anwenden. Im folgenden Beispiel sind die statischen Assertionen in früheren Versionen von Visual Studio erfolgreich, jedoch nicht in Visual Studio 2017 Version 15.3:

```cpp
#include <type_traits>

using Array = char[1];

static_assert(std::is_convertible<Array, Array>::value);
static_assert(std::is_convertible<const Array, const Array>::value, "");
static_assert(std::is_convertible<Array&, Array>::value, "");
static_assert(std::is_convertible<Array, Array&>::value, "");
```

`std::is_convertible<From, To>` wird berechnet, indem überprüft wird, ob eine imaginäre Funktionsdefinition wohlgeformt ist:

```cpp 
   To test() { return std::declval<From>(); }
```

### <a name="private-destructors-and-stdisconstructible"></a>Private Destruktoren und std::is_constructible

Frühere Versionen des Compilers ignorieren, ob ein Destruktor privat war, wenn über das Ergebnis von [std::is_constructible](standard-library/is-constructible-class.md) entschieden wird. Dies wird nun berücksichtigt. Im folgenden Beispiel sind die statischen Assertionen in früheren Versionen von Visual Studio erfolgreich, jedoch nicht in Visual Studio 2017 Version 15.3:

```cpp
#include <type_traits>

class PrivateDtor {
   PrivateDtor(int) { }
private:
   ~PrivateDtor() { }
};

// This assertion used to succeed. It now correctly fails.
static_assert(std::is_constructible<PrivateDtor, int>::value);
```

Private Destruktoren führen dazu, dass ein Typ nicht konstruierbar ist. `std::is_constructible<T, Args...>` wird berechnet, als würde die folgende Deklaration geschrieben:

```cpp
   T obj(std::declval<Args>()...)
```

Dieser Aufruf impliziert einen Destruktoraufruf.

### <a name="c2668-ambiguous-overload-resolution"></a>C2668: Mehrdeutige Überladungsauflösung

Frühere Versionen des Compilers konnten manchmal keine Mehrdeutigkeiten erkennen, wenn durch die Verwendung von sowohl Deklarationen als auch argumentabhängigen Lookups mehrere Kandidaten gefunden wurden. Dies kann zum Auswählen einer falschen Überladung und zu unerwartetem Laufzeitverhalten führen. Im folgenden Beispiel löst Visual Studio 2017 Version 15.3 ordnungsgemäß C2668 aus: "f": Mehrdeutiger Aufruf einer überladenen Funktion:

```cpp
namespace N {
   template<class T>
   void f(T&, T&);

   template<class T>
   void f();
}

template<class T>
void f(T&, T&);

struct S {};
void f()
{
   using N::f; 

   S s1, s2;
   f(s1, s2); // C2668
}
```

Um den Code zu korrigieren, entfernen Sie die Anweisung `N::f`, wenn Sie `::f()` aufrufen wollten.

### <a name="c2660-local-function-declarations-and-argument-dependent-lookup"></a>C2660: Lokale Funktionsdeklarationen und argumentabhängiges Lookup

Lokale Funktionsdeklarationen verbergen die Funktitonsdeklaration im umschließenden Bereich und deaktivieren das argumentabhängige Lookup. Jedoch haben frühere Versionen des Compilers in diesem Fall ein argumentabhängiges Lookup durchgeführt, was zum Auswählen einer falschen Überladung oder zu unerwartetem Laufzeitverhalten führen konnte. Der Fehler liegt in der Regel in einer falschen Signatur der lokalen Funktionsdeklaration. Im folgenden Beispiel löst Visual Studio 2017 Version 15.3 ordnungsgemäß C2660 aus: "f": Funktion akzeptiert keine 2 Argumente:

```cpp
struct S {};
void f(S, int);

void g()
{
   void f(S); // C2660 'f': function does not take 2 arguments:
   // or void f(S, int);
   S s;
   f(s, 0);
}
```

Um das Problem zu beheben, ändern Sie entweder die Signatur `f(S)`, oder entfernen Sie diese.

### <a name="c5038-order-of-initialization-in-initializer-lists"></a>C5038: Reihenfolge der Initialisierung in Initialisiererlisten

Klassenmember werden in der Reihenfolge initialisiert, in der sie deklariert werden, nicht in der Reihenfolge, in der Sie in Initialisiererlisten erscheinen. Frühere Versionen des Compilers haben keine Warnung ausgegeben, wenn sich die Reihenfolge der Initialisiererliste von der Deklarationsreihenfolge unterschied. Dies konnte zu undefiniertem Laufzeitverhalten führen, wenn die Initialisierung eines Members von einem anderen Member in der Liste abhing, der bereits initialisiert wird. Im folgenden Beispiel löst Visual Studio 2017 Version 15.3 (mit **/Wall**) die folgende Warnung C5038 aus: „Data member 'A::y' will be initialized after data member 'A::x'“ (Datenmember "A::y" wird nach Datenmember "A::x" initialisiert):

```cpp
struct A
{
    A(int a) : y(a), x(y) {} // Initialized in reverse, y reused
    int x;
    int y;
};
```

Um das Problem zu beheben, ordnen Sie die Initialisiererliste so an, dass die Reihenfolge mit der Reihenfolge der Deklarationen übereinstimmt. Eine ähnliche Warnung wird ausgelöst, wenn ein oder beide Initialisierer auf Member der Basisklasse verweisen.

Beachten Sie, dass die Warnung standardmäßig deaktiviert ist und sich nur auf mit **/Wall** kompilierten Code auswirkt.

## <a name="update_155"></a>Fehlerkorrekturen und andere Verhaltensänderungen in Visual Studio 2017 Version 15.5

### <a name="partial-ordering-change"></a>Teilweise Änderung der Reihenfolge

Der Compiler weist nun den folgenden Code ordnungsgemäß zurück und gibt die richtige Fehlermeldung aus:

```cpp
template<typename... T>
int f(T* ...)
{
    return 1;
}

template<typename T>
int f(const T&)
{
    return 2;
}

int main()
{
    int i = 0;
    f(&i);    // C2668
}
```

```Output
t161.cpp
t161.cpp(16): error C2668: 'f': ambiguous call to overloaded function
t161.cpp(8): note: could be 'int f<int*>(const T &)'
        with
        [
            T=int*
        ]
t161.cpp(2): note: or       'int f<int>(int*)'
t161.cpp(16): note: while trying to match the argument list '(int*)'
```

Das Problem im Beispiel oben ist, dass es zwei Unterschiede in den Typen gibt (const im Vergleich zu non-const und pack im Vergleich zu non-pack). Um den Compilerfehler zu beseitigen, entfernen Sie einen der Unterschiede. Dies ermöglicht es dem Compiler, die Funktionen eindeutig zu sortieren.

```cpp
template<typename... T>
int f(T* ...)
{
    return 1;
}

template<typename T>
int f(T&)
{
    return 2;
}

int main()
{
    int i = 0;
    f(&i);
}
```

### <a name="exception-handlers"></a>Ausnahmehandler

Handler, die auf ein Array oder einen Funktionstyp verweisen, stimmen niemals mit einem Ausnahmeobjekt überein. Der Compiler hält sich nun ordnungsgemäß an diese Regel und gibt eine Warnung der Stufe 4 aus. Es ordnet auch einen Handler von `char*` oder `wchar_t*` nicht mehr einem Zeichenfolgenliteral zu, wenn **/Zc:strictStrings** verwendet wird.

```cpp
int main()
{
    try {
        throw "";
    }
    catch (int (&)[1]) {} // C4843 (This should always be dead code.)
    catch (void (&)()) {} // C4843 (This should always be dead code.)
    catch (char*) {} // This should not be a match under /Zc:strictStrings
}
```

```Output
warning C4843: 'int (&)[1]': An exception handler of reference to array or function type is unreachable, use 'int*' instead
warning C4843: 'void (__cdecl &)(void)': An exception handler of reference to array or function type is unreachable, use 'void (__cdecl*)(void)' instead
```
Mit dem folgenden Code wird der Fehler vermieden:

```cpp
catch (int (*)[1]) {}
```

### <a name="tr1"></a>Std::TR1-Namespace ist veraltet

Der `std::tr1`-Namespace, der nicht dem Standard entspricht, ist nun sowohl im C++14- als auch im C++17-Modus als veraltet markiert. In Visual Studio-2017 Version 15.5 löst der folgende Code C4996 aus:

```cpp
#include <functional>
#include <iostream>
using namespace std;

int main() {
    std::tr1::function<int (int, int)> f = std::plus<int>(); //C4996
    cout << f(3, 5) << std::endl;
    f = std::multiplies<int>();
    cout << f(3, 5) << std::endl;
}
```

```Output
warning C4996: 'std::tr1': warning STL4002: The non-Standard std::tr1 namespace and TR1-only machinery are deprecated and will be REMOVED. You can define _SILENCE_TR1_NAMESPACE_DEPRECATION_WARNING to acknowledge that you have received this warning.
```

Um den Fehler zu beheben, entfernen Sie den Verweis auf den `tr1`-Namespace:

```cpp
#include <functional>
#include <iostream>
using namespace std;

int main() {
    std::function<int (int, int)> f = std::plus<int>();
    cout << f(3, 5) << std::endl;
    f = std::multiplies<int>();
    cout << f(3, 5) << std::endl;
}
```

### <a name="annex_d"></a>Features der Standardbibliothek in Anhang D sind als veraltet markiert.

Wenn der Compilerschalter des **/std:c++17**-Modus festgelegt ist, werden fast alle Features der Standardbibliothek in Anhang D als veraltet markiert.

In Visual Studio-2017 Version 15.5 löst der folgende Code C4996 aus:

```cpp
#include <iterator>

class MyIter : public std::iterator<std::random_access_iterator_tag, int> {
public:
    // ... other members ...
};

#include <type_traits>

static_assert(std::is_same<MyIter::pointer, int*>::value, "BOOM");
```

```Output
warning C4996: 'std::iterator<std::random_access_iterator_tag,int,ptrdiff_t,_Ty*,_Ty &>::pointer': warning STL4015: The std::iterator class template (used as a base class to provide typedefs) is deprecated in C++17. (The <iterator> header is NOT deprecated.) The C++ Standard has never required user-defined iterators to derive from std::iterator. To fix this warning, stop deriving from std::iterator and start providing publicly accessible typedefs named iterator_category, value_type, difference_type, pointer, and reference. Note that value_type is required to be non-const, even for constant iterators. You can define _SILENCE_CXX17_ITERATOR_BASE_CLASS_DEPRECATION_WARNING or _SILENCE_ALL_CXX17_DEPRECATION_WARNINGS to acknowledge that you have received this warning.
```

Um den Fehler zu beheben, befolgen Sie die Anweisungen im Text der Warnung, wie im folgenden Code gezeigt:

```cpp
#include <iterator>

class MyIter {
public:
    typedef std::random_access_iterator_tag iterator_category;
    typedef int value_type;
    typedef ptrdiff_t difference_type;
    typedef int* pointer;
    typedef int& reference;

    // ... other members ...
};

#include <type_traits>

static_assert(std::is_same<MyIter::pointer, int*>::value, "BOOM");
```

### <a name="unreferenced-local-variables"></a>Unreferenzierte lokale Variablen

In Visual Studio 15.5 wird die Warnung C4189 in den meisten Fällen ausgegeben, wie im folgenden Code gezeigt:

```cpp
void f() {
    char s[2] = {0}; // C4189. Either use the variable or remove it.
}

```

```Output
warning C4189: 's': local variable is initialized but not referenced
```

Um den Fehler zu beheben, entfernen Sie die nicht verwendete Variable.

### <a name="single-line-comments"></a>Einzeilige Kommentare

In Visual Studio 2017 Version 15.5 werden die Warnungen C4001 und C4179 nicht mehr vom C-Compiler ausgegeben. Zuvor wurden sie nur unter dem Compilerschalter **/ Za** ausgegeben.  Die Warnungen werden nicht mehr benötigt, weil einzeilige Kommentare seit C99 Teil des C-Standards sind.

```cpp
/* C only */
#pragma warning(disable:4001) //C4619
#pragma warning(disable:4179)
// single line comment
//* single line comment */
```

```Output
warning C4619: #pragma warning: there is no warning number '4001'
```

Wenn der Code nicht abwärtskompatibel sein muss, können Sie die Warnung vermeiden, indem Sie die C4001/C4179-Unterdrückung entfernen. Wenn der Code abwärts kompatibel sein muss, unterdrücken Sie nur C4619.

```C
/* C only */

#pragma warning(disable:4619)
#pragma warning(disable:4001)
#pragma warning(disable:4179)

// single line comment
/* single line comment */
```

### <a name="declspec-attributes-with-extern-c-linkage"></a>__declspec-Attribute mit externer "C"-Verknüpfung 

In früheren Versionen von Visual Studio hat der Compiler `__declspec(...)`-Attribute ignoriert, wenn `__declspec(...)` vor der `extern "C"`-Verknüpfungsspezifikation angewendet wurde. Dieses Verhalten führte dazu, dass Code generiert wurde, den der Benutzer nicht beabsichtigt hatte (mit möglichen Auswirkungen auf die Laufzeit). Die Warnung wurde in Visual Studio Version 15.3 hinzugefügt, war aber standardmäßig deaktiviert. In Visual Studio 2017 Version 15.5 ist die Warnung standardmäßig aktiviert.

```cpp
__declspec(noinline) extern "C" HRESULT __stdcall //C4768
```

```Output
warning C4768: __declspec attributes before linkage specification are ignored
```

Um den Fehler zu beheben, platzieren Sie die Verknüpfungsspezifikation vor dem Attribut __declspec:

```cpp
extern "C" __declspec(noinline) HRESULT __stdcall
```

Diese neue Warnung C4768 wird für einige Windows SDK-Header ausgegeben, die mit Visual Studio 2017 15.3 oder älter ausgeliefert wurden (Beispiel: Version 10.0.15063.0, auch bekannt als RS2 SDK). Spätere Versionen von Windows SDK-Headern (speziell ShlObj.h und ShlObj_core.h) wurden jedoch so korrigiert, dass sie diese Warnung nicht ausgeben. Wenn Sie sehen, dass diese Warnung von Windows SDK-Headern ausgegeben wird, können Sie diese Aktionen ausführen:

1. Wechseln Sie zum neuesten Windows SDK, das mit Visual Studio 2017 Version 15.5 ausgeliefert wurde.
2. Deaktivieren Sie die Warnung um den #include-Teil der Windows SDK-Headeranweisung:

   ```cpp
   #pragma warning (push)
   #pragma warning(disable:4768)
   #include <shlobj.h>
   #pragma warning (pop)
   ```

### <a name="extern_linkage"></a>Externe constexpr-Verknüpfung 

In früheren Versionen von Visual Studio hat der Compiler immer eine interne `constexpr`-Variablenverknüpfung ausgegeben, selbst wenn die Variable als `extern` markiert wurde. In Visual Studio 2017 Version 15.5 ermöglicht ein neuer Compilerschalter (**/Zc:extern7Constexpr**) das richtige standardkonforme Verhalten. Letztendlich wird dies die Standardeinstellung sein.

```cpp
extern constexpr int x = 10;
```

```Output
error LNK2005: "int const x" already defined
```

Wenn eine Headerdatei eine Variable enthält, die als `extern constexpr` deklariert ist, muss sie als `__declspec(selectany)` markiert werden, damit ihre doppelten Deklarationen richtig kombiniert werden:

```cpp
extern constexpr __declspec(selectany) int x = 10;
```

### <a name="typeid-cant-be-used-on-incomplete-class-type"></a>typeid kann nicht für einen unvollständigen Klassentyp verwendet werden.

In früheren Versionen von Visual Studio ließ der Compiler fälschlicherweise den folgenden Code zu, was zu potenziell falschen Typinformationen führte. In Visual Studio 2017 Version 15.5 löst der Compiler ordnungsgemäß einen Fehler aus:

```cpp
#include <typeinfo>

struct S;

void f() { typeid(S); } //C2027 in 15.5
```

```Output
error C2027: use of undefined type 'S'
```

### <a name="stdisconvertible-target-type"></a>std::is_convertible-Zieltyp

`std::is_convertible` erfordert, dass der Zieltyp ein gültiger Rückgabetyp ist. In früheren Versionen von Visual Studio ließ der Compiler fälschlicherweise abstrakte Typen zu, was zu falscher Überladungsauflösung und unbeabsichtigtem Laufzeitverhalten führen konnte.  Der folgende Code löst jetzt ordnungsgemäß c2338 aus:

```cpp
#include <type_traits>

struct B { virtual ~B() = 0; };
struct D : public B { virtual ~D(); };

static_assert(std::is_convertible<D, B>::value, "fail"); // C2338 in 15.5
```

Um den Fehler zu vermeiden, sollten Sie bei der Verwendung von `is_convertible` Zeigertypen vergleichen, da ein Vergleich ohne Zeigertyp möglicherweise zu einem Fehler führt, wenn ein Typ abstrakt ist:

```cpp
#include <type_traits>

struct B { virtual ~B() = 0; };
struct D : public B { virtual ~D(); };

static_assert(std::is_convertible<D *, B *>::value, "fail");
```

### <a name="noexcept_removal"></a> Entfernen der dynamischen Ausnahmespezifikation und noexcept

In C++17 ist `throw()` ein Alias für `noexcept`, `throw(<type list>)` und `throw(...)` werden entfernt, und bestimmte Typen können `noexcept` enthalten. Dies kann zu Quellkompatibilitätsproblemen mit Code führen, der mit C++14 oder früher konform ist. Der Schalter **/Zc:noexceptTypes-** kann verwendet werden, um zur C++14-Version von `noexcept` zurückzukehren, während der C++17-Modus im Allgemeinen verwendet wird. Dies ermöglicht es Ihnen, Ihren Quellcode zu aktualisieren, um ihn an C++17 anzupassen, ohne dass Sie Ihren gesamten `throw()`-Code zur gleichen Zeit neu schreiben müssen.

Der Compiler diagnostiziert nun auch eine größere Anzahl nicht übereinstimmender Ausnahmespezifikationen in Deklarationen im C++17-Modus oder mit **/permissive-** mit der neuen Warnung C5043.

Der folgende Code generiert C5043 und C5040 in Visual Studio 2017 Version 15.5, wenn der Parameter **/std:c++17** verwendet wird:

```cpp
void f() throw(); // equivalent to void f() noexcept;
void f() {} // warning C5043
void g() throw(); // warning C5040

struct A {
    virtual void f() throw();
};

struct B : A {
    virtual void f() { } // error C2694
};
```
Um die Fehler zu entfernen, während Sie noch **/std:c++17** verwenden, fügen Sie entweder den Schalter **/Zc:noexceptTypes-** zur Befehlszeile hinzu, oder aktualisieren Sie Ihren Code, um `noexcept` zu verwenden, wie im folgenden Beispiel gezeigt:

```cpp
void f() noexcept;
void f() noexcept { }
void g() noexcept(false);

struct A {
    virtual void f() noexcept;
};

struct B : A {
    virtual void f() noexcept { }
};
```

### <a name="inline-variables"></a>Inlinevariablen

Statische constexpr-Datenmember sind nun implizit inline. Ihre Deklaration innerhalb einer Klasse ist nun also ihre Definition. Die Verwendung einer Out-of-Line-Definition für einen statischen constexpr-Datenmember ist redundant und nun veraltet. In Visual Studio 2017 Version 15.5 generiert der folgende Code jetzt Warnung C5041, wenn der Parameter **/std:c++17** angewendet wird. *'size': Out-of-line Definition für statischen constexpr-Datenmember ist nicht erforderlich und ist in C++17 veraltet*:

```cpp
struct X {
    static constexpr int size = 3;
};
const int X::size; // C5041
```

### <a name="extern-c-declspec-warning-c4768-now-on-by-default"></a>extern "C" __declspec(...) Warnung C4768 jetzt standardmäßig aktiviert

Die Warnung wurde in Visual Studio Version 2017 Version 15.3 hinzugefügt, war aber standardmäßig deaktiviert. In Visual Studio 2017 Version 15.5 ist sie jedoch standardmäßig aktiviert. Siehe [Neue Warnung zu declspec-Attributen](#declspec), um weitere Informationen zu erhalten.

### <a name="defaulted-functions-and-declspecnothrow"></a>Standardfunktionen und __declspec(nothrow)

Der Compiler erlaubte es bisher, Standardfunktionen mit `__declspec(nothrow)` zu deklarieren, wenn die entsprechenden Basis-/Memberfunktionen Ausnahmen zuließen. Dieses Verhalten steht im Widerspruch zum C++-Standard und kann zur Laufzeit zu undefiniertem Verhalten führen. Der Standard verlangt, dass solche Funktionen als gelöscht definiert werden, wenn es eine Abweichung von der Ausnahmespezifikation gibt.  Unter **/std:c++17** löst der folgende Code C2280 aus: *Es wurde versucht, auf eine gelöschte Funktion zu verweisen“. Funktion wurde implizit gelöscht, weil die explizite Ausnahmespezifikation mit der impliziten Deklaration nicht kompatibel ist.*:


```cpp
struct A {
    A& operator=(const A& other) { // No exception specification; this function may throw.
        ...
    }
};

struct B : public A {
    __declspec(nothrow) B& operator=(const B& other) = default;
};

int main()
{
    B b1, b2;
    b2 = b1; // error C2280
}
```

Um diesen Code zu korrigieren, entfernen Sie entweder __declspec(nothrow) aus der Standardfunktion, oder entfernen Sie `= default`, und geben Sie eine Definition für die Funktion zusammen mit der erforderlichen Ausnahmebehandlung an:

```cpp
struct A {
    A& operator=(const A& other) {
        // ...
    }
};

struct B : public A {
    B& operator=(const B& other) = default;
};

int main()
{
    B b1, b2;
    b2 = b1;
}
```
### <a name="noexcept-and-partial-specializations"></a>noexcept und Teilspezialisierungen
Mit noexcept im Typsystem können Teilspezialisierungen für die Zuordnung bestimmter „aufrufbarer“ Typen möglicherweise zu einem Fehler beim Kompilieren oder zum Auswählen der primären Vorlage aufgrund einer fehlenden Teilspezialisierung für Zeiger auf noexcept-Funktionen führen.

In solchen Fällen kann es erforderlich sein, zusätzliche Teilspezialisierungen hinzuzufügen, um die noexcept-Funktionszeiger und noexcept-Zeiger auf Memberfunktionen zu verarbeiten. Diese Überladungen sind nur im **/std:c++17**-Modus zulässig. Wenn die Abwärtskompatibilität mit C++14 aufrechterhalten werden muss und Sie Code schreiben, den andere nutzen, sollten Sie diese neuen Überladungen innerhalb von `#ifdef`-Anweisungen schützen. Wenn Sie in einem eigenständigen Modul arbeiten, können Sie anstelle von `#ifdef`-Schutz einfach mit dem Schalter **/Zc:noexceptTypes-** kompilieren.

Der folgende Code wird unter **/std:c++14** kompiliert, führt aber unter **/std:c++17** zum Fehler C2027: „Verwendung von undefiniertem Typ 'A\<T>'“:

```cpp
template <typename T> struct A;

template <>
struct A<void(*)()>
{
    static const bool value = true;
};

template <typename T>
bool g(T t)
{
    return A<T>::value;
}

void f() noexcept {}

int main()
{
    return g(&f) ? 0 : 1; // C2027
}
```

Der folgende Code ist unter **/std:c++17** erfolgreich, da der Compiler die neue Teilspezialisierung `A<void (*)() noexcept>` auswählt:

```cpp
template <typename T> struct A;

template <>
struct A<void(*)()>
{
    static const bool value = true;
};

template <>
struct A<void(*)() noexcept>
{
    static const bool value = true;
};

template <typename T>
bool g(T t)
{
    return A<T>::value;
}

void f() noexcept {}

int main()
{
    return g(&f) ? 0 : 1; // OK
}
```

## <a name="see-also"></a>Siehe auch

[Visual C++-Sprachkonformität](visual-cpp-language-conformance.md)  
