---
title: Verbesserungen an C++ bei der Übereinstimmung mit Standards
ms.date: 05/16/2019
description: Microsoft C++ in Visual Studio 2019 bewegt sich auf die vollständige Konformität mit dem Sprachstandard C++20 zu.
ms.technology: cpp-language
author: mikeblome
ms.author: mblome
ms.openlocfilehash: 02b778f10ad94342c922a4e79a856cc2a7d53076
ms.sourcegitcommit: 28eae422049ac3381c6b1206664455dbb56cbfb6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2019
ms.locfileid: "66451218"
---
# <a name="c-conformance-improvements-in-visual-studio-2019-rtw-and-version-161improvements161"></a>Verbesserungen der C++-Konformität in Visual Studio 2019 (RTW und Version [16.1](#improvements_161))

## <a name="improvements-in-visual-studio-2019-rtw"></a>Verbesserungen in Visual Studio 2019 (RTW)

Visual Studio 2019 (RTW) enthält die folgenden Verbesserungen der Konformität, Fehlerbehebungen und Verhaltensänderungen des Microsoft C++-Compilers (MSVC).

**Hinweis**: C++20-Features werden im Modus `/std:c++latest` zur Verfügung gestellt, bis die C++20-Implementierung für den Compiler und für IntelliSense abgeschlossen ist. Zu diesem Zeitpunkt wird der Compilermodus `/std:c++20` eingeführt.

### <a name="improved-modules-support-for-templates-and-error-detection"></a>Verbesserte Unterstützung von Modulen für Vorlagen und die Fehlererkennung

Module entsprechen nun offiziell dem C++20-Standard. Die verbesserte Unterstützung wurde in Visual Studio 2017 Version 15.9 hinzugefügt. Weitere Informationen finden Sie unter [Better template support and error detection in C++ Modules with MSVC 2017 version 15.9 (Verbesserte Unterstützung von Vorlagen und Fehlererkennung in C++-Modulen mit MSVC 2017 Version 15.9)](https://devblogs.microsoft.com/cppblog/better-template-support-and-error-detection-in-c-modules-with-msvc-2017-version-15-9/).

### <a name="modified-specification-of-aggregate-type"></a>Geänderte Spezifikation des Aggregattyps

Die Spezifikation von Aggregattypen wurde in C++20 geändert (siehe [Prohibit aggregates with user-declared constructors (Verbieten von Aggregaten mit benutzerdeklarierten Konstruktoren)](https://wg21.link/p1008r1)). In Visual Studio 2019 ist eine Klasse mit einem beliebigen benutzerdeklarierten Konstruktor (z. B. Einschließen von mit `= default` oder `= delete` deklarierten Konstruktoren) gemäß `/std:c++latest` kein Aggregat. Zuvor wurden Klassen nur durch von Benutzern bereitgestellte Konstruktoren als Aggregat disqualifiziert. Diese Änderung führt weitere Einschränkungen für die Initialisierung solcher Typen ein.

Der folgende Code wird in Visual Studio 2017 fehlerfrei kompiliert, löst jedoch gemäß `/std:c++latest` die Fehler C2280 und C2440 in Visual Studio 2019 aus:

```cpp
struct A
{
    A() = delete; // user-declared ctor
};

struct B
{
    B() = default; // user-declared ctor
    int i = 0;
};

A a{}; // ill-formed in C++20, previously well-formed
B b = { 1 }; // ill-formed in C++20, previously well-formed
```

### <a name="partial-support-for-operator-"></a>Teilweise Unterstützung für den Operator „<=>“

[P0515R3](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0515r3.pdf) C++20 führt den Operator für Dreiwegevergleiche `<=>` ein, der auch als „Raumschiffoperator“ bekannt ist. Visual Studio 2019 im `/std:c++latest`-Modus führt teilweise Unterstützung für den Operator ein, indem Fehler für die Syntax ausgelöst wird, die nun unzulässig ist. Der folgende Code wird beispielsweise in Visual Studio 2017 fehlerfrei kompiliert, löst gemäß `/std:c++latest` in Visual Studio 2019 jedoch mehrere Fehler aus:

```cpp
struct S
{
       bool operator<=(const S&) const { return true; }
};

template <bool (S::*)(const S&) const>
struct U { };
int main(int argc, char** argv)
{
       U<&S::operator<=> u; // In Visual Studio 2019 raises C2039, 2065, 2146.
}
```

Fügen Sie ein Leerzeichen in die betroffene Zeile vor der letzten geschweiften Klammer ein, um die Fehler zu vermeiden: `U<&S::operator<= > u;`.

### <a name="references-to-types-with-mismatched-cv-qualifiers"></a>Verweise auf Typen mit nicht übereinstimmenden CV-Qualifizierern

MSVC hat zuvor die direkte Einbindung von Verweisen auf einen Typ mit nicht übereinstimmenden CV-Qualifizierern unter der obersten Ebene zugelassen. Die könnte die Anpassung vermeintlicher const-Daten erlauben, auf die verwiesen wird, und der Compiler erstellt nun gemäß des Standards einen temporären Wert. In Visual Studio 2017 wird der folgende Code ohne Warnungen kompiliert. In Visual Studio 2019 löst der Compiler die *Warnung C4172 aus: \<func:#1 "?PData@X@@QBEABQBXXZ"> Adresse einer lokalen Variablen oder eines temporären Werts wird zurückgegeben*.

```cpp
struct X
{
    const void* const& PData() const
    {
        return _pv;
    }

    void* _pv;
};

int main()
{
    X x;
    auto p = x.PData(); // C4172
}
```
### <a name="reinterpretcast-from-an-overloaded-function"></a>Der Operator `reinterpret_cast` einer überladenen Funktion

Das Argument für `reinterpret_cast` entspricht keinem der Kontexte, in denen die Adresse einer überladenen Funktion zulässig ist. Der folgende Code wird in Visual Studio 2017 fehlerfrei kompiliert. In Visual Studio 2019 wird jedoch die folgende Warnung ausgelöst: *C2440: 'overloaded-function' kann nicht in 'fp' konvertiert werden*:

```cpp
int f(int) { return 1; }
int f(float) { return .1f; }
using fp = int(*)(int);

int main()
{
    fp r = reinterpret_cast<fp>(&f);
}
```

Verwenden Sie für dieses Szenario eine zulässige Umwandlung, um den Fehler zu vermeiden:

```cpp
int f(int);
int f(float);
using fp = int(*)(int);

int main()
{
    fp r = static_cast<fp>(&f); // or just &f;
}
```

### <a name="lambda-closures"></a>Lambda-Closures

Gemäß C++14 sind Lambda-Closure-Typen nicht literal. Die primäre Folge dieser Regel ist, dass ein Lambda keinen `constexpr`-Variablen zugewiesen werden kann. Der folgende Code wird in Visual Studio 2017 fehlerfrei kompiliert, löst in Visual Studio 2019 jedoch die Warnung *C2127: 'l': ungültige Initialisierung der Entität 'constexpr' mit einem nicht konstanten Ausdruck* aus:

```cpp
int main()
{
    constexpr auto l = [] {}; // C2127 in VS2019
}
```

Entfernen Sie entweder den `constexpr`-Qualifizierer, oder ändern Sie den Konformitätsmodus in `/std:c++17`, um diesen Fehler zu vermeiden.

### <a name="stdcreatedirectory-failure-codes"></a>Fehlercodes für std::create_directory

[P1164](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2019/p1164r1.pdf) des C++20-Standards wurde bedingungslos implementiert. Dadurch wurde `std::create_directory` so geändert, dass überprüft wird, ob das Ziel beim Auftreten des Fehlers bereits ein Verzeichnis war. Zuvor wurden alle Fehler vom Typ ERROR_ALREADY_EXISTS in erfolgreiche Codes umgewandelt, die jedoch kein Verzeichnis erstellt haben.

### <a name="operatorstdostream-nullptrt"></a>operator<<(std::ostream, nullptr_t)

Gemäß [LWG 2221](https://cplusplus.github.io/LWG/issue2221) wurde `operator<<(std::ostream, nullptr_t)` zum Schreiben von nullptrs in Streams hinzugefügt. 

### <a name="additional-parallel-algorithms"></a>Zusätzliche parallele Algorithmen

Neue parallele Versionen von `is_sorted`, `is_sorted_until`, `is_partitioned`, `set_difference`, `set_intersection`, `is_heap` und `is_heap_until` wurden hinzugefügt.

### <a name="atomic-initialization"></a>Atomische Initialisierung

[P0883 "Fixing atomic initialization"](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0883r1.pdf) (Beheben der atomischen Initialisierung) ändert `std::atomic` in die Initialisierung des enthaltenen Werts von T, anstatt eine Standardinitialisierung durchzuführen. Die Behebung wird aktiviert, wenn Clang/LLVM mit der Microsoft-Standardbibliothek verwendet wird. Sie ist derzeit für den C++-Compiler von Microsoft als Workaround für einen Fehler in der Verarbeitung von constexpr deaktiviert.

### <a name="removecvref-and-removecvreft"></a>remove_cvref und remove_cvref_t

Die Typmerkmale `remove_cvref` und `remove_cvref_t` aus [P0550](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0550r2.pdf) wurden implementiert. Diese entfernen die reference- und CV-Qualifizierer eines Typs ohne verfallende Funktionen und Arrays in Zeigern (im Gegensatz zu `std::decay` und `std::decay_t`).

### <a name="feature-test-macros"></a>Makros für Featuretests

Die Entwicklung der [Featuretestmakros (P0941R2)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0941r2.html) ist nun abgeschlossen. Dadurch wird `__has_cpp_attribute` unterstützt. Featuretestmakros werden in allen Standardmodi unterstützt.

### <a name="prohibit-aggregates-with-user-declared-constructors"></a>Unterbinden von Aggregaten mit benutzerdeklarierten Konstruktoren

[C++20 P1008R1 - prohibiting aggregates with user-declared constructors (Unterbinden von Aggregaten mit benutzerdeklarierten Konstruktoren)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p1008r1.pdf) ist abgeschlossen.

## <a name="improvements_161"></a> Verbesserungen in Visual Studio 2019 Version 16.1

### <a name="char8t"></a>char8_t

[P0482r6](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0482r6.html). C++20 führt einen neuen Zeichentyp ein, der für die Darstellung von UTF-8-Codeeinheiten verwendet wird. U8-Zeichenfolgenliterale in C++20 verfügen über den Typ `const char8_t[N]` anstelle von `const char[N]` (der vorherige Typ). Ähnliche Änderungen wurden in [N2231](http://www.open-std.org/jtc1/sc22/wg14/www/docs/n2231.htm) für den C-Standard vorgeschlagen. Vorschläge für die Wiederherstellung der Abwärtskompatibilität von char8_t wurden in [P1423r0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2019/p1423r0.html) geäußert. In Visual Studio 2019 Version 16.1 wurde dem C++-Compiler von Microsoft Unterstützung für char8_t hinzugefügt, wenn die Compileroption **/Zc:char8_t** angegeben wird. Zukünftig erfolgt die Unterstützung mit [/std:c++latest](../../build/reference/std-specify-language-standard-version.md), was mithilfe von **/Zc:char8_t-** in das C++17-Verhalten zurückversetzt werden kann. Der EDG-Compiler, der IntelliSense betreibt, unterstützt dies noch nicht, weshalb vermeidbare Intune-spezifische Fehler auftreten, die sich nicht auf die tatsächliche Kompilierung auswirken.

#### <a name="example"></a>Beispiel

```cpp
const char* s = u8"Hello"; // C++17
const char8_t* s = u8"Hello"; // C++20
```

### <a name="stdtypeidentity-metafunction-and-stdidentity-function-object"></a>Die std::type_identity-Metafunktion und das std::identity-Funktionsobjekt

[P0887R1 type_identity](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0887r1.pdf). Die veraltete `std::identity`-Klassenvorlagenerweiterung wurde entfernt und durch die `std::type_identity`-Metafunktion und das `std::identity`-Funktionsobjekt von C++20 ersetzt. Beides ist nur in [/std:c++latest](../../build/reference/std-specify-language-standard-version.md) verfügbar. 

Im folgenden Beispiel wird die Veraltungswarnung C4996 für `std::identity` (in \<type_traits> definiert) in Visual Studio 2017 erzeugt: 

```cpp
#include <type_traits>

using T = std::identity<int>::type;
T x, y = std::identity<T>{}(x);
int i = 42;
long j = std::identity<long>{}(i);
```

Im folgenden Beispiel wird die Verwendung des neuen `std::identity`-Funktionsobjekts (in \<functional> definiert) gemeinsam mit der neuen `std::type_identity`-Metafunktion veranschaulicht:

```cpp
#include <type_traits>
#include <functional>

using T = std::type_identity<int>::type;
T x, y = std::identity{}(x);
int i = 42;
long j = static_cast<long>(i);
```

### <a name="syntax-checks-for-generic-lambdas"></a>Syntaxprüfung für generische Lambdas

Die neue Lambdaverarbeitung ermöglicht im Konformitätsmodus einige syntaktische Überprüfungen in generischen Lambdas in [/std:c++latest](../../build/reference/std-specify-language-standard-version.md) oder anderen Sprachmodi, die **/experimental:newLambdaProcessor** aufweisen. 

Dieser Code wird in Visual Studio 2017 fehlerfrei kompiliert, erzeugt in Visual Studio 2019 jedoch den Fehler *C2760: Syntaxfehler: Unerwartetes Token '\<id-expr>'. Erwartet: 'id-expression'* :

```cpp
void f() {
    auto a = [](auto arg) {
        decltype(arg)::Type t;
    };
}
```

Im folgenden Beispiel wird die richtige Syntax veranschaulicht, die nun vom Compiler erzwungen wird:

```cpp
void f() {
    auto a = [](auto arg) {
        typename decltype(arg)::Type t;
    };
}
```

### <a name="argument-dependent-lookup-for-function-calls"></a>Argumentbezogene Suchen nach Funktionsaufrufen

[P0846R0](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0846r0.html) (C++20) Die Möglichkeit, Funktionsvorlagen über argumentbezogene Suchen nach Funktionsaufrufausdrücken zu suchen, wurde mit expliziten Vorlagenargumenten erweitert. Erfordert **/std:c++latest**.

### <a name="designated-initialization"></a>Designierte Initialisierung

[P0329R4](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0329r4.pdf) (C++20) Die designierte Initialisierung ermöglicht, dass bestimmte Member in der Aggregatinitialisierung mithilfe der `Type t { .member = expr }`-Syntax ausgewählt werden können. Erfordert **/std:c++latest**.

### <a name="new-and-updated-standard-library-functions-c20"></a>Neue und aktualisierte Standardbibliotheksfunktionen (C++20)

- `starts_with()` und `ends_with()` für `basic_string` und `basic_string_view`.
- `contains()` für assoziative Container.
- `remove()`, `remove_if()` und `unique()` für ` list` und `forward_list` geben nun `size_type` zurück.
- `shift_left()` und `shift_right()` wurden zu \<algorithm> hinzugefügt.

## <a name="bug-fixes-and-behavior-changes-in-visual-studio-2019-rtw"></a>Fehlerbehebungen und Verhaltensänderungen in Visual Studio 2019 RTW

### <a name="correct-diagnostics-for-basicstring-range-constructor"></a>Richtige Diagnose für den Bereichskonstruktor „basic_string“

In Visual Studio 2019 unterdrückt der Bereichskonstruktor `basic_string` nicht mehr die Compilerdiagnose mit `static_cast`. Der folgende Code wird in Visual Studio 2017 fehlerfrei kompiliert, obwohl bei der Konvertierung von `wchar_t` in `char` ein Datenverlust auftreten kann, wenn `out` initialisiert wird:

```cpp
std::wstring ws = /* … */;
std::string out(ws.begin(), ws.end());
```

Visual Studio 2019 löst ordnungsgemäß die Warnung *C4244: Konvertierung von 'wchar_t' in 'const _Elem', möglicher Datenverlust* aus. Sie können std::string wie im folgenden Beispiel initialisieren, um die Warnung zu vermeiden:

```cpp
std::wstring ws = L"Hello world";
std::string out;
for (wchar_t ch : ws)
{
    out.push_back(static_cast<char>(ch));
}
```

### <a name="incorrect-calls-to--and---under-clr-or-zw-are-now-correctly-detected"></a>Fehlerhafte Aufrufe von „+=“ und „-=“ in „/clr“ oder „/ZW“ werden nun ordnungsgemäß erkannt

Mit Visual Studio 2017 wurde ein Fehler eingeführt, durch den der Compiler Fehler stillschweigend ignoriert hat und keinen Code für ungültige Aufrufe von „+=“ und „-=“ in `/clr` oder `/ZW` generiert hat. Der folgende Code wird in Visual Studio 2017 fehlerfrei kompiliert, löst in Visual Studio 2019 jedoch ordnungsgemäß den *Fehler C2845: 'System::String ^': Zeigerarithmetik ist für diesen Typ nicht zulässig* aus:

```cpp
public enum class E { e };

void f(System::String ^s)
{
    s += E::e; // C2845 in VS2019
}
```

Verwenden Sie den Operator mit der Methode „ToString()“, um den Fehler in diesem Beispiel zu vermeiden: `s += E::e.ToString();`.

### <a name="initializers-for-inline-static-data-members"></a>Initialisierer für statische Inline-Datenmember

Ungültiger Memberzugriff innerhalb der Initialisierer `inline` und `static constexpr` wird nun ordnungsgemäß erkannt. Der folgende Beispielcode wird in Visual Studio 2017 fehlerfrei kompiliert, jedoch wird in Visual Studio 2019 im `/std:c++17`-Modus der *Fehler C2248: cannot access private member declared in class 'X'* (Zugriff auf den in der Klasse 'X' deklarierten Member ist nicht möglich) ausgelöst.

```cpp
struct X
{
    private:
        static inline const int c = 1000;
};

struct Y : X
{
    static inline int d = c; // C2248 in Visual Studio 2019
};
```

Deklarieren Sie den Member `X::c` als geschützt, um diesen Fehler zu vermeiden:

```cpp
struct X
{
    protected:
        static inline const int c = 1000;
};
```

### <a name="c4800-reinstated"></a>Wiederherstellung der Warnung C4800

MSVC hatte eine Leistungswarnung (C4800) für die implizite Konvertierung in boolesche Werte, die zu viele Störungen verursacht hat und nicht unterdrückbar war, weshalb diese in Visual Studio 2017 entfernt wurde. Allerdings gab es während des Lebenszyklus von Visual Studio 2017 viel Feedback zu den nützlichen Fällen, die dank dieser Warnung behoben werden konnten. Daher wurde die Warnung C4800 sorgfältig angepasst und mit der zugehörigen Warnung C4165 in Visual Studio 2019 wiedereingeführt. Beide können mithilfe einer expliziten Umwandlung oder einem Vergleich mit dem Wert 0 (null) des entsprechenden Typs mühelos unterdrückt werden. Die Warnung C4800 ist eine standardmäßig deaktivierte Warnung der Stufe 4, und die Warnung C4165 ist eine standardmäßig deaktivierte Warnung der Stufe 3. Beide können mithilfe der Compileroption `/Wall` gefunden werden.

Im folgenden Beispiel werden die Warnungen C4800 und C4165 in `/Wall` ausgelöst:

```cpp
bool test(IUnknown* p)
{
    bool valid = p; // warning C4800: Implicit conversion from 'IUnknown*' to bool. Possible information loss
    IDispatch* d = nullptr;
    HRESULT hr = p->QueryInterface(__uuidof(IDispatch), reinterpret_cast<void**>(&d));
    return hr; // warning C4165: 'HRESULT' is being converted to 'bool'; are you sure this is what you want?
}
```

Sie können den Code folgendermaßen schreiben, um die Warnungen im vorherigen Beispiel zu vermeiden:

```cpp
bool test(IUnknown* p)
{
    bool valid = p != nullptr; // OK
    IDispatch* d = nullptr;
    HRESULT hr = p->QueryInterface(__uuidof(IDispatch), reinterpret_cast<void**>(&d));
    return SUCCEEDED(hr);  // OK
}
```

### <a name="local-class-member-function-doesnt-have-a-body"></a>Lokale Klassenmemberfunktion enthält keinen Text

In Visual Studio 2017 wird die Warnung *C4822: Local class member function doesn't have a body* (Lokale Klassenmemberfunktion enthält keinen Text) nur ausgelöst, wenn die Compileroption `/w14822` explizit festgelegt ist. Sie wird nicht mit `/Wall` angezeigt. In Visual Studio 2019 ist die Warnung C4822 standardmäßig deaktiviert und in `/Wall` auffindbar, ohne dass `/w14822` explizit festgelegt sein muss.

```cpp
void foo()
{
    struct A
        {
            int boo(); // warning C4822
        };
}
```

### <a name="function-template-bodies-containing-constexpr-if-statements"></a>Funktionsvorlagentexte, die if constexpr-Anweisungen enthalten

Für Funktionsvorlagentexte, die `if constexpr`-Anweisungen enthalten, sind einige auf die Analyse bezogene `/permissive-`-Überprüfungen aktiviert. Der folgende Code würde in Visual Studio 2017 die Warnung *C7510: 'Type': use of dependent type name must be prefixed with 'typename'* ('Type': für die Verwendung des abhängigen Typnamens muss das Präfix 'typename' vorangestellt werden) nur erzeugen, wenn die `/permissive-`-Option nicht festgelegt ist. Der gleiche Code löst in Visual Studio 2019 Fehler aus, unabhängig davon, ob die `/permissive-`-Option festgelegt ist:

```cpp
template <typename T>

int f()
{
    T::Type a; // error C7510

    if constexpr (T::val)
    {
        return 1;
    }
    else
    {
        return 2;
    }
}

struct X
{
    using Type = X;
    constexpr static int val = 1;
};

int main()
{
    return f<X>();
}

```

Fügen Sie das Schlüsselwort `typename` zur Deklaration von `a` hinzu, um den Fehler zu vermeiden: `typename T::Type a;`.

### <a name="inline-assembly-code-is-not-supported-in-a-lambda-expression"></a>Inlineassemblycode wird in Lambdaausdrücken nicht unterstützt

Das Visual C++-Team wurde vor Kurzem auf ein Sicherheitsproblem hingewiesen, durch das die Verwendung von Inlineassemblern innerhalb eines Lambdaausdrucks bei der Ausführung zur Beschädigung von „edp“ (das Register für Rückgabeadressen) führen kann. Ein böswilliger Angreifer könnte sich dieses Szenario zunutze machen. Aufgrund der Art dieses Problems, der Tatsache, dass der Inlineassembler nur für x86 unterstützt wird, und wegen der mangelhaften Interaktion des Inlineassemblers mit dem Rest des Compilers, wurde das Verbieten von Inlineassemblern in Lambdaausdrücken als sicherste Lösung für dieses Problem ausgewählt.

Hinweis: Die einzige Verwendung eines Inlineassemblers innerhalb eines Lambdaausdrucks, die in freier Wildbahn angetroffen wurde, galt dem Erfassen der Rückgabeadresse. In diesem Szenario können Sie die Rückgabeadresse auf allen Plattformen erfassen, indem Sie einfach die intrinsische Compilerfunktion `_ReturnAddress()` verwenden.

Der folgende Code erzeugt die Warnung *C7552: Inlineassembler wird in einem Lambda-Ausdruck nicht unterstützt* sowohl in Visual Studio 2017 Version 15.9 als auch in Visual Studio 2019:

```cpp
#include <cstdio>

int f()
{
    int y = 1724;
    int x = 0xdeadbeef;

    auto lambda = [&]
    {
        __asm {

            mov eax, x
            mov y, eax
        }
    };

    lambda();
    return y;
}
```

Verschieben Sie den Assemblycode wie im folgenden Beispiel gezeigt in eine benannte Funktion, um diesen Fehler zu vermeiden:

```cpp
#include <cstdio>

void g(int& x, int& y)
{
    __asm {
        mov eax, x
        mov y, eax
    }
}

int f()
{
    int y = 1724;
    int x = 0xdeadbeef;
    auto lambda = [&]
    {
        g(x, y);
    };
    lambda();
    return y;
}

int main()
{
    std::printf("%d\n", f());
}
```

### <a name="iterator-debugging-and-stdmoveiterator"></a>Iteratordebuggen und std::move_iterator

Das Feature für das Iteratordebuggen kann `std::move_iterator` nun ordnungsgemäß entpacken. Beispielsweise kann `std::copy(std::move_iterator<std::vector<int>::iterator>, std::move_iterator<std::vector<int>::iterator>, int*)` nun den schnellen Pfad `memcpy` binden.

### <a name="fixes-for-xkeycheckh-keyword-enforcement"></a>Fehlerbehebung der Schlüsselworterzwingung \<xkeycheck.h>

Die makro-ähnliche Schlüsselworterzwingung \<xkeycheck.h> der Standardbibliothek wurde behoben, sodass nun das tatsächliche Schlüsselwort ermittelt wird, anstelle einer generischen Meldung. C++20-Schlüsselwörter werden ebenfalls unterstützt, und es wird vermieden, dass IntelliSense zufällige Schlüsselwörter als Makros erkennt.

### <a name="allocator-types-un-deprecated"></a>Aufgehobene Veraltung von Zuweisungstypen

Die Veraltung von `std::allocator<void>`, `std::allocator::size_type` und `std::allocator::difference_type` wurde aufgehoben.

### <a name="correct-warning-for-narrowing-string-conversions"></a>Richtige Warnungen für einschränkende Zeichenfolgenkonvertierungen

Ein `static_cast`-Operator, der fälschlicherweise nicht vom Standard aufgerufen wurde und C4244-Einschränkungswarnungen unterdrückt hat, wurde aus std::string entfernt. Der Versuch, `std::string::string(const wchar_t*, const wchar_t*)` aufzurufen, resultiert nun ordnungsgemäß in der Warnung *C4244: "narrowing a wchar_t into a char."* („wchar_t“ wird einschränkend in „char“ konvertiert).

### <a name="various-filesystem-correctness-fixes"></a>Verschiedene Korrekturen der Genauigkeit von \<filesystem>

- Das Fehlschlagen von `std::filesystem::last_write_time` beim Versuch, den letzten Schreibzugriff eines Verzeichnisses zu ändern, wurde behoben.
- Der Konstruktor `std::filesystem::directory_entry` speichert nun ein fehlgeschlagenes Ergebnis, anstatt eine Ausnahme auszulösen, wenn ein nicht vorhandener Zielpfad angegeben wird.
- Die Version von `std::filesystem::create_directory` mit zwei Parametern wurde geändert, sodass nun die Version mit einem Parameter aufgerufen wird, da die zugrundeliegende `CreateDirectoryExW`-Funktion `copy_symlink` ausführen würde, wenn „_p“ eine symbolische Verknüpfung ist.
- `std::filesystem::directory_iterator` schlägt nicht mehr fehl, wenn eine fehlerhafte symbolische Verknüpfung auftritt.
- `std::filesystem::space` akzeptiert jetzt relative Pfade.
- `std::filesystem::path::lexically_relative` wird nicht mehr durch nachstehende Schrägstriche behindert (siehe [LWG 3096](https://cplusplus.github.io/LWG/issue3096)).
- Das Ablehnen von Pfaden mit umgekehrten Schrägstrichen von `CreateSymbolicLinkW` in `std::filesystem::create_symlink` wurde behoben.
- Ein Problem wurde behoben, durch das die `delete`-Funktion des POSIX-Löschmodus unter Windows 10 LTSB 1609 vorhanden war, aber nicht in der Lage war, Dateien zu löschen.
- Die Kopierkonstruktoren und Kopierzuweisungsoperatoren von `std::boyer_moore_searcher` und `std::boyer_moore_horspool_searcher` sind nun in der Lage, Kopiervorgänge tatsächlich durchzuführen.

### <a name="parallel-algorithms-on-windows-8-and-later"></a>Parallele Algorithmen unter Windows 8 und höher

Die Bibliothek mit parallelen Algorithmen verwendet unter Windows 8 und höher nun ordnungsgemäß die echte `WaitOnAddress`-Familie, anstatt immer die gefälschten Versionen von Windows 7 und früher zu verwenden.

### <a name="stdsystemcategorymessage-whitespace"></a>Leerraum bei std::system_category::message()

`std::system_category::message()` schneidet nachstehenden Leerraum von der zurückgegebenen Meldung nun ab.

### <a name="stdlinearcongruentialengine-divide-by-zero"></a>Division durch 0 (null) bei std::linear_congruential_engine

Einige Bedingungen wurden behoben, die dazu führten, dass `std::linear_congruential_engine` eine Division durch 0 (null) durchführte.

### <a name="fixes-for-iterator-unwrapping"></a>Fehlerbehebungen für das Entpacken von Iteratoren

Die Funktion zum Entpacken von Iteratoren, die zuerst in Visual Studio 2017 Version 15.8 für Programmierer zur Verfügung gestellt wurde (wie unter https://devblogs.microsoft.com/cppblog/stl-features-and-fixes-in-vs-2017-15-8/ beschrieben), entpackt Iteratoren, die von Standardbibliotheksiteratoren abgeleitet wurden, nicht mehr. Ein Benutzer, der beispielsweise von `std::vector<int>::iterator` abgeleitet wird und versucht, das Verhalten anzupassen, erhält nun das angepasste Verhalten, wenn er Algorithmen der Standardbibliothek aufruft, anstelle des Verhaltens eines Zeigers.
Die reserve-Funktion für ungeordnete Container reserviert N-Elemente nun tatsächlich (siehe [LWG 2156](https://cplusplus.github.io/LWG/issue2156)).

### <a name="time-handling"></a>Behandlung von Zeit

- Zuvor führten einige Zeitwerte, die an die Parallelitätsbibliothek übergeben wurden, zu einem Überlauf, z. B. `condition_variable::wait_for(seconds::max())`. Diese mittlerweile behobenen Überläufe haben das Verhalten in einem scheinbar willkürlichen 29-tägigen Zyklus geändert (wenn von den zugrundeliegenden Win32-APIs akzeptierte uint32_t Millisekunden zu einem Überlauf führten).

- Der <ctime>-Header deklariert „timespec“ und „timespec_get“ im Namespace „std“ jetzt ordnungsgemäß und im globalen Namespace.

### <a name="various-fixes-for-containers"></a>Verschiedene Fehlerbehebungen für Container

- Viele interne Containerfunktionen der Standardbibliothek sind nun privat, um die Funktionsweise von IntelliSense zu verbessern. In zukünftigen Releases von MSVC sind weitere Fehlerbehebungen zu erwarten, die Member als privat kennzeichnen.

- Probleme bei der Richtigkeit der Ausnahmesicherheit, durch die knotenbasierte Container wie `list`, `map` und `unordered_map` beschädigt wurden, wurden behoben. Während einem `propagate_on_container_copy_assignment`- oder `propagate_on_container_move_assignment`-Neuzuweisungsvorgang würden Sie den Sentinelknoten des Containers mit der alten Zuweisung freistellen, die alte Zuweisung mit der POCCA/POCMA-Zuweisung überschreiben und dann versuchen, den Sentinelknoten der neuen Zuweisung abzurufen. Wenn diese Zuweisung fehlschlägt, ist der Container beschädigt und kann sogar nicht zerstört werden, da der Besitz eines Sentinelknotens eine feste Datenstrukturinvariante darstellt. Dieser Fehler wurde behoben, sodass der neue Sentinelknoten der Zuweisung des Quellcontainers zugewiesen wird, bevor der vorhandene Sentinelknoten zerstört wird.

- Die Container wurden behoben, sodass sie Zuweisungen immer in `propagate_on_container_copy_assignment`, `propagate_on_container_move_assignment` und `propagate_on_container_swap` kopieren/verschieben/tauschen. Dies gilt auch für Zuweisungen mit einer Deklaration von `is_always_equal`.

- Überladungen für Funktionen zum Zusammenführen von Containern und Extrahieren von Membern wurden hinzugefügt, die rvalue-Container gemäß [P0083 "Splicing Maps And Sets"](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/p0083r3.pdf) (Zusammenführen von Zuordnen und Festlegungen).

### <a name="stdbasicistreamread-processing-of-rn--n"></a>Verarbeitung von \r\n => \n durch std::basic_istream::read

`std::basic_istream::read` wurde behoben, sodass bei der Verarbeitung von \r\n => \n nicht temporär in den angegebenen Puffer geschrieben wird. Hierbei wird ein Teil des Leistungsvorteils geopfert, der in Visual Studio 2017 Version 15.8 für Lesevorgänge erzielt wurde, jedoch werden die Verbesserungen der Effizienz durch Vermeiden von 3 virtuellen Aufrufen pro Zeichen beibehalten.

### <a name="stdbitset-constructor"></a>Konstruktor von std::bitset

Der Konstruktor von `std::bitset` liest die Einsen und Nullen von großen Bitsets nicht mehr in umgekehrter Reihenfolge.

### <a name="stdpairoperator-regression"></a>Regression von std::pair::operator=

Eine Regression im Zuweisungsoperator von `std::pair` wurde behoben, die bei der Implementierung von [LWG 2729 "Missing SFINAE on std::pair::operator="; (SFINAE für std::pair::operator= fehlt)](https://cplusplus.github.io/LWG/issue2729) eingeführt wurde. Typen, die in `std::pair` konvertiert werden können, werden nun wieder ordnungsgemäß akzeptiert.

### <a name="non-deduced-contexts-for-addconstt"></a>Nicht abgeleitete Kontexte für add_const_t

Ein kleiner Fehler bei Typmerkmalen wurde behoben, bei dem `add_const_t` und zugehörige Funktionen einem nicht abgeleiteten Kontext entsprechen sollten. Das heißt, `add_const_t` sollte ein Alias für `typename add_const<T>::type` sein, nicht für `const T`.

## <a name="see-also"></a>Siehe auch

[Neues in Visual Studio 2019](../what-s-new-for-visual-cpp-in-visual-studio.md)