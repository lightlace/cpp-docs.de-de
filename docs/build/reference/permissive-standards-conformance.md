---
title: -liberalen - (Einhaltung von Standards) | Microsoft Docs
ms.date: 11/11/2016
ms.technology:
- cpp-tools
ms.topic: article
f1_keywords:
- /permissive
- VC.Project.VCCLCompilerTool.ConformanceMode
dev_langs:
- C++
helpviewer_keywords:
- /permissive compiler options [C++]
- -permissive compiler options [C++]
- Standards conformance compiler options
- permissive compiler options [C++]
ms.assetid: db1cc175-6e93-4a2e-9396-c3725d2d8f71
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 09b24e96752e61f4d09efc3780e0e60ffed8effd
ms.sourcegitcommit: eeb2b5ad8d3d22514a7b9bd7d756511b69ae0ccf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2018
---
# <a name="permissive--standards-conformance"></a>/ liberalen-(Einhaltung von Standards)

Geben Sie die Konformität der Standardmodus für den Compiler. Verwenden Sie diese Option, helfen Ihnen beim Identifizieren und Beheben der Konformitätsprobleme in Ihrem Code sie Richtigkeit und besser portierbar machen.

## <a name="syntax"></a>Syntax

> **/permissive-**

## <a name="remarks"></a>Hinweise

Sie können die **/ einschränkend sein-** -Compileroption Compilerverhalten standardkonformen angeben. Diese Option deaktiviert einschränkend sein Verhalten und legt die [/Zc](../../build/reference/zc-conformance.md) Compileroptionen für strikte Konformität. In der IDE ist diese Option auch IntelliSense-Modul "Unterstreichen" nicht konforme-Code.

Wird standardmäßig die **/ liberalen-** Option wird festgelegt, in neuen Projekten, die von Visual Studio 2017 Version 15.5 und höheren Versionen erstellt. Es ist nicht standardmäßig in früheren Versionen festgelegt. Wenn die Option festgelegt ist, der Compiler diagnostische Fehler generiert oder Warnungen, wenn nicht standardmäßige Sprachkonstrukte im Code erkannt werden, einschließlich einige häufige Fehler in der Pre-C ++ 11-Code.

Die **/ liberalen-** Option ist kompatibel mit fast allen die Headerdateien, von der neuesten Windows-Kits, z. B. das Software Development Kit (SDK) oder Windows-Treiber Kit (WDK), im Herbst Ersteller SDK für Windows (10.0.16299.0) ab. Ältere Versionen des SDK können nicht unter kompiliert **/ liberalen-** für verschiedene Code Konformität Gründe Datenquelle. Der Compiler und SDKs für andere Version Zeitachsen, daher entstehen verbleibenden Probleme. Probleme mit bestimmten Header, finden Sie unter [Probleme mit Windows-Header](#windows-header-issues) unten.

Die **/ liberalen-** -Option wird die [/Zc: strictstrings](../../build/reference/zc-conformance.md) und [/Zc: rvaluecast](../../build/reference/zc-conformance.md) Optionen konforme Verhalten. Sie standardmäßig nicht konforme Verhalten verwendet. Sie können bestimmte übergeben **/Zc** Optionen nach **/ liberalen-** in der Befehlszeile aus, um dieses Verhalten zu überschreiben.

In Versionen des Compilers Anfangs in Visual Studio 2017 Version 15.3 die **/ liberalen-** -Option wird die [/Zc:ternary](../../build/reference/zc-ternary.md) Option. Der Compiler implementiert auch weitere Anforderungen für Zweiphasen Namenssuche. Wenn die **/ liberalen-** Option festgelegt ist, wird der Compiler analysiert Funktion und der Klasse Vorlagendefinitionen, Identifizieren von abhängigen und nicht abhängigen Namen in den Vorlagen verwendet. In dieser Version wird nur die Abhängigkeitsanalyse Namen ausgeführt.

Umgebungsspezifische-Erweiterungen und Language-Bereiche, die der Standard der Implementierung verlässt sind nicht betroffen, durch **/ liberalen-**. Z. B. der Microsoft-spezifische `__declspec`, Aufrufkonvention und die strukturierte Ausnahmebehandlung Keywords-Eigenschaft, und compilerspezifisch pragma-Direktiven oder Attribute sind nicht gekennzeichnet, vom Compiler in **/ liberalen-** Modus.

Die **/ liberalen-** Option verwendet die Konformität-Unterstützung in der aktuellen Compilerversion an, um zu bestimmen, welche Sprachkonstrukte nicht konforme sind. Die Option wird nicht festgelegt, wenn Ihr Code auf eine bestimmte Version der C++-standard entspricht. Verwenden Sie zum Aktivieren aller implementierten Compiler-Unterstützung für die neuesten Entwurfsstandard der [/std:latest](../../build/reference/std-specify-language-standard-version.md) Option. Um die Unterstützung des Compilers, der derzeit implementierten C ++ 17-standard einzuschränken, verwenden die [/std:c ++ 17](../../build/reference/std-specify-language-standard-version.md) Option. Um die Unterstützung des Compilers weitestgehend mit dem C ++ 14-Standard mehr einzuschränken, verwenden die [/std:c ++ 14](../../build/reference/std-specify-language-standard-version.md) die Standardeinstellung ist die Option.

Nicht alle C ++ 11, C ++ 14 oder C ++ 17 standardkonformen Code wird vom Visual C++-Compiler in Visual Studio 2017 unterstützt. Die **/ liberalen-** Option möglicherweise Probleme im Hinblick auf einige Aspekte der zweiphasigen Namenssuche, binden einen nicht konstanten Verweis an einen temporären, Init Kopie wird als direkte Init behandelt, können mehrere benutzerdefinierte Konvertierungen in nicht erkannt Initialisierung oder alternativer Token für logische Operatoren und anderen Bereichen Übereinstimmung nicht unterstützt. Weitere Informationen über Konformitätsprobleme in Visual C++ finden Sie unter [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).

### <a name="how-to-fix-your-code"></a>Wie den Code diesen Fehler beheben

Hier sind einige Beispiele für Code, der als nicht konforme Verwendung erkannt **/ liberalen-**, zusammen mit vorgeschlagenen Möglichkeiten, um das Problem behoben haben.

#### <a name="use-default-as-an-identifier-in-native-code"></a>Verwenden Sie standardmäßig als Bezeichner in systemeigenem code

```cpp
void func(int default); // Error C2321: 'default' is a keyword, and
                        // cannot be used in this context
```

#### <a name="lookup-members-in-dependent-base"></a>Mitglieder der Suche in abhängigen Basis

```cpp
template <typename T>
struct B {
    void f();
};

template <typename T>
struct D : public B<T> // B is a dependent base because its type
                       // depends on the type of T.
{
    // One possible fix is to uncomment the following line.
    // If this is a type, don't forget the 'typename' keyword.
    // using B<T>::f;

    void g() {
        f(); // error C3861: 'f': identifier not found
             // Another fix is to change it to 'this->f();'
    }
};

void h() {
    D<int> d;
    d.g();
}
```

#### <a name="use-of-qualified-names-in-member-declarations"></a>Verwendung von qualifizierte Namen in Memberdeklarationen

```cpp
struct A {
    void A::f() { } // error C4596: illegal qualified name in member
                    // declaration.
                    // Remove redundant 'A::' to fix.
};
```

#### <a name="initialize-multiple-union-members-in-a-member-initializer"></a>Initialisieren Sie mehrere union-Member im Initialisierer für ein Element

```cpp
union U
{
    U()
        : i(1), j(1) // error C3442: Initializing multiple members of
                     // union: 'U::i' and 'U::j'.
                     // Remove all but one of the initializations to fix.
    {}
    int i;
    int j;
};
```

#### <a name="hidden-friend-name-lookup-rules"></a>Name-Suchregeln ausgeblendete "Friend"

```cpp
// Example 1
struct S {
    friend void f(S *);
};
// Uncomment this declaration to make the hidden friend visible:
// void f(S *); // This declaration makes the hidden friend visible

using type = void (*)(S *);
type p = &f; // error C2065: 'f': undeclared identifier.
```

```cpp
// Example 2
struct S {
    friend void f(S *);
};
void g() {
    // Using nullptr instead of S prevents argument dependent lookup in S
    f(nullptr); // error C3861: 'f': identifier not found

    S *p = nullptr;
    f(S); // Hidden friend now found via argument-dependent lookup.
}
```

#### <a name="use-scoped-enums-in-array-bounds"></a>Verwenden Sie die Bereichsbezogene Enumerationen in Arraygrenzen

```cpp
enum class Color {
    Red, Green, Blue
};

int data[Color::Blue]; // error C3411: 'Color' is not valid as the size
                       // of an array as it is not an integer type.
                       // Cast to type size_t or int to fix.
```

#### <a name="use-for-each-in-native-code"></a>Verwenden Sie für jede in systemeigenem code

```cpp
void func() {
    int array[] = {1, 2, 30, 40};
    for each (int i in array) // error C4496: nonstandard extension
                              // 'for each' used: replace with
                              // ranged-for statement:
                              // for (int i: array)
    {
        // ...
    }
}
```

#### <a name="use-of-atl-attributes"></a>Verwendung von ATL-Attributen

```cpp
// Example 1
[uuid("594382D9-44B0-461A-8DE3-E06A3E73C5EB")]
class A {};
```

```cpp
// Fix for example 1
class __declspec(uuid("594382D9-44B0-461A-8DE3-E06A3E73C5EB")) B {};
```

```cpp
// Example 2
[emitidl];
[module(name="Foo")];

[object, local, uuid("9e66a290-4365-11d2-a997-00c04fa37ddb")]
__interface ICustom {
    HRESULT Custom([in] longl, [out, retval] long*pLong);
    [local] HRESULT CustomLocal([in] longl, [out, retval] long*pLong);
};

[coclass, appobject, uuid("9e66a294-4365-11d2-a997-00c04fa37ddb")]
class CFoo : public ICustom
{};
```

```cpp
// Fix for example 2
// First, create the *.idl file. The vc140.idl generated file can be 
// used to automatically obtain a *.idl file for the interfaces with 
// annotation. Second, add a midl step to your build system to make 
// sure that the C++ interface definitions are outputted. 
// Last, adjust your existing code to use ATL directly as shown in 
// the atl implementation section.

-- IDL  FILE--
import "docobj.idl";

[object, local, uuid(9e66a290-4365-11d2-a997-00c04fa37ddb)]
interface ICustom : IUnknown {
    HRESULT Custom([in] longl, [out,retval] long*pLong);
    [local] HRESULT CustomLocal([in] longl, [out,retval] long*pLong);
};

[ version(1.0), uuid(29079a2c-5f3f-3325-99a1-3ec9c40988bb) ]
library Foo {
    importlib("stdole2.tlb");
    importlib("olepro32.dll");

    [version(1.0), appobject, uuid(9e66a294-4365-11d2-a997-00c04fa37ddb)]
    coclass CFoo { interface ICustom; };
}

-- ATL IMPLEMENTATION--
#include <idl.header.h>
#include <atlbase.h>

class ATL_NO_VTABLE CFooImpl : public ICustom,
    public ATL::CComObjectRootEx<CComMultiThreadModel>
{
    public:BEGIN_COM_MAP(CFooImpl)
    COM_INTERFACE_ENTRY(ICustom)
    END_COM_MAP()
};
```

#### <a name="ambiguous-conditional-operator-arguments"></a>Mehrdeutige Bedingungsoperator Argumente

In Versionen des Compilers vor Visual Studio 2017 Version 15.3, akzeptiert der Compiler Argumente der bedingte Operator (oder ternärer Operator) `?:` mehrdeutig gemäß dem Standard angesehen. In **/ liberalen-** Modus, der Compiler gibt jetzt eine oder mehrere Diagnosen in Fällen, die Kompilierung ohne die Diagnose in früheren Versionen.

Common Fehlern können aus dieser Änderung sind:

- Fehler C2593 generiert: "Operator"? ist nicht eindeutig

- Fehler C2679 generiert: Binär '?': Es konnte kein Operator gefunden werden, der einen rechten Operanden vom Typ 'B' akzeptiert (oder keine geeignete Konvertierung)

- Fehler C2678: binäre '?': Es konnte kein Operator gefunden werden, der einen linksseitigen Operanden vom Typ "A" akzeptiert (oder keine geeignete Konvertierung)

- Fehler C2446: ':': keine Konvertierung von 'B' in 'A'

Eine typische Code, Muster, die dieses Problem verursachen kann, entsteht durch einige Klasse C einer nicht expliziten Konstruktor von einem anderen Typ T und einer nicht expliziten Konvertierungsoperator Typ t enthält In diesem Fall sind die Konvertierung des 2. Arguments in den Typ des der 3rd und die Konvertierung des 3. Arguments in den Typ des der 2. gültige Konvertierungen gemäß dem Standard mehrdeutig ist.

```cpp
// Example 1: class that provides conversion to and initialization from some type T
struct A
{
    A(int);
    operator int() const;
};

extern bool cond;

A a(42);
// Accepted when /Zc:ternary or /permissive- is not used:
auto x = cond ? 7 : a; // A: permissive behavior prefers A(7) over (int)a
// Accepted always:
auto y = cond ? 7 : int(a);
auto z = cond ? A(7) : a;
```

Besteht eine wichtige Ausnahme dieses allgemeine Muster, wenn T einer der Null-terminierte Zeichenfolgentypen darstellt (z. B. `const char *`, `const char16_t *`usw.) und das tatsächliche Argument `?:` ist eine Zeichenfolge literal des entsprechenden Typs. C ++ 17-Semantik von C ++ 14 geändert. Daher wird der Code in Beispiel 2 unter akzeptiert **/std:c ++ 14** und abgelehnten unter **/std:c ++ 17** Wenn **/Zc:ternary** oder **/permissive-**verwendet wird.

```cpp
// Example 2: exception from the above
struct MyString
{
    MyString(const char* s = "") noexcept;  // from char*
    operator const char* () const noexcept; //   to char*
};

extern bool cond;

MyString s; 
// Using /std:c++14, /permissive- or /Zc:ternary behavior
// is to prefer MyString("A") over (const char*)s
// but under /std:c++17 this line causes error C2445:
auto x = cond ? "A" : s;
// You can use a static_cast to resolve the ambiguity:
auto y = cond ? "A" : static_cast<const char*>(s);
```

Ein weiterer Fall, in denen möglicherweise Fehler angezeigt, wird, in Bedingte Operatoren mit einem Argument des Typs `void`. Dieser Fall kann häufig in der ASSERT-ähnliche Makros sein.

```cpp
// Example 3: void arguments
void myassert(const char* text, const char* file, int line);
// Accepted when /Zc:ternary or /permissive- is not used:
#define ASSERT_A(ex) (void)((ex) ? 1 : myassert(#ex, __FILE__, __LINE__))
// Accepted always:
#define ASSERT_B(ex) (void)((ex) ? void() : myassert(#ex, __FILE__, __LINE__))
```

Sie können z. B. in der Vorlage Metaprogrammierung, in dem Bedingungsoperator Ergebnistypen unter ändern können auch auftreten **/Zc:ternary** und **/ liberalen-**. Eine Möglichkeit zum Beheben dieses Problems ist die Verwendung [std::remove_reference](../../standard-library/remove-reference-class.md) auf dem sich ergebenden Typ.

```cpp
// Example 4: different result types 
extern bool cond;
extern int count;
char  a = 'A'; 
const char  b = 'B'; 
decltype(auto) x = cond ? a : b; // char without, const char& with /Zc:ternary 
const char (&z)[2] = count > 3 ? "A" : "B"; // const char* without /Zc:ternary 
```

#### <a name="two-phase-name-look-up-partial"></a>Zweiphasen-Namen suchen (teilweise)

Wenn die **/ liberalen-** in Visual Studio 2017 Version 15.3 Option festgelegt ist, wird der Compiler analysiert Funktion und der Klasse Vorlagendefinitionen, Identifizieren von abhängigen und nicht abhängigen Namen in Vorlagen nach Bedarf für Zweiphasen-Namen verwendet Suche. In dieser Version wird nur die Abhängigkeitsanalyse Namen ausgeführt. Insbesondere dazu führen, dass nicht abhängigen Namen, die nicht im Kontext der Vorlagendefinition deklariert werden eine diagnosemeldung, gemäß dem ISO C++-Standards. Allerdings Binden von nicht abhängigen Namen, die erfordern, dass das Argument abhängige Nachschlagen im Kontext Definition erfolgt nicht.

```cpp
// dependent base
struct B {
    void g();
};

template<typename T>
struct D : T {
    void f() {
        // The call to g was incorrectly allowed in VS2017:
        g();  // Now under /permissive-: C3861
        // Possible fixes:
        // this->g();
        // T::g();
    }
};

int main()
{
    D<B> d;
    d.f();
}
```

### <a name="windows-header-issues"></a>Probleme mit Windows-header

Die **/ liberalen-** Option ist für Versionen von Windows-Kits, bevor Windows fallen Ersteller Update SDK (10.0.16299.0) oder die Version Windows Treiber Treiberkits (WDK) 1709 zu streng. Es wird empfohlen, Sie auf die neuesten Versionen der Windows-Kits aktualisieren, damit verwenden **/ liberalen-** im Code-Treiber Windows oder ein Gerät.

Bestimmte Header-Dateien in Windows fallen Ersteller Update SDK (10.0.16299.0) oder das Windows-Treiber Kit (WDK) 1709, immer noch Probleme, die sie durch Verwendung einer inkompatiblen machen **/ liberalen-**. Um diese Probleme zu umgehen, sollten Sie die Verwendung dieser Header auf nur diese Quellcodedateien, die sie benötigen, und entfernen Sie einschränken, die **/ liberalen-** option, wenn Sie diese bestimmte Quellcodedateien kompilieren. Die folgenden Probleme gelten für Windows fallen Ersteller Update SDK (10.0.16299.0) zur Verfügung:

#### <a name="issue-in-umqueryh"></a>Problem beim um\Query.h

Bei Verwendung der **/ liberalen-** -Compilerschalter verwenden, die `tagRESTRICTION` Struktur nicht aufgrund der case(RTOr) Member kompiliert 'oder'.

```cpp
struct tagRESTRICTION
    {
    ULONG rt;
    ULONG weight;
    /* [switch_is][switch_type] */ union _URes
        {
        /* [case()] */ NODERESTRICTION ar;
        /* [case()] */ NODERESTRICTION or;  // error C2059: syntax error: '||'
        /* [case()] */ NODERESTRICTION pxr;
        /* [case()] */ VECTORRESTRICTION vr;
        /* [case()] */ NOTRESTRICTION nr;
        /* [case()] */ CONTENTRESTRICTION cr;
        /* [case()] */ NATLANGUAGERESTRICTION nlr;
        /* [case()] */ PROPERTYRESTRICTION pr;
        /* [default] */  /* Empty union arm */
        } res;
    };
```

Um dieses Problem zu beheben, kompilieren Sie Dateien, Query.h ohne einschließlich, die **/ liberalen-** Option.

#### <a name="issue-in-umcellularapioemh"></a>Issue in um\cellularapi_oem.h

Bei Verwendung der **/ liberalen-** Compilerschalter, die Vorwärtsdeklaration `enum UICCDATASTOREACCESSMODE` bewirkt, dass eine Warnung:

```cpp
typedef enum UICCDATASTOREACCESSMODE UICCDATASTOREACCESSMODE; // C4471
```

Die Vorwärtsdeklaration ohne bereichseinschränkung ist eine Microsoft-Erweiterung. Um dieses Problem zu beheben, kompilieren Sie Dateien, cellularapi_oem.h ohne einschließlich, die **/ liberalen-** oder verwenden Sie die [/WD](../../build/reference/compiler-option-warning-level.md) Option aus, um die Warnung C4471 unterdrücken.

#### <a name="issue-in-umomscripth"></a>Issue in um\omscript.h

In C ++ 03 eine Konvertierung von einem Zeichenfolgenliteral zu BSTR (d. h. einer Typdefinition, "Wchar_t *") ist als veraltet markiert, aber zulässig. In C ++ 11 ist die Konvertierung nicht mehr zulässig.

```cpp
virtual /* [id] */ HRESULT STDMETHODCALLTYPE setExpression(
    /* [in] */ __RPC__in BSTR propname,
    /* [in] */ __RPC__in BSTR expression,
    /* [in][defaultvalue] */ __RPC__in BSTR language = L"") = 0; // C2440
```

Um dieses Problem zu beheben, kompilieren Sie Dateien, omscript.h ohne einschließlich, die **/ liberalen-** oder verwenden Sie **/Zc:strictStrings-** stattdessen.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

Verwenden Sie in Visual Studio 2017 Version 15.5 und höher dieses Verfahren aus:

1. Öffnen Sie das Projekt **Eigenschaftenseiten** (Dialogfeld).

1. Unter **Konfigurationseigenschaften**, erweitern Sie die **C/C++-** Ordner, und wählen Sie die **Sprache** Eigenschaftenseite.

1. Ändern der **Konformitätsmodus** Eigenschaftswert an **Ja (/ liberalen-)**. Wählen Sie **OK** oder **übernehmen** zum Speichern der Änderungen.

Verwenden Sie in Versionen vor Visual Studio 2017 Version 15.5 dieses Verfahren:

1. Öffnen Sie das Projekt **Eigenschaftenseiten** (Dialogfeld).

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **Befehlszeile** Eigenschaftenseite.

1. Geben Sie die **/ liberalen-** -Compileroption in der **Zusatzoptionen** Feld. Wählen Sie **OK** oder **übernehmen** zum Speichern der Änderungen.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)   
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)
