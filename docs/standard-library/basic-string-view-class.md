---
title: Basic_string_view-Klasse
ms.date: 04/20/2019
f1_keywords:
- xstring/std::basic_string_view
- xstring/std::basic_string_view::allocator_type
- xstring/std::basic_string_view::const_iterator
- xstring/std::basic_string_view::const_pointer
- xstring/std::basic_string_view::const_reference
- xstring/std::basic_string_view::const_reverse_iterator
- xstring/std::basic_string_view::difference_type
- xstring/std::basic_string_view::iterator
- xstring/std::basic_string_view::npos
- xstring/std::basic_string_view::pointer
- xstring/std::basic_string_view::reference
- xstring/std::basic_string_view::reverse_iterator
- xstring/std::basic_string_view::size_type
- xstring/std::basic_string_view::traits_type
- xstring/std::basic_string_view::value_type
- xstring/std::basic_string_view::append
- xstring/std::basic_string_view::assign
- xstring/std::basic_string_view::at
- xstring/std::basic_string_view::back
- xstring/std::basic_string_view::begin
- xstring/std::basic_string_view::c_str
- xstring/std::basic_string_view::capacity
- xstring/std::basic_string_view::cbegin
- xstring/std::basic_string_view::cend
- xstring/std::basic_string_view::clear
- xstring/std::basic_string_view::compare
- xstring/std::basic_string_view::copy
- xstring/std::basic_string_view::_Copy_s
- xstring/std::basic_string_view::crbegin
- xstring/std::basic_string_view::crend
- xstring/std::basic_string_view::data
- xstring/std::basic_string_view::empty
- xstring/std::basic_string_view::end
- xstring/std::basic_string_view::erase
- xstring/std::basic_string_view::find
- xstring/std::basic_string_view::find_first_not_of
- xstring/std::basic_string_view::find_first_of
- xstring/std::basic_string_view::find_last_not_of
- xstring/std::basic_string_view::find_last_of
- xstring/std::basic_string_view::front
- xstring/std::basic_string_view::get_allocator
- xstring/std::basic_string_view::insert
- xstring/std::basic_string_view::length
- xstring/std::basic_string_view::max_size
- xstring/std::basic_string_view::pop_back
- xstring/std::basic_string_view::push_back
- xstring/std::basic_string_view::rbegin
- xstring/std::basic_string_view::rend
- xstring/std::basic_string_view::remove_prefix
- xstring/std::basic_string_view::remove_suffix
- xstring/std::basic_string_view::replace
- xstring/std::basic_string_view::reserve
- xstring/std::basic_string_view::resize
- xstring/std::basic_string_view::rfind
- xstring/std::basic_string_view::shrink_to_fit
- xstring/std::basic_string_view::size
- xstring/std::basic_string_view::substr
- xstring/std::basic_string_view::swap
helpviewer_keywords:
- std::basic_string_view
- std::basic_string_view, allocator_type
- std::basic_string_view, const_iterator
- std::basic_string_view, const_pointer
- std::basic_string_view, const_reference
- std::basic_string_view, const_reverse_iterator
- std::basic_string_view, difference_type
- std::basic_string_view, iterator
- std::basic_string_view, npos
- std::basic_string_view, pointer
- std::basic_string_view, reference
- std::basic_string_view, reverse_iterator
- std::basic_string_view, size_type
- std::basic_string_view, traits_type
- std::basic_string_view, value_type
- std::basic_string_view, append
- std::basic_string_view, assign
- std::basic_string_view, at
- std::basic_string_view, back
- std::basic_string_view, begin
- std::basic_string_view, c_str
- std::basic_string_view, capacity
- std::basic_string_view, cbegin
- std::basic_string_view, cend
- std::basic_string_view, clear
- std::basic_string_view, compare
- std::basic_string_view, copy
- std::basic_string_view, crbegin
- std::basic_string_view, crend
- std::basic_string_view, data
- std::basic_string_view, empty
- std::basic_string_view, end
- std::basic_string_view, erase
- std::basic_string_view, find
- std::basic_string_view, find_first_not_of
- std::basic_string_view, find_first_of
- std::basic_string_view, find_last_not_of
- std::basic_string_view, find_last_of
- std::basic_string_view, front
- std::basic_string_view, get_allocator
- std::basic_string_view, insert
- std::basic_string_view, length
- std::basic_string_view, max_size
- std::basic_string_view, pop_back
- std::basic_string_view, push_back
- std::basic_string_view, rbegin
- std::basic_string_view, rend
- std::basic_string_view, remove_prefix
- std::basic_string_view, remove_suffix
- std::basic_string_view, replace
- std::basic_string_view, reserve
- std::basic_string_view, resize
- std::basic_string_view, rfind
- std::basic_string_view, shrink_to_fit
- std::basic_string_view, size
- std::basic_string_view, substr
- std::basic_string_view, swap
ms.assetid: a9c3e0a2-39bf-4c8a-b093-9abe30839591
ms.openlocfilehash: 0ac5e3d528881f7b1caa0a1dcdae0161a6777e57
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2019
ms.locfileid: "64346938"
---
# <a name="basicstringview-class"></a>Basic_string_view-Klasse

Die Klassenvorlage `basic_string_view<charT>` wurde hinzugefügt, in C ++ 17 dienen, wie eine sichere und effiziente Möglichkeit für eine Funktion, die verschiedene übernehmen unabhängig vom stagingstatus Zeichenfolgentypen ohne die Funktion, die für diese Typen vorlagenbasiert werden müssen. Die Klasse enthält einen Zeiger nicht besitzt, um eine fortlaufende Folge von Zeichendaten und eine Länge, die die Anzahl der Zeichen in der Sequenz angibt. Keine Annahme erfolgt in Bezug auf das gibt an, ob die Sequenz Null-terminiert ist.

Die Standardbibliothek definiert einige spezialisierungen, die basierend auf dem Typ der Elemente:

-  `string_view`
-  `wstring_view`
-  `u16string_view`
-  `u32string_view`

In diesem Dokument bezieht sich der Begriff "String_view" in der Regel auf eines dieser Typdefinitionen.

Eine String_view beschreibt die minimalen gemeinsame Schnittstelle, die zum Lesen von Zeichenfolgendaten. Sie bietet es sich um Konstanten Zugriff auf die zugrunde liegenden Daten. Es ist kein Kopien (mit Ausnahme der `copy` Funktion). Daten können, oder es darf keine null-Werte ('\0') an einer beliebigen Position. Eine String_view hat keine Kontrolle über die Lebensdauer des Objekts. Es ist der Verantwortung des Aufrufers, stellen Sie sicher, dass die zugrunde liegenden Zeichenfolgendaten gültig ist.

Eine Funktion, die einen Parameter vom Typ String_view akzeptiert kann vorgenommen werden, mit einem beliebigen Typ String-ähnliche arbeiten, ohne die Funktion in eine Vorlage festlegen oder die Funktion, die eine bestimmte Teilmenge von Zeichenfolgentypen einschränken. Die einzige Voraussetzung ist, dass eine implizite Konvertierung vom Zeichenfolgentyp String_view vorhanden ist. Alle Standardzeichenfolge Typen sind implizit konvertierbar in einem String_view, die den gleichen Elementtyp enthält. Das heißt, eine `std::string` konvertierbar ist eine `string_view` aber nicht für eine `wstring_view`.

Das folgende Beispiel zeigt eine nicht-Vorlagenfunktion `f` , akzeptiert einen Parameter vom Typ `wstring_view`. Mit Argumenten vom Typ aufgerufen werden kann `std::wstring`, `wchar_t*`, und `winrt::hstring`.

```cpp
// compile with: /std:c++17
// string_view that uses elements of wchar_t
void f(wstring_view);

// pass a std::wstring:
const std::wstring& s { L"Hello" };
f(s);

// pass a C-style null-terminated string (string_view is not null-terminated):
const wchar_t* ns = L"Hello";
f(ns);

// pass a C-style character array of len characters (excluding null terminator):
const wchar_t* cs { L"Hello" };
size_t len { 5 };
f({cs,len});

// pass a WinRT string
winrt::hstring hs { L"Hello" };
f(hs);
```

## <a name="syntax"></a>Syntax

```cpp
template <class CharType, class Traits = char_traits<CharType>>
class basic_string_view;
```

### <a name="parameters"></a>Parameter

*CharType*<br/>
Der Typ der Zeichen, die in der String_view gespeichert sind. Die C++ Standardbibliothek bietet die folgenden typedefs-Elementen für spezialisierungen dieser Vorlage.
- [String_view](../standard-library/string-view-typedefs.md#string_view) für Elemente des Typs **Char**
- [Wstring_view](../standard-library/string-view-typedefs.md#wstring_view), für die **"wchar_t"**
- [u16string_view](../standard-library/string-view-typedefs.md#u16string_view) für **char16_t**
- [u32string_view](../standard-library/string-view-typedefs.md#u32string_view) für **char32_t**.

*Merkmale*<br/>
Standardmäßig [Char_traits](char-traits-struct.md)<*CharType*>.

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[basic_string_view](#basic_string_view)|Erstellt eine String_view, die leer ist, sonst zeigt auf das gesamte oder einen Teil eines anderen Zeichenfolgenobjekts Daten oder auf ein C-Stil-Zeichenarray.|

### <a name="typedefs"></a>Typedefs

|Typname|Beschreibung|
|-|-|
|**const_iterator**|Random-Access-Iterator, der gelesen werden kann **const** Elemente.|
|**const_pointer**|`using const_pointer = const value_type*;`|
|**const_reference**|`using const_reference = const value_type&;`|
|**const_reverse_iterator**|`using const_reverse_iterator = std::reverse_iterator<const_iterator>;`|
|**difference_type**|`using difference_type = ptrdiff_t;`|
|**Iterator**|`using iterator = const_iterator;`|
|**npos**|`static constexpr size_type npos = size_type(-1);`|
|**Zeiger**|`using pointer = value_type*;`|
|**Verweis**|`using reference = value_type&;`|
|**reverse_iterator**|`using reverse_iterator = const_reverse_iterator;`|
|**size_type**|`using size_type = size_t;`|
|**traits_type**|`using traits_type = Traits;`|
|**value_type**|`using value_type = CharType;`|

### <a name="member-operators"></a>Member-Operatoren

|Operator|Beschreibung|
|-|-|
|[operator=](#op_eq)|Ein Zeichenfolgenobjekt String_view oder konvertiert werden kann und eine andere String_view zugewiesen.|
|[operator\[\]](#op_at)|Gibt das Element am angegebenen Index zurück.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[at](#at)|Gibt eine Const_reference auf das Element an einer angegebenen Position zurück.|
|[Rückseite](#back)|Gibt eine Const_reference bis zum letzten Element zurück.|
|[begin](#begin)|Gibt einen const-Iterator, der das erste Element zurück. (String_views sind unveränderlich.)|
|[cbegin](#cbegin)|Identisch mit [beginnen](#begin).|
|[cend](#cend)|Gibt einen const-Iterator, der auf eine Stelle hinter dem letzten Element verweist.|
|[copy](#copy)|Kopiert höchstens eine angegebene Anzahl von Zeichen aus einer indizierten Position in einer Quelle String_view in ein Zielzeichenarray. (Nicht empfohlen. Verwenden Sie _Copy_s stattdessen.)|
|[_Copy_s](#_copy_s)|Sichere CRT-Copy-Funktion.|
|[compare](#compare)|Vergleicht einen String_view mit einer angegebenen String_view zu bestimmen, ob diese gleich sind, oder wenn eine lexikografisch kleiner als das andere ist.|
|[crbegin](#crbegin)|Identisch mit [Rbegin](#rbegin).|
|[crend](#crend)|Identisch mit [rend](#rend).|
|[data](#data)|Gibt einen unformatierten Zeiger ist nicht Besitzer mit der Zeichensequenz zurück.|
|[empty](#empty)|Testet, ob die String_view Zeichen enthält.|
|[end](#end)|Identisch mit [Cend](#cend).|
|[find](#find)|Sucht in vorwärts gerichteter Reihenfolge nach dem ersten Vorkommen einer Teilzeichenfolge, die mit eine bestimmten Zeichensequenz übereinstimmt.|
|[find_first_not_of](#find_first_not_of)|Sucht nach dem ersten Zeichen, das kein Element eines angegebenen String_view oder konvertiert werden String-Objekt ist.|
|[find_first_of](#find_first_of)|Sucht nach dem ersten Zeichen, das einem Element eines angegebenen String_view oder konvertiert werden String-Objekt entspricht.|
|[find_last_not_of](#find_last_not_of)|Sucht nach dem letzten Zeichen, das kein Element eines angegebenen String_view oder konvertiert werden String-Objekt ist.|
|[find_last_of](#find_last_of)|Sucht nach dem letzten Zeichen, das ein Element eines angegebenen String_view oder konvertiert werden String-Objekt ist.|
|[Vorderseite](#front)|Gibt eine Const_reference auf das erste Element zurück.|
|[length](#length)|Gibt die aktuelle Anzahl der Elemente zurück.|
|[max_size](#max_size)|Gibt die maximale Anzahl von Zeichen, die eine String_view enthalten könnte zurück.|
|[rbegin](#rbegin)|Gibt einen const-Iterator, der das erste Element in einer umgekehrten String_view nachfolgt.|
|[remove_prefix](#remove_prefix)|Verschiebt den Zeiger vorwärts durch die angegebene Anzahl von Elementen.|
|[remove_suffix](#remove_suffix)|Reduziert die Größe der Ansicht durch die angegebene Anzahl von Elementen, die von der Rückseite ab.|
|[rend](#rend)|Gibt einen const-Iterator, der auf eine Stelle hinter dem letzten Element einer umgekehrten String_view verweist.|
|[rfind](#rfind)|Sucht eine String_view in umgekehrter Reihenfolge nach dem ersten Vorkommen einer Teilzeichenfolge, die mit eine bestimmten Zeichensequenz übereinstimmt.|
|[size](#size)|Gibt die aktuelle Anzahl der Elemente zurück.|
|[substr](#substr)|Gibt eine Teilzeichenfolge mit einer angegebenen Länge, beginnend am angegebenen Index.|
|[swap](#swap)|Tauschen Sie den Inhalt von zwei String_views.|

## <a name="remarks"></a>Hinweise

Wenn eine Funktion aufgefordert wird, eine Sequenz zu generieren, die länger als [max_size](#max_size)-Elemente ist, wird von der Funktion ein Längenfehler gemeldet, indem ein Objekt des Typs [length_error](../standard-library/length-error-class.md) ausgelöst wird.

## <a name="requirements"></a>Anforderungen

[Std: c ++ 17](../build/reference/std-specify-language-standard-version.md) oder höher

**Header:** \<string_view>

**Namespace:** std

## <a name="at"></a>  basic_string_view::at

Gibt eine Const_reference auf das Zeichen am angegebenen Index 0-basierte zurück.

```cpp
constexpr const_reference at(size_type offset) const;
```

### <a name="parameters"></a>Parameter

*offset*<br/>
Der Index des Elements verwiesen werden.

### <a name="return-value"></a>Rückgabewert

Eine Const_reference auf das Zeichen an der Position, die durch den Parameterindex angegeben.

### <a name="remarks"></a>Hinweise

Das erste Element hat einen Index von 0 (null) und die folgenden Elemente werden nacheinander durch positiven ganze Zahlen indiziert, damit eine String_view Länge *n* verfügt über eine *n*th-Element ab, das durch die Anzahl *n -* 1. **am** löst eine Ausnahme für ungültige Indizes, im Gegensatz zu [Operator\[\]](#op_at). 

Im Allgemeinen empfehlen wir **am** für Sequenzen wie z. B. `std::vector` und String_view sollte nicht verwendet werden. Ein ungültiger Index, die an eine Sequenz ist ein logischer Fehler, der ermittelt und während der Entwicklung behoben werden sollten. Wenn ein Programm nicht absolut sicher nicht, dass die Indizes gültig sind, sollte getestet werden, nicht aufrufen at() und Ausnahmen zur Verteidigung gegen unvorsichtige Programmierung abhängig.

Finden Sie unter [basic_string_view::operator\[ \] ](#op_at) für Weitere Informationen.

### <a name="example"></a>Beispiel

```cpp
// basic_string_view_at.cpp
// compile with: /EHsc
#include <string_view>
#include <iostream>

int main()
{
    using namespace std;

    const string_view  str1("Hello world");
    string_view::const_reference refStr2 = str1.at(8); // 'r'
}
```

## <a name="back"></a>  basic_string_view::Back

Gibt eine Const_reference bis zum letzten Element zurück.

```cpp
constexpr const_reference back() const;
```

### <a name="return-value"></a>Rückgabewert

Eine Const_reference bis zum letzten Element in der String_view.

### <a name="remarks"></a>Hinweise

Löst eine Ausnahme aus, wenn die String_view leer ist.

Beachten Sie, dass nach einem String_view geändert wird, z. B. durch Aufrufen von `remove_suffix`, und klicken Sie dann das Element, das von dieser Funktion zurückgegebenen nicht mehr mit dem letzten Element in der zugrunde liegenden Daten ist.

### <a name="example"></a>Beispiel

Eine String_view, die mit einem C-Zeichenfolgenliteral erstellt wird, enthält keine das abschließende Null und somit auch im folgenden Beispiel `back` 'p' und nicht '\0' zurückgegeben.

```cpp
char c[] = "Help"; // char[5]
string_view sv{ c };
cout << sv.size(); // size() == 4
cout << sv.back() << endl; // p 
```

Eingebettete NULL-Werte werden als ein anderes Zeichen behandelt:

```cpp
string_view e = "embedded\0nulls"sv;
cout << boolalpha << (e.back() == 's'); // true
```

## <a name="basic_string_view"></a>  basic_string_view::basic_string_view

Erstellt eine String_view an.

```cpp
constexpr basic_string_view() noexcept;
constexpr basic_string_view(const basic_string_view&) noexcept = default;
constexpr basic_string_view(const charT* str);
constexpr basic_string_view(const charT* str, size_type len);
```

### <a name="parameters"></a>Parameter

*str*<br/>
Der Zeiger auf die Zeichenwerte.

*len*<br/>
Die Anzahl der Zeichen in der Ansicht eingeschlossen werden sollen.

## <a name="remarks"></a>Hinweise

Die Konstruktoren mit einem Diagramm *-Parameter wird davon ausgegangen, dass die Eingabe wird auf Null endet, aber das abschließende Zeichen Null nicht in der String_view enthalten ist.

Sie können auch eine String_view mit einem Literal erstellen. Finden Sie unter [Operator "" Sv](string-view-operators.md#op_sv).

## <a name="begin"></a>  basic_string_view::begin

Identisch mit [Cbegin](#cbegin).

```cpp
constexpr const_iterator begin() const noexcept;
```

### <a name="return-value"></a>Rückgabewert
Gibt eine Const_iterator, der das erste Element zurück.

## <a name="cbegin"></a>  basic_string_view::cbegin

Gibt eine Const_iterator, der das erste Element im Bereich adressiert.

```cpp
constexpr const_iterator cbegin() const noexcept;
```

### <a name="return-value"></a>Rückgabewert

Ein **const** Iterator mit wahlfreiem Zugriff, der verweist auf das erste Element des Bereichs, oder die Position direkt hinter das Ende eines leeren Bereichs (für einen leeren Bereich gilt `cbegin() == cend()`).

## <a name="cend"></a>  basic_string_view::cend

Gibt eine Const_iterator, der die Position direkt hinter dem letzten Element in einem Bereich adressiert.

```cpp
constexpr const_iterator cend() const noexcept;
```

### <a name="return-value"></a>Rückgabewert

Ein **const** Iterator mit wahlfreiem Zugriff, der direkt hinter das Ende des Bereichs verweist.

### <a name="remarks"></a>Hinweise

Der von `cend` zurückgegebene Wert darf nicht dereferenziert werden.

## <a name="compare"></a> basic_string_view::Compare

Führt einen Vergleich Groß-/Kleinschreibung beachten, mit einem angegebenen String_view (oder Zeichenfolgentyp konvertiert werden kann), zu bestimmen, ob die beiden Objekte gleich sind, oder wenn eine lexikografisch kleiner als das andere ist. Die [ \<String_view > Operatoren](string-view-operators.md) verwenden Sie diese Memberfunktion auf, um Vergleiche durchzuführen.

```cpp
constexpr int compare(basic_string_view strv) const noexcept;
constexpr int compare(size_type pos, size_type num, basic_string_view strv) const;
constexpr int compare(size_type pos, size_type num, basic_string_view strv, size_type offset, size_type num2) const;
constexpr int compare(const charT* ptr) const;
constexpr int compare(size_type pos, size_type num, const charT* ptr) const;
constexpr int compare(size_type pos, size_type num, const charT* ptr, size_type num2) const;
```

### <a name="parameters"></a>Parameter

*strv*<br/>
Die String_view, die mit diesem String_view verglichen werden soll.

*pos*<br/>
Der Index des diesem String_view, an dem der Vergleich beginnt.

*num*<br/>
Die maximale Anzahl von Zeichen aus dieser String_view verglichen werden soll.

*num2*<br/>
Die maximale Anzahl von Zeichen aus *Strv* verglichen werden soll.

*offset*<br/>
Der Index des *Strv* an dem der Vergleich beginnt.

*ptr*<br/>
Die C-Zeichenfolge mit diesem String_view verglichen werden soll.

### <a name="return-value"></a>Rückgabewert

Ein negativer Wert, wenn diese String_view ist kleiner als *Strv* oder *Ptr*; NULL, wenn die beiden Zeichenfolgen gleich sind; oder ein positiver Wert sind, ist diese String_view größer als *Strv*oder *Ptr*.

### <a name="remarks"></a>Hinweise

Die `compare` Memberfunktionen führen einen Groß-/Kleinschreibung Vergleich entweder vollständig oder teilweise jeder Sequenz von Zeichen. 

### <a name="example"></a>Beispiel

```cpp
// basic_string_view_compare.cpp
// compile with: /EHsc
#include <string_view>
#include <iostream>
#include <string>

using namespace std;

string to_alpha(int result)
{
   if (result < 0) return " less than ";
   else if (result == 0) return " equal to ";
   else return " greater than ";
}

int main()
{
   // The first member function compares
   // two string_views
   string_view sv_A("CAB");
   string_view sv_B("CAB");
   cout << "sv_A is " << sv_A << endl;
   cout << "sv_B is " << sv_B << endl;
   int comp1 = sv_A.compare(sv_B);
   cout << "sv_A is" << to_alpha(comp1) << "sv_B.\n";

   // The second member function compares part of
   // an operand string_view to another string_view
   string_view sv_C("AACAB");
   string_view sv_D("CAB");
   cout << "sv_C is: " << sv_C << endl;
   cout << "sv_D is: " << sv_D << endl;
   int comp2a = sv_C.compare(2, 3, sv_D);
   cout << "The last three characters of sv_C are" 
       << to_alpha(comp2a) << "sv_D.\n";

   int comp2b = sv_C.compare(0, 3, sv_D);
   cout << "The first three characters of sv_C are" 
       << to_alpha(comp2b) << "sv_D.\n";

   // The third member function compares part of
   // an operand string_view to part of another string_view
   string_view sv_E("AACAB");
   string_view sv_F("DCABD");
   cout << "sv_E: " << sv_E << endl;
   cout << "sv_F is: " << sv_F << endl;
   int comp3a = sv_E.compare(2, 3, sv_F, 1, 3);
   cout << "The three characters from position 2 of sv_E are"
       << to_alpha(comp3a) 
       << "the 3 characters of sv_F from position 1.\n";

   // The fourth member function compares
   // an operand string_view to a C string
   string_view sv_G("ABC");
   const char* cs_A = "DEF";
   cout << "sv_G is: " << sv_G << endl;
   cout << "cs_A is: " << cs_A << endl;
   int comp4a = sv_G.compare(cs_A);
   cout << "sv_G is" << to_alpha(comp4a) << "cs_A.\n";

   // The fifth member function compares part of
   // an operand string_view to a C string
   string_view sv_H("AACAB");
   const char* cs_B = "CAB";
   cout << "sv_H is: " << sv_H << endl;
   cout << "cs_B is: " << cs_B << endl;
   int comp5a = sv_H.compare(2, 3, cs_B);
   cout << "The last three characters of sv_H are"
      << to_alpha(comp5a) << "cs_B.\n";

   // The sixth member function compares part of
   // an operand string_view to part of an equal length of
   // a C string
   string_view sv_I("AACAB");
   const char* cs_C = "ACAB";
   cout << "sv_I is: " << sv_I << endl;
   cout << "cs_C: " << cs_C << endl;
   int comp6a = sv_I.compare(1, 3, cs_C, 3);
   cout << "The 3 characters from position 1 of sv_I are"
      << to_alpha(comp6a) << "the first 3 characters of cs_C.\n";
}
```

```Output
sv_A is CAB
sv_B is CAB
sv_A is equal to sv_B.
sv_C is: AACAB
sv_D is: CAB
The last three characters of sv_C are equal to sv_D.
The first three characters of sv_C are less than sv_D.
sv_E: AACAB
sv_F is: DCABD
The three characters from position 2 of sv_E are equal to the 3 characters of sv_F from position 1.
sv_G is: ABC
cs_A is: DEF
sv_G is less than cs_A.
sv_H is: AACAB
cs_B is: CAB
The last three characters of sv_H are equal to cs_B.
sv_I is: AACAB
cs_C: ACAB
The 3 characters from position 1 of sv_I are equal to the first 3 characters of cs_C.
```

## <a name="copy"></a>  basic_string_view::Copy

Kopiert höchstens eine angegebene Anzahl von Zeichen aus einer indizierten Position in einer Quelle String_view in ein Zielzeichenarray. Es wird empfohlen, dass Sie der sicheren Funktion mithilfe [basic_string_view::_Copy_s](#_copy_s) stattdessen.

```cpp
size_type copy(charT* ptr, size_type count, size_type offset = 0) const;
```

### <a name="parameters"></a>Parameter

*ptr*<br/>
Das Zielzeichenarray, in das die Elemente kopiert werden sollen.

*count*<br/>
Die Anzahl der Zeichen, höchstens aus der Quelle String_view kopiert werden.

*offset*<br/>
Die Anfangsposition in der Quelle String_view aus dem kopiert werden, vorgenommen werden.

### <a name="return-value"></a>Rückgabewert

Die Anzahl der tatsächlich kopierten Zeichen.

### <a name="remarks"></a>Hinweise

Es wird kein NULL-Zeichen ans Ende der Kopie angefügt.

## <a name="_copy_s"></a>  basic_string_view::_Copy_s

Secure CRT-Copy-Funktion nicht verwendet werden [Kopie](#copy).

```cpp
size_type _Copy_s(
    value_type* dest,
    size_type dest_size,
    size_type count,
    size_type _Off = 0) const;
```

### <a name="parameters"></a>Parameter

*dest*<br/>
Das Zielzeichenarray, in das die Elemente kopiert werden sollen.

*dest_size*<br/>
Die Größe des *Dest*.

_ *Anzahl* die Anzahl der Zeichen, höchstens aus der Quellzeichenfolge kopiert werden.

*_Off*<br/>
Die Anfangsposition in der Quellzeichenfolge, ab der Kopien erstellt werden dürfen.

### <a name="return-value"></a>Rückgabewert

Die Anzahl der tatsächlich kopierten Zeichen.

### <a name="remarks"></a>Hinweise

Es wird kein NULL-Zeichen ans Ende der Kopie angefügt.

 Weitere Informationen finden Sie unter [c-runtime-library/security-features-in-the-crt](../c-runtime-library/security-features-in-the-crt.md).

## <a name="crbegin"></a>  basic_string_view::crbegin

Gibt einen Const_reverse_iterator, der das erste Element in einer umgekehrten String_view nachfolgt.

```cpp
constexpr const_reverse_iterator crbegin() const noexcept;
```

### <a name="return-value"></a>Rückgabewert

Einen Const_reverse_iterator, der das erste Element in einer umgekehrten String_view nachfolgt. 

## <a name="crend"></a>  basic_string_view::crend

Identisch mit [rend](#rend). 

```cpp
constexpr const_reverse_iterator crend() const noexcept;
```

### <a name="return-value"></a>Rückgabewert

Gibt einen Const_reverse_iterator, die erste Position direkt hinter das Ende einer umgekehrten String_view Adressen zurück.

## <a name="data"></a>  basic_string_view::Data

Gibt einen unformatierten Zeiger ist nicht Besitzer mit der Konstanten Zeichensequenz des Objekts, das verwendet wurde, um die String_view zu erstellen.

```cpp
constexpr value_type *data() const noexcept;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger-auf-Const auf das erste Element der Zeichenfolge ist.

### <a name="remarks"></a>Hinweise

Die Zeichen kann nicht der Zeiger geändert werden.

Eine Folge von Zeichen von String_view ist nicht unbedingt auf Null endende. Der Rückgabetyp für `data` ist keine gültige C-Zeichenfolge, da kein Null-Zeichen angehängt wird. Das Null-Zeichen "\0" hat keine besondere Bedeutung in einem Objekt vom Typ String_view und möglicherweise ein Teil des Objekts String_view genau wie jedes andere Zeichen.

## <a name="empty"></a>  basic_string_view::Empty

Testet, ob die String_view Zeichen oder nicht enthält.

```cpp
constexpr bool empty() const noexcept;
```

### <a name="return-value"></a>Rückgabewert

**"true"** , wenn das Objekt String_view keine Zeichen enthält; **"false"** Wenn sie mindestens ein Zeichen enthält.

### <a name="remarks"></a>Hinweise

Die Memberfunktion ist äquivalent zu [Größe](#size)() == 0.

## <a name="end"></a>  basic_string_view::End

Gibt ein random-Access-Const_iterator, der auf eine Stelle hinter dem letzten Element verweist.

```cpp
constexpr const_iterator end() const noexcept;
```

### <a name="return-value"></a>Rückgabewert

Gibt ein random-Access-Const_iterator, der auf eine Stelle hinter dem letzten Element verweist.

### <a name="remarks"></a>Hinweise

`end` Dient zum Testen, ob eine Const_iterator am Ende der String_view erreicht hat. Der von `end` zurückgegebene Wert darf nicht dereferenziert werden.

## <a name="find"></a>  basic_string_view::Find

Sucht eine String_view vorwärts nach dem ersten Vorkommen eines Zeichens oder einer Teilzeichenfolge, die eine angegebene Folge von Zeichen steht.

```cpp
constexpr size_type find(basic_string_view str, size_type offset = 0) const noexcept;
constexpr size_type find(charT chVal, size_type offset = 0) const noexcept;
constexpr size_type find(const charT* ptr, size_type offset, size_type count) const;
constexpr size_type find(const charT* ptr, size_type offset = 0) const;
```

### <a name="parameters"></a>Parameter

*str*<br/>
Die String_view für die die Memberfunktion ist, um zu suchen.

*chVal*<br/>
Der Zeichenwert, nach dem die Memberfunktion suchen soll.

*offset*<br/>
Der Index, an dem die Suche begonnen werden soll.

*ptr*<br/>
Die C-Zeichenfolge, die für die die Memberfunktion ist, um zu suchen.

*count*<br/>
Die Anzahl der Zeichen in *Ptr*, vom ersten Zeichen vorwärts.

### <a name="return-value"></a>Rückgabewert

Der Index des ersten Zeichens der Teilzeichenfolge, nach der bei Erfolg gesucht wird; andernfalls `npos`.

## <a name="find_first_not_of"></a>  basic_string_view::find_first_not_of

Sucht nach dem ersten Zeichen, das nicht auf ein Element eines angegebenen String_view oder konvertiert werden String-Objekt ist.

```cpp
constexpr size_type find_first_not_of(basic_string_view str, size_type offset = 0) const noexcept;
constexpr size_type find_first_not_of(charT chVal, size_type offset = 0) const noexcept;
constexpr size_type find_first_not_of(const charT* ptr, size_type offset, size_type count) const;
constexpr size_type find_first_not_of(const charT* ptr, size_type offset = 0) const;
```

### <a name="parameters"></a>Parameter

*str*<br/>
Die String_view für die die Memberfunktion ist, um zu suchen.

*chVal*<br/>
Der Zeichenwert, nach dem die Memberfunktion suchen soll.

*offset*<br/>
Der Index, an dem die Suche begonnen werden soll.

*ptr*<br/>
Die C-Zeichenfolge, die für die die Memberfunktion ist, um zu suchen.

*count*<br/>
Die Anzahl der Zeichen, vorwärts aus dem ersten Zeichen in der C-Zeichenfolge, die für die die Memberfunktion ist, um zu suchen.

### <a name="return-value"></a>Rückgabewert

Der Index des ersten Zeichens der Teilzeichenfolge, nach der bei Erfolg gesucht wird; andernfalls `npos`.

## <a name="find_first_of"></a>  basic_string_view::find_first_of

Sucht nach dem ersten Zeichen, das ein Element in einer angegebenen String_view entspricht.

```cpp
constexpr size_type find_first_of(basic_string_view str, size_type offset = 0) const noexcept;
constexpr size_type find_first_of(charT chVal, size_type offset = 0) const noexcept;
constexpr size_type find_first_of(const charT* str, size_type offset, size_type count) const;
constexpr size_type find_first_of(const charT* str, size_type offset = 0) const;
```

### <a name="parameters"></a>Parameter

*chVal*<br/>
Der Zeichenwert, nach dem die Memberfunktion suchen soll.

*offset*<br/>
Der Index, an dem die Suche begonnen werden soll.

*ptr*<br/>
Die C-Zeichenfolge, die für die die Memberfunktion ist, um zu suchen.

*count*<br/>
Die Anzahl der Zeichen, vorwärts aus dem ersten Zeichen in der C-Zeichenfolge, die für die die Memberfunktion ist, um zu suchen.

*str*<br/>
Die String_view für die die Memberfunktion ist, um zu suchen.

### <a name="return-value"></a>Rückgabewert

Der Index des ersten Zeichens der Teilzeichenfolge, nach der bei Erfolg gesucht wird; andernfalls `npos`.

## <a name="find_last_not_of"></a>  basic_string_view::find_last_not_of

Sucht nach dem letzten Zeichen, das nicht auf ein Element in einer angegebenen String_view ist.

```cpp
constexpr size_type find_last_not_of(basic_string_view str, size_type offset = npos) const noexcept;
constexpr size_type find_last_not_of(charT chVal, size_type offset = npos) const noexcept;
constexpr size_type find_last_not_of(const charT* ptr, size_type offset, size_type count) const;
constexpr size_type find_last_not_of(const charT* ptr, size_type offset = npos) const;
```

### <a name="parameters"></a>Parameter

*str*<br/>
Die String_view für die die Memberfunktion ist, um zu suchen.

*chVal*<br/>
Der Zeichenwert, nach dem die Memberfunktion suchen soll.

*offset*<br/>
Der Index, an dem die Suche ist, um den Vorgang abzuschließen.

*ptr*<br/>
Die C-Zeichenfolge, die für die die Memberfunktion ist, um zu suchen.

*count*<br/>
Die Anzahl der Zeichen, vorwärts aus dem ersten Zeichen in *Ptr*.

### <a name="return-value"></a>Rückgabewert

Der Index des ersten Zeichens der Teilzeichenfolge, nach der bei Erfolg gesucht wird; andernfalls `string_view::npos`.

## <a name="find_last_of"></a>  basic_string_view::find_last_of

Sucht nach dem letzten Zeichen, das ein Element in einer angegebenen String_view entspricht.

```cpp
constexpr size_type find_last_of(basic_string_view str, size_type offset = npos) const noexcept;
constexpr size_type find_last_of(charT chVal, size_type offset = npos) const noexcept;
constexpr size_type find_last_of(const charT* ptr, size_type offset, size_type count) const;
constexpr size_type find_last_of(const charT* ptr, size_type offset = npos) const;
```

### <a name="parameters"></a>Parameter

*str*<br/>
Die String_view für die die Memberfunktion ist, um zu suchen.

*chVal*<br/>
Der Zeichenwert, nach dem die Memberfunktion suchen soll.

*offset*<br/>
Der Index, an dem die Suche ist, um den Vorgang abzuschließen.

*ptr*<br/>
Die C-Zeichenfolge, die für die die Memberfunktion ist, um zu suchen.

*count*<br/>
Die Anzahl der Zeichen, vorwärts aus dem ersten Zeichen in der C-Zeichenfolge, die für die die Memberfunktion ist, um zu suchen.

### <a name="return-value"></a>Rückgabewert

Falls erfolgreich, der Index des letzten Zeichens der gesuchten Teilzeichenfolge, andernfalls `npos`.

## <a name="front"></a>  basic_string_view::Front

Gibt eine Const_reference auf das erste Element zurück.

```cpp
constexpr const_reference front() const;
```

### <a name="return-value"></a>Rückgabewert

Eine Const_reference auf das erste Element.

### <a name="remarks"></a>Hinweise

Löst eine Ausnahme aus, wenn die String_view leer ist.

## <a name="length"></a> basic_string_view::Length

Gibt die aktuelle Anzahl der Elemente zurück.

```cpp
constexpr size_type length() const noexcept;
```

### <a name="remarks"></a>Hinweise

Die Memberfunktion ist identisch mit [size](#size).

## <a name="max_size"></a>  basic_string_view::max_size

Gibt die maximale Anzahl von Zeichen, die eine String_view enthalten kann.

```cpp
constexpr size_type max_size() const noexcept;
```

### <a name="return-value"></a>Rückgabewert

Die maximale Anzahl von Zeichen, die eine String_view kann enthalten.

### <a name="remarks"></a>Hinweise

Eine Ausnahme vom Typ [Length_error](../standard-library/length-error-class.md) wird ausgelöst, wenn ein Vorgang eine String_view mit einer Länge von mehr als erzeugt `max_size()`.

## <a name="op_eq"></a>  basic_string_view::Operator =

Ein Zeichenfolgenobjekt String_view oder konvertiert werden kann und eine andere String_view zugewiesen.

```cpp
constexpr basic_string_view& operator=(const basic_string_view&) noexcept = default;
```
### <a name="example"></a>Beispiel

```cpp
   string_view s = "Hello";
   string_view s2 = s;
```
## <a name="op_at"></a>  basic_string_view::Operator]

Bietet eine Const_reference auf das Zeichen mit einem angegebenen Index.

```cpp
constexpr const_reference operator[](size_type offset) const;
```

### <a name="parameters"></a>Parameter

*offset*<br/>
Der Index des Elements verwiesen werden.

### <a name="return-value"></a>Rückgabewert

Eine Const_reference auf das Zeichen an der Position, die durch den Parameterindex angegeben.

### <a name="remarks"></a>Hinweise

Das erste Element hat einen Index von 0 (null), und die folgenden Elemente werden nacheinander durch positiven ganze Zahlen indiziert, damit eine String_view Länge *n* verfügt über eine *n*th-Element ab, das durch die Anzahl *n* - 1.

`operator[]` ist schneller als die Memberfunktion [am](#at) für die Bereitstellung von Lesezugriff auf die Elemente einer String_view.

`operator[]` überprüft nicht, ob der Index, der als Argument übergebenen gültig ist. Ein ungültiger Index, der an übergebene `operator[]` führt zu nicht definiertem Verhalten.

Der zurückgegebene Verweis kann für ungültig erklärt werden, wenn die zugrunde liegenden Zeichenfolgendaten geändert oder vom besitzenden Objekt gelöscht.

Beim Kompilieren mit [ \_ITERATOR\_DEBUGGEN\_Ebene](../standard-library/iterator-debug-level.md) auf 1 oder 2 festgelegt wird, ein Laufzeitfehler auf, wenn Sie versuchen, ein Element außerhalb der Grenzen des das String_view zuzugreifen. Weitere Informationen finden Sie unter [Checked Iterators](../standard-library/checked-iterators.md).

## <a name="rbegin"></a>  basic_string_view::rbegin

Gibt einen const-Iterator zum ersten Element in einer umgekehrten String_view zurück.

```cpp
constexpr const_reverse_iterator rbegin() const noexcept;
```

### <a name="return-value"></a>Rückgabewert

Gibt einen Iterator mit zufälligem Zugriff zurück, auf das erste Element in einer umgekehrten String_view, Adressierung, was mit dem letzten Element in der entsprechenden nicht umgekehrten String_view wäre.

### <a name="remarks"></a>Hinweise

`rbegin` wird zusammen mit einem umgekehrten String_view wie [beginnen](#begin) mit einem String_view verwendet wird. `rbegin` kann verwendet werden, um eine Iteration rückwärts zu initialisieren.

## <a name="remove_prefix"></a> basic_string_view::remove_prefix

Verschiebt den Zeiger vorwärts durch die angegebene Anzahl von Elementen.

```cpp
constexpr void remove_prefix(size_type n);
```

### <a name="remarks"></a>Hinweise

Bewirkt, dass die zugrunde liegenden Daten unverändert. Bewegt sich der Zeiger von String_view vorwärts durch n Elemente und legt die Private `size` Datenmember, Größe: n.

## <a name="remove_suffix"></a> basic_string_view::remove_suffix

Reduziert die Größe der Ansicht durch die angegebene Anzahl von Elementen, die von der Rückseite ab.

```cpp
constexpr void remove_suffix(size_type n);
```

### <a name="remarks"></a>Hinweise

Bewirkt, dass die zugrunde liegenden Daten und den Zeiger zu unverändert bleiben. Legt die Private `size` Datenmember, Größe: n.

## <a name="rend"></a>  basic_string_view::rend

Gibt einen const-Iterator, der auf eine Stelle hinter dem letzten Element einer umgekehrten String_view verweist.

```cpp
constexpr reverse_iterator rend() const noexcept;
```

### <a name="return-value"></a>Rückgabewert

Ein const_reverse-Iterator mit wahlfreiem Zugriff, die auf eine Stelle hinter dem letzten Element einer umgekehrten String_view verweist.

### <a name="remarks"></a>Hinweise

`rend` wird zusammen mit einem umgekehrten String_view wie [End](#end) mit einem String_view verwendet wird. `rend` kann verwendet werden, um zu testen, ob ein umgekehrter Iterator das Ende seiner String_view erreicht hat. Der von `rend` zurückgegebene Wert darf nicht dereferenziert werden.

## <a name="rfind"></a>  basic_string_view::rfind

Sucht eine String_view in umgekehrter Reihenfolge nach einer Teilzeichenfolge, die mit eine bestimmten Zeichensequenz übereinstimmt.

```cpp
constexpr size_type rfind(basic_string_view str, size_type offset = npos) const noexcept;
constexpr size_type rfind(charT chVal, size_type offset = npos) const noexcept;
constexpr size_type rfind(const charT* ptr, size_type offset, size_type count) const;
constexpr size_type rfind(const charT* ptr, size_type offset = npos) const;
```

### <a name="parameters"></a>Parameter

*chVal*<br/>
Der Zeichenwert, nach dem die Memberfunktion suchen soll.

*offset*<br/>
Der Index, an dem die Suche begonnen werden soll.

*ptr*<br/>
Die C-Zeichenfolge, die für die die Memberfunktion ist, um zu suchen.

*count*<br/>
Die Anzahl der Zeichen, vorwärts aus dem ersten Zeichen in der C-Zeichenfolge, die für die die Memberfunktion ist, um zu suchen.

*str*<br/>
Die String_view für die die Memberfunktion ist, um zu suchen.

### <a name="return-value"></a>Rückgabewert

Der Index des ersten Zeichens der Teilzeichenfolge bei erfolgreicher Ausführung; andernfalls `npos`.

## <a name="size"></a>  basic_string_view::Size

Gibt die Anzahl der Elemente in der String_view zurück.

```cpp
constexpr size_type size() const noexcept;
```

### <a name="return-value"></a>Rückgabewert

Die Länge der String_view.

### <a name="remarks"></a>Hinweise

Eine String_view ändern, die Länge, z. B. indem `remove_prefix` und `remove_suffix`. Da dies nicht die zugrunde liegenden Zeichenfolgendaten ändert, ist die Größe einer String_view nicht unbedingt die Größe des zugrunde liegenden Daten.

## <a name="substr"></a>  basic_string_view::SUBSTR

Gibt eine String_view, die die angegebene Anzahl von Zeichen (höchstens) von einer angegebenen Position darstellt.

```cpp
constexpr basic_string_view substr(size_type offset = 0, size_type count = npos) const;
```

### <a name="parameters"></a>Parameter

*offset*<br/>
Ein Index, suchen das Element an der Position, von der die Kopie, hat den Standardwert 0 erstellt wird.

*count*<br/>
Die Anzahl der Zeichen in die Teilzeichenfolge, eingeschlossen werden soll, wenn sie vorhanden sind.

### <a name="return-value"></a>Rückgabewert

Ein String_view-Objekt, das die angegebene untergeordneten Sequenz von Elementen darstellt.

## <a name="swap"></a>  basic_string_view::Swap

Tauscht zwei String_views, anders ausgedrückt: die Zeiger auf die zugrunde liegenden Zeichenfolgendaten, und die Größe an.

```cpp
constexpr void swap(basic_string_view& sv) noexcept;
```

### <a name="parameters"></a>Parameter

*sv*<br/>
Die Quelle String_view, deren Werte Zeiger und Größe sind, mit der die Ziel-String_view ausgetauscht werden sollen.

## <a name="see-also"></a>Siehe auch

[\<string_view>](../standard-library/string-view.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
