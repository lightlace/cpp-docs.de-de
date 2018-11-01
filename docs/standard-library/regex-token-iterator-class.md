---
title: regex_token_iterator-Klasse
ms.date: 09/10/2018
f1_keywords:
- regex/std::regex_token_iterator
- regex/std::regex_token_iterator::regex_type
- regex/std::regex_token_iterator::value_type
- regex/std::regex_token_iterator::iterator_category
- regex/std::regex_token_iterator::difference_type
- regex/std::regex_token_iterator::pointer
- regex/std::regex_token_iterator::reference
- regex/std::regex_token_iterator::operator==
- regex/std::regex_token_iterator::operator!=
- regex/std::regex_token_iterator::operator*
- regex/std::regex_token_iterator::operator->
- regex/std::regex_token_iterator::operator++
helpviewer_keywords:
- std::regex_token_iterator [C++]
- std::regex_token_iterator [C++], regex_type
- std::regex_token_iterator [C++], value_type
- std::regex_token_iterator [C++], iterator_category
- std::regex_token_iterator [C++], difference_type
- std::regex_token_iterator [C++], pointer
- std::regex_token_iterator [C++], reference
ms.assetid: a213ba48-8e4e-4b6b-871a-2637acf05f15
ms.openlocfilehash: 2cb66ce4cbee0936211e5e991b18f3ae4b8a7fe5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50473514"
---
# <a name="regextokeniterator-class"></a>regex_token_iterator-Klasse

Iteratorklasse für Teilübereinstimmungen.

## <a name="syntax"></a>Syntax

```cpp
template<class BidIt,
   class Elem = typename std::iterator_traits<BidIt>::value_type,
   class RxTraits = regex_traits<Elem> >
class regex_token_iterator
```

## <a name="parameters"></a>Parameter

*BidIt*<br/>
Der Itertatortyp für Teilübereinstimmungen.

*Elem*<br/>
Der zu entsprechende Elementtyp.

*RXtraits*<br/>
Merkmalklasse für Elemente.

## <a name="remarks"></a>Hinweise

Die Vorlagenklasse beschreibt ein Objekt mit einem konstanten Forward-Iterator. Vom Konzept her enthält sie ein `regex_iterator` -Objekt, das in der Klasse verwendet wird, um in einer Zeichenfolge nach Übereinstimmungen eines regulären Ausdrucks zu suchen. In der Klasse werden Objekte des Typs `sub_match<BidIt>` extrahiert, die den Teilübereinstimmungen entsprechen, die durch die Indexwerte im gespeicherten Vektor `subs` für jede Übereinstimmung des regulären Ausdrucks gekennzeichnet sind.

Der Indexwert -1 kennzeichnet die Zeichenfolge, die unmittelbar nach dem Ende der vorherigen Übereinstimmung des regulären Ausdrucks oder, wenn es keine vorherige Übereinstimmung eines regulären Ausdrucks gab, am Anfang der Zeichenfolge beginnt und sich, ohne es zu enthalten, bis zum ersten Zeichen der aktuellen Übereinstimmung des regulären Ausdrucks oder bis zum Ende der Zeichenfolge erstreckt, wenn es keine aktuelle Übereinstimmung gibt. Jeder andere Indexwert `idx` kennzeichnet die Inhalte der Erfassungsgruppe, die in `it.match[idx]`enthalten ist.

### <a name="members"></a>Member

|Member|Standardwert|
|-|-|
|`private regex_iterator<BidIt, Elem, RXtraits> it`||
|`private vector<int> subs`||
|`private int pos`||

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[regex_token_iterator](#regex_token_iterator)|Erstellt den Iterator.|

### <a name="typedefs"></a>Typedefs

|Typname|Beschreibung|
|-|-|
|[difference_type](#difference_type)|Der Typ einer Iteratordifferenz.|
|[iterator_category](#iterator_category)|Der Typ der Iteratorkategorie.|
|[Zeiger](#pointer)|Der Typ eines Zeigers auf eine Übereinstimmung.|
|[Verweis](#reference)|Der Typ eines Verweises auf eine Teilübereinstimmung.|
|[regex_type](#regex_type)|Der Typ des regulären Ausdrucks, der übereinstimmen soll.|
|[value_type](#value_type)|Der Typ einer Teilübereinstimmung.|

### <a name="operators"></a>Operatoren

|Operator|Beschreibung|
|-|-|
|[Operator!=](#op_neq)|Vergleicht Iteratoren auf Ungleichheit.|
|[operator*](#op_star)|Greift auf die gekennzeichnete Teilübereinstimmung zu.|
|[operator++](#op_add_add)|Erhöht den Iterator.|
|[operator==](#op_eq_eq)|Vergleicht Iteratoren auf Gleichheit.|
|[operator->](#op_arrow)|Greift auf die gekennzeichnete Teilübereinstimmung zu.|

## <a name="requirements"></a>Anforderungen

**Header:** \<regex >

**Namespace:** std

## <a name="example"></a>Beispiel

```cpp
#include <regex>
#include <iostream>

typedef std::regex_token_iterator<const char *> Myiter;
int main()
    {
    const char *pat = "aaxaayaaz";
    Myiter::regex_type rx("(a)a");
    Myiter next(pat, pat + strlen(pat), rx);
    Myiter end;

// show whole match
    for (; next != end; ++next)
        std::cout << "match == " << next->str() << std::endl;
    std::cout << std::endl;

// show prefix before match
    next = Myiter(pat, pat + strlen(pat), rx, -1);
    for (; next != end; ++next)
        std::cout << "match == " << next->str() << std::endl;
    std::cout << std::endl;

// show (a) submatch only
    next = Myiter(pat, pat + strlen(pat), rx, 1);
    for (; next != end; ++next)
        std::cout << "match == " << next->str() << std::endl;
    std::cout << std::endl;

// show prefixes and submatches
    std::vector<int> vec;
    vec.push_back(-1);
    vec.push_back(1);
    next = Myiter(pat, pat + strlen(pat), rx, vec);
    for (; next != end; ++next)
        std::cout << "match == " << next->str() << std::endl;
    std::cout << std::endl;

// show prefixes and whole matches
    int arr[] = {-1, 0};
    next = Myiter(pat, pat + strlen(pat), rx, arr);
    for (; next != end; ++next)
        std::cout << "match == " << next->str() << std::endl;
    std::cout << std::endl;

// other members
    Myiter it1(pat, pat + strlen(pat), rx);
    Myiter it2(it1);
    next = it1;

    Myiter::iterator_category cat = std::forward_iterator_tag();
    Myiter::difference_type dif = -3;
    Myiter::value_type mr = *it1;
    Myiter::reference ref = mr;
    Myiter::pointer ptr = &ref;

    dif = dif; // to quiet "unused" warnings
    ptr = ptr;

    return (0);
    }
```

```Output
match == aa
match == aa
match == aa

match ==
match == x
match == y
match == z

match == a
match == a
match == a

match ==
match == a
match == x
match == a
match == y
match == a
match == z

match ==
match == aa
match == x
match == aa
match == y
match == aa
match == z
```

## <a name="difference_type"></a> regex_token_iterator::difference_type

Der Typ einer Iteratordifferenz.

```cpp
typedef std::ptrdiff_t difference_type;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für `std::ptrdiff_t`.

## <a name="iterator_category"></a> regex_token_iterator::iterator_category

Der Typ der Iteratorkategorie.

```cpp
typedef std::forward_iterator_tag iterator_category;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für `std::forward_iterator_tag`.

## <a name="op_neq"></a> regex_token_iterator::operator!=

Vergleicht Iteratoren auf Ungleichheit.

```cpp
bool operator!=(const regex_token_iterator& right);
```

### <a name="parameters"></a>Parameter

*right*<br/>
Der Iterator für den Vergleich.

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt `!(*this == right)`zurück.

## <a name="op_star"></a> regex_token_iterator::operator*

Greift auf die gekennzeichnete Teilübereinstimmung zu.

```cpp
const sub_match<BidIt>& operator*();
```

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt ein `sub_match<BidIt>` -Objekt zurück, das der Erfassungsgruppe entspricht, die durch den Indexwert `subs[pos]`gekennzeichnet ist.

## <a name="op_add_add"></a> regex_token_iterator::operator++

Erhöht den Iterator.

```cpp
regex_token_iterator& operator++();

regex_token_iterator& operator++(int);
```

### <a name="remarks"></a>Hinweise

Wenn der gespeicherte Iterator `it` ein Iterator am Ende der Sequenz ist, legt der erste Operator den gespeicherten Wert `pos` auf den Wert von `subs.size()` fest (wodurch er ein Iterator am Ende der Sequenz wird). Andernfalls erhöht der Operator den gespeicherten Wert `pos`. Wenn das Ergebnis dem Wert `subs.size()` entspricht, wird der gespeicherte Wert `pos` auf 0 (null) festgelegt und der gespeicherte Iterator `it` wird erhöht. Wenn beim Inkrementieren der gespeicherte Iterator keinem Iterator am Ende der Sequenz entspricht, führt der Operator keine weitere Aktion aus. Andernfalls, wenn das Ende der vorherigen Übereinstimmung sich am Ende der Zeichenfolge befand, legt der Operator den gespeicherten Wert von `pos` auf `subs.size()` fest. Andernfalls erhöht der Operator wiederholt den gespeicherten Wert `pos` bis auf `pos == subs.size()` oder `subs[pos] == -1` (wodurch sichergestellt wird, dass die nächste Dereferenzierung des Iterators das Ende der Zeichenfolge zurückgibt, wenn einer der Indexwerte -1 ist). In allen Fällen gibt der Operator das Objekt zurück.

Der zweite Operator erstellt eine Kopie des Objekts, erhöht das Objekt und gibt dann die Kopie zurück.

## <a name="op_eq_eq"></a> regex_token_iterator::operator==

Vergleicht Iteratoren auf Gleichheit.

```cpp
bool operator==(const regex_token_iterator& right);
```

### <a name="parameters"></a>Parameter

*right*<br/>
Der Iterator für den Vergleich.

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt `it == right.it && subs == right.subs && pos == right.pos`zurück.

## <a name="op_arrow"></a> regex_token_iterator::operator-&gt;

Greift auf die gekennzeichnete Teilübereinstimmung zu.

```cpp
const sub_match<BidIt> * operator->();
```

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt einen Zeiger auf ein `sub_match<BidIt>` -Objekt zurück, das der Erfassungsgruppe entspricht, die durch den Indexwert `subs[pos]`gekennzeichnet ist.

## <a name="pointer"></a> regex_token_iterator::pointer

Der Typ eines Zeigers auf eine Übereinstimmung.

```cpp
typedef sub_match<BidIt> *pointer;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für `sub_match<BidIt>*`, wobei `BidIt` der Vorlagenparameter ist.

## <a name="reference"></a> regex_token_iterator::reference

Der Typ eines Verweises auf eine Teilübereinstimmung.

```cpp
typedef sub_match<BidIt>& reference;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für `sub_match<BidIt>&`, wobei `BidIt` der Vorlagenparameter ist.

## <a name="regex_token_iterator"></a> regex_token_iterator::regex_token_iterator

Erstellt den Iterator.

```cpp
regex_token_iterator();

regex_token_iterator(BidIt first, BidIt last,
    const regex_type& re, int submatch = 0,
    regex_constants::match_flag_type f = regex_constants::match_default);

regex_token_iterator(BidIt first, BidIt last,
    const regex_type& re, const vector<int> submatches,
    regex_constants::match_flag_type f = regex_constants::match_default);

template <std::size_t N>
regex_token_iterator(BidIt first, BidIt last,
    const regex_type& re, const int (&submatches)[N],
    regex_constants::match_flag_type f = regex_constants::match_default);
```

### <a name="parameters"></a>Parameter

*Erste*<br/>
Anfang der Sequenz, die übereinstimmen soll.

*last*<br/>
Ende der Sequenz, die übereinstimmen soll.

*RE*<br/>
Regulärer Ausdruck für Übereinstimmungen.

*f*<br/>
Flags für Übereinstimmungen.

### <a name="remarks"></a>Hinweise

Der erste Konstruktor erstellt einen Sequenzende-Iterator.

Der zweite Konstruktor erstellt ein Objekt, dessen gespeicherter Iterator `it` auf `regex_iterator<BidIt, Elem, RXtraits>(first, last, re, f)`initialisiert wird, dessen gespeicherter Vektor `subs` genau eine ganze Zahl mit dem Wert `submatch`enthält und dessen gespeicherter Wert `pos` gleich 0 (null) ist. Hinweis: Das resultierende Objekt extrahiert für jede erfolgreiche Übereinstimmung des regulären Ausdrucks die Teilübereinstimmung, die durch den Indexwert `submatch` gekennzeichnet ist.

Der dritte Konstruktor erstellt ein Objekt, dessen gespeicherter Iterator `it` auf `regex_iterator<BidIt, Elem, RXtraits>(first, last, re, f)`initialisiert wird, dessen gespeicherter Vektor `subs` genau eine Kopie des Konstruktorarguments `submatches`enthält und dessen gespeicherter Wert `pos` gleich 0 (null) ist.

Der vierte Konstruktor erstellt ein Objekt, dessen gespeicherter Iterator `it` auf `regex_iterator<BidIt, Elem, RXtraits>(first, last, re, f)`initialisiert wird, dessen gespeicherter Vektor `subs` die `N` Werte enthält, auf die das Konstruktorargument `submatches`zeigt, und dessen gespeicherter Wert `pos` gleich 0 (null) ist.

## <a name="regex_type"></a> regex_token_iterator::regex_type

Der Typ des regulären Ausdrucks, der übereinstimmen soll.

```cpp
typedef basic_regex<Elem, RXtraits> regex_type;
```

### <a name="remarks"></a>Hinweise

Die Typedef ist ein Synonym für `basic_regex<Elem, RXtraits>`.

## <a name="value_type"></a> regex_token_iterator::value_type

Der Typ einer Teilübereinstimmung.

```cpp
typedef sub_match<BidIt> value_type;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für `sub_match<BidIt>`, wobei `BidIt` der Vorlagenparameter ist.

## <a name="see-also"></a>Siehe auch

[\<regex>](../standard-library/regex.md)<br/>
[regex_constants-Klasse](../standard-library/regex-constants-class.md)<br/>
[regex_error-Klasse](../standard-library/regex-error-class.md)<br/>
[\<regex>-Funktionen](../standard-library/regex-functions.md)<br/>
[regex_iterator-Klasse](../standard-library/regex-iterator-class.md)<br/>
[\<regex>-Operatoren](../standard-library/regex-operators.md)<br/>
[regex_traits-Klasse](../standard-library/regex-traits-class.md)<br/>
[\<regex>-Typdefinitionen](../standard-library/regex-typedefs.md)<br/>
