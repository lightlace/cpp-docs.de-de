---
title: basic_regex-Klasse
ms.date: 09/10/2018
f1_keywords:
- regex/std::basic_regex
helpviewer_keywords:
- basic_regex class
ms.assetid: 8a18c6b4-f22a-4cfd-bc16-b4267867ebc3
ms.openlocfilehash: 0799bbcbfb7cdbc1ee1755cf387de2aee46db027
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50633404"
---
# <a name="basicregex-class"></a>basic_regex-Klasse

Umschließt einen regulären Ausdruck.

## <a name="syntax"></a>Syntax

```cpp
template <class Elem, class RXtraits>
class basic_regex
```

## <a name="parameters"></a>Parameter

*Elem*<br/>
Der zu entsprechende Elementtyp.

*RXtraits*<br/>
Merkmalklasse für Elemente.

## <a name="remarks"></a>Hinweise

Die Vorlagenklasse beschreibt ein Objekt, das einen regulären Ausdruck enthält. Objekte dieser Vorlagenklasse können übergeben werden, an die Vorlagenfunktionen [Regex_match](../standard-library/regex-functions.md#regex_match), [Regex_search](../standard-library/regex-functions.md#regex_search), und [Regex_replace](../standard-library/regex-functions.md#regex_replace), zusammen mit geeigneten Textzeichenfolgen-Argumenten, Um nach Text suchen, die dem regulären Ausdruck übereinstimmt. Es gibt zwei spezialisierungen dieser Vorlagenklasse mit den Typdefinitionen [Regex](../standard-library/regex-typedefs.md#regex) für Elemente des Typs **Char**, und [Wregex](../standard-library/regex-typedefs.md#wregex) für Elemente des Typs  **"wchar_t"**.

Das Vorlagenargument *RXtraits* beschreibt verschiedene wichtige Eigenschaften der Syntax von regulären Ausdrücken, die von der Vorlagenklasse unterstützt. Eine Klasse, die diese Merkmale des regulären Ausdrucks angibt, muss dieselbe externe Schnittstelle wie ein Objekt der Vorlagenklasse [regex_traits-Class](../standard-library/regex-traits-class.md) haben.

Einige Funktionen akzeptieren eine Operandensequenz, die einen regulären Ausdruck definiert. Sie können eine solche Operandensequenz wie folgt angeben:

`ptr` – eine nullterminierte Sequenz (z. B. eine C-Zeichenfolge für *Elem* vom Typ **Char**) beginnend bei `ptr` (keinen null-Zeiger sein muss), wobei das abschließende Element der Wert ist `value_type()` und ist nicht Teil der operandensequenz

`ptr`, `count` – eine Sequenz von `count`-Elementen, die bei `ptr` (darf kein NULL-Zeiger sein) beginnen

`str` – die vom `basic_string`-Objekt `str` angegebene Sequenz

`first`, `last` – eine Sequenz von Elementen, die durch die Iteratoren `first` und `last` im Bereich `[first, last)` abgegrenzt werden

`right` – das `basic_regex`-Objekt `right`

Diese Memberfunktionen akzeptieren auch ein Argument `flags` , verschiedene Optionen für die Interpretation des regulären Ausdrucks zusätzlich zu den beschriebenen angibt, die *RXtraits* Typ.

### <a name="members"></a>Member

|Member|Standardwert|
|-|-|
|public static const Flag_type icase|regex_constants::icase|
|public static const Flag_type nosubs|regex_constants::nosubs|
|public static const Flag_type zu optimieren.|regex_constants::Optimize|
|public static const Flag_type sortieren|regex_constants::COLLATE|
|public static const Flag_type ECMAScript|regex_constants::ECMAScript|
|public static const Flag_type basic|regex_constants::Basic|
|public static const Flag_type erweitert|regex_constants::Extended|
|public static const Flag_type awk|regex_constants::awk|
|public static const Flag_type grep|regex_constants::GREP|
|public static const Flag_type egrep|regex_constants::egrep|
|Private RXtraits "traits"||

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[basic_regex](#basic_regex)|Konstruiert das reguläre Ausdrucksobjekt.|

### <a name="typedefs"></a>Typedefs

|Typname|Beschreibung|
|-|-|
|[flag_type](#flag_type)|Der Typ der Syntaxoptionsflags.|
|[locale_type](#locale_type)|Der Typ des gespeicherten Gebietsschemaobjekts.|
|[value_type](#value_type)|Der Elementtyp.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[assign](#assign)|Weist dem Objekt für einen regulären Ausdruck einen Wert zu.|
|[flags](#flags)|Gibt Syntaxoptionsflags zurück.|
|[get_loc](#get_loc)|Gibt das gespeicherte Gebietsschemaobjekt zurück.|
|[imbue](#imbue)|Ändert das gespeicherte Gebietsschemaobjekt.|
|[mark_count](#mark_count)|Gibt die Anzahl der übereinstimmenden Teilausdrücke zurück.|
|[swap](#swap)|Tauscht zwei Objekte mit regulärem Ausdruck.|

### <a name="operators"></a>Operatoren

|Operator|Beschreibung|
|-|-|
|[operator=](#op_eq)|Weist dem Objekt für einen regulären Ausdruck einen Wert zu.|

## <a name="requirements"></a>Anforderungen

**Header:** \<regex >

**Namespace:** std

## <a name="example"></a>Beispiel

```cpp
// std__regex__basic_regex.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

using namespace std;

int main()
{
    regex::value_type elem = 'x';
    regex::flag_type flag = regex::grep;

    elem = elem;  // to quiet "unused" warnings
    flag = flag;

    // constructors
    regex rx0;
    cout << "match(\"abc\", \"\") == " << boolalpha
        << regex_match("abc", rx0) << endl;

    regex rx1("abcd", regex::ECMAScript);
    cout << "match(\"abc\", \"abcd\") == " << boolalpha
        << regex_match("abc", rx1) << endl;

    regex rx2("abcd", 3);
    cout << "match(\"abc\", \"abc\") == " << boolalpha
        << regex_match("abc", rx2) << endl;

    regex rx3(rx2);
    cout << "match(\"abc\", \"abc\") == " << boolalpha
        << regex_match("abc", rx3) << endl;

    string str("abcd");
    regex rx4(str);
    cout << "match(string(\"abcd\"), \"abc\") == " << boolalpha
        << regex_match("abc", rx4) << endl;

    regex rx5(str.begin(), str.end() - 1);
    cout << "match(string(\"abc\"), \"abc\") == " << boolalpha
        << regex_match("abc", rx5) << endl;
    cout << endl;

    // assignments
    rx0 = "abc";
    rx0 = rx1;
    rx0 = str;

    rx0.assign("abcd", regex::ECMAScript);
    rx0.assign("abcd", 3);
    rx0.assign(rx1);
    rx0.assign(str);
    rx0.assign(str.begin(), str.end() - 1);

    rx0.swap(rx1);

    // mark_count
    cout << "\"abc\" mark_count == "
        << regex("abc").mark_count() << endl;
    cout << "\"(abc)\" mark_count == "
        << regex("(abc)").mark_count() << endl;

    // locales
    regex::locale_type loc = rx0.imbue(locale());
    cout << "getloc == imbued == " << boolalpha
        << (loc == rx0.getloc()) << endl;

    // initializer_list
    regex rx6({ 'a', 'b', 'c' }, regex::ECMAScript);
    cout << "match(\"abc\") == " << boolalpha
        << regex_match("abc", rx6);
    cout << endl;
}
```

```Output
match("abc", "") == false
match("abc", "abcd") == false
match("abc", "abc") == true
match("abc", "abc") == true
match(string("abcd"), "abc") == false
match(string("abc"), "abc") == true

"abc" mark_count == 0
"(abc)" mark_count == 1
getloc == imbued == true
match("abc") == true
```

## <a name="assign"></a> basic_regex::assign

Weist dem Objekt für einen regulären Ausdruck einen Wert zu.

```cpp
basic_regex& assign(
    const basic_regex& right);

basic_regex& assign(
    const Elem* ptr,
    flag_type flags = ECMAScript);

basic_regex& assign(
    const Elem* ptr,
    size_type len,
    flag_type flags = ECMAScript);

basic_regex& assign(
    initializer_list<_Elem> IList,
    flag_type flags = regex_constants::ECMAScript);

template <class STtraits, class STalloc>
basic_regex& assign(
    const basic_string<Elem, STtraits, STalloc>& str,
    flag_type flags = ECMAScript);

template <class InIt>
basic_regex& assign(
    InIt first, InIt last,
    flag_type flags = ECMAScript);
```

### <a name="parameters"></a>Parameter

*STtraits*<br/>
Merkmalklasse für eine Zeichenfolgequelle.

*STalloc*<br/>
Zuweisungsklasse für eine Zeichenfolgequelle.

*InIt*<br/>
Eingabeiteratortyp für eine Bereichsquelle.

*right*<br/>
Zu kopierende RegEx-Quelle.

*ptr*<br/>
Zeiger zum Anfang der zu kopierenden Sequenz.

*flags*<br/>
Syntaxoptionsflags, die beim Kopieren hinzugefügt werden.

*Len/TD >*<br/>
Länge der zu kopierenden Sequenz.

*str*<br/>
Zu kopierende Zeichenfolge.

*Erste*<br/>
Anfang der zu kopierenden Sequenz.

*last*<br/>
Ende der zu kopierenden Sequenz.

*IList*<br/>
Das zu kopierende initializer_list-Element.

### <a name="remarks"></a>Hinweise

Jede Memberfunktion ersetzt den regulären Ausdruck, der in `*this` enthalten ist durch den regulären Ausdruck, der in der Operandensequenz enthalten ist und gibt dann `*this` zurück.

## <a name="basic_regex"></a> basic_regex::basic_regex

Konstruiert das reguläre Ausdrucksobjekt.

```cpp
basic_regex();

explicit basic_regex(
    const Elem* ptr,
    flag_type flags);

explicit basic_regex(
    const Elem* ptr,
    size_type len,
    flag_type flags);

basic_regex(
    const basic_regex& right);

basic_regex(
    initializer_list<Type> IList,
    flag_type flags);

template <class STtraits, class STalloc>
explicit basic_regex(
    const basic_string<Elem, STtraits, STalloc>& str,
    flag_type flags);

template <class InIt>
explicit basic_regex(
    InIt first,
    InIt last,
    flag_type flags);
```

### <a name="parameters"></a>Parameter

*STtraits*<br/>
Merkmalklasse für eine Zeichenfolgequelle.

*STalloc*<br/>
Zuweisungsklasse für eine Zeichenfolgequelle.

*InIt*<br/>
Eingabeiteratortyp für eine Bereichsquelle.

*right*<br/>
Zu kopierende RegEx-Quelle.

*ptr*<br/>
Zeiger zum Anfang der zu kopierenden Sequenz.

*flags*<br/>
Syntaxoptionsflags, die beim Kopieren hinzugefügt werden.

*Len/TD >*<br/>
Länge der zu kopierenden Sequenz.

*str*<br/>
Zu kopierende Zeichenfolge.

*Erste*<br/>
Anfang der zu kopierenden Sequenz.

*last*<br/>
Ende der zu kopierenden Sequenz.

*IList*<br/>
Das zu kopierende initializer_list-Element.

### <a name="remarks"></a>Hinweise

Alle Konstruktoren speichern ein standardmäßig erstelltes Objekt vom Typ `RXtraits`.

Der erste Konstruktor erstellt ein leeres `basic_regex`-Objekt. Die anderen Konstruktoren erstellen ein `basic_regex`-Objekt, das den regulären Ausdruck enthält, der von der Operandensequenz beschrieben wird.

Ein leeres `basic_regex` -Objekt entspricht keiner Zeichensequenz, die bei der Übergabe an [Regex_match](../standard-library/regex-functions.md#regex_match), [Regex_search](../standard-library/regex-functions.md#regex_search), oder [Regex_replace](../standard-library/regex-functions.md#regex_replace).

## <a name="flag_type"></a> basic_regex::flag_type

Der Typ der Syntaxoptionsflags.

```cpp
typedef regex_constants::syntax_option_type flag_type;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für [regex_constants::syntax_option_type](../standard-library/regex-constants-class.md#syntax_option_type).

## <a name="flags"></a> basic_regex::flags

Gibt Syntaxoptionsflags zurück.

```cpp
flag_type flags() const;
```

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt den Wert des `flag_type`-Arguments zurück, das an den letzten Aufruf einer der [basic_regex::assign](#assign)-Memberfunktionen übergeben wurde. Wenn kein Aufruf erfolgt ist, wird der an den Konstruktor übergebene Wert zurückgegeben.

## <a name="getloc"></a> basic_regex::getloc

Gibt das gespeicherte Gebietsschemaobjekt zurück.

```cpp
locale_type getloc() const;
```

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt `traits.` [regex_traits::getloc](../standard-library/regex-traits-class.md#getloc)`()` zurück.

## <a name="imbue"></a> basic_regex::imbue

Ändert das gespeicherte Gebietsschemaobjekt.

```cpp
locale_type imbue(locale_type loc);
```

### <a name="parameters"></a>Parameter

*Loc*<br/>
Das zu speichernde Gebietsschemaobjekt.

### <a name="remarks"></a>Hinweise

Die Memberfunktion leert `*this` und gibt `traits.`[regex_traits::imbue](../standard-library/regex-traits-class.md#imbue)`(loc)` zurück.

## <a name="locale_type"></a> basic_regex::locale_type

Der Typ des gespeicherten Gebietsschemaobjekts.

```cpp
typedef typename RXtraits::locale_type locale_type;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für [regex_traits::locale_type](../standard-library/regex-traits-class.md#locale_type).

## <a name="mark_count"></a> basic_regex::mark_count

Gibt die Anzahl der übereinstimmenden Teilausdrücke zurück.

```cpp
unsigned mark_count() const;
```

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt die Anzahl der Erfassungsgruppen im regulären Ausdruck zurück.

## <a name="op_eq"></a> basic_regex::operator=

Weist dem Objekt für einen regulären Ausdruck einen Wert zu.

```cpp
basic_regex& operator=(const basic_regex& right);

basic_regex& operator=(const Elem *str);

template <class STtraits, class STalloc>
basic_regex& operator=(const basic_string<Elem, STtraits, STalloc>& str);
```

### <a name="parameters"></a>Parameter

*STtraits*<br/>
Merkmalklasse für eine Zeichenfolgequelle.

*STalloc*<br/>
Zuweisungsklasse für eine Zeichenfolgequelle.

*right*<br/>
Zu kopierende RegEx-Quelle.

*str*<br/>
Zu kopierende Zeichenfolge.

### <a name="remarks"></a>Hinweise

Jeder Operator ersetzt den regulären Ausdruck, der in `*this` enthalten ist, durch den regulären Ausdruck, der in der Operandensequenz enthalten ist, und gibt dann `*this`zurück.

## <a name="swap"></a> basic_regex::swap

Tauscht zwei Objekte mit regulärem Ausdruck.

```cpp
void swap(basic_regex& right) throw();
```

### <a name="parameters"></a>Parameter

*right*<br/>
Das Objekt mit regulärem Ausdruck, gegen das getauscht werden soll.

### <a name="remarks"></a>Hinweise

Die Memberfunktion tauscht die regulären Ausdrücke zwischen `*this` und *rechten*. Die Funktion führt dies in konstanter Zeit aus und löst keine Ausnahmen aus.

## <a name="value_type"></a> basic_regex::value_type

Der Elementtyp.

```cpp
typedef Elem value_type;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für den Vorlagenparameter *Elem*.

## <a name="see-also"></a>Siehe auch

[\<regex>](../standard-library/regex.md)<br/>
[regex_match](../standard-library/regex-functions.md#regex_match)<br/>
[regex_search](../standard-library/regex-functions.md#regex_search)<br/>
[regex_replace](../standard-library/regex-functions.md#regex_replace)<br/>
[regex](../standard-library/regex-typedefs.md#regex)<br/>
[wregex](../standard-library/regex-typedefs.md#wregex)<br/>
[regex_traits-Klasse](../standard-library/regex-traits-class.md)<br/>
