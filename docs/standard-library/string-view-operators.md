---
title: '&lt;string_view&gt; -Operatoren'
ms.date: 04/19/2019
f1_keywords:
- xstring/basic_string_view::operator!=
- xstring/basic_string_view::operator&gt;
- xstring/basic_string_view::operator&gt;=
- xstring/basic_string_view::operator&lt;
- xstring/basic_string_view::operator&lt;&lt;
- xstring/basic_string_view::operator&lt;=
- xstring/basic_string_view::operator+
- xstring/basic_string_view::operator==
helpviewer_keywords:
- std::basic_string_view::operator!=
- std::basic_string_view::operator&gt;
- std::basic_string_view::operator&gt;=
- std::basic_string_view::operator&lt;
- std::basic_string_view::operator&lt;&lt;
- std::basic_string_view::operator&lt;=, std::basic_string_view::operator==
ms.openlocfilehash: caa6e515428cc0ea767eef20e819753c8f7ff8f9
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459217"
---
# <a name="ltstringviewgt-operators"></a>&lt;string_view&gt; -Operatoren

Verwenden Sie diese Operatoren zum Vergleichen von zwei string_view-Objekten bzw. eines string_view-Objekts sowie eines anderen Zeichen folgen Objekts (z. b. [Std:: String](basic-string-class.md)oder **Char\*** ), für das eine implizite Konvertierung bereitgestellt wird. 

||||
|-|-|-|
|[Operator!=](#op_neq)|[operator&gt;](#op_gt)|[operator&gt;=](#op_gt_eq)|
|[operator&lt;](#op_lt)|[operator&lt;&lt;](#op_lt_lt)|[operator&lt;=](#op_lt_eq)|
|[operator==](#op_eq_eq)|[Operator "" SV](#op_sv)|

## <a name="op_neq"></a>Operator! =

Testet, ob das Objekt links vom Operator ungleich dem Objekt rechts vom Operator ist.

```cpp
template <class CharType, class Traits>
bool operator!=(
    const basic_string_view<CharType, Traits>& left,
    const basic_string_view<CharType, Traits>& right);

template <class CharType, class Traits>
bool operator!=(
    const basic_string_view<CharType, Traits>& left,
    convertible_string_type right);

template <class CharType, class Traits>
bool operator!=(
    convertible_string_type left,
    const basic_string_view<CharType, Traits>& right);
```

### <a name="parameters"></a>Parameter

*linken*\
Alle konvertierbaren Zeichen folgen Typen oder ein Objekt `basic_string_view` vom Typ, das verglichen werden soll.

*Richting*\
Alle konvertierbaren Zeichen folgen Typen oder ein Objekt `basic_string_view` vom Typ, das verglichen werden soll.

### <a name="return-value"></a>Rückgabewert

**true** , wenn das Objekt links vom Operator nicht lexikografisch gleich dem Objekt auf der rechten Seite ist; andernfalls **false**.

### <a name="remarks"></a>Hinweise

Eine implizite Konvertierung muss von *convertible_string_type* zu string_view auf der anderen Seite vorhanden sein. 

Der Vergleich basiert auf einem Paar weisen lexikografischen Vergleich der Zeichen folgen. Wenn Sie die gleiche Anzahl von Elementen aufweisen und die Elemente alle gleich sind, sind die beiden Objekte gleich. Andernfalls sind sie ungleich.

## <a name="op_eq_eq"></a>Operator = =

Testet, ob das Objekt links vom Operator gleich dem Objekt rechts vom Operator ist.

```cpp
template <class CharType, class Traits>
bool operator==(
    const basic_string_view<CharType, Traits>& left,
    const basic_string_view<CharType, Traits>& right);

template <class CharType, class Traits>
bool operator==(
    const basic_string_view<CharType, Traits>& left,
    convertible_string_type right);

template <class CharType, class Traits>
bool operator==(
    convertible_string_type left,
    const basic_string_view<CharType, Traits>& right);
```

### <a name="parameters"></a>Parameter

*linken*\
Alle konvertierbaren Zeichen folgen Typen oder ein Objekt `basic_string_view` vom Typ, das verglichen werden soll.

*Richting*\
Alle konvertierbaren Zeichen folgen Typen oder ein Objekt `basic_string_view` vom Typ, das verglichen werden soll.

### <a name="return-value"></a>Rückgabewert

**true** , wenn das Objekt links vom Operator lexikografisch gleich dem Objekt auf der rechten Seite ist; andernfalls **false**.

### <a name="remarks"></a>Hinweise

Eine implizite Konvertierung muss von *convertible_string_type* zu string_view auf der anderen Seite vorhanden sein. 

Der Vergleich basiert auf einem Paar weisen lexikografischen Vergleich der Zeichen folgen. Wenn Sie die gleiche Anzahl von Elementen aufweisen und die Elemente alle gleich sind, sind die beiden Objekte gleich.


## <a name="op_lt"></a>-Operator&lt;

Testet, ob das Objekt links vom Operator kleiner als das Objekt auf der rechten Seite ist sidestring_view
```cpp
template <class CharType, class Traits>
bool operator<(
    const basic_string_view<CharType, Traits>& left,
    const basic_string_view<CharType, Traits>& right);

template <class CharType, class Traits>
bool operator<(
    const basic_string_view<CharType, Traits>& left,
    convertible_string_type right);

template <class CharType, class Traits>
bool operator<(
    convertible_string_type left,
    const basic_string_view<CharType, Traits>& right);
```

### <a name="parameters"></a>Parameter

*linken*\
Alle konvertierbaren Zeichen folgen Typen oder ein Objekt `basic_string_view` vom Typ, das verglichen werden soll.

*Richting*\
Alle konvertierbaren Zeichen folgen Typen oder ein Objekt `basic_string_view` vom Typ, das verglichen werden soll.

### <a name="return-value"></a>Rückgabewert

**true** , wenn das Objekt links vom Operator lexikografisch kleiner ist als das Objekt auf der rechten Seite. andernfalls **false**.

### <a name="remarks"></a>Hinweise

Eine implizite Konvertierung muss von *convertible_string_type* zu string_view auf der anderen Seite vorhanden sein. 

Der Vergleich basiert auf einem Paar weisen lexikografischen Vergleich der Zeichen folgen. Wenn das erste ungleiche paar von Zeichen gefunden wird, wird das Ergebnis dieses Vergleichs zurückgegeben. Wenn keine ungleichen Zeichen gefunden werden, aber eine Sequenz kürzer ist, ist die kürzere Sequenz kleiner als die längere Sequenz. Mit anderen Worten: "Cat" ist kleiner als "Katzen".

### <a name="example"></a>Beispiel

```cpp
#include <string>
#include <string_view>

using namespace std;

int main()
{
    string_view sv1 { "ABA" };
    string_view sv2{ "ABAC" };
    string_view sv3{ "ABAD" };
    string_view sv4{ "ABACE" };

    bool result = sv2 > sv1; // true
    result = sv3 > sv2; // true
    result = sv3 != sv1; // true
    result = sv4 < sv3; // true because `C` < `D`
}
```

## <a name="op_lt_eq"></a>KOM&lt;=

Testet, ob das Objekt links vom Operator kleiner oder gleich dem Objekt auf der rechten Seite ist.

```cpp
template <class CharType, class Traits>
bool operator<=(
    const basic_string_view<CharType, Traits>& left,
    const basic_string_view<CharType, Traits>& right);

template <class CharType, class Traits>
bool operator<=(
    const basic_string_view<CharType, Traits>& left,
    convertible_string_type right);

template <class CharType, class Traits>
bool operator<=(
    convertible_string_type left,
    const basic_string_view<CharType, Traits>& right);
```

### <a name="parameters"></a>Parameter

*linken*\
Alle konvertierbaren Zeichen folgen Typen oder ein Objekt `basic_string_view` vom Typ, das verglichen werden soll.

*Richting*\
Alle konvertierbaren Zeichen folgen Typen oder ein Objekt `basic_string_view` vom Typ, das verglichen werden soll.

### <a name="return-value"></a>Rückgabewert

**true** , wenn das Objekt links vom Operator lexikografisch kleiner als oder gleich dem Objekt rechts vom Operator ist. andernfalls **false**.

### <a name="remarks"></a>Hinweise

Siehe [Operator&lt;](#op_lt).

## <a name="op_lt_lt"></a>KOM&lt;&lt;

Schreibt ein string_view-Objekt in einen Ausgabestream.

```cpp
template <class CharType, class Traits>
inline basic_ostream<CharType, Traits>& operator<<(
    basic_ostream<CharType, Traits>& Ostr, const basic_string_view<CharType, Traits> Str);
```

### <a name="parameters"></a>Parameter

*Ostr*\
ein Ausgabestream, in den geschrieben wird.

*SRT*\
Der string_view, der in einen Ausgabestream eingegeben werden soll.

### <a name="return-value"></a>Rückgabewert

ein Ausgabestream, in den geschrieben wird.

### <a name="remarks"></a>Hinweise

Verwenden Sie diesen Operator, um den Inhalt eines string_view in einen Ausgabestream einzufügen, z. b. " [Std:: cout](iostream.md#cout)".

## <a name="op_gt"></a>-Operator&gt;

Testet, ob das Objekt links vom Operator größer als das Objekt auf der rechten Seite ist.

```cpp
template <class CharType, class Traits>
bool operator>(
    const basic_string_view<CharType, Traits>& left,
    const basic_string_view<CharType, Traits>& right);

template <class CharType, class Traits>
bool operator>(
    const basic_string_view<CharType, Traits>& left,
    convertible_string_type right);

template <class CharType, class Traits>
bool operator>(
    convertible_string_type left,
    const basic_string_view<CharType, Traits>& right);
```

### <a name="parameters"></a>Parameter

*linken*\
Alle konvertierbaren Zeichen folgen Typen oder ein Objekt `basic_string_view` vom Typ, das verglichen werden soll.

*Richting*\
Alle konvertierbaren Zeichen folgen Typen oder ein Objekt `basic_string_view` vom Typ, das verglichen werden soll.

### <a name="return-value"></a>Rückgabewert

**true** , wenn das Objekt links vom Operator lexikografisch größer als das string_view-Objekt rechts vom Operator ist. andernfalls **false**.

### <a name="remarks"></a>Hinweise

Siehe [Operator&lt;](#op_lt).

## <a name="op_gt_eq"></a>KOM&gt;=

Testet, ob das Objekt links vom Operator größer oder gleich dem Objekt auf der rechten Seite ist.

```cpp
template <class CharType, class Traits>
bool operator>=(
    const basic_string_view<CharType, Traits>& left,
    const basic_string_view<CharType, Traits>& right);

template <class CharType, class Traits>
bool operator>=(
    const basic_string_view<CharType, Traits>& left,
    convertible_string_type right);

template <class CharType, class Traits>
bool operator>=(
    convertible_string_type left,
    const basic_string_view<CharType, Traits>& right);
```

### <a name="parameters"></a>Parameter

*linken*\
Alle konvertierbaren Zeichen folgen Typen oder ein Objekt `basic_string_view` vom Typ, das verglichen werden soll.

*Richting*\
Alle konvertierbaren Zeichen folgen Typen oder ein Objekt `basic_string_view` vom Typ, das verglichen werden soll.

### <a name="return-value"></a>Rückgabewert

**true** , wenn das-Objekt links vom Operator lexikografisch größer als oder gleich dem-Objekt rechts vom Operator ist. andernfalls **false**.

### <a name="remarks"></a>Hinweise

Siehe [Operator&lt;](#op_lt).

## <a name="op_sv"></a>Operator "" SV (string_view-Literale)

Erstellt ein string_view aus einem Zeichenfolgenliteral. Erfordert Namespace `std::literals::string_view_literals`. 

### <a name="example"></a>Beispiel

```cpp

using namespace std;
using namespace literals::string_view_literals;

    string_view sv{ "Hello"sv };
    wstring_view wsv{ L"Hello"sv };
    u16string_view sv16{ u"Hello"sv };
    u32string_view sv32{ U"Hello"sv };
```

## <a name="see-also"></a>Siehe auch

[\<string_view >](../standard-library/string-view.md)
