---
title: regex_iterator-Klasse
ms.date: 09/10/2018
f1_keywords:
- regex/std::regex_iterator
- regex/std::regex_iterator::operator==
- regex/std::regex_iterator::operator!=
- regex/std::regex_iterator::operator*
- regex/std::regex_iterator::operator->
- regex/std::regex_iterator::operator++
helpviewer_keywords:
- std::regex_iterator
- std::regex_iterator::operator==
- std::regex_iterator::operator!=
- std::regex_iterator::operator*
- std::regex_iterator::operator->
- std::regex_iterator::operator++
ms.assetid: 0cfd8fd0-5a95-4f3c-bf8e-6ef028c423d3
ms.openlocfilehash: 937c217cdef6895aaa3adb1499f1fde8f67fd513
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50482627"
---
# <a name="regexiterator-class"></a>regex_iterator-Klasse

Iteratorklasse für Übereinstimmungen.

## <a name="syntax"></a>Syntax

```cpp
template<class BidIt,
   class Elem = typename std::iterator_traits<BidIt>::value_type,
   class RxTraits = regex_traits<Elem> >
class regex_iterator
```

## <a name="parameters"></a>Parameter

*BidIt*<br/>
Der Itertatortyp für Teilübereinstimmungen.

*Elem*<br/>
Der zu entsprechende Elementtyp.

*RXtraits*<br/>
Merkmalklasse für Elemente.

## <a name="remarks"></a>Hinweise

Die Vorlagenklasse beschreibt ein Objekt mit einem konstanten Forward-Iterator. Anschließend extrahiert sie Objekte des Typs `match_results<BidIt>` durch wiederholtes Anwenden seines regulären Ausdrucksobjekts `*pregex` auf die vom Iteratorbereich `[begin, end)`definierte Zeichenfolge.

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[regex_iterator](#regex_iterator)|Erstellt den Iterator.|

### <a name="typedefs"></a>Typedefs

|Typname|Beschreibung|
|-|-|
|[difference_type](#difference_type)|Der Typ einer Iteratordifferenz.|
|[iterator_category](#iterator_category)|Der Typ der Iteratorkategorie.|
|[Zeiger](#pointer)|Der Typ eines Zeigers auf eine Übereinstimmung.|
|[Verweis](#reference)|Der Typ eines Verweises auf eine Übereinstimmung.|
|[regex_type](#regex_type)|Der Typ des regulären Ausdrucks, der übereinstimmen soll.|
|[value_type](#value_type)|Der Typ einer Übereinstimmung.|

### <a name="operators"></a>Operatoren

|Operator|Beschreibung|
|-|-|
|[Operator!=](#op_neq)|Vergleicht Iteratoren auf Ungleichheit.|
|[operator*](#op_star)|Greift auf die gekennzeichnete Übereinstimmung zu.|
|[operator++](#op_add_add)|Erhöht den Iterator.|
|[operator=](#op_eq)|Vergleicht Iteratoren auf Gleichheit.|
|[operator->](#op_arrow)|Greift auf die gekennzeichnete Übereinstimmung zu.|

## <a name="requirements"></a>Anforderungen

**Header:** \<regex >

**Namespace:** std

## <a name="examples"></a>Beispiele

Beispiele zu regulären Ausdrücken finden Sie in den folgenden Themen:

- [regex_match](../standard-library/regex-functions.md#regex_match)

- [regex_replace](../standard-library/regex-functions.md#regex_replace)

- [regex_search](../standard-library/regex-functions.md#regex_search)

- [swap](../standard-library/regex-functions.md#swap)

```cpp
// std__regex__regex_iterator.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

typedef std::regex_iterator<const char *> Myiter;
int main()
    {
    const char *pat = "axayaz";
    Myiter::regex_type rx("a");
    Myiter next(pat, pat + strlen(pat), rx);
    Myiter end;

    for (; next != end; ++next)
        std::cout << "match == " << next->str() << std::endl;

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
match == a
match == a
match == a
```

## <a name="difference_type"></a> regex_iterator::difference_type

Der Typ einer Iteratordifferenz.

```cpp
typedef std::ptrdiff_t difference_type;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für `std::ptrdiff_t`.

## <a name="iterator_category"></a> regex_iterator::iterator_category

Der Typ der Iteratorkategorie.

```cpp
typedef std::forward_iterator_tag iterator_category;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für `std::forward_iterator_tag`.

## <a name="op_neq"></a> regex_iterator::operator!=

Vergleicht Iteratoren auf Ungleichheit.

```cpp
bool operator!=(const regex_iterator& right);
```

### <a name="parameters"></a>Parameter

*right*<br/>
Der Iterator für den Vergleich.

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt `!(*this == right)`zurück.

## <a name="op_star"></a> regex_iterator::operator*

Greift auf die gekennzeichnete Übereinstimmung zu.

```cpp
const match_results<BidIt>& operator*();
```

### <a name="remarks"></a>Hinweise

Diese Memberfunktion gibt den gespeicherten Wert `match`zurück.

## <a name="op_add_add"></a> regex_iterator::operator++

Erhöht den Iterator.

```cpp
regex_iterator& operator++();
regex_iterator& operator++(int);
```

### <a name="remarks"></a>Hinweise

Wenn die aktuelle Übereinstimmung keine Zeichen enthält, ruft der erste Operator `regex_search(begin, end, match, *pregex, flags | regex_constants::match_prev_avail | regex_constants::match_not_null)`auf. Andernfalls verschiebt er den gespeicherten Wert `begin` so, dass dieser auf das erste Zeichen nach der aktuellen Übereinstimmung zeigt, und ruft dann `regex_search(begin, end, match, *pregex, flags | regex_constants::match_prev_avail)`auf. Schlägt die Suche fehl, legt der Operator in beiden Fällen das Objekt auf einen Sequenzende-Iterator fest. Der Operator gibt das Objekt zurück.

Der zweite Operator erstellt eine Kopie des Objekts, erhöht das Objekt und gibt dann die Kopie zurück.

## <a name="op_eq"></a> regex_iterator::operator=

Vergleicht Iteratoren auf Gleichheit.

```cpp
bool operator==(const regex_iterator& right);
```

### <a name="parameters"></a>Parameter

*right*<br/>
Der Iterator für den Vergleich.

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt "true" zurück, wenn `*this` und *rechten* sind Sequenzende Iteratoren oder wenn weder ein Sequenzende Iterator ist und `begin == right.begin`, `end == right.end`, `pregex == right.pregex`, und `flags == right.flags`. Andernfalls wird „false“ zurückgegeben.

## <a name="op_arrow"></a> regex_iterator::operator-&gt;

Greift auf die gekennzeichnete Übereinstimmung zu.

```cpp
const match_results<BidIt> * operator->();
```

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt die Adresse des gespeicherten Werts `match`zurück.

## <a name="pointer"></a> regex_iterator::pointer

Der Typ eines Zeigers auf eine Übereinstimmung.

```cpp
typedef match_results<BidIt> *pointer;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für `match_results<BidIt>*`, wobei `BidIt` der Vorlagenparameter ist.

## <a name="reference"></a> regex_iterator::reference

Der Typ eines Verweises auf eine Übereinstimmung.

```cpp
typedef match_results<BidIt>& reference;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für `match_results<BidIt>&`, wobei `BidIt` der Vorlagenparameter ist.

## <a name="regex_iterator"></a> regex_iterator::regex_iterator

Erstellt den Iterator.

```cpp
regex_iterator();

regex_iterator(BidIt first,
    BidIt last,
    const regex_type& re,
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

Der erste Konstruktor erstellt einen Sequenzende-Iterator. Der zweite Konstruktor initialisiert den gespeicherten Wert `begin` mit *erste*, die gespeicherten Wert `end` mit *letzten*, die gespeicherten Wert `pregex` mit `&re`, und die gespeicherten Wert `flags` mit *f*. Anschließend wird `regex_search(begin, end, match, *pregex, flags)`aufgerufen. Wenn bei der Suche ein Fehler auftritt, legt der Konstruktor für das Objekt einen Sequenzende-Iterator fest.

## <a name="regex_type"></a> regex_iterator::regex_type

Der Typ des regulären Ausdrucks, der übereinstimmen soll.

```cpp
typedef basic_regex<Elem, RXtraits> regex_type;
```

### <a name="remarks"></a>Hinweise

Die Typedef ist ein Synonym für `basic_regex<Elem, RXtraits>`.

## <a name="value_type"></a> regex_iterator::value_type

Der Typ einer Übereinstimmung.

```cpp
typedef match_results<BidIt> value_type;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für `match_results<BidIt>`, wobei `BidIt` der Vorlagenparameter ist.

## <a name="see-also"></a>Siehe auch

[\<regex>](../standard-library/regex.md)<br/>
[regex_constants-Klasse](../standard-library/regex-constants-class.md)<br/>
[regex_error-Klasse](../standard-library/regex-error-class.md)<br/>
[\<regex>-Funktionen](../standard-library/regex-functions.md)<br/>
[regex_iterator-Klasse](../standard-library/regex-iterator-class.md)<br/>
[\<regex>-Operatoren](../standard-library/regex-operators.md)<br/>
[regex_token_iterator-Klasse](../standard-library/regex-token-iterator-class.md)<br/>
[regex_traits-Klasse](../standard-library/regex-traits-class.md)<br/>
[\<regex>-Typdefinitionen](../standard-library/regex-typedefs.md)<br/>
