---
title: "Compilerverbesserungen an C++ bei der Übereinstimmung | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8801dbdb-ca0b-491f-9e33-01618bff5ae9
author: BrianPeek
ms.author: brpeek
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
translationtype: Human Translation
ms.sourcegitcommit: f9e63f47a8df69b52a6a12688e84602981d20dae
ms.openlocfilehash: 2d86588df2b20861dff5b940d2f0c7c3afd857fb
ms.lasthandoff: 03/21/2017

---
   
# <a name="c-conformance-improvements-in-includevsdev15mdmiscincludesvsdev15mdmd"></a>Verbesserungen an C++ bei der Übereinstimmung in [!INCLUDE[vs_dev15_md](misc/includes/vs_dev15_md.md)]

## <a name="new-language-features"></a>Neue Sprachfunktionen  
Der Compiler ist jetzt zusammen mit dem Support für generalisierte contextpr und NSDMI für Aggregate für Funktionen, die im C++14-Standard hinzugefügt werden, vollständig. Beachten Sie, dass dem Compiler noch einige Funktionen der C++11- und C++98-Standards fehlen. Eine Tabelle mit dem aktuellen Compilerstatus finden Sie unter [Visual C++-Sprachkonformität](visual-cpp-language-conformance.md).

### <a name="c11"></a>C++11:
**SFINAE-Support für Ausdrücke in mehr Bibliotheken** Der Visual C++-Compiler verbessert weiterhin die Unterstützung der SFINAE für Ausdrücke, die für die Vorlagenargumentableitung und Ersetzung erforderlich ist, in dem die Ausdrücke „decltype“ und „constexpr“ möglicherweise als Vorlagenparameter angezeigt werden. Weitere Informationen finden Sie unter [Expression SFINAE improvements in Visual Studio 2017 RC (Verbesserungen der SFINAE für Ausdrücke in Visual Studio 2017)](https://blogs.msdn.microsoft.com/vcblog/2016/06/07/expression-sfinae-improvements-in-vs-2015-update-3). 


### <a name="c-14"></a>C++ 14:
**NSDMI für Aggregate** Ein Aggregat ist ein Array oder eine Klasse mit keinem vom Benutzer bereitgestellten Konstruktor, keinen privaten oder geschützten nicht statischen Datenmembern, keinen Basisklassen und keinen virtuellen Funktionen. Ab C++&14; können Aggregate Memberinitialisierer enthalten. Weitere Informationen finden Sie unter [Member initializers and aggregates (Memberinitialisierer und Aggregate)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3605.html).

**Erweiterte constexpr** Ausdrücke, die als „constexpr“ deklariert sind, dürfen jetzt bestimmte Arten von Deklarationen, if- und switch-Anweisungen, Schleifenanweisungen und Mutation der Objekte enthalten, deren Lebensdauer in der Auswertung von constexpr-Ausdrücken begann. Darüber hinaus ist es nicht mehr erforderlich, dass eine nicht statische Memberfunktion von constexpr implizit const ist. Weitere Informationen finden Sie unter [Relaxing constraints on constexpr functions (Lockerung der Einschränkungen auf constexpr-Funktionen)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2013/n3652.html). 

### <a name="c17"></a>C++17:
**Knappes static_assert** (verfügbar mit /std:c++latest) In C++17 ist der Nachrichtenparameter für static_assert optional. Weitere Informationen finden Sie unter [Extending static_assert, v2 (Erweitern des static_assert, v2)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2014/n3928.pdf). 

**[[fallthrough]]-Attribut** (mit /std:c++latest) Das [[fallthrough]]-Attribut kann im Kontext der switch-Anweisungen verwendet werden, als Hinweis für den Compiler, dass das Fall-Through-Verhalten vorgesehen ist. Dadurch wird verhindert, dass der Compiler in solchen Fällen Warnungen ausgeben kann. Weitere Informationen finden Sie unter [Wording for [[fallthrough]] attribute (Worlaut für [[fallthrough]]-Attribut)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0188r0.pdf). 

**Generalisierte bereichsbasierte for-Schleifen** (kein Compilerschalter erforderlich) Bereichsbasierte for-Schleifen erfordern nicht mehr, dass begin() und end() Objekte des gleichen Typs zurückgeben. Dadurch kann end() ein Sentinelobjekt zurückgeben, das von Bereichen verwendet wird, die im Ranges-V3-Vorschlag definiert sind. Weitere Informationen finden Sie unter [Generalizing the Range-Based For Loop (Bereichsbasierte for-Schleife generalisieren)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0184r0.html) und [range-v3 library on GitHub (Range-v3-Bibliothek auf GitHub)](https://github.com/ericniebler/range-v3). 


Eine vollständige Liste der Konformitätsverbesserungen bis zum Visual Studio 2015 Update 3 finden Sie unter [Visual C++ What's New 2003 through 2015 (Visual C++ – Neues von 2003 bis 2015)](https://msdn.microsoft.com/en-us/library/mt723604.aspx).

## <a name="bug-fixes"></a>Fehlerkorrekturen
### <a name="copy-list-initialization"></a>copy-list-Initialisierung
Visual Studio 2017 löst ordnungsgemäß Compilerfehler im Zusammenhang mit der Erstellung von Objekten mithilfe von Initialisiererlisten aus, die nicht in Visual Studio 2015 abgefangen wurden und die zu Abstürzen oder einem nicht definierten Laufzeitverhalten führen können.  Laut N4594 13.3.1.7p1 in der copy-list-Initialisierung, muss der Compiler einen expliziten Konstruktor für die Überladungsauflösung berücksichtigen, aber er muss einen Fehler auslösen, wenn diese Überladung tatsächlich ausgewählt wird. 

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
Visual Studio 2017 löst ordnungsgemäß einen Fehler aus, wenn der linke Operand eines bedingten Auswertungsvorgangs in einem constexpr-Kontext ungültig ist. Der folgende Code wird in Visual Studio 2015 kompiliert, aber nicht in Visual Studio 2017:

```cpp  
template<int N>
struct array 
{
       int size() const { return N; }
};

constexpr bool f(const array<1> &arr)
{
       return arr.size() == 10 || arr.size() == 11; // error starting in Visual Studio 2017
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
Für mit CStringW erstellte und verwaltete Zeichenfolgen sollte der bereitgestellte „Operator LPCWSTR()“ verwendet werden, um ein CStringW-Objekt in einen C-Zeiger umzuwandeln, der von der Formatzeichenfolge erwartet wird.

```cpp  
CStringW str1;
CStringW str2;
str1.Format(… , static_cast<LPCWSTR>(str2));
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
Entsprechend dem C++-Standard verfügt eine Klasse, die innerhalb eines anonymen Namespace deklariert wird, über interne Verknüpfungen und kann daher nicht exportiert werden. In Visual Studio 2015 und früheren Versionen wurde diese Regel nicht durchgesetzt. In Visual Studio 2017 wird die Regel teilweise durchgesetzt. Das folgende Beispiel löst in Visual Studio 2017 diesen Fehler aus: „Fehler C2201: 'const `anonymous namespace'::S1::`vftable'': Externe Bindung erforderlich, um Export/Import zu ermöglichen“.

```cpp
namespace
{
    struct __declspec(dllexport) S1 { virtual void f() {} }; //C2201
}
```

### <a name="classes-declared-in-anonymous-namespaces"></a>In anonymen Namespaces deklarierte Klassen
Entsprechend dem C++-Standard verfügt eine Klasse, die innerhalb eines anonymen Namespace deklariert wird, über interne Verknüpfungen und kann daher nicht exportiert werden. In Visual Studio 2015 und früheren Versionen wurde diese Regel nicht durchgesetzt. In Visual Studio 2017 wird die Regel teilweise durchgesetzt. Das folgende Beispiel löst in Visual Studio 2017 diesen Fehler aus: „Fehler C2201: 'const `anonymous namespace'::S1::`vftable'': Externe Bindung erforderlich, um Export/Import zu ermöglichen“.

```cpp
struct __declspec(dllexport) S1 { virtual void f() {} }; //C2201
```

### <a name="default-initializers-for-value-class-members-ccli"></a>Standardinitialisierer für Wertklassenmember (C++/CLI)
In Visual Studio 2015 und früher, ließ der Compiler einen Standardmember-Initialisierer für einen Member einer Wertklasse zu, ignorierte diesen aber.  Standardinitialisierung einer Wertklasse initialisiert die Elemente immer auf null; ein Standardkonstruktor ist nicht zulässig.  In Visual Studio 2017 lösen Standardmember-Initialisierer einen Compilerfehler aus, wie im folgenden Beispiel gezeigt:

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

## <a name="see-also"></a>Siehe auch  
[Visual C++-Sprachkonformität](visual-cpp-language-conformance.md)  

