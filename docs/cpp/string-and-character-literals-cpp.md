---
title: Zeichen folgen-und Zeichen Literale (C++)
description: Deklarieren und Definieren von Zeichen folgen-und Zeichen Literalen in C++.
ms.date: 07/29/2019
f1_keywords:
- R
- L
- u
- u8
- LR
- uR
- u8R
helpviewer_keywords:
- literal strings [C++]
- string literals [C++]
ms.assetid: 61de8f6f-2714-4e7b-86b6-a3f885d3b9df
ms.openlocfilehash: 9fce1ef9636aaa85be71cafffb5c4247e5c2e2d9
ms.sourcegitcommit: 20a1356193fbe0ddd1002e798b952917eafc3439
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68661524"
---
# <a name="string-and-character-literals--c"></a>Zeichen folgen-und Zeichen Literale (C++)

C++ unterstützt verschiedene Zeichenfolgen- und Zeichentypen und bietet Möglichkeiten Literalwerte dieser einzelnen Typen auszudrücken. In Ihrem Quellcode stellen Sie die Inhalte Ihrer Zeichen- und Zeichenfolgenliterale mit einem Zeichensatz dar. Universelle Zeichennamen und Escapezeichen ermöglichen es Ihnen, eine beliebige Zeichenfolge darzustellen, indem Sie nur den grundlegenden Quellzeichensatz verwenden. Ein unformatiertes Zeichenfolgenliteral ermöglicht es Ihnen, die Verwendung von Escapezeichen zu vermeiden, und kann verwendet werden, um alle Typen von Zeichenfolgenliteralen auszudrücken. Sie können auch Literale erstellen `std::string` , ohne zusätzliche Konstruktions-oder Konvertierungs Schritte ausführen zu müssen.

```cpp
#include <string>
using namespace std::string_literals; // enables s-suffix for std::string literals

int main()
{
    // Character literals
    auto c0 =   'A'; // char
    auto c1 = u8'A'; // char
    auto c2 =  L'A'; // wchar_t
    auto c3 =  u'A'; // char16_t
    auto c4 =  U'A'; // char32_t

    // String literals
    auto s0 =   "hello"; // const char*
    auto s1 = u8"hello"; // const char*, encoded as UTF-8
    auto s2 =  L"hello"; // const wchar_t*
    auto s3 =  u"hello"; // const char16_t*, encoded as UTF-16
    auto s4 =  U"hello"; // const char32_t*, encoded as UTF-32

    // Raw string literals containing unescaped \ and "
    auto R0 =   R"("Hello \ world")"; // const char*
    auto R1 = u8R"("Hello \ world")"; // const char*, encoded as UTF-8
    auto R2 =  LR"("Hello \ world")"; // const wchar_t*
    auto R3 =  uR"("Hello \ world")"; // const char16_t*, encoded as UTF-16
    auto R4 =  UR"("Hello \ world")"; // const char32_t*, encoded as UTF-32

    // Combining string literals with standard s-suffix
    auto S0 =   "hello"s; // std::string
    auto S1 = u8"hello"s; // std::string
    auto S2 =  L"hello"s; // std::wstring
    auto S3 =  u"hello"s; // std::u16string
    auto S4 =  U"hello"s; // std::u32string

    // Combining raw string literals with standard s-suffix
    auto S5 =   R"("Hello \ world")"s; // std::string from a raw const char*
    auto S6 = u8R"("Hello \ world")"s; // std::string from a raw const char*, encoded as UTF-8
    auto S7 =  LR"("Hello \ world")"s; // std::wstring from a raw const wchar_t*
    auto S8 =  uR"("Hello \ world")"s; // std::u16string from a raw const char16_t*, encoded as UTF-16
    auto S9 =  UR"("Hello \ world")"s; // std::u32string from a raw const char32_t*, encoded as UTF-32
}
```

Ein Zeichenfolgenliteral kann kein Präfix, auch kein `u8`-, `L`-, `u`- und  `U` -Präfix haben, um Codierung für schmale Zeichen (Einzelbyte oder Multibyte), UTF-8, breite Zeichen (UCS-2- oder UTF-16), UTF-16 bzw. UTF-32 zu kennzeichnen. Ein unformatierte Zeichenfolgenliterale kann `UR` , `u8R`, `LR`, `uR`und Präfixe für die rohversions Entsprechungen dieser Codierungen aufweisen `R`.  Um temporäre oder statische `std::string` Werte zu erstellen, können Sie Zeichen folgen Literale oder unformatierte Zeichen folgen Literale mit einem `s` -Suffix verwenden. Weitere Informationen finden Sie im Abschnitt [Zeichen folgen Literale](#string-literals) weiter unten. Weitere Informationen zum grundlegenden Quell Zeichensatz, zu universellen Zeichennamen und zum Verwenden von Zeichen aus erweiterten Codepages in Ihrem Quellcode finden Sie unter [Zeichensätze](../cpp/character-sets.md).

## <a name="character-literals"></a>Zeichenliterale

Ein *Zeichenfolgenliteral* besteht aus einem konstanten Zeichen. Es wird durch das Zeichen dargestellt, das von einfachen Anführungszeichen eingeschlossen ist. Es gibt fünf Arten von Zeichenliteralen:

- Gewöhnliche Zeichen Literale vom Typ " **char**", z. b.`'a'`

- UTF-8-Zeichen Literale vom Typ " **char**", z. b.`u8'a'`

- Breite Zeichenliterale vom Typ `wchar_t`, beispielsweise `L'a'`

- UTF-16-Zeichen Literale vom `char16_t`Typ, z. b.`u'a'`

- UTF-32-Zeichen Literale vom `char32_t`Typ, z. b.`U'a'`

Das Zeichen, das für ein zeichenliteralzeichen verwendet wird, kann ein beliebiges Zeichen sein,\\mit Ausnahme des umgekehrten Schrägstrichs (' '), des einfachen Anführungs Zeichens (') oder der Zeilen Vorlage. Reservierte Zeichen können mit einer Escapesequenz angegeben werden. Zeichen können mit universellen Zeichennamen angegeben werden, solange der Typ groß genug ist, das Zeichen zu enthalten.

### <a name="encoding"></a>Codierung

Zeichen Literale werden basierend auf dem Präfix unterschiedlich codiert.

- Ein Zeichenliteral ohne ein Präfix ist ein normales Zeichenliteral. Der Wert eines normalen Zeichenliterals, das ein einzelnes Zeichen, eine Escapesequenz oder einen universellen Zeichennamen enthält, der im Ausführungs Zeichensatz dargestellt werden kann, hat einen Wert, der dem numerischen Wert seiner Codierung im Ausführungs Zeichensatz entspricht. Ein normales Zeichenliteral, das mehr als ein Zeichen, eine Escapesequenz oder einen universellen Zeichennamen enthält, ist ein *multizeichenliteral*. Ein multizeichenliteral oder ein normales Zeichenliteral, das nicht im Ausführungs Zeichensatz dargestellt werden kann, wird bedingt unterstützt, weist den Typ " **int**" auf, und sein Wert ist Implementierungs definiert.

- Ein Zeichenliteral, das `L` mit dem Präfix beginnt, ist ein breit Zeichenliteral. Der Wert eines breit Zeichenliterals, das ein einzelnes Zeichen, eine Escapesequenz oder einen universellen Zeichennamen enthält, hat einen Wert, der gleich dem numerischen Wert der zugehörigen Codierung in der Ausführungs weite Zeichen Gruppe ist, es sei denn, das Zeichenliteral hat keine Darstellung im der Ausführungs weite Zeichensatz. in diesem Fall ist der Wert Implementierungs definiert. Der Wert eines breit Zeichenliterals mit mehreren Zeichen, Escapesequenzen oder universellen Zeichennamen ist Implementierungs definiert.

- Ein Zeichen Literale, das mit `u8` dem Präfix beginnt, ist ein UTF-8-Zeichenliteral. Der Wert eines UTF-8-Zeichenliterals, das ein einzelnes Zeichen, eine Escapesequenz oder einen universellen Zeichennamen enthält, weist einen Wert auf, der mit seinem ISO 10646-Code Punkt Wert identisch ist, wenn er durch eine einzelne UTF-8-Code Einheit dargestellt werden kann (entspricht den C0-Steuerelementen und dem Unicode-Block). Wenn der Wert nicht durch eine einzelne UTF-8-Code Einheit dargestellt werden kann, ist das Programm falsch formatiert. Ein UTF-8-Zeichenliteral, das mehr als ein Zeichen, eine Escapesequenz oder einen universellen Zeichennamen enthält, ist falsch formatiert.

- Ein Zeichen Literale, das mit `u` dem Präfix beginnt, ist ein UTF-16-Zeichenliteral. Der Wert eines UTF-16-Zeichenliterals, das ein einzelnes Zeichen, eine Escapesequenz oder einen universellen Zeichennamen enthält, hat einen Wert, der gleich seinem ISO 10646-Code Punkt Wert ist, wenn er durch eine einzelne UTF-16-Code Einheit (entsprechend der grundlegenden mehrsprachigen Ebene) dargestellt werden kann. ). Wenn der Wert nicht durch eine einzelne UTF-16-Code Einheit dargestellt werden kann, ist das Programm falsch formatiert. Ein UTF-16-Zeichenliteral, das mehr als ein Zeichen, eine Escapesequenz oder einen universellen Zeichennamen enthält, ist falsch formatiert.

- Ein Zeichen Literale, das mit `U` dem Präfix beginnt, ist ein UTF-32-Zeichenliteral. Der Wert eines UTF-32-Zeichenliterals, das ein einzelnes Zeichen, eine Escapesequenz oder einen universellen Zeichennamen enthält, weist einen Wert auf, der dem ISO 10646-Code Punkt Wert entspricht. Ein UTF-32-Zeichenliteral, das mehr als ein Zeichen, eine Escapesequenz oder einen universellen Zeichennamen enthält, ist falsch formatiert.

###  <a name="bkmk_Escape"></a>Escapesequenzen

Es gibt drei Arten von Escapesequenzen: einfache, oktale und hexadezimale. Escapesequenzen können folgendermaßen aussehen:

|Wert|Escapesequenz|
|-----------|---------------------|
| Zeilenumbruch | \\Nr |
| Umgekehrter Schrägstrich | \\\\ |
| Horizontaler Tabulator | \\Bund |
| Fragezeichen | ? \- oder einen \\? |
| Vertikaler Tabulator | \\v |
| Einfaches Anführungszeichen | \\' |
| Rückschritt | \\b |
| Doppeltes Anführungszeichen | \\" |
| Wagenrücklauf | \\r |
| das Nullzeichen | \\0 |
| Seitenvorschub | \\f |
| Oktal | \\OOO |
| Warnung (Glocke) | \\a |
| Hexadezimal | \\xhhh |

Dieser Beispielcode zeigt einige Beispiele für Escapezeichen mit normalen Zeichen Literalen. Die gleiche Escapesequenzsyntax ist für die anderen zeichenliteraltypen gültig.

```cpp
#include <iostream>
using namespace std;

int main() {
    char newline = '\n';
    char tab = '\t';
    char backspace = '\b';
    char backslash = '\\';
    char nullChar = '\0';

    cout << "Newline character: " << newline << "ending" << endl; // Newline character:
                                                                  //  ending
    cout << "Tab character: " << tab << "ending" << endl; // Tab character : ending
    cout << "Backspace character: " << backspace << "ending" << endl; // Backspace character : ending
    cout << "Backslash character: " << backslash << "ending" << endl; // Backslash character : \ending
    cout << "Null character: " << nullChar << "ending" << endl; //Null character:  ending
}
```

**Microsoft-spezifisch**

Zum Erstellen eines Werts aus einem normalen zeichenliteralzeichen (eines ohne ein Präfix) konvertiert der Compiler das Zeichen oder die Zeichen Sequenz zwischen einfachen Anführungszeichen in 8-Bit-Werte innerhalb einer 32-Bit-Ganzzahl. Mehrere Zeichen im Literal belegen entsprechende Bytes nach Bedarf vom höherwertigen zum niederwertigen Byte. Zum Erstellen eines **char** -Werts nimmt der Compiler das nieder wertige Byte an. Um einen **wchar_t** oder `char16_t` einen Wert zu erstellen, nimmt der Compiler das nieder wertige Wort an. Der Compiler warnt, dass das Ergebnis abgeschnitten wird, wenn irgendwelche Bits über dem zugewiesenen Byte oder Word Bits festgelegt sind.

```cpp
char c0    = 'abcd';    // C4305, C4309, truncates to 'd'
wchar_t w0 = 'abcd';    // C4305, C4309, truncates to '\x6364'
```

Eine oktale Escapesequenz ist ein umgekehrter Schrägstrich gefolgt von einer Sequenz von bis 3 Oktalziffern. Das Verhalten einer oktalen Escapesequenz, die scheinbar mehr als drei Ziffern enthält, wird als eine 3-stellige oktale Sequenz behandelt, gefolgt von den nachfolgenden Ziffern als Zeichen, was zu überraschenden Ergebnissen führen kann. Beispiel:

```cpp
char c1 = '\100';   // '@'
char c2 = '\1000';  // C4305, C4309, truncates to '0'
```

Eine Escapesequenzen, die scheinbar nicht oktale Zeichen enthält, wird als eine oktale Sequenz bis zu dem letzten oktalen Zeichen gefolgt von den verbleibenden Zeichen ausgewertet. Beispiel:

```cpp
char c3 = '\009';   // '9'
char c4 = '\089';   // C4305, C4309, truncates to '9'
char c5 = '\qrs';   // C4129, C4305, C4309, truncates to 's'
```

Eine hexadezimale Escapesequenz ist ein umgekehrter Schrägstrich, gefolgt von dem Zeichen `x`, gefolgt von einer Sequenz von hexadezimalen Zeichen. Eine Escapesequenz, die keine Hexadezimalziffern enthält, verursacht den Compilerfehler C2153 "Hexadezimale Literale müssen mindestens eine hexadezimale Ziffer enthalten". Führende Nullen werden ignoriert. Eine Escapesequenz, die anscheinend hexadezimale und nicht hexadezimale Zeichen beinhaltet, wird als eine hexadezimale Escapesequenz bis zum letzten hexadezimalen Zeichen gefolgt von den nicht hexadezimalen Zeichen ausgewertet. In einem normalen oder mit einem vorangestellten vorangestellten Zeichen literalen ist der höchste Hexadezimalwert 0xFF. In einem Breitzeichenliteral mit dem Präfix L oder u ist 0xFFFF der höchste Hexadezimalwert. In einem Breitzeichenliteral mit dem Präfix U ist 0xFFFFFFFF der höchste Hexadezimalwert.

```cpp
char c6 = '\x0050'; // 'P'
char c7 = '\x0pqr'; // C4305, C4309, truncates to 'r'
```

Enthält ein Breitzeichenliteral mit dem Präfix `L` mehr als ein Zeichen, wird der Wert des ersten Zeichens übernommen. Nachfolgende Zeichen werden ignoriert, anders als das Verhalten des entsprechenden normalen Zeichenliterals.

```cpp
wchar_t w1 = L'\100';   // L'@'
wchar_t w2 = L'\1000';  // C4066 L'@', 0 ignored
wchar_t w3 = L'\009';   // C4066 L'\0', 9 ignored
wchar_t w4 = L'\089';   // C4066 L'\0', 89 ignored
wchar_t w5 = L'\qrs';   // C4129, C4066 L'q' escape, rs ignored
wchar_t w6 = L'\x0050'; // L'P'
wchar_t w7 = L'\x0pqr'; // C4066 L'\0', pqr ignored
```

**Microsoft-spezifisch beenden**

Der umgekehrte Schrägstrich (\\) ist ein Zeilen Fortsetzungs Zeichen, wenn er am Ende einer Zeile platziert wird. Wenn ein umgekehrter Schrägstrich als Zeichenliteral angezeigt werden soll, müssen Sie zwei umgekehrte Schrägstriche in einer Zeile (`\\`) eingeben. Weitere Informationen zum Zeilenfortsetzungszeichen finden Sie unter [Phases of Translation](../preprocessor/phases-of-translation.md).

###  <a name="bkmk_UCN"></a> Universelle Zeichennamen

In Zeichenliteralen und systemeigenen (nicht unformatierten) Zeichenfolgenliteralen kann jedes Zeichen durch einen universellen Zeichennamen dargestellt werden.  Universelle Zeichennamen werden durch ein Präfix `\U` gefolgt von einem achtstelligen Unicode-Codepunkt oder durch ein Präfix `\u` , gefolgt von einem vierstelligen Unicode-Codepunkt, gebildet. Alle acht bzw. vier Ziffern müssen vorhanden sein, damit sich ein wohlgeformter universeller Zeichenname ergibt.

```cpp
char u1 = 'A';          // 'A'
char u2 = '\101';       // octal, 'A'
char u3 = '\x41';       // hexadecimal, 'A'
char u4 = '\u0041';     // \u UCN 'A'
char u5 = '\U00000041'; // \U UCN 'A'
```

#### <a name="surrogate-pairs"></a>Ersatzzeichenpaare

Universelle Zeichennamen können keine Werte im Ersatz Zeichencode punktbereich D800 und-DFFF codieren. Für Unicode-Ersatzzeichenpaare geben Sie den universellen Zeichennamen an, indem Sie `\UNNNNNNNN`verwenden, wobei NNNNNNNN ein achtstellige Codepunkt für das Zeichen ist. Der Compiler generiert ggf. ein Ersatz Zeichenpaar.

In C++03 kann in der Sprache nur eine Teilmenge der Zeichen durch deren universelle Zeichennamen dargestellt werden und sind einige universelle Zeichennamen zulässig, die tatsächlich keine gültigen Unicode-Zeichen darstellen. Dieser Fehler wurde im Standard c++ 11 korrigiert. In C++11 können sowohl für Zeichen- und Zeichenfolgenliterale als auch für Bezeichner universelle Zeichennamen verwendet werden.  Weitere Informationen zu universellen Zeichennamen finden Sie unter [Character Sets](../cpp/character-sets.md). Weitere Informationen zu Unicode finden Sie unter [Unicode](https://msdn.microsoft.com/library/dd374081). Weitere Informationen zu Ersatzzeichenpaaren finden Sie im Artikel über [Ersatzzeichenpaare und zusätzliche Zeichen](/windows/desktop/Intl/surrogates-and-supplementary-characters).

## <a name="string-literals"></a>Zeichen folgen Literale

Ein Zeichenfolgenliteral stellt eine Folge von Zeichen dar, die zusammen eine auf NULL endende Zeichenfolge bilden. Die Zeichen müssen zwischen doppelten Anführungszeichen eingeschlossen werden. Es gibt die folgenden Arten von Zeichenfolgenliteralen:

### <a name="narrow-string-literals"></a>Schmale Zeichen folgen Literale

Ein enges Zeichenfolgenliteralzeichen ist ein durch Trennzeichen getrenntes, mit Null endendes Array vom `const char[n]`Typ, wobei n die Länge des Arrays in Bytes ist. Ein Schmalzeichenfolgenliteral kann jedes Grafikzeichen außer einem doppelten Anführungszeichen (`"`), umgekehrten Schrägstrichen (`\`) oder Zeilenumbruchzeichen enthalten. Ein Schmalzeichenfolgenliteral kann auch die oben aufgelisteten Escapesequenzen sowie universelle Zeichennamen enthalten, die in ein Byte passen.

```cpp
const char *narrow = "abcd";

// represents the string: yes\no
const char *escaped = "yes\\no";
```

#### <a name="utf-8-encoded-strings"></a>UTF-8 codierte Zeichenfolgen

Eine UTF-8-codierte Zeichenfolge ist ein durch Trennzeichen getrenntes, mit doppelten Anführungszeichen getrenntes Array vom `const char[n]`Typ, wobei *n* die Länge des codierten Arrays in Bytes ist. Ein mit dem Präfix u8 versehenes Zeichenfolgenliteral kann jedes Grafikzeichen außer einem doppelten Anführungszeichen (`"`), umgekehrten Schrägstrichen (`\`) oder Zeilenumbruchzeichen enthalten. Ein mit dem Präfix u8 versehenes Zeichenfolgenliteral kann auch die Escapesequenzen, die oben aufgelistet sind, sowie jeden universellen Zeichennamen enthalten.

```cpp
const char* str1 = u8"Hello World";
const char* str2 = u8"\U0001F607 is O:-)";
```

### <a name="wide-string-literals"></a>Breite Zeichen folgen Literale

Ein breites Zeichenfolgenliteralzeichen ist ein mit Null endendes Array von konstantenwchar_t, dem das Präfix "`L`" vorangestellt ist und ein beliebiges Grafikzeichen außer\\dem doppelten Anführungszeichen ("), dem umgekehrten Schrägstrich () oder dem Zeilen Vorstrich enthält Ein Breitzeichenfolgenliteral kann die Escapesequenzen, die oben aufgelistet sind, sowie jeden universellen Zeichennamen enthalten.

```cpp
const wchar_t* wide = L"zyxw";
const wchar_t* newline = L"hello\ngoodbye";
```

#### <a name="char16t-and-char32t-c11"></a>char16_t und char32_t (C ++ 11)

C ++ 11 stellt die portablen `char16_t` (16-Bit-Unicode) und `char32_t` (32-Bit-Unicode)-Zeichentypen vor:

```cpp
auto s3 = u"hello"; // const char16_t*
auto s4 = U"hello"; // const char32_t*
```

### <a name="raw-string-literals-c11"></a>Unformatierte Zeichen folgen Literale (c++ 11)

Bei einem unformatierten zeichenfolgenliteralformat handelt es sich um ein mit Null endendes Array – eines beliebigen Zeichen Typs –, das beliebige Grafiken enthält,\\einschließlich Anführungszeichen ("), umgekehrtem Schrägstrich () oder Zeilen vorzeilenzeichen. Unformatierte Zeichenfolgenliterale werden häufig in regulären Ausdrücken, die Zeichenklassen verwenden, und in HTML-Zeichenfolgen und XML-Zeichenfolgen verwendet. Beispiele finden Sie im folgenden Artikel: [Bjarne Stroustrup FAQ zu c++ 11](http://www.stroustrup.com/C++11FAQ.html).

```cpp
// represents the string: An unescaped \ character
const char* raw_narrow = R"(An unescaped \ character)";
const wchar_t* raw_wide = LR"(An unescaped \ character)";
const char*       raw_utf8  = u8R"(An unescaped \ character)";
const char16_t* raw_utf16 = uR"(An unescaped \ character)";
const char32_t* raw_utf32 = UR"(An unescaped \ character)";
```

Ein Trennzeichen ist eine benutzerdefinierte Sequenz von bis zu 16 Zeichen, die der öffnenden Klammer eines unformatierten Zeichenfolgenliterals unmittelbar vorangestellt wird und unmittelbar auf die schließende Klammer folgt.  Beispielsweise ist in `R"abc(Hello"\()abc"` die Zeichenfolge `abc` die Trennzeichensequenz und `Hello"\(`der Zeichenfolgeninhalt. Sie können ein Trennzeichen verwenden, um unformatierte Zeichenfolgen eindeutig zu machen, die doppelte Anführungszeichen und Klammern enthalten. Diese Zeichenfolgenliterale verursacht einen Compilerfehler

```cpp
// meant to represent the string: )"
const char* bad_parens = R"()")";  // error C2059
```

Durch ein Trennzeichen wird er jedoch behoben:

```cpp
const char* good_parens = R"xyz()")xyz";
```

Sie können ein unformatierte Zeichen folgen Literale erstellen, das in der Quelle einen Zeilen Umleitungs Zeichen (nicht das Escapezeichen) enthält:

```cpp
// represents the string: hello
//goodbye
const wchar_t* newline = LR"(hello
goodbye)";
```

### <a name="stdstring-literals-c14"></a>Std:: String-Literale (c++ 14)

`std::string`Literale sind Implementierungen der Standard Bibliothek benutzerdefinierter Literale (siehe unten), die als `"xyz"s` (mit einem `s` Suffix) dargestellt werden. Diese Art von Zeichenfolgenliteralen erzeugt ein `std::string`temporäres `std::u32string`Objekt vom `std::u16string`Typ, `std::wstring`, oder, je nachdem, welches Präfix angegeben ist. Wenn kein Präfix, wie oben, verwendet wird `std::string` , wird ein erstellt. `L"xyz"s`erzeugt eine `std::wstring`. `u"xyz"s`erzeugt einen [Std:: u16string](../standard-library/string-typedefs.md#u16string)und `U"xyz"s` erzeugt eine [Std:: u32string](../standard-library/string-typedefs.md#u32string).

```cpp
//#include <string>
//using namespace std::string_literals;
string str{ "hello"s };
string str2{ u8"Hello World" };
wstring str3{ L"hello"s };
u16string str4{ u"hello"s };
u32string str5{ U"hello"s };
```

Das `s` Suffix kann auch auf unformatierten Zeichenfolgenliteralen verwendet werden:

```cpp
u32string str6{ UR"(She said "hello.")"s };
```

`std::string`Literale werden im-Namespace `std::literals::string_literals` in der \<Zeichen folgen-> Header Datei definiert. Da `std::literals::string_literals`und `std::literals` beide als [inlinenamespaces](../cpp/namespaces-cpp.md)deklariert werden, wird `std::literals::string_literals` automatisch so behandelt, als ob sie direkt zum Namespace `std`gehören.

### <a name="size-of-string-literals"></a>Größe von Zeichenfolgenliteralen

Bei ANSI `char*` -Zeichen folgen und anderen Single-Byte-Codierungen (nicht UTF-8) ist die Größe (in Byte) eines Zeichenfolgenliterals die Anzahl der Zeichen plus 1 für das abschließende Null-Zeichen. Für alle anderen Zeichenfolgentypen ist die Größe nicht streng mit der Anzahl der Zeichen verknüpft. UTF-8 verwendet bis zu vier **char** -Elemente zum Codieren einiger *Code Einheiten*, `char16_t` und `wchar_t` oder codiert als UTF-16 können zwei Elemente (für insgesamt vier Bytes) verwenden, um eine einzelne *Code Einheit*zu codieren. In diesem Beispiel wird die Größe eines Breitzeichenfolgenliterals in Bytes gezeigt:

```cpp
const wchar_t* str = L"Hello!";
const size_t byteSize = (wcslen(str) + 1) * sizeof(wchar_t);
```

Beachten Sie `strlen()` , `wcslen()` dass und nicht die Größe des abschließenden NULL-Zeichens enthalten, dessen Größe gleich der Elementgröße des Zeichen folgen Typs ist: ein Byte für `char*` eine Zeichenfolge, zwei `wchar_t*` Bytes `char16_t*` für-oder-Zeichen folgen und vier Bytes für `char32_t*` Zeichen folgen.

Die maximale Länge eines Zeichenfolgenliterals beträgt 65.535 bytes. Diese Begrenzung gilt sowohl für schmale Zeichenfolgenliterale als auch für breite Zeichenfolgenliterale.

### <a name="modifying-string-literals"></a>Ändern von Zeichen folgen literalen

Da Zeichen folgen Literale (ohne `std::string` Literale) Konstanten sind, wird beim Versuch, Sie zu ändern – `str[2] = 'A'`beispielsweise – ein Compilerfehler verursacht.

**Microsoft-spezifisch**

In Microsoft C++können Sie mithilfe eines Zeichenfolgenliterals einen Zeiger auf nicht-Konstante **char** oder **wchar_t**initialisieren. Diese nicht konstante Initialisierung ist in C99-Code zulässig, in c++ 98 jedoch veraltet und wurde in c++ 11 entfernt. Ein Versuch, die Zeichenfolge zu ändern, verursacht eine Zugriffsverletzung, wie in diesem Beispiel:

```cpp
wchar_t* str = L"hello";
str[2] = L'a'; // run-time error: access violation
```

Sie können bewirken, dass der Compiler einen Fehler ausgibt, wenn ein Zeichenfolgenliterals in einen Non_const-Zeichen Zeiger konvertiert wird, wenn Sie die Compileroption [/Zc: strictstrings (String-literaltypkonvertierung deaktivieren)](../build/reference/zc-strictstrings-disable-string-literal-type-conversion.md) festlegen. Dies empfiehlt sich für mit den Standards kompatiblen portablen Code. Außerdem empfiehlt es sich, das Schlüsselwort " **Auto** " zu verwenden, um zeichenfolgenliteralinitialisierte Zeiger zu deklarieren, da es in den richtigen (Konstanten) Typ aufgelöst wird. In diesem Codebeispiel wird ein Versuch abgefangen, zur Kompilierungszeit in ein Zeichenfolgenliteral zu schreiben:

```cpp
auto str = L"hello";
str[2] = L'a'; // C3892: you cannot assign to a variable that is const.
```

In einigen Fällen können identische Zeichenfolgenliterale "zusammengelegt" werden, um Speicherplatz in der ausführbaren Datei zu sparen. Im Zeichenfolgenliteral-Pooling bewirkt der Compiler, dass alle Verweise auf ein bestimmtes Zeichenfolgenliteral auf die gleiche Position im Arbeitsspeicher zeigen, anstatt dass alle Verweise auf eine separate Instanz des Zeichenfolgenliterals zeigen. Verwenden Sie die [/GF](../build/reference/gf-eliminate-duplicate-strings.md) -Compileroption, um Stringpooling zu aktivieren.

**Microsoft-spezifisch beenden**

### <a name="concatenating-adjacent-string-literals"></a>Verketten von benachbarten Zeichenfolgenliteralen

Benachbarte breite oder schmale Zeichenfolgenliterale werden verkettet. Diese Deklaration ist:

```cpp
char str[] = "12" "34";
```

mit dieser Deklaration identisch:

```cpp
char atr[] = "1234";
```

und mit dieser Deklaration identisch:

```cpp
char atr[] =  "12\
34";
```

Durch die Verwendung eingebetteter hexadezimaler Escapesequenzen für die Angabe von Zeichenfolgenliterale können unerwartete Ergebnisse verursacht werden. Im folgenden Beispiel soll ein Zeichenfolgenliteral erstellt werden, das ASCII 5-Zeichen enthält, gefolgt von den Zeichen f, i, v und e:

```cpp
"\x05five"
```

Das eigentliche Ergebnis ist ein hexadezimales 5F, also der ASCII-Code für einen Unterstrich, gefolgt von den Zeichen i, v und e. Sie können eines der folgenden Elemente verwenden, um das richtige Ergebnis zu erhalten:

```cpp
"\005five"     // Use octal literal.
"\x05" "five"  // Use string splicing.
```

`std::string`Literale, da Sie Typen `std::string` sind, können mit dem Operator verkettet werden `+` , der für [basic_string](../standard-library/basic-string-class.md) -Typen definiert ist. Sie können auch auf die gleiche Weise wie benachbarte Zeichenfolgenliterale verkettet werden. In beiden Fällen müssen die Zeichenfolgencodierung und das Suffix übereinstimmen:

```cpp
auto x1 = "hello" " " " world"; // OK
auto x2 = U"hello" " " L"world"; // C2308: disagree on prefix
auto x3 = u8"hello" " "s u8"world"s; // OK, agree on prefixes and suffixes
auto x4 = u8"hello" " "s u8"world"z; // C3688, disagree on suffixes
```

### <a name="string-literals-with-universal-character-names"></a>Zeichenfolgenliterale mit universellen Zeichennamen

In systemeigenen (nicht unformatierten) Zeichenfolgenliteralen können universelle Zeichennamen verwendet werden, um jedes beliebige Zeichen darzustellen, solange der jeweilige universelle Zeichenname als ein oder mehrere Zeichen im string-Datentyp codiert werden kann.  Beispielsweise kann ein universeller Zeichenname, der ein erweitertes Zeichen darstellt, nicht in einer schmalen Zeichenfolge über die ANSI-Codepage codiert werden, er kann aber in schmalen Zeichenfolgen in einigen Multibyte-Codepages oder in UTF-8-Zeichenfolgen oder in einer breiten Zeichenfolge codiert werden. In c++ 11 wird die Unicode-Unterstützung durch `char16_t*` die `char32_t*` Zeichen folgen Typen und erweitert:

```cpp
// ASCII smiling face
const char*     s1 = ":-)";

// UTF-16 (on Windows) encoded WINKING FACE (U+1F609)
const wchar_t*  s2 = L"😉 = \U0001F609 is ;-)";

// UTF-8  encoded SMILING FACE WITH HALO (U+1F607)
const char*     s3 = u8"😇 = \U0001F607 is O:-)";

// UTF-16 encoded SMILING FACE WITH OPEN MOUTH (U+1F603)
const char16_t* s4 = u"😃 = \U0001F603 is :-D";

// UTF-32 encoded SMILING FACE WITH SUNGLASSES (U+1F60E)
const char32_t* s5 = U"😎 = \U0001F60E is B-)";
```

## <a name="see-also"></a>Siehe auch

[Zeichensätze](../cpp/character-sets.md)<br/>
[Numerische, boolesche und Zeigerliterale](../cpp/numeric-boolean-and-pointer-literals-cpp.md)<br/>
[Benutzerdefinierte Literale](../cpp/user-defined-literals-cpp.md)
