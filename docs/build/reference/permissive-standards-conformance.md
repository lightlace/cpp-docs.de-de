---
title: / PERMISSIVE--(Übereinstimmung mit Standards)
ms.date: 06/21/2018
f1_keywords:
- /permissive
- VC.Project.VCCLCompilerTool.ConformanceMode
helpviewer_keywords:
- /permissive compiler options [C++]
- -permissive compiler options [C++]
- Standards conformance compiler options
- permissive compiler options [C++]
ms.assetid: db1cc175-6e93-4a2e-9396-c3725d2d8f71
ms.openlocfilehash: 5590996c7598016365bb122977084835830f95ab
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57820792"
---
# <a name="permissive--standards-conformance"></a>/ PERMISSIVE--(Übereinstimmung mit Standards)

Geben Sie die Konformität der Standardmodus für den Compiler. Verwenden Sie diese Option, um zu erkennen und beheben Konformitätsprobleme in Ihrem Code sowohl korrekter und besser portierbar.

## <a name="syntax"></a>Syntax

> **/permissive-**

## <a name="remarks"></a>Hinweise

Diese Option wird in Visual Studio 2017 und höher unterstützt.

Sie können die **/ PERMISSIVE--** -Compileroption verwenden, um die standardkonforme Compilerverhalten anzugeben. Diese Option deaktiviert die höchste Verhalten und legt die [/Zc](zc-conformance.md) Compileroptionen für strikte Konformität. In der IDE ist diese Option auch IntelliSense-Engine "Unterstreichen" nicht konforme-Code.

In der Standardeinstellung die **/ PERMISSIVE--** Option wird festgelegt, in neuen Projekten, die von Visual Studio 2017 Version 15.5 und höher erstellt. Es ist nicht standardmäßig in früheren Versionen festgelegt. Wenn die Option festgelegt ist, der Compiler diagnostische Fehler generiert oder Warnungen, wenn nicht standardmäßige Sprachkonstrukte, die in Ihrem Code erkannt werden, einschließlich der einige häufige Fehler in vor-C ++ 11-Code.

Die **/ PERMISSIVE--** Option ist kompatibel mit fast allen die Header-Dateien aus den neuesten Windows-Kits, z. B. Software Development Kit (SDK) oder Windows Driver Kit (WDK), das Windows Fall Creators-SDK (10.0.16299.0) ab. Ältere Versionen des SDK können nicht unter kompiliert **/ PERMISSIVE--** für verschiedene aus der Code Konformitätsgründen Datenquelle. Der Compiler und den Versand von SDKs für andere Version von Zeitachsen, daher gibt es einige andere sind. Bestimmte Header-Datei finden Sie [Probleme der Windows-Header](#windows-header-issues) unten.

Die **/ PERMISSIVE--** Optionssätze der [/Zc: strictstrings](zc-conformance.md) und [/Zc: rvaluecast](zc-conformance.md) Optionen konforme Verhalten. Wird standardmäßig nicht konformes Verhalten. Sie können bestimmte übergeben **/Zc** Optionen nach **/ PERMISSIVE--** in der Befehlszeile zum Überschreiben dieses Verhaltens.

In Versionen des Compilers Anfangs in Visual Studio 2017 Version 15.3 führt das **/ PERMISSIVE--** Optionssätze der [/Zc:ternary](zc-ternary.md) Option. Der Compiler implementiert außerdem weitere Anforderungen für die Zweiphasen-Namenssuche. Wenn die **/ PERMISSIVE--** Option festgelegt ist, wird der Compiler analysiert die Funktion und der Klasse Vorlagendefinitionen identifizierenden abhängige und unabhängige Namen, die in den Vorlagen verwendet. In dieser Version wird nur die Abhängigkeitsanalyse Namen ausgeführt.

Umgebung-spezifische Erweiterungen und Language-Bereiche, die der Standard der Implementierung lässt sind nicht betroffen, durch **/ PERMISSIVE--**. Z. B. der Microsoft-spezifische `__declspec`, Aufrufkonvention und strukturierte Ausnahmebehandlung, Schlüsselwörter und compilerspezifischen Pragma-Anweisungen oder Attribute werden nicht vom Compiler als gekennzeichnet **/ PERMISSIVE--** Modus.

Die **/ PERMISSIVE--** Option verwendet die Übereinstimmung mit Standards-Unterstützung in der aktuellen Compilerversion, um zu bestimmen, welche Sprachkonstrukte werden nicht konforme. Die Option wird nicht festgelegt werden, wenn Ihr Code eine bestimmte Version von der C++-standard entspricht. Um alle implementierten Compiler-Unterstützung für den neuesten Draft Standard zu aktivieren, verwenden die [/std:latest](std-specify-language-standard-version.md) Option. Um die Unterstützung des Compilers auf den derzeit implementierten C ++ 17-standard zu beschränken, verwenden Sie die [/Std: c ++ 17](std-specify-language-standard-version.md) Option. Um die Unterstützung des Compilers weitestgehend mit dem C ++ 14-Standard mehr einzuschränken, verwenden die [/Std: c ++ 14](std-specify-language-standard-version.md) Option, die der Standardwert ist.

Nicht alle C ++ 11, C ++ 14 und C ++ 17 standardkonforme Code wird von der MSVC-Compiler in Visual Studio 2017 unterstützt. Abhängig von der Version von Visual Studio die **/ PERMISSIVE--** Option möglicherweise nicht erkennen von Problemen in Bezug auf einige Aspekte des Zweiphasen-Namenssuche, binden einen nicht konstanten Verweis an einen temporären, Kopie Init als direkte Init behandelt, sodass mehrere benutzerdefinierte Konvertierungen in einer Initialisierung oder alternativer Token für die logischen Operatoren und anderen Bereichen der Konformität nicht unterstützt. Weitere Informationen über Konformitätsprobleme in Visual C++ finden Sie unter [Nonstandard Behavior](../../cpp/nonstandard-behavior.md). Die Leistungsfähigkeit der abzurufenden **/ PERMISSIVE--**, Visual Studio auf die neueste Version zu aktualisieren.

### <a name="how-to-fix-your-code"></a>Wie Sie Ihren Code zu beheben

Hier sind einige Beispiele für Code, der erkannt wird, als nicht konforme Verwendung **/ PERMISSIVE--**, sowie Vorschläge für die Probleme zu beheben.

#### <a name="use-default-as-an-identifier-in-native-code"></a>Verwenden Sie die Standardeinstellung als Bezeichner in nativem code

```cpp
void func(int default); // Error C2321: 'default' is a keyword, and
                        // cannot be used in this context
```

#### <a name="lookup-members-in-dependent-base"></a>Lookup-Member in abhängigen Basis

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

#### <a name="use-of-qualified-names-in-member-declarations"></a>Verwenden der qualifizierte Namen in den Memberdeklarationen

```cpp
struct A {
    void A::f() { } // error C4596: illegal qualified name in member
                    // declaration.
                    // Remove redundant 'A::' to fix.
};
```

#### <a name="initialize-multiple-union-members-in-a-member-initializer"></a>Mehrere union-Member in Memberinitialisierer initialisieren

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

#### <a name="hidden-friend-name-lookup-rules"></a>Suchregeln für ausgeblendete Friend-name

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

#### <a name="use-scoped-enums-in-array-bounds"></a>Verwenden von bereichsbezogenen Enumerationen in der Arraygrenzen

```cpp
enum class Color {
    Red, Green, Blue
};

int data[Color::Blue]; // error C3411: 'Color' is not valid as the size
                       // of an array as it is not an integer type.
                       // Cast to type size_t or int to fix.
```

#### <a name="use-for-each-in-native-code"></a>Bei den einzelnen in nativem code

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

#### <a name="ambiguous-conditional-operator-arguments"></a>Mehrdeutige Bedingungsoperator-Argumente

In Versionen des Compilers vor Visual Studio 2017 Version 15.3, akzeptiert der Compiler Argumente der bedingte Operator (oder ein ternärer Operator) `?:` , gelten als nicht eindeutig durch den Standard. In **/ PERMISSIVE--** Modus, der Compiler gibt jetzt eine oder mehrere Diagnosen in Fällen, die ohne Diagnose in früheren Versionen kompiliert.

Common-Fehler, die durch diese Änderung verursacht möglicherweise sind:

- error C2593: 'operator ?' ist nicht eindeutig

- Fehler C2679 generiert: binäre '?': Es konnte kein Operator gefunden werden, der einen rechtsseitigen Operanden vom Typ "B" akzeptiert (oder es ist keine zulässige Konvertierung)

- Fehler C2678: binäre '?': Es konnte kein Operator gefunden werden, der einen linksseitigen Operanden vom Typ "A" akzeptiert (oder es ist keine zulässige Konvertierung)

- Fehler C2446: ":": keine Konvertierung von 'B' in 'A'

Eine typische Codemuster, die dieses Problem verursachen können ist, wenn eine Klasse C zu Typ "t". ein nichtexpliziter Konstruktor von einem anderen Typ T und eine nicht explizite Konvertierungsoperator bereitstellt In diesem Fall sind sowohl für die Konvertierung des 2. Arguments in den Typ der 3. als auch für die Konvertierung des 3. Arguments in den Typ der 2. gültige Konvertierungen, die gemäß dem Standard nicht eindeutig ist.

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

Besteht eine wichtige Ausnahme dieses allgemeine Muster, wenn T einer der Null-terminierte Zeichenfolgentypen darstellt (z. B. `const char *`, `const char16_t *`usw.) und das tatsächliche Argument auf `?:` ist eine Zeichenfolge Literale des entsprechenden Typs. C ++ 17 wurde Semantik von C ++ 14 geändert werden. Daher wird der Code in Beispiel 2 unter akzeptiert **/Std: c ++ 14** oder abgelehnte unter **/Std: c ++ 17** beim **/Zc:ternary** oder **/permissive-** verwendet wird.

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

Ein weiterer Fall, in denen möglicherweise Fehler angezeigt, wird, in bedingten Operatoren mit einem Argument des Typs `void`. Dieser Fall kann häufig in der ASSERT-ähnliche Makros sein.

```cpp
// Example 3: void arguments
void myassert(const char* text, const char* file, int line);
// Accepted when /Zc:ternary or /permissive- is not used:
#define ASSERT_A(ex) (void)((ex) ? 1 : myassert(#ex, __FILE__, __LINE__))
// Accepted always:
#define ASSERT_B(ex) (void)((ex) ? void() : myassert(#ex, __FILE__, __LINE__))
```

Sie sehen möglicherweise auch Fehler in Vorlage Metaprogrammierung, auf denen Ergebnistypen der bedingte Operator unter ändern können **/Zc:ternary** und **/ PERMISSIVE--**. Eine Möglichkeit zum Beheben dieses Problems ist die Verwendung [std::remove_reference](../../standard-library/remove-reference-class.md) auf dem sich ergebenden Typ.

```cpp
// Example 4: different result types
extern bool cond;
extern int count;
char  a = 'A';
const char  b = 'B';
decltype(auto) x = cond ? a : b; // char without, const char& with /Zc:ternary
const char (&z)[2] = count > 3 ? "A" : "B"; // const char* without /Zc:ternary
```

#### <a name="two-phase-name-look-up"></a>Zweiphasen-Namen suchen

Wenn die **/ PERMISSIVE--** Option festgelegt ist, wird der Compiler analysiert die Funktion und der Klasse Vorlagendefinitionen, abhängige und unabhängige Namen in Vorlagen nach Bedarf für Zweiphasen-Namenssuche identifizieren. In Visual Studio 2017 Version 15.3 wird die Abhängigkeitsanalyse Namen ausgeführt. Vor allem dazu führen, dass nicht abhängigen Namen, die nicht im Kontext der Vorlagendefinition deklariert sind eine diagnosemeldung gemäß dem ISO C++-Standards. In Visual Studio 2017 Version 15.7 wird die Bindung von nicht abhängigen-Namen, die Argument abhängige Suche in der Definition Kontext erfordern auch durchgeführt.

```cpp
// dependent base
struct B {
    void g() {}
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

Wenn Sie das Legacyverhalten für die Zweiphasen-Suche, aber andernfalls **/ PERMISSIVE--** Verhalten hinzufügen der **/Zc:twoPhase-** Option.

### <a name="windows-header-issues"></a>Windows-Header-Probleme

Die **/ PERMISSIVE--** Option ist für Versionen von der Windows-Kits, bevor Windows Fall Creators Update SDK (10.0.16299.0) oder die Windows-Treiberkit (WDK)-Version 1709 zu streng. Es wird empfohlen, Sie auf die neuesten Version von der Windows-Kits aktualisieren, damit verwenden **/ PERMISSIVE--** in Ihrem Code für Windows oder ein Gerät Treiber.

Bestimmte Headerdateien in der Windows-April 2018 Update SDK (10.0.17134.0), das Windows Fall Creators Update SDK (10.0.16299.0) oder Windows Driver Kit (WDK) 1709 immer noch Probleme, die sie mit der Verwendung von nicht kompatibel machen **/permissive-**. Um diese Probleme zu umgehen, sollten Sie die Verwendung dieser Header einschränken, um nur die Quellcodedateien, in denen diese, und Entfernen der **/ PERMISSIVE--** option, wenn Sie diese bestimmte Quellcodedateien kompilieren.

Diese Veröffentlichung WinRT WRL-Header in der Windows April 2018 Update SDK (10.0.17134.0) sind nicht mit Bereinigen **/ PERMISSIVE--**. Um diese Probleme zu umgehen, verwenden entweder nicht **/ PERMISSIVE--**, oder verwenden Sie **/ PERMISSIVE--** mit **/Zc:twoPhase-** bei der Arbeit mit den folgenden Headern:

- Probleme im winrt/wrl/async.h

   ```Output
   C:\Program Files (x86)\Windows Kits\10\Include\10.0.17134.0\winrt\wrl\async.h(483): error C3861: 'TraceDelegateAssigned': identifier not found
   C:\Program Files (x86)\Windows Kits\10\Include\10.0.17134.0\winrt\wrl\async.h(491): error C3861: 'CheckValidStateForDelegateCall': identifier not found
   C:\Program Files (x86)\Windows Kits\10\Include\10.0.17134.0\winrt\wrl\async.h(509): error C3861: 'TraceProgressNotificationStart': identifier not found
   C:\Program Files (x86)\Windows Kits\10\Include\10.0.17134.0\winrt\wrl\async.h(513): error C3861: 'TraceProgressNotificationComplete': identifier not found
   ```

- Problem beim winrt/wrl/implements.h

   ```Output
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\winrt\wrl\implements.h(2086): error C2039: 'SetStrongReference': is not a member of 'Microsoft::WRL::Details::WeakReferenceImpl'
   ```

Diese Veröffentlichung Benutzermodus-Header in der Windows April 2018 Update SDK (10.0.17134.0) sind nicht mit Bereinigen **/ PERMISSIVE--**. Um diese Probleme zu umgehen, verwenden Sie keine **/ PERMISSIVE--** bei der Arbeit mit den folgenden Headern:

- Probleme im um/Tune.h

   ```Output
   C:\ProgramFiles(x86)\Windows Kits\10\include\10.0.17134.0\um\tune.h(139): error C3861: 'Release': identifier not found
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\tune.h(559): error C3861: 'Release': identifier not found
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\tune.h(1240): error C3861: 'Release': identifier not found
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\tune.h(1240): note: 'Release': function declaration must be available as none of the arguments depend on a template parameter
   ```

- Problem beim um/spddkhlp.h

   ```Output
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\spddkhlp.h(759): error C3861: 'pNode': identifier not found
   ```

- Probleme im um/refptrco.h

   ```Output
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\refptrco.h(179): error C2760: syntax error: unexpected token 'identifier', expected 'type specifier'
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\refptrco.h(342): error C2760: syntax error: unexpected token 'identifier', expected 'type specifier'
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\refptrco.h(395): error C2760: syntax error: unexpected token 'identifier', expected 'type specifier'
   ```

Diese Probleme sind spezifisch für den Benutzermodus-Header in das Windows Fall Creators Update SDK (10.0.16299.0):

- Problem beim um/Query.h

   Bei Verwendung der **/ PERMISSIVE--** -Compilerschalter verwenden, die `tagRESTRICTION` Struktur wird nicht kompiliert, aufgrund der case(RTOr)-Member "oder".

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

   Um dieses Problem zu beheben, kompilieren Sie die Dateien, die Query.h ohne enthalten die **/ PERMISSIVE--** Option.

- Problem beim um/cellularapi_oem.h

   Bei Verwendung der **/ PERMISSIVE--** Compilerschalter, die Vorwärtsdeklaration `enum UICCDATASTOREACCESSMODE` bewirkt, dass eine Warnung:

   ```cpp
   typedef enum UICCDATASTOREACCESSMODE UICCDATASTOREACCESSMODE; // C4471
   ```

   Die Vorwärtsdeklaration einer Enumeration ohne bereichseinschränkung ist ein Microsoft-Erweiterung. Um dieses Problem zu beheben, kompilieren Sie die Dateien, die cellularapi_oem.h ohne enthalten die **/ PERMISSIVE--** oder verwenden Sie die [/WD](compiler-option-warning-level.md) Option aus, um die Warnung C4471 zu unterdrücken.

- Problem beim um/omscript.h

   In C ++ 03, eine Konvertierung aus einem Zeichenfolgenliteral in einen BSTR (Dies ist eine Typedef für "Wchar_t *') ist als veraltet markiert, aber zulässig. In C ++ 11 ist die Konvertierung nicht mehr zulässig.

   ```cpp
   virtual /* [id] */ HRESULT STDMETHODCALLTYPE setExpression(
       /* [in] */ __RPC__in BSTR propname,
       /* [in] */ __RPC__in BSTR expression,
       /* [in][defaultvalue] */ __RPC__in BSTR language = L"") = 0; // C2440
   ```

   Um dieses Problem zu beheben, kompilieren Sie die Dateien, die omscript.h ohne enthalten die **/ PERMISSIVE--** oder verwenden Sie **/Zc:strictStrings-** stattdessen.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

Verwenden Sie in Visual Studio 2017 Version 15.5 und höher dieses Verfahren aus:

1. Öffnen des Projekts **Eigenschaftenseiten** Dialogfeld.

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **Sprache** Eigenschaftenseite.

1. Ändern der **Konformitätsmodus** Eigenschaftswert **Ja (/ PERMISSIVE--)**. Wählen Sie **OK** oder **übernehmen** zum Speichern der Änderungen.

Verwenden Sie in Versionen vor Visual Studio 2017 Version 15.5 dieses Verfahren:

1. Öffnen des Projekts **Eigenschaftenseiten** Dialogfeld.

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **Befehlszeile** Eigenschaftenseite.

1. Geben Sie die **/ PERMISSIVE--** -Compileroption in der **zusätzliche Optionen** Feld. Wählen Sie **OK** oder **übernehmen** zum Speichern der Änderungen.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

- [MSVC-Compiler-Optionen](compiler-options.md)
- [MSVC-Compiler-Befehlszeilensyntax](compiler-command-line-syntax.md)
