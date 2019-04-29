---
title: /Zc:ternary (erzwingen bedingter Operator Regeln)
ms.date: 3/06/2018
f1_keywords:
- /Zc:ternary
helpviewer_keywords:
- /Zc:ternary
- Zc:ternary
- -Zc:ternary
ms.openlocfilehash: cb9a4f8468a9cb57af711cdca36ee343e5092493
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62315431"
---
# <a name="zcternary-enforce-conditional-operator-rules"></a>/Zc:ternary (erzwingen bedingter Operator Regeln)

Aktivieren Sie die Erzwingung von C++-Standard-Regeln für die Typen und die Qualifizierung von const oder volatile (KA) der zweiten und dritten Operanden in einem Ausdruck des Bedingungsoperators.

## <a name="syntax"></a>Syntax

> **/Zc:ternary**[**-**]

## <a name="remarks"></a>Hinweise

Visual Studio, Version 15.3 kann Compiler-Unterstützung für C++ standard bedingte (oder ternärer) Operator (**?:**) Verhalten. Der C++-Standard erfordert entweder die Operanden für den gleichen Typ und cv-Qualifikation, oder nur einer der Operanden in den gleichen Typ und cv-Qualifizierung als die andere eindeutig konvertierbar sein, oder für eine oder beide der Operanden eines Throw-Ausdrucks zu sein werden. In Versionen vor Visual Studio, Version 15.5 ließ der Compiler Konvertierungen, die vom Standard mehrdeutig berücksichtigt werden. Wenn die **/Zc:ternary** angegeben wurde, wird der Compiler entspricht dem Standard und lehnt Code, der die Regeln für die übereinstimmenden Typen und cv-Qualifizierung der zweiten und dritten Operanden nicht erfüllt.

Die **/Zc:ternary** Option ist standardmäßig deaktiviert. Verwendung **/Zc:ternary** auf konforme Verhalten zu aktivieren, oder **/Zc:ternary-** das vorherige Compilerverhalten für nicht konforme explizit angeben. Die [/ PERMISSIVE--](permissive-standards-conformance.md) Option implizit ermöglicht diese Option, aber sie kann überschrieben werden, mithilfe von **/Zc:ternary-**.

### <a name="examples"></a>Beispiele

Dieses Beispiel zeigt, wie eine Klasse, die beide nicht explizite Initialisierung von einem Typ und die Konvertierung in einen Typ enthält, mehrdeutige Konvertierungen führen kann. Dieser Code wird standardmäßig vom Compiler akzeptiert, jedoch zurückgewiesen, wenn **/Zc:ternary** oder **/ PERMISSIVE--** angegeben ist.

```cpp
// zcternary1.cpp
// Compile by using: cl /EHsc /W4 /nologo /Zc:ternary zcternary1.cpp

struct A
{
   long l;
   A(int i) : l{i} {}    // explicit prevents conversion of int
   operator int() const { return static_cast<int>(l); }
};

int main()
{
   A a(42);
   // Accepted when /Zc:ternary (or /permissive-) is not used
   auto x = true ? 7 : a;  // old behavior prefers A(7) over (int)a
   auto y = true ? A(7) : a;   // always accepted
   auto z = true ? 7 : (int)a; // always accepted
   return x + y + z;
}
```

Die Korrektur erforderlich ist, stellen eine explizite Umwandlung in die bevorzugte gemeinsamen Typ oder eine Richtung der Konvertierung von der Teilnahme an der Compilersuche nach einer typübereinstimmung verhindern, indem Sie die Konvertierung explizit zu machen.

Eine wichtige Ausnahme dieses allgemeine Muster ist, wenn der Typ der Operanden eines der Null-terminierte Zeichenfolge-Datentypen, wie z. B. `const char*`, `const char16_t*`und so weiter. Sie können auch reproduzieren, dies mit Arraytypen und den Zeigertypen, die, denen Sie zum decay. Das Verhalten bei der tatsächlichen zweite oder dritte Operand, der?: ein Zeichenfolgenliteral eines entsprechenden Typs hängt von der standard der Sprache verwendet. C ++ 17 wurde die Semantik für diesen Fall von C ++ 14 geändert werden. Der Code im folgenden Beispiel wird daher unter akzeptiert **/Std: c ++ 14** (die Standardeinstellung des Compilers) ist jedoch zurückgewiesen, wenn **/Std: c ++ 17** angegeben ist.

```cpp
// zcternary2.cpp
// Compile by using: cl /EHsc /W4 /nologo /Zc:ternary /std:c++17 zcternary2.cpp

struct MyString
{
   const char * p;
   MyString(const char* s = "") noexcept : p{s} {} // from char*
   operator const char*() const noexcept { return p; } // to char*
};

int main()
{
   MyString s;
   auto x = true ? "A" : s; // MyString: permissive prefers MyString("A") over (const char*)s
}
```

Um diesen Code zu beheben, wandeln Sie explizit einer der Operanden.

Klicken Sie unter **/Zc:ternary**Compiler lehnt bedingten Operatoren, in denen eines der Argumente vom ist, Typ "void", und der andere Operand keines Throw-Ausdrucks. Eine übliche Verwendung dieser ist im ASSERT-ähnliche Makros:

```cpp
// zcternary3.cpp
// Compile by using: cl /EHsc /W4 /nologo /Zc:ternary /c zcternary3.cpp

void myassert(const char* text, const char* file, int line);
#define ASSERT(ex) (void)((ex) ? 0 : myassert(#ex, __FILE__, __LINE__))
// To fix, define it this way instead:
// #define ASSERT(ex) (void)((ex) ? void() : myassert(#ex, __FILE__, __LINE__))

int main()
{
   ASSERT(false);  // C3447
}
```

Die typische Lösung besteht einfach das Argument nicht "void" mit void() ersetzen.

Dieses Beispiel zeigt Code, der einen Fehler in beiden Verzeichnissen generiert **/Zc:ternary** und **/Zc:ternary-**:

```cpp
// zcternary4.cpp
// Compile by using:
//   cl /EHsc /W4 /nologo /Zc:ternary zcternary4.cpp
//   cl /EHsc /W4 /nologo /Zc:ternary zcternary4.cpp

int main() {
   auto p1 = [](int a, int b) { return a > b; };
   auto p2 = [](int a, int b) { return a > b; };
   auto p3 = true ? p1 : p2; // C2593 under /Zc:ternary, was C2446
}
```

Dieser Code hat zuvor dieser Fehler auf:

```Output
error C2446: ':': no conversion from 'foo::<lambda_f6cd18702c42f6cd636bfee362b37033>' to 'foo::<lambda_717fca3fc65510deea10bc47e2b06be4>'
note: No user-defined-conversion operator available that can perform this conversion, or the operator cannot be called
```

Mit **/Zc:ternary** klarer wird Ihr die Ursache für Fehler, die auf Architekturen, in denen eine der mehrere implementierungsdefinierte Aufrufkonventionen verwendet werden, um jede Lambda zu generieren, gibt des Compilers keine Priorität für diese die konnte die möglichen Lambda-Signaturen unterscheiden. Die neue Ausgabe sieht folgendermaßen aus:

```Output
error C2593: 'operator ?' is ambiguous
note: could be 'built-in C++ operator?(bool (__cdecl *)(int,int), bool (__cdecl *)(int,int))'
note: or       'built-in C++ operator?(bool (__stdcall *)(int,int), bool (__stdcall *)(int,int))'
note: or       'built-in C++ operator?(bool (__fastcall *)(int,int), bool (__fastcall *)(int,int))'
note: or       'built-in C++ operator?(bool (__vectorcall *)(int,int), bool (__vectorcall *)(int,int))'
note: while trying to match the argument list '(foo::<lambda_717fca3fc65510deea10bc47e2b06be4>, foo::<lambda_f6cd18702c42f6cd636bfee362b37033>)'
```

Eine häufige Ursache für Probleme im Zusammenhang mit der Einführung von **/Zc:ternary** stammt aus der Verwendung des bedingten Operators in Metaprogrammierung-Vorlage, wie einige der Ergebnistypen unter diesem Switch zu ändern. Das folgende Beispiel zeigt zwei Fälle, in denen **/Zc:ternary** Ergebnistyp eines bedingten Ausdrucks, in einem nicht-Meta-Programmierung Kontext ändert:

```cpp
// zcternary5.cpp
// Compile by using: cl /EHsc /W4 /nologo /Zc:ternary zcternary5.cpp

int main(int argc, char**) {
   char a = 'A';
   const char b = 'B';
   decltype(auto) x = true ? a : b; // char without, const char& with /Zc:ternary
   const char(&z)[2] = argc > 3 ? "A" : "B"; // const char* without /Zc:ternary
   return x > *z;
}
```

Die typische Lösung in solchen Fällen ist die Anwendung eine `std::remove_reference` Merkmal "auf dem Ergebnis" Geben Sie bei Bedarf, um das alte Verhalten zu erhalten.

Weitere Informationen über Konformitätsprobleme in Visual C++ finden Sie unter [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **Befehlszeile** Eigenschaftenseite.

1. Ändern der **zusätzliche Optionen** Eigenschaft sollen **/Zc:ternary** oder **/Zc:ternary-** und wählen Sie dann **OK**.

## <a name="see-also"></a>Siehe auch

[/Zc (Übereinstimmung)](zc-conformance.md)
