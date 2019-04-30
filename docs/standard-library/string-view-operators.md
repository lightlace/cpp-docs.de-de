---
title: '&lt;String_view&gt; Operatoren'
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
ms.openlocfilehash: 1fbb7faf7d6fc92a053c0f4d47575c5c53c7968e
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2019
ms.locfileid: "64346918"
---
# <a name="ltstringviewgt-operators"></a>&lt;String_view&gt; Operatoren

Diese Operatoren zum Vergleichen von zwei String_view-Objekte, oder eine String_view und eines anderen Zeichenfolgenobjekts verwenden (z. B. [Std:: String](basic-string-class.md), oder **Char\***) für die eine implizite Konvertierung bereitgestellt wird. 

||||
|-|-|-|
|[Operator!=](#op_neq)|[operator&gt;](#op_gt)|[operator&gt;=](#op_gt_eq)|
|[operator&lt;](#op_lt)|[operator&lt;&lt;](#op_lt_lt)|[operator&lt;=](#op_lt_eq)|
|[operator==](#op_eq_eq)|[operator""sv](#op_sv)|

## <a name="op_neq"></a> Operator! =

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

*left*<br/>
Alle in String-Datentyp oder ein Objekt vom Typ `basic_string_view` verglichen werden soll.

*right*<br/>
Alle in String-Datentyp oder ein Objekt vom Typ `basic_string_view` verglichen werden soll.

### <a name="return-value"></a>Rückgabewert

**"true"** ist das Objekt auf der linken Seite des Operators nicht lexikografisch gleich dem Objekt auf der rechten Seite; andernfalls **"false"**.

### <a name="remarks"></a>Hinweise

Eine implizite Konvertierung muss vorhanden sein, von *Convertible_string_type* auf die String_view auf der anderen Seite. 

Der Vergleich basiert auf einem paarweisen lexikografischen Vergleich der Zeichenfolgen. Sie haben die gleiche Anzahl von Elementen und die Elemente gleich sind, dass die beiden Objekte gleich sind. Andernfalls sind sie ungleich.

## <a name="op_eq_eq"></a> Operator ==

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

*left*<br/>
Alle in String-Datentyp oder ein Objekt vom Typ `basic_string_view` verglichen werden soll.

*right*<br/>
Alle in String-Datentyp oder ein Objekt vom Typ `basic_string_view` verglichen werden soll.

### <a name="return-value"></a>Rückgabewert

**"true"** ist das Objekt links vom Operator lexikografisch gleich dem Objekt auf der rechten Seite; andernfalls **"false"**.

### <a name="remarks"></a>Hinweise

Eine implizite Konvertierung muss vorhanden sein, von *Convertible_string_type* auf die String_view auf der anderen Seite. 

Der Vergleich basiert auf einem paarweisen lexikografischen Vergleich der Zeichenfolgen. Sie haben die gleiche Anzahl von Elementen und die Elemente gleich sind, dass die beiden Objekte gleich sind.


## <a name="op_lt"></a>-Operator&lt;

Testet, ob das Objekt links vom Operator kleiner als das Objekt auf der richtigen Sidestring_view ist
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

*left*<br/>
Alle in String-Datentyp oder ein Objekt vom Typ `basic_string_view` verglichen werden soll.

*right*<br/>
Alle in String-Datentyp oder ein Objekt vom Typ `basic_string_view` verglichen werden soll.

### <a name="return-value"></a>Rückgabewert

**"true"** Wenn das Objekt links vom Operator lexikografisch kleiner als das Objekt auf der rechten Seite ist; andernfalls **"false"**.

### <a name="remarks"></a>Hinweise

Eine implizite Konvertierung muss vorhanden sein, von *Convertible_string_type* auf die String_view auf der anderen Seite. 

Der Vergleich basiert auf einem paarweisen lexikografischen Vergleich der Zeichenfolgen. Wenn das erste ungleichen Paar Zeichen gefunden wird, wird das Ergebnis dieses Vergleichs zurückgegeben. Wenn keine ungleichen Zeichen gefunden werden, aber eine Sequenz kürzer ist, ist die kürzere Sequenz kleiner als die längere Zeichenfolge. Das heißt, ist kleiner als "Cats", "Katze".

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

## <a name="op_lt_eq"></a> Operator&lt;=

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

*left*<br/>
Alle in String-Datentyp oder ein Objekt vom Typ `basic_string_view` verglichen werden soll.

*right*<br/>
Alle in String-Datentyp oder ein Objekt vom Typ `basic_string_view` verglichen werden soll.

### <a name="return-value"></a>Rückgabewert

**"true"** , wenn das Objekt links vom Operator lexikografisch kleiner als oder gleich dem Objekt auf der rechten Seite ist; andernfalls ist **"false"**.

### <a name="remarks"></a>Hinweise

Finden Sie unter [Operator&lt;](#op_lt).

## <a name="op_lt_lt"></a> Operator&lt;&lt;

Schreibt eine String_view in einen Ausgabestream an.

```cpp
template <class CharType, class Traits>
inline basic_ostream<CharType, Traits>& operator<<(
    basic_ostream<CharType, Traits>& Ostr, const basic_string_view<CharType, Traits> Str);
```

### <a name="parameters"></a>Parameter

*Ostr*<br/>
Ein Ausgabestream geschrieben wird.

*Str*<br/>
Die String_view in einen Ausgabestream eingegeben werden.

### <a name="return-value"></a>Rückgabewert

Ein Ausgabestream geschrieben wird.

### <a name="remarks"></a>Hinweise

Verwenden Sie diesen Operator, um den Inhalt einer String_view in einen Ausgabestream einzufügen z. B. mit [Std:: cout](iostream.md#cout).

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

*left*<br/>
Alle in String-Datentyp oder ein Objekt vom Typ `basic_string_view` verglichen werden soll.

*right*<br/>
Alle in String-Datentyp oder ein Objekt vom Typ `basic_string_view` verglichen werden soll.

### <a name="return-value"></a>Rückgabewert

**"true"** ist das Objekt links vom Operator lexikografisch größer als das String_view-Objekt auf der rechten Seite ist; andernfalls **"false"**.

### <a name="remarks"></a>Hinweise

Finden Sie unter [Operator&lt;](#op_lt).

## <a name="op_gt_eq"></a> Operator&gt;=

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

*left*<br/>
Alle in String-Datentyp oder ein Objekt vom Typ `basic_string_view` verglichen werden soll.

*right*<br/>
Alle in String-Datentyp oder ein Objekt vom Typ `basic_string_view` verglichen werden soll.

### <a name="return-value"></a>Rückgabewert

**"true"** ist das Objekt links vom Operator lexikografisch größer als oder gleich dem Objekt auf der rechten Seite; andernfalls **"false"**.

### <a name="remarks"></a>Hinweise

Finden Sie unter [Operator&lt;](#op_lt).

## <a name="op_sv"></a> Operator"" Sv (String_view literal)

Erstellt eine String_view aus einem Zeichenfolgenliteral. Muss Namespace `std::literals::string_view_literals`. 

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

[\<string_view>](../standard-library/string-view.md)<br/>
