---
title: /permissive- (Übereinstimmung mit Standards)
ms.date: 03/08/2019
f1_keywords:
- /permissive
- VC.Project.VCCLCompilerTool.ConformanceMode
helpviewer_keywords:
- /permissive compiler options [C++]
- -permissive compiler options [C++]
- Standards conformance compiler options
- permissive compiler options [C++]
ms.assetid: db1cc175-6e93-4a2e-9396-c3725d2d8f71
ms.openlocfilehash: aca0fbc6a2ca36ceae26ba060b5bf92fea79c32c
ms.sourcegitcommit: fd0f8839da5c6a3663798a47c6b0bb6e63b518bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70273726"
---
# <a name="permissive--standards-conformance"></a>/permissive- (Übereinstimmung mit Standards)

Legen Sie den Standard Konformitäts Modus für den Compiler fest. Verwenden Sie diese Option, um Kompatibilitätsprobleme in Ihrem Code zu identifizieren und zu beheben, um das Problem zu korrigieren und zu Portier barer zu machen.

## <a name="syntax"></a>Syntax

> **/permissive-**

## <a name="remarks"></a>Hinweise

Diese Option wird in Visual Studio 2017 und höher unterstützt.

Mit der **/permissive-** -Compileroption können Sie ein standardkonformes Compilerverhalten angeben. Mit dieser Option werden einschränkend sein Verhalten deaktiviert und die [/Zc](zc-conformance.md) -Compileroptionen für strikte Konformität festgelegt. In der IDE bewirkt diese Option auch, dass die IntelliSense-Engine nicht konformen Code unterstreicht.

Standardmäßig wird die **/permissive-** -Option in neuen Projekten festgelegt, die von Visual Studio 2017 Version 15,5 und höheren Versionen erstellt wurden. Sie wird in früheren Versionen nicht standardmäßig festgelegt. Wenn die Option festgelegt ist, generiert der Compiler Diagnosefehler oder Warnungen, wenn nicht standardmäßige Sprachkonstrukte im Code erkannt werden, einschließlich einiger allgemeiner Fehler in vor C + + 11-Code.

Die **/permissive-** -Option ist mit fast allen Header Dateien aus den neuesten Windows-Kits wie dem Software Development Kit (SDK) oder dem Windows-Treiberkit (WDK) kompatibel, beginnend mit dem Windows Fall Creators SDK (10.0.16299.0). Ältere Versionen des SDK können möglicherweise nicht unter **/permissive-** für verschiedene Gründe für die Konformität mit Quell Code kompiliert werden. Der Compiler und die SDBs liefern verschiedene releasezeitimelines, daher gibt es einige verbleibende Probleme. Informationen zu bestimmten Header Dateien finden Sie weiter unten Unterprobleme mit dem [Windows-Header](#windows-header-issues) .

Mit der **/permissive-** -Option werden die Optionen [/Zc: referencebinding](zc-referencebinding-enforce-reference-binding-rules.md), [/Zc: strictstrings](zc-strictstrings-disable-string-literal-type-conversion.md)und [/Zc: rvaluecast](zc-rvaluecast-enforce-type-conversion-rules.md) auf das konforme Verhalten festgelegt. Diese Optionen werden standardmäßig als nicht konformes Verhalten verwendet. Sie können bestimmte **/Zc** -Optionen nach **/permissive-** in der Befehlszeile übergeben, um dieses Verhalten zu überschreiben.

In Versionen des Compilers ab Visual Studio 2017, Version 15,3, legt die Option " **/permissive-** " die Option [/Zc: Ternary](zc-ternary.md) fest. Der Compiler implementiert auch weitere Anforderungen für die zweistufige Namenssuche. Wenn die **/permissive-** -Option festgelegt ist, analysiert der Compiler Funktions-und Klassen Vorlagen Definitionen und identifiziert abhängige und nicht abhängige Namen, die in den Vorlagen verwendet werden. In dieser Version wird nur die namens Abhängigkeits Analyse durchgeführt.

Umgebungs spezifische Erweiterungen und Sprachbereiche, die der Standard für die Implementierung verlässt, sind von **/permissive-** nicht betroffen. Beispielsweise werden die Microsoft-spezifischen `__declspec`Schlüsselwörter, die Aufruf Konvention und die strukturierte Ausnahmebehandlung sowie compilerspezifische pragma-Direktiven oder Attribute nicht vom Compiler im **/permissive-** -Modus gekennzeichnet.

Die **/permissive-** -Option verwendet die Übereinstimmungs Unterstützung in der aktuellen Compilerversion, um zu bestimmen, welche Sprachkonstrukte nicht kompatibel sind. Die Option bestimmt nicht, ob Ihr Code einer bestimmten Version des C++ Standards entspricht. Um alle implementierten Compilerunterstützung für den neuesten Entwurfs Standard zu aktivieren, verwenden Sie die Option [/Std: Latest](std-specify-language-standard-version.md) . Um die Compilerunterstützung auf den derzeit implementierten c++ 17-Standard einzuschränken, verwenden Sie die Option [/Std: c++ 17](std-specify-language-standard-version.md) . Verwenden Sie die Option [/Std: c++ 14](std-specify-language-standard-version.md) , um die Compilerunterstützung auf eine genauere Übereinstimmung mit dem c++ 14-Standard zu beschränken.

Der MSVC-Compiler in allen Versionen von Visual Studio 2017 unterstützt nicht alle standardmäßig übereinstimmenden Codes von c++ 11, c++ 14 und c++ 17. Abhängig von der Version von Visual Studio erkennt die **/permissive-** -Option möglicherweise keine Probleme bezüglich einiger Aspekte der zweistufigen Namenssuche, bindet einen nicht konstanten Verweis auf ein temporäres Element, behandelt Copy init als Direct init und ermöglicht mehrere benutzerdefinierte Konvertierungen in der Initialisierung oder Alternative Token für logische Operatoren sowie andere nicht unterstützte Übereinstimmungs Bereiche. Weitere Informationen über Konformitätsprobleme in Visual C++ finden Sie unter [Nonstandard Behavior](../../cpp/nonstandard-behavior.md). Um **/permissive-** optimal zu nutzen, aktualisieren Sie Visual Studio auf die neueste Version.

### <a name="how-to-fix-your-code"></a>So beheben Sie Ihren Code

Im folgenden finden Sie einige Beispiele für Code, der als nicht kompatibel erkannt wird, wenn Sie **/permissive-** verwenden, zusammen mit empfohlenen Möglichkeiten, um die Probleme zu beheben.

#### <a name="use-default-as-an-identifier-in-native-code"></a>Standard als Bezeichner in nativem Code verwenden

```cpp
void func(int default); // Error C2321: 'default' is a keyword, and
                        // cannot be used in this context
```

#### <a name="look-up-members-in-dependent-base"></a>Member in abhängiger Basis suchen

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

#### <a name="use-of-qualified-names-in-member-declarations"></a>Verwendung qualifizierter Namen in Element Deklarationen

```cpp
struct A {
    void A::f() { } // error C4596: illegal qualified name in member
                    // declaration.
                    // Remove redundant 'A::' to fix.
};
```

#### <a name="initialize-multiple-union-members-in-a-member-initializer"></a>Initialisieren mehrerer Unionmember in einem Members-Initialisierer

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

#### <a name="hidden-friend-name-lookup-rules"></a>Such Regeln für ausgeblendete Friend-Namen

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

#### <a name="use-scoped-enums-in-array-bounds"></a>Verwenden von Bereichs bezogenen Aufständen in Array Grenzen

```cpp
enum class Color {
    Red, Green, Blue
};

int data[Color::Blue]; // error C3411: 'Color' is not valid as the size
                       // of an array as it is not an integer type.
                       // Cast to type size_t or int to fix.
```

#### <a name="use-for-each-in-native-code"></a>Verwenden Sie für jedes in nativem Code.

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

#### <a name="ambiguous-conditional-operator-arguments"></a>Mehrdeutige bedingte Operator Argumente

In Versionen des Compilers vor Visual Studio 2017 Version 15,3 akzeptierte der Compiler Argumente für den bedingten Operator (oder ternären Operator) `?:` , die vom Standard als mehrdeutig angesehen werden. Im **/permissive-** -Modus gibt der Compiler nun eine oder mehrere Diagnosen in Fällen aus, die in früheren Versionen ohne Diagnose kompiliert wurden.

Häufige Fehler, die sich aus dieser Änderung ergeben können, sind:

- Fehler C2593: "Operator?" ist mehrdeutig

- Fehler C2679: binary '? ': Es wurde kein Operator gefunden, der einen rechtsseitigen Operanden vom Typ ' B ' annimmt (oder es ist keine akzeptable Konvertierung zulässig).

- Fehler C2678: binary '? ': Es wurde kein Operator gefunden, der einen linken Operanden vom Typ ' a ' annimmt (oder es ist keine akzeptable Konvertierung zulässig).

- Fehler C2446: ":": keine Konvertierung von "B" in "A".

Ein typisches Code muster, das dieses Problem verursachen kann, ist, wenn eine Klasse C einen nicht expliziten Konstruktor von einem anderen Typ t und einen nicht expliziten Konvertierungs Operator für den Typ t bereitstellt. In diesem Fall handelt es sich bei der Konvertierung des zweiten Arguments in den Typ des dritten Arguments und bei der Konvertierung des dritten Arguments in den Typ des zweiten Arguments um gültige Konvertierungen. Da beide gültig sind, ist sie gemäß dem Standard mehrdeutig.

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

Es gibt eine wichtige Ausnahme für dieses gängige Muster, wenn T einen der null-terminierten Zeichen folgen Typen (z `const char *` `const char16_t *`. b., usw.) darstellt und das eigentliche `?:` Argument für ein Zeichenfolgenliteralwert des entsprechenden Typs ist. C++ 17 hat die Semantik von c++ 14 geändert. Folglich wird der Code in Beispiel 2 unter **/Std: c++ 14** akzeptiert und unter **/Std: c++ 17** abgelehnt, wenn **/Zc: Ternary** oder **/permissive-** verwendet wird.

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

Ein weiterer Fall, in dem möglicherweise Fehler auftreten, ist in bedingten Operatoren `void`mit einem Argument vom Typ. Dieser Fall kann in Assert-ähnlichen Makros häufig vorkommen.

```cpp
// Example 3: void arguments
void myassert(const char* text, const char* file, int line);
// Accepted when /Zc:ternary or /permissive- is not used:
#define ASSERT_A(ex) (void)((ex) ? 1 : myassert(#ex, __FILE__, __LINE__))
// Accepted always:
#define ASSERT_B(ex) (void)((ex) ? void() : myassert(#ex, __FILE__, __LINE__))
```

Möglicherweise werden auch Fehler in der Vorlagen Metaprogrammierung angezeigt, bei denen sich die Ergebnistypen bedingter Operatoren unter **/Zc: Ternary** und **/permissive-** ändern können. Eine Möglichkeit, dieses Problem zu beheben, ist die Verwendung von [Std:: remove_reference](../../standard-library/remove-reference-class.md) für den resultierenden Typ.

```cpp
// Example 4: different result types
extern bool cond;
extern int count;
char  a = 'A';
const char  b = 'B';
decltype(auto) x = cond ? a : b; // char without, const char& with /Zc:ternary
const char (&z)[2] = count > 3 ? "A" : "B"; // const char* without /Zc:ternary
```

#### <a name="two-phase-name-look-up"></a>Zwei-Phasen-Namenssuche

Wenn die **/permissive-** -Option festgelegt ist, analysiert der Compiler Funktions-und Klassen Vorlagen Definitionen und identifiziert abhängige und nicht abhängige Namen, die in Vorlagen verwendet werden, wie für die zwei-Phasen-Namenssuche erforderlich. In Visual Studio 2017 Version 15,3 wird die namens Abhängigkeits Analyse durchgeführt. Insbesondere nicht abhängige Namen, die nicht im Kontext einer Vorlagen Definition deklariert werden, verursachen eine Diagnose Meldung gemäß den ISO C++ -Standards. In Visual Studio 2017 Version 15,7 wird auch das Binden von nicht abhängigen Namen, für die ein Argument abhängiges suchen im Definitions Kontext erforderlich ist, vorgenommen.

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

Wenn Sie Legacy Verhalten für die zweistufige Suche wünschen, aber andernfalls **/permissive-** Verhalten möchten, fügen Sie die Option **/Zc: twophase-** hinzu.

### <a name="windows-header-issues"></a>Windows-Header Probleme

Die **/permissive-** -Option ist für Versionen der Windows-Kits vor dem Windows Fall Creators Update SDK (10.0.16299.0) oder Windows Driver Kit (WDK) Version 1709 zu streng. Es wird empfohlen, ein Update auf die neuesten Versionen der Windows-Kits durchführen, um **/permissive-** im Windows-oder Gerätetreiber Code zu verwenden.

Bestimmte Header Dateien im Windows-SDK für den 2018 Windows-Update-SDK (10.0.17134.0), das Windows Fall Creators Update SDK (10.0.16299.0) oder das Windows-Treiberkit (WDK) 1709 haben weiterhin Probleme, die Sie mit der Verwendung von **/permissive-** nicht kompatibel machen. Um diese Probleme zu umgehen, empfiehlt es sich, die Verwendung dieser Header auf die Quell Code Dateien zu beschränken, die Sie benötigen, und die **/permissive-** -Option zu entfernen, wenn Sie diese speziellen Quell Code Dateien kompilieren.

Diese WinRT-WRL-Header, die im 2018 Windows SDK-Update SDK (10.0.17134.0) veröffentlicht wurden, sind mit **/permissive-** nicht bereinigt. Um diese Probleme zu umgehen, verwenden Sie entweder **/permissive-** nicht, oder verwenden Sie **/permissive-** mit **/Zc: twophase** , wenn Sie mit diesen Headern arbeiten:

- Probleme in WinRT/WRL/Async. h

   ```Output
   C:\Program Files (x86)\Windows Kits\10\Include\10.0.17134.0\winrt\wrl\async.h(483): error C3861: 'TraceDelegateAssigned': identifier not found
   C:\Program Files (x86)\Windows Kits\10\Include\10.0.17134.0\winrt\wrl\async.h(491): error C3861: 'CheckValidStateForDelegateCall': identifier not found
   C:\Program Files (x86)\Windows Kits\10\Include\10.0.17134.0\winrt\wrl\async.h(509): error C3861: 'TraceProgressNotificationStart': identifier not found
   C:\Program Files (x86)\Windows Kits\10\Include\10.0.17134.0\winrt\wrl\async.h(513): error C3861: 'TraceProgressNotificationComplete': identifier not found
   ```

- Problem in WinRT/WRL/implementiert. h

   ```Output
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\winrt\wrl\implements.h(2086): error C2039: 'SetStrongReference': is not a member of 'Microsoft::WRL::Details::WeakReferenceImpl'
   ```

Diese im Windows April 2018 Update SDK (10.0.17134.0) veröffentlichten benutzermodusheader sind mit **/permissive-** nicht bereinigt. Um diese Probleme zu umgehen, verwenden Sie **/permissive-** nicht, wenn Sie mit diesen Headern arbeiten:

- Probleme in "um/Tune. h"

   ```Output
   C:\ProgramFiles(x86)\Windows Kits\10\include\10.0.17134.0\um\tune.h(139): error C3861: 'Release': identifier not found
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\tune.h(559): error C3861: 'Release': identifier not found
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\tune.h(1240): error C3861: 'Release': identifier not found
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\tune.h(1240): note: 'Release': function declaration must be available as none of the arguments depend on a template parameter
   ```

- Problem in "um/spddkhlp. h"

   ```Output
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\spddkhlp.h(759): error C3861: 'pNode': identifier not found
   ```

- Probleme in "um/refptrco. h"

   ```Output
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\refptrco.h(179): error C2760: syntax error: unexpected token 'identifier', expected 'type specifier'
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\refptrco.h(342): error C2760: syntax error: unexpected token 'identifier', expected 'type specifier'
   C:\Program Files (x86)\Windows Kits\10\include\10.0.17134.0\um\refptrco.h(395): error C2760: syntax error: unexpected token 'identifier', expected 'type specifier'
   ```

Diese Probleme gelten speziell für Benutzermodus-Header im Windows Fall Creators Update SDK (10.0.16299.0):

- Problem in "um/Abfrage. h"

   Wenn Sie den **/permissive-** -Compilerschalter `tagRESTRICTION` verwenden, wird die-Struktur aufgrund des Case (rtor)-Members ' or ' nicht kompiliert.

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

   Um dieses Problem zu beheben, kompilieren Sie Dateien, die "Query. h" enthalten, ohne die **/permissive-** -Option.

- Problem in "um/cellularapi_oem. h"

   Wenn Sie den **/permissive-** -Compilerschalter verwenden, verursacht `enum UICCDATASTOREACCESSMODE` die vorwärts Deklaration von eine Warnung:

   ```cpp
   typedef enum UICCDATASTOREACCESSMODE UICCDATASTOREACCESSMODE; // C4471
   ```

   Die vorwärts Deklaration von Enumeration ohne Bereichs Einschränkung ist eine Microsoft-Erweiterung. Um dieses Problem zu beheben, kompilieren Sie Dateien, die cellularapi_oem. h enthalten, ohne die **/permissive-** -Option, oder verwenden Sie die Option [/WD](compiler-option-warning-level.md) , um die Warnung C4471 zu verwenden.

- Problem in "um/omscript. h"

   In c++ 03 ist eine Konvertierung eines Zeichenfolgenliterals in BSTR (eine typedef in "wchar_t *") veraltet, aber zulässig. In c++ 11 ist die Konvertierung nicht mehr zulässig.

   ```cpp
   virtual /* [id] */ HRESULT STDMETHODCALLTYPE setExpression(
       /* [in] */ __RPC__in BSTR propname,
       /* [in] */ __RPC__in BSTR expression,
       /* [in][defaultvalue] */ __RPC__in BSTR language = L"") = 0; // C2440
   ```

   Um dieses Problem zu beheben, kompilieren Sie Dateien, die omscript. h enthalten, ohne die **/permissive-** -Option, oder verwenden Sie stattdessen **/Zc: strictstrings-** .

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

Verwenden Sie in Visual Studio 2017 Version 15,5 und höheren Versionen folgendes Verfahren:

1. Öffnen Sie das Dialogfeld **Eigenschaften Seiten** des Projekts.

1. Wählen Sie die **Eigenschaften Seite Konfigurations Eigenschaften** > **C++C/**  > Sprache aus.

1. Ändern Sie den Eigenschafts Wert für den **Konformitäts Modus** in **Ja (/permissive-)** . Wählen Sie **OK** oder **anwenden** aus, um die Änderungen zu speichern.

Verwenden Sie in Versionen vor Visual Studio 2017 Version 15,5 folgendes Verfahren:

1. Öffnen Sie das Dialogfeld **Eigenschaften Seiten** des Projekts.

1. Klicken Sie auf der Eigenschaftenseite auf **Konfigurationseigenschaften** > **C/C++**  > **Befehlszeile**.

1. Geben Sie die **/permissive-** -Compileroption im Feld **zusätzliche Optionen** ein. Wählen Sie **OK** oder **anwenden** aus, um die Änderungen zu speichern.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Compileroptionen](compiler-options.md)\
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)
