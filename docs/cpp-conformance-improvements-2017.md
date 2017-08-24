---
title: "Compilerverbesserungen an C++ bei der Übereinstimmung | Microsoft-Dokumentation"
ms.custom: 
ms.date: 06/05/2017
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
ms.sourcegitcommit: 467fc9fdbdf1df73590e5ca498067eb2a5b5c900
ms.openlocfilehash: 42b93960a6e0b829f3501c92a081953cf1051be4
ms.contentlocale: de-de
ms.lasthandoff: 08/14/2017

---
   
# <a name="c-conformance-improvements-in-includevsdev15mdmiscincludesvsdev15mdmd"></a>Verbesserungen an C++ bei der Übereinstimmung in [!INCLUDE[vs_dev15_md](misc/includes/vs_dev15_md.md)]

## <a name="new-language-features"></a>Neue Sprachfunktionen  
Der Compiler ist jetzt zusammen mit dem Support für generalisierte contextpr und NSDMI für Aggregate für Funktionen, die im C++14-Standard hinzugefügt werden, vollständig. Beachten Sie, dass dem Compiler noch einige Funktionen der C++11- und C++98-Standards fehlen. Eine Tabelle mit dem aktuellen Compilerstatus finden Sie unter [Visual C++-Sprachkonformität](visual-cpp-language-conformance.md).

### <a name="c11"></a>C++11:
**SFINAE-Support für Ausdrücke in mehr Bibliotheken** Der Visual C++-Compiler verbessert weiterhin die Unterstützung der SFINAE für Ausdrücke, die für die Vorlagenargumentableitung und Ersetzung erforderlich ist, in dem die Ausdrücke „decltype“ und „constexpr“ möglicherweise als Vorlagenparameter angezeigt werden. Weitere Informationen finden Sie unter [Expression SFINAE improvements in Visual Studio 2017 RC (Verbesserungen der SFINAE für Ausdrücke in Visual Studio 2017)](https://blogs.msdn.microsoft.com/vcblog/2016/06/07/expression-sfinae-improvements-in-vs-2015-update-3). 


### <a name="c-14"></a>C++ 14:
**NSDMI für Aggregate** Ein Aggregat ist ein Array oder eine Klasse mit keinem vom Benutzer bereitgestellten Konstruktor, keinen privaten oder geschützten nicht statischen Datenmembern, keinen Basisklassen und keinen virtuellen Funktionen. Ab C++ 14 können Aggregate Memberinitialisierer enthalten. Weitere Informationen finden Sie unter [Member initializers and aggregates (Memberinitialisierer und Aggregate)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3605.html).

**Erweiterte constexpr** Ausdrücke, die als „constexpr“ deklariert sind, dürfen jetzt bestimmte Arten von Deklarationen, if- und switch-Anweisungen, Schleifenanweisungen und Mutation der Objekte enthalten, deren Lebensdauer in der Auswertung von constexpr-Ausdrücken begann. Darüber hinaus ist es nicht mehr erforderlich, dass eine nicht statische Memberfunktion von constexpr implizit const ist. Weitere Informationen finden Sie unter [Relaxing constraints on constexpr functions (Lockerung der Einschränkungen auf constexpr-Funktionen)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3652.html). 

### <a name="c17"></a>C++17:
**Knappes static_assert** (verfügbar mit /std:c++latest) In C++17 ist der Nachrichtenparameter für static_assert optional. Weitere Informationen finden Sie unter [Extending static_assert, v2 (Erweitern des static_assert, v2)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3928.pdf). 

**[[fallthrough]]-Attribut** (mit /std:c++latest) Das [[fallthrough]]-Attribut kann im Kontext der switch-Anweisungen verwendet werden, als Hinweis für den Compiler, dass das Fall-Through-Verhalten vorgesehen ist. Dadurch wird verhindert, dass der Compiler in solchen Fällen Warnungen ausgeben kann. Weitere Informationen finden Sie unter [Wording for [[fallthrough]] attribute (Worlaut für [[fallthrough]]-Attribut)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0188r0.pdf). 

**Generalisierte bereichsbasierte for-Schleifen** (kein Compilerschalter erforderlich) Bereichsbasierte for-Schleifen erfordern nicht mehr, dass begin() und end() Objekte des gleichen Typs zurückgeben. Dadurch kann end() ein Sentinelobjekt zurückgeben, das von Bereichen verwendet wird, die im Ranges-V3-Vorschlag definiert sind. Weitere Informationen finden Sie unter [Generalizing the Range-Based For Loop (Bereichsbasierte for-Schleife generalisieren)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0184r0.html) und [range-v3 library on GitHub (Range-v3-Bibliothek auf GitHub)](https://github.com/ericniebler/range-v3). 

**Visual Studio 2017 Version 15.3**:

**constexpr-Lambdas** Lambdaausdrücke können jetzt in konstanten Ausdrücken verwendet werden. Weitere Informationen finden Sie unter [Constexpr Lambda](http://open-std.org/JTC1/SC22/WG21/docs/papers/2015/n4487.pdf).

**„if constexpr“ in Funktionsvorlagen** Eine Funktionsvorlage kann `if constexpr`-Anweisungen zum Branchen zur Kompilierzeit enthalten. Weitere Informationen finden Sie unter [if constexpr](http://open-std.org/JTC1/SC22/WG21/docs/papers/2016/p0128r1.html).

**Auswahlanweisungen mit Initialisierern** Eine `if`-Anweisung kann einen Initialisierer enthalten, der im Blockbereich innerhalb der Anweisung selbst eine Variable einführt. Weitere Informationen finden Sie unter [Selection statements with initializer](http://www.open-std.org/JTC1/SC22/WG21/docs/papers/2016/p0305r1.html) (Auswahlanweisungen mit Initialisierer).

**[[maybe_unused]]- und [[nodiscard]]-Attribute** Neue Attribute zum Unterdrücken von Warnungen, wenn eine Entität nicht verwendet wird, oder zum Erstellen einer Warnung, wenn der Rückgabewert eines Funktionsaufrufs verworfen wird. Weitere Informationen finden Sie unter [Wording for maybe_unused attribute](http://open-std.org/JTC1/SC22/WG21/docs/papers/2016/p0212r0.pdf) (Formulierungen für maybe_unused-Attribut) und [Proposal of unused, nodiscard and fallthrough attributes](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0068r0.pdf) (Vorschlag der Attribute „unused“, „nodiscard“ und „fallthrough“).

**Verwenden von Attributnamespaces ohne Wiederholung** Neue Syntax, um nur einen einzigen Namespacebezeichner in einer Attributliste zu aktivieren. Weitere Informationen finden Sie unter [Attribute in C++](cpp/attributes2.md).

**Strukturierte Bindungen** Es ist jetzt möglich, einen Wert mit individuellen Namen für die verschiedenen Komponenten in einer einzigen Anweisung zu speichern. Dies gilt, wenn der Wert ein Array, „std::tuple“ oder „std::pair“ ist oder nur öffentliche, nicht statische Datenmember enthält. Weitere Informationen finden Sie unter [Structured Bindings](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0144r0.pdf) (Strukturierte Bindungen).

**Erstellungsregeln für enum-Klassenwerte** Es gibt jetzt eine implizite/nicht einschränkende Umwandlung des zugrunde liegenden Typs einer bereichsbezogenen Enumeration in die Enumeration selbst, wenn deren Definition keinen Enumerator einführt und die Quelle eine list-initialization-Syntax verwendet. Weitere Informationen finden Sie unter [Construction Rules for enum class Values ](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0138r2.pdf) (Erstellungsregeln für enum-Klassenwerte).

**Erfassen von „*this“ anhand des Werts** Das \*this-Objekt in einem Lambdaausdruck kann jetzt anhand des Werts erfasst werden. Das ermöglicht Szenarien, in denen das Lambda in parallelen und asynchronen Vorgängen aufgerufen wird, insbesondere in neueren Computerarchitekturen. Weitere Informationen finden Sie unter [Lambda Capture of \*this by Value as [=,\*this]](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0018r3.html) (Lambdaerfassung von „*this“ anhand des Werts als [=,*this]).

**Entfernen von „operator++“ für „bool“** „operator++“ wird in `bool`-Typen nicht mehr unterstützt. Weitere Informationen finden Sie unter [Remove Deprecated operator++(bool)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0002r1.html) (Veralteten „operator++(bool)“ entfernen).

**Entfernen des veralteten Schlüsselworts „register“** Das Schlüsselwort `register`, das zuvor als veraltet gekennzeichnet war (und vom Visual C++-Compiler ignoriert wurde), wurde jetzt aus der Sprache entfernt. Weitere Informationen finden Sie unter [Remove Deprecated Use of the register Keyword](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/p0001r1.html) (Entfernen der Verwendung des veralteten register-Schlüsselworts).

Eine vollständige Liste der Konformitätsverbesserungen bis zum Visual Studio 2015 Update 3 finden Sie unter [Visual C++ What's New 2003 through 2015 (Visual C++ – Neues von 2003 bis 2015)](https://msdn.microsoft.com/en-us/library/mt723604.aspx).

## <a name="bug-fixes"></a>Fehlerkorrekturen
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
Deklarieren Sie die Funktion array::size() als constexpr, oder entfernen Sie den Qualifizierer constexpr von f, um den Fehler zu beheben. 

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
                        // as an argument to a variadic function
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
Deklarieren Sie den Operator int() als konstant, um den Fehler zu korrigieren. 

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
Um SFINAE für Ausdrücke zu unterstützen, analysiert der Compiler jetzt decltype-Argumente, wenn die Vorlagen deklariert, aber nicht instanziiert sind. Wenn eine unabhängige Spezialisierung im decltype-Argument gefunden wird, wird sie nicht zum Zeitpunkt der Instanziierung zurückgestellt werden. Sie wird sofort verarbeitet, und alle resultierenden Fehler können zu diesem Zeitpunkt untersucht werden.  

Das folgende Beispiel zeigt einen solchen Compilerfehler, der zum Zeitpunkt der Deklaration ausgelöst wird:

```cpp  
#include <utility>
template <class T, class ReturnT, class... ArgsT> class IsCallable
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
In Visual Studio 2015 und früher hat der Compiler in einigen Fällen fälschlicherweise eine Standardeigenschaft als einen Standardindexer kategorisiert. Es war möglich das Problem zu umzugehen, indem mithilfe des „default“-Bezeichners auf die Eigenschaft zugegriffen wurde. Die Lösung selbst wurde problematisch, nachdem default als Schlüsselwort in C++11 eingeführt wurde. Aus diesem Grund wurden in Visual Studio 2017 Fehler behoben, die die Problemumgehung erforderten, und der Compiler löst jetzt einen Fehler aus, wenn „default“ verwendet wird, um auf die Standardeigenschaft für eine Klasse zuzugreifen.

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
In früheren Versionen von Visual Studio gab der Compiler mitunter keine Fehlermeldung bei falsch formatierten Aufrufen einer gelöschten Membervorlage zurück, wodurch zur Laufzeit möglicherweise Abstürze verursacht wurden. Mit dem folgenden Code wird nun C2280 generiert: „‘int S<int>::f<int>(void)': Es wurde versucht, auf eine gelöschte Funktion zu verweisen“:
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
Visual Studio 2017 Version 15.3 verbessert Voraussetzungsprüfungen für Typmerkmale so, dass der Standard strenger befolgt wird. Eine solche Prüfung erfolgt für „assignable“. Mit dem folgenden Code wird in Updateversion 15.3 C2139 generiert:

```cpp
struct S; 
enum E; 
 
static_assert(!__is_assignable(S, S), "fail"); // C2139 in 15.3
static_assert(__is_convertible_to(E, E), "fail"); // C2139 in 15.3
```

### <a name="new-compiler-warning-and-runtime-checks-on-native-to-managed-marshaling"></a>Neue Compilerwarnung und CLR-Prüfungen für Marshalling von nativ zu verwaltet
Aufrufe nativer Funktionen aus verwalteten Funktionen erfordern Marshalling. Die CLR führt das Marshalling aus, versteht aber nicht die C++-Semantik. Wenn Sie ein natives Objekt nach Wert übergeben, ruft die CLR entweder den Kopierkonstruktor des Objekts auf oder verwendet BitBlt, was zu einem nicht definiertem Verhalten zur Laufzeit führt. 
 
Nun gibt der Compiler eine Warnung aus, wenn er zur Kompilierzeit erkennt, dass ein natives Objekt mit gelöschtem Kopierkonstruktor zwischen der nativen und verwalteten Grenze nach Wert übergeben wird. In den Fällen, in denen dem Compiler zur Kompilierzeit keine Informationen vorliegen, fügt er eine Laufzeitprüfung hinzu, sodass das Programm sofort „std::terminate“ aufruft, sobald ein falsch formatiertes Marshalling erfolgt. In der Updateversion 15.3 generiert der folgende Code C4606 „A“: Die Übergabe eines Arguments nach Wert zwischen einer nativen und verwalteten Grenze erfordert einen gültigen Kopierkonstruktor. Andernfalls ist das Laufzeitverhalten nicht definiert“.
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
    f(A()); // This call from managed to native requires marshalling. The CLR doesn't understand C++ and uses BitBlt, which will result in a double-free later. 
}
```
Um den Fehler zu beheben, entfernen Sie die Direktive `#pragma managed`, um den Aufrufer als nativ zu markieren und Marshalling zu vermeiden. 

### <a name="experimental-api-warning-for-winrt"></a>Warnung zu experimenteller API für WinRT
WinRT-APIs, die zu Experimentier- und Feedbackzwecken veröffentlicht werden, sind mit `Windows.Foundation.Metadata.ExperimentalAttribute` markiert. In Visual Studio 2017 Version 15.3 generiert der Compiler die Warnung C4698, wenn er auf dieses Attribut trifft. Einige APIs in früheren Versionen des Windows SDK wurden bereits mit dem Attribut markiert, sodass Aufrufe dieser APIs das Auslösen dieser Compilerwarnung verursachen. Bei neueren Windows SDKs wurde das Attribut aus allen gelieferten Typen entfernt. Doch wenn Sie ein älteres SDK verwenden, müssen Sie diese Warnungen für alle Aufrufe gelieferter Typen unterdrücken.
Der folgende Code erzeugt die Warnung C4698: „‘Windows::Storage::IApplicationDataStatics2::GetForUserAsync‘ ist nur für Evaluierungszwecke gedacht und kann in künftigen Updates geändert oder entfernt werden“:
```cpp
Windows::Storage::IApplicationDataStatics2::GetForUserAsync() //C4698
```

Fügen Sie #pragma hinzu, um die Warnung zu deaktivieren:

```cpp
#pragma warning(push) 
#pragma warning(disable:4698) 
 
Windows::Storage::IApplicationDataStatics2::GetForUserAsync() 
 
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
In C++ ist „this“ ein prvalue des Typzeigers auf X. Sie können nicht die Adresse von „this“ verwenden oder sie an einen „lvalue“-Verweis binden. In früheren Versionen von Visual Studio konnte es Ihnen der Compiler ermöglichen, diese Einschränkung mithilfe einer Umwandlung zu umgehen. In Visual Studio 2017 Version 15.3 generiert der Compiler Fehler C2664.

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
Standardarguments sind in Out-of-Line-Definitionen von Memberfunktionen in Vorlagenklassen nicht zulässig. Der Compiler gibt unter „/permissive“ eine Warnung und unter „/permissive-“ einen harten Fehler aus. 

In früheren Versionen von Visual Studio konnte der folgende falsch formatierte Code einen Absturz zur Laufzeit verursachen. Visual Studio 2017 Version 15.3 generiert die Warnung C5034: "A<T>::f": Eine Out-of-Line-Definition eines Members einer Klassenvorlage kann keine Standardargumente haben:
```cpp
 
template <typename T> 
struct A { 
    T f(T t, bool b = false); 
}; 
 
template <typename T> 
T A<T>::f(T t, bool b = false) // C5034
{ 
... 
}
```
Entfernen Sie das Standardargument „= False“, um den Fehler zu beheben. 

### <a name="use-of-offsetof-with-compound-member-designator"></a>Verwendung von „offsetof“ mit zusammengesetztem Memberkennzeichner
In Visual Studio 2017 Version 15.3 führt das Verwenden von „offsetof(T, m)“, wobei „m“ ein zusammengesetzter Memberkennzeichner ist, zu einer Warnung, wenn die Kompilierung mit der Option „/Wall“ erfolgt. Der folgende Code ist falsch formatiert und kann möglicherweise zur Laufzeit einen Absturz verursachen. Visual Studio 2017 Version 15.3 generiert die Warnung C4841: Nicht standardmäßige Erweiterung verwendet: In offsetof verwendeter Bezeichner für Verbundmitglied:

```cpp
  
struct A { 
int arr[10]; 
}; 
 
// warning C4841: non-standard extension used: compound member designator in offsetof 
constexpr auto off = offsetof(A, arr[2]);
```
Um den Code zu korrigieren, deaktivieren Sie die Warnung mit einem Pragma, oder ändern Sie den Code so, dass „offsetof“ nicht verwendet wird: 

```cpp
#pragma warning(push) 
#pragma warning(disable: 4841) 
constexpr auto off = offsetof(A, arr[2]); 
#pragma warning(pop) 
```

### <a name="using-offsetof-with-static-data-member-or-member-function"></a>Verwenden von „offsetof“ mit statischem Datenmember oder mit Memberfunktion
In Visual Studio 2017 Version 15.3 führt das Verwenden von „offsetof(T, m)“, wobei „m“ ein statischer Datenmember oder eine Memberfunktion ist, zu einem Fehler. Mit dem folgenden Code wird der Fehler C4597: „Nicht definiertes Verhalten: offsetof auf Memberfunktion ‚foo‘ angewendet“ und der Fehler C4597: „Nicht definiertes Verhalten: offsetof auf statischen Datenmember ‚bar‘ angewendet" generiert:
```cpp
 
#include <cstddef> 
 
struct A { 
int foo() { return 10; } 
static constexpr int bar = 0; 
}; 
 
constexpr auto off = offsetof(A, foo); 
Constexpr auto off2 = offsetof(A, bar);
```
 
Dieser Code ist falsch formatiert und kann möglicherweise zur Laufzeit einen Absturz verursachen. Um den Fehler zu beheben, ändern Sie den Code so, dass das nicht definierte Verhalten nicht mehr aufgerufen wird. Dies ist nicht portierbarer Code, der vom C++-Standard nicht zugelassen ist.

### <a name="new-warning-on-declspec-attributes"></a>Neue Warnung zu „declspec“-Attributen
In Visual Studio 2017 Version 15.3 ignoriert der Compiler Attribute nicht mehr, wenn „__declspec(...)“ vor der externen Verknüpfungsspezifikation „C“ angewendet wird. Zuvor hat der Compiler das Attribut ignoriert, was zu Problemen zur Laufzeit führen konnte. Wenn die Option `/Wall /WX` festgelegt ist, generiert der folgende Code die Warnung C4768: „__declspec-Attribute vor Verknüpfungsspezifikation werden ignoriert“:

```cpp
 
__declspec(noinline) extern "C" HRESULT __stdcall //C4768
```

Um die Warnung zu korrigieren, fügen Sie zuerst externes „C“ hinzu:

```cpp
extern "C" __declspec(noinline) HRESULT __stdcall
```
Diese Warnung ist standardmäßig deaktiviert und wirkt sich nur auf den mit `/Wall /WX` kompilierten Code aus.

### <a name="decltype-and-calls-to-deleted-destructors"></a>decltype und Aufrufe gelöschter Destruktoren
In früheren Versionen von Visual Studio erkannte der Compiler nicht, wenn ein Aufruf eines gelöschten Destruktors im Kontext des Ausdrucks erfolgte, der „decltype“ zugeordnet war. In Visual Studio 2017 Version 15.3 erzeugt der folgende Code Fehler C2280: "A<T>::~A(void)": Es wurde versucht, auf eine gelöschte Funktion zu verweisen:

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
 
Die Warnung wird unter „/Wv:18“ ausgeschlossen und ist auf der Warnstufe W2 standardmäßig aktiviert.


### <a name="stdisconvertible-for-array-types"></a>std::is_convertible für Arraytypen
Frühere Versionen des Compilers haben zu falschen Ergebnissen für [std::is_convertible](standard-library/is-convertible-class.md) für Arraytypen geführt. Dadurch mussten Bibliotheksautoren bei der Verwendung der Typeigenschaft `std::is_convertible<…>` besondere Schreibweisen für den Visual C++-Compiler anwenden. Im folgenden Beispiel sind die statischen Assertionen in früheren Versionen von Visual Studio erfolgreich, jedoch nicht in Visual Studio 2017 Version 15.3:

```cpp
#include <type_traits>
 
using Array = char[1];
 
static_assert(std::is_convertible<Array, Array>::value);
static_assert(std::is_convertible<const Array, const Array>::value, "");
static_assert(std::is_convertible<Array&, Array>::value, "");
static_assert(std::is_convertible<Array, Array&>::value, "");
```

**std::is_convertible<From, To>** wird berechnet, indem überprüft wird, ob eine imaginäre Funktionsdefinition wohlgeformt ist:
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

Private Destruktoren führen dazu, dass ein Typ nicht konstruierbar ist. **std::is_constructible<T, Args…>** wird berechnet, als würde die folgende Deklaration geschrieben:
```cpp 
   T obj(std::declval<Args>()…)
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
Um den Code zu korrigieren, entfernen Sie die Anweisung „using N::f“, wenn Sie „::f()“ aufrufen wollten.

### <a name="c2660-local-function-declarations-and-argument-dependent-lookup"></a>C2660: Lokale Funktionsdeklarationen und argumentabhängiges Lookup
Lokale Funktionsdeklarationen verbergen die Funktitonsdeklaration im umschließenden Bereich und deaktivieren das argumentabhängige Lookup.
Jedoch haben frühere Versionen des Visual C++-Compilers in diesem Fall ein argumentabhängiges Lookup durchgeführt, was zum Auswählen einer falschen Überladung oder zu unerwartetem Laufzeitverhalten führen konnte. Der Fehler liegt in der Regel in einer falschen Signatur der lokalen Funktionsdeklaration. Im folgenden Beispiel löst Visual Studio 2017 Version 15.3 ordnungsgemäß C2660 aus: "f": Funktion akzeptiert keine 2 Argumente:

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

Um das Problem zu beheben, ändern Sie entweder die Signatur **f(S)**, oder entfernen Sie diese.

### <a name="c5038-order-of-initialization-in-initializer-lists"></a>C5038: Reihenfolge der Initialisierung in Initialisiererlisten
Klassenmember werden in der Reihenfolge initialisiert, in der sie deklariert werden, nicht in der Reihenfolge, in der Sie in Initialisiererlisten erscheinen. Frühere Versionen des Compilers haben keine Warnung ausgegeben, wenn sich die Reihenfolge der Initialisiererliste von der Deklarationsreihenfolge unterschied. Dies konnte zu undefiniertem Laufzeitverhalten führen, wenn die Initialisierung eines Members von einem anderen Member in der Liste abhing, der bereits initialisiert wird. Im folgenden Beispiel löst Visual Studio 2017 Version 15.3 (mit „/Wall“) die folgende Warnung aus: C5038: Datenmember "A::y" wird nach Datenmember "A::x" initialisiert:

```cpp
struct A
{
    A(int a) : y(a), x(y) {} // Initialized in reverse, y reused
    int x;
    int y;
};

```
Um das Problem zu beheben, ordnen Sie die Initialisiererliste so an, dass die Reihenfolge mit der Reihenfolge der Deklarationen übereinstimmt. Eine ähnliche Warnung wird ausgelöst, wenn ein oder beide Initialisierer auf Member der Basisklasse verweisen.

Beachten Sie, dass die Warnung standardmäßig deaktiviert ist und sich nur auf mit „/Wall“ kompilierten Code auswirkt.

## <a name="see-also"></a>Siehe auch  
[Visual C++-Sprachkonformität](visual-cpp-language-conformance.md)  

