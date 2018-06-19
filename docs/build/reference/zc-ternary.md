---
title: /Zc:ternary (Bedingungsoperator-Regeln erzwingen) | Microsoft Docs
ms.date: 3/06/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Zc:ternary
dev_langs:
- C++
helpviewer_keywords:
- /Zc:ternary
- Zc:ternary
- -Zc:ternary
author: corob-msft
ms.author: corob
ms.openlocfilehash: 613381795fb962e1f10ec01598748b617b7543aa
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32380822"
---
# <a name="zcternary-enforce-conditional-operator-rules"></a>/Zc:ternary (Bedingungsoperator-Regeln erzwingen)

Aktivieren Sie Erzwingung der C++-Standard-Regeln für die Typen und const oder volatile (cv) Qualifizierung der zweiten und dritten Operanden in einem Ausdruck des Bedingungsoperators.

## <a name="syntax"></a>Syntax

> **/Zc:ternary**[**-**]

## <a name="remarks"></a>Hinweise

Visual Studio, Version 15.3 kann Compiler-Unterstützung für C++ standard bedingte (oder ternärer) Operator (**?:**) Verhalten. Der C++-Standard erfordert entweder die Operanden für den gleichen Typ und cv-Qualifizierung oder nur ein Operand für den gleichen Typ und cv-Qualifizierung, wie die anderen eindeutig konvertierbar sein, oder für eine oder beide der Operanden ein Throw-Ausdruck sein werden. In Versionen vor Visual Studio Version 15.5 zulässig der Compiler Konvertierungen, die gemäß dem Standard mehrdeutig berücksichtigt werden. Wenn die **/Zc:ternary** angegeben wird, der Compiler entspricht dem Standard und weist der Code, der die Regeln für übereinstimmende Typen und cv-Qualifizierung der zweiten und dritten Operanden nicht erfüllt.

Die **/Zc:ternary** Option ist standardmäßig deaktiviert. Verwendung **/Zc:ternary** um konforme Verhalten zu aktivieren oder **/Zc:ternary-** das vorherige Compilerverhalten für nicht konforme explizit angeben. Die [/ liberalen-](permissive-standards-conformance.md) Option implizit kann mit dieser Option, jedoch können sie mithilfe von außer Kraft gesetzt werden **/Zc:ternary-**.

### <a name="examples"></a>Beispiele

Dieses Beispiel zeigt, wie eine Klasse, die beide nicht explizite Initialisierung aus einem Typ und die Konvertierung in einen Typ bereitstellt, mehrdeutige Konvertierungen führen kann. Dieser Code wird standardmäßig vom Compiler akzeptiert, jedoch zurückgewiesen, wenn **/Zc:ternary** oder **/ liberalen-** angegeben ist.

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

Stellen eine explizite Umwandlung in den bevorzugten gemeinsamen Typ oder zu verhindern, dass eine Richtung der Konvertierung aus der Beteiligung am die Compilersuche nach einer typübereinstimmung durch die Konvertierung explizites ist die Lösung, die erforderlich sind.

Eine wichtige Ausnahme dieses allgemeine Muster ist, wenn der Typ der Operanden einen der Typen Null-terminierte Zeichenfolge wie z. B. `const char*`, `const char16_t*`und so weiter. Sie können auch reproduzieren, dies mit Arraytypen und der Zeiger, die sie zum decay. Das Verhalten bei der tatsächlichen zweite oder dritte Operand?: ist ein Zeichenfolgenliteral vom entsprechenden Typ hängt von der standardmäßigen Sprache verwendet. C ++ 17-Semantik für diesen Fall von C ++ 14 geändert. Daher wird der Code im folgenden Beispiel unter akzeptiert **/std:c ++ 14** (Compiler-Standard), wird jedoch zurückgewiesen, wenn **/std:c ++ 17** angegeben ist.

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

Zur Behebung dieses Codes Umwandeln einer der Operanden explizit an.

Klicken Sie unter **/Zc:ternary**, der Compiler lehnt Bedingte Operatoren, in denen eines der Argumente vom ist, Typ "void", und der andere Operand keiner Throw-Ausdruck. Eine übliche Verwendung dieser ist in der ASSERT-ähnliche Makros:

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

Die typischen Lösung besteht darin, ersetzen Sie das Argument nicht "void" mit void().

In diesem Beispiel enthält Code, der generiert einen Fehler unter beiden **/Zc:ternary** und **/Zc:ternary-**:

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

Dieser Code wurde zuvor dieser Fehler zugewiesen:

```Output
error C2446: ':': no conversion from 'foo::<lambda_f6cd18702c42f6cd636bfee362b37033>' to 'foo::<lambda_717fca3fc65510deea10bc47e2b06be4>'
note: No user-defined-conversion operator available that can perform this conversion, or the operator cannot be called
```

Mit **/Zc:ternary** wird klarer, der Grund für Fehler; in Architekturen, in denen keines mehrere implementierungsdefinierte Aufrufkonventionen konnte verwendet werden, um jede Lambda generieren, der Compiler keine Einstellung untereinander drückt die konnte die möglichen Lambda-Signaturen unterscheiden. Die neue Ausgabe sieht folgendermaßen aus:

```Output
error C2593: 'operator ?' is ambiguous
note: could be 'built-in C++ operator?(bool (__cdecl *)(int,int), bool (__cdecl *)(int,int))'
note: or       'built-in C++ operator?(bool (__stdcall *)(int,int), bool (__stdcall *)(int,int))'
note: or       'built-in C++ operator?(bool (__fastcall *)(int,int), bool (__fastcall *)(int,int))'
note: or       'built-in C++ operator?(bool (__vectorcall *)(int,int), bool (__vectorcall *)(int,int))'
note: while trying to match the argument list '(foo::<lambda_717fca3fc65510deea10bc47e2b06be4>, foo::<lambda_f6cd18702c42f6cd636bfee362b37033>)'
```

Eine häufige Ursache von Problemen im Zusammenhang mit der Übernahme von **/Zc:ternary** die Verwendung des bedingten Operators in der Vorlage Metaprogrammierung stammt, wie einige der Ergebnistypen unter diesem Switch ändern. Das folgende Beispiel zeigt zwei Fälle, in denen **/Zc:ternary** ändert ein bedingter Ausdruck Ergebnistyp in einem Kontext Meta-Programmierung:

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

Die üblichen Auflösung in solchen Fällen angewendet wird eine `std::remove_reference` Merkmal "auf dem Ergebnis" geben, falls erforderlich, um das alte Verhalten beizubehalten.

Weitere Informationen über Konformitätsprobleme in Visual C++ finden Sie unter [Nonstandard Behavior](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **Befehlszeile** Eigenschaftenseite.

1. Ändern der **Zusatzoptionen** Eigenschaft einschließen **/Zc:ternary** oder **/Zc:ternary-** und wählen Sie dann **OK**.

## <a name="see-also"></a>Siehe auch

[/Zc (Übereinstimmung)](../../build/reference/zc-conformance.md)  
