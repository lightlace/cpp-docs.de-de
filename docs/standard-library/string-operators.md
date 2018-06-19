---
title: '&lt;string&gt;-Operatoren | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- string/std::operator!=
- string/std::operator&gt;
- string/std::operator&gt;&gt;
- string/std::operator&gt;=
- string/std::operator&lt;
- string/std::operator&lt;&lt;
- string/std::operator&lt;=
- string/std::operator+
- string/std::operator==
dev_langs:
- C++
ms.assetid: 33ce8f05-06c7-45d3-a0cb-bcd27cf93910
helpviewer_keywords:
- std::operator!= (string)
- std::operator&gt; (string)
- std::operator&gt;&gt; (string)
- std::operator&gt;= (string)
- std::operator&lt; (string)
- std::operator&lt;&lt; (string)
- std::operator&lt;= (string), std::operator== (string)
ms.openlocfilehash: b0ca7da732786c2f0ff6087052b5867150702a5e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33862483"
---
# <a name="ltstringgt-operators"></a>&lt;string&gt;-Operatoren

||||
|-|-|-|
|[operator!=](#op_neq)|[operator&gt;](#op_gt)|[operator&gt;&gt;](#op_gt_gt)|
|[operator&gt;=](#op_gt_eq)|[operator&lt;](#op_lt)|[operator&lt;&lt;](#op_lt_lt)|
|[operator&lt;=](#op_lt_eq)|[operator+](#op_add)|[operator==](#op_eq_eq)|

## <a name="op_add"></a> operator+

Verkettet zwei Zeichenfolgenobjekte.

```cpp
template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator> operator+(
    const basic_string<CharType, Traits, Allocator>& left,
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator> operator+(
    const basic_string<CharType, Traits, Allocator>& left,
    const CharType* right);

template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator> operator+(
    const basic_string<CharType, Traits, Allocator>& left,
    const CharType right);

template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator> operator+(
    const CharType* left,
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator> operator+(
    const CharType left,
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator>&& operator+(
    const basic_string<CharType, Traits, Allocator>& left,
    const basic_string<CharType, Traits, Allocator>&& right);

template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator>&& operator+(
    const basic_string<CharType, Traits, Allocator>&& left,
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator>&& operator+(
    const basic_string<CharType, Traits, Allocator>&& left,
    const basic_string<CharType, Traits, Allocator>&& right);

template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator>&& operator+(
    const basic_string<CharType, Traits, Allocator>&& left,
    const CharType* right);

template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator>&& operator+(
    const basic_string<CharType, Traits, Allocator>&& left,
    CharType right);

template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator>&& operator+(
    const CharType* left,
    const basic_string<CharType, Traits, Allocator>&& right);

template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator>&& operator+(
    CharType left,
    const basic_string<CharType, Traits, Allocator>&& right);
```

### <a name="parameters"></a>Parameter

`left` Eine Zeichenfolge im C-Format oder ein Objekt des Typs `basic_string` , verkettet werden soll.

`right` Eine Zeichenfolge im C-Format oder ein Objekt des Typs `basic_string` , verkettet werden soll.

### <a name="return-value"></a>Rückgabewert

Die Zeichenfolge, die die Verkettung der Eingabezeichenfolgen ist.

### <a name="remarks"></a>Hinweise

Jede der Funktionen überlädt `operator+`, um zwei Objekte der Vorlagenklasse [basic_string-Klasse](../standard-library/basic-string-class.md) zu verketten. Alle effektiv return `basic_string` \< **CharType**, **Traits**, **Allocator**> (_ *Links*). [append](../standard-library/basic-string-class.md#append)(\_ *rechts*).

### <a name="example"></a>Beispiel

```cpp
// string_op_con.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   // Declaring an object of type basic_string<char>
   string s1 ( "anti" );
   string s2 ( "gravity" );
   cout << "The basic_string s1 = " << s1 << "." << endl;
   cout << "The basic_string s2 = " << s2 << "." << endl;

   // Declaring a C-style string
   char *s3 = "heroine";
   cout << "The C-style string s3 = " << s3 << "." << endl;

   // Declaring a character constant
   char c1 = '!';
   cout << "The character constant c1 = " << c1 << "." << endl;

   // First member function: concatenates an  object
   // of type basic_string with an object of type basic_string
   string s12 = s1 + s2;
   cout << "The string concatenating s1 & s2 is: " << s12 << endl;

   // Second & fourth member functions: concatenate an object
   // of type basic_string with an object of C-syle string type
   string s1s3 = s1 + s3;
   cout << "The string concatenating s1 & s3 is: " << s1s3 << endl;

   // Third & fifth member functions: concatenate an object
   // of type basic_string with a character constant
   string s1s3c1 = s1s3 + c1;
   cout << "The string concatenating s1 & s3 is: " << s1s3c1 << endl;
}
```

```Output
The basic_string s1 = anti.
The basic_string s2 = gravity.
The C-style string s3 = heroine.
The character constant c1 = !.
The string concatenating s1 & s2 is: antigravity
The string concatenating s1 & s3 is: antiheroine
The string concatenating s1 & s3 is: antiheroine!
```

## <a name="op_neq"></a> operator!=

Testet, ob das Zeichenfolgenobjekt links vom Operator ungleich dem Zeichenfolgenobjekt rechts vom Operator ist.

```cpp
template <class CharType, class Traits, class Allocator>
bool operator!=(
    const basic_string<CharType, Traits, Allocator>& left,
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
bool operator!=(
    const basic_string<CharType, Traits, Allocator>& left,
const CharType* right);

template <class CharType, class Traits, class Allocator>
bool operator!=(
    const CharType* left,
    const basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parameter

`left` Eine Zeichenfolge im C-Format oder ein Objekt des Typs `basic_string` verglichen werden soll.

`right` Eine Zeichenfolge im C-Format oder ein Objekt des Typs `basic_string` verglichen werden soll.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn das Zeichenfolgenobjekt links vom Operator lexikografisch ungleich dem Zeichenfolgenobjekt rechts vom Operator ist, andernfalls **FALSE**.

### <a name="remarks"></a>Hinweise

Der Vergleich zwischen den Zeichenfolgenobjekten basiert auf einem paarweisen lexikografischen Vergleich ihrer Zeichen. Zwei Zeichenfolgen sind gleich, wenn die gleiche Anzahl von Zeichen und ihre jeweiligen Zeichenwerte identisch sind. Andernfalls sind sie ungleich.

### <a name="example"></a>Beispiel

```cpp
// string_op_ne.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // Declaring an objects of type basic_string<char>
   string s1 ( "pluck" );
   string s2 ( "strum" );
   cout << "The basic_string s1 = " << s1 << "." << endl;
   cout << "The basic_string s2 = " << s2 << "." << endl;

   // Declaring a C-style string
   char *s3 = "pluck";
   cout << "The C-style string s3 = " << s3 << "." << endl;

   // First member function: comparison between left-side object
   // of type basic_string & right-side object of type basic_string
   if ( s1 != s2 )
      cout << "The strings s1 & s2 are not equal." << endl;
   else
      cout << "The strings s1 & s2 are equal." << endl;

   // Second member function: comparison between left-side object
   // of type basic_string & right-side object of C-syle string type
   if ( s1 != s3 )
      cout << "The strings s1 & s3 are not equal." << endl;
   else
      cout << "The strings s1 & s3 are equal." << endl;

   // Third member function: comparison between left-side object
   // of C-syle string type & right-side object of type basic_string
   if ( s3 != s2 )
      cout << "The strings s3 & s2 are not equal." << endl;
   else
      cout << "The strings s3 & s2 are equal." << endl;
}
```

```Output
The basic_string s1 = pluck.
The basic_string s2 = strum.
The C-style string s3 = pluck.
The strings s1 & s2 are not equal.
The strings s1 & s3 are equal.
The strings s3 & s2 are not equal.
```

## <a name="op_eq_eq"></a> operator==

Testet, ob das Zeichenfolgenobjekt links vom Operator gleich dem Zeichenfolgenobjekt rechts vom Operator ist.

```cpp
template <class CharType, class Traits, class Allocator>
bool operator==(
    const basic_string<CharType, Traits, Allocator>& left,
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
bool operator==(
    const basic_string<CharType, Traits, Allocator>& left,
    const CharType* right);

template <class CharType, class Traits, class Allocator>
bool operator==(
    const CharType* left,
    const basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parameter

`left` Eine Zeichenfolge im C-Format oder ein Objekt des Typs `basic_string` verglichen werden soll.

`right` Eine Zeichenfolge im C-Format oder ein Objekt des Typs `basic_string` verglichen werden soll.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn das Zeichenfolgenobjekt links vom Operator lexikografisch gleich dem Zeichenfolgenobjekt rechts vom Operator ist, andernfalls **FALSE**.

### <a name="remarks"></a>Hinweise

Der Vergleich zwischen den Zeichenfolgenobjekten basiert auf einem paarweisen lexikografischen Vergleich ihrer Zeichen. Zwei Zeichenfolgen sind gleich, wenn die gleiche Anzahl von Zeichen und ihre jeweiligen Zeichenwerte identisch sind. Andernfalls sind sie ungleich.

### <a name="example"></a>Beispiel

```cpp
// string_op_eq.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // Declaring an objects of type basic_string<char>
   string s1 ( "pluck" );
   string s2 ( "strum" );
   cout << "The basic_string s1 = " << s1 << "." << endl;
   cout << "The basic_string s2 = " << s2 << "." << endl;

   // Declaring a C-style string
   char *s3 = "pluck";
   cout << "The C-style string s3 = " << s3 << "." << endl;

   // First member function: comparison between left-side object
   // of type basic_string & right-side object of type basic_string
   if ( s1 == s2 )
      cout << "The strings s1 & s2 are equal." << endl;
   else
      cout << "The strings s1 & s2 are not equal." << endl;

   // Second member function: comparison between left-side object
   // of type basic_string & right-side object of C-syle string type
   if ( s1 == s3 )
      cout << "The strings s1 & s3 are equal." << endl;
   else
      cout << "The strings s1 & s3 are not equal." << endl;

   // Third member function: comparison between left-side object
   // of C-syle string type & right-side object of type basic_string
   if ( s3 == s2 )
      cout << "The strings s3 & s2 are equal." << endl;
   else
      cout << "The strings s3 & s2 are not equal." << endl;
}
```

```Output
The basic_string s1 = pluck.
The basic_string s2 = strum.
The C-style string s3 = pluck.
The strings s1 & s2 are not equal.
The strings s1 & s3 are equal.
The strings s3 & s2 are not equal.
```

## <a name="op_lt"></a> operator&lt;

Testet, ob das Zeichenfolgenobjekt links vom Operator kleiner als das Zeichenfolgenobjekt rechts vom Operator ist.

```cpp
template <class CharType, class Traits, class Allocator>
bool operator<(
    const basic_string<CharType, Traits, Allocator>& left,
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
bool operator<(
    const basic_string<CharType, Traits, Allocator>& left,
    const CharType* right);

template <class CharType, class Traits, class Allocator>
bool operator<(
    const CharType* left,
    const basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parameter

`left` Eine Zeichenfolge im C-Format oder ein Objekt des Typs `basic_string` verglichen werden soll.

`right` Eine Zeichenfolge im C-Format oder ein Objekt des Typs `basic_string` verglichen werden soll.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn das Zeichenfolgenobjekt links vom Operator lexikografisch kleiner als das Zeichenfolgenobjekt rechts vom Operator ist, andernfalls **FALSE**.

### <a name="remarks"></a>Hinweise

Ein lexikografischer Vergleich zwischen Zeichenfolgen vergleicht diese zeichenweise, bis:

- Er zwei korrespondierende ungleiche Zeichen findet, und deren Vergleich als Ergebnis des Vergleichs zweier Zeichenfolgen genommen wird.

- Er keine Ungleichheiten findet, aber eine Zeichenfolge mehr Zeichen hat als die andere und die kürzere Zeichenfolge als kleiner als die längere Zeichenfolge betrachtet wird.

- Er keine Ungleichheiten findet und feststellt, dass die Zeichenfolgen die gleiche Anzahl von Zeichen haben und daher gleich sind.

### <a name="example"></a>Beispiel

```cpp
// string_op_lt.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   // Declaring an objects of type basic_string<char>
   string s1 ( "strict" );
   string s2 ( "strum" );
   cout << "The basic_string s1 = " << s1 << "." << endl;
   cout << "The basic_string s2 = " << s2 << "." << endl;

   // Declaring a C-style string
   char *s3 = "strict";
   cout << "The C-style string s3 = " << s3 << "." << endl;

   // First member function: comparison between left-side object
   // of type basic_string & right-side object of type basic_string
   if ( s1 < s2 )
      cout << "The string s1 is less than the string s2." << endl;
   else
      cout << "The string s1 is not less than the string s2." << endl;

   // Second member function: comparison between left-hand object
   // of type basic_string & right-hand object of C-syle string type
   if ( s1 < s3 )
      cout << "The string s1 is less than the string s3." << endl;
   else
      cout << "The string s1 is not less than the string s3." << endl;

   // Third member function: comparison between left-hand object
   // of C-syle string type & right-hand object of type basic_string
   if ( s3 < s2 )
      cout << "The string s3 is less than the string s2." << endl;
   else
      cout << "The string s3 is not less than the string s2." << endl;
}
```

```Output
The basic_string s1 = strict.
The basic_string s2 = strum.
The C-style string s3 = strict.
The string s1 is less than the string s2.
The string s1 is not less than the string s3.
The string s3 is less than the string s2.
```

## <a name="op_lt_eq"></a> operator&lt;=

Testet, ob das Zeichenfolgenobjekt links vom Operator kleiner als oder gleich dem Zeichenfolgenobjekt rechts vom Operator ist.

```cpp
template <class CharType, class Traits, class Allocator>
bool operator<=(
    const basic_string<CharType, Traits, Allocator>& left,
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
bool operator<=(
    const basic_string<CharType, Traits, Allocator>& left,
    const CharType* right);

template <class CharType, class Traits, class Allocator>
bool operator<=(
    const CharType* left,
    const basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parameter

`left` Eine Zeichenfolge im C-Format oder ein Objekt des Typs `basic_string` verglichen werden soll.

`right` Eine Zeichenfolge im C-Format oder ein Objekt des Typs `basic_string` verglichen werden soll.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn das Zeichenfolgenobjekt links vom Operator lexikografisch kleiner als oder gleich dem Zeichenfolgenobjekt rechts vom Operator ist, andernfalls **FALSE**.

### <a name="remarks"></a>Hinweise

Ein lexikografischer Vergleich zwischen Zeichenfolgen vergleicht diese zeichenweise, bis:

- Er zwei korrespondierende ungleiche Zeichen findet, und deren Vergleich als Ergebnis des Vergleichs zweier Zeichenfolgen genommen wird.

- Er keine Ungleichheiten findet, aber eine Zeichenfolge mehr Zeichen hat als die andere und die kürzere Zeichenfolge als kleiner als die längere Zeichenfolge betrachtet wird.

- Er keine Ungleichheiten findet und feststellt, dass die Zeichenfolgen die gleiche Anzahl von Zeichen haben und daher gleich sind.

### <a name="example"></a>Beispiel

```cpp
// string_op_le.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // Declaring an objects of type basic_string<char>
   string s1 ( "strict" );
   string s2 ( "strum" );
   cout << "The basic_string s1 = " << s1 << "." << endl;
   cout << "The basic_string s2 = " << s2 << "." << endl;

   // Declaring a C-style string
   char *s3 = "strict";
   cout << "The C-style string s3 = " << s3 << "." << endl;

   // First member function: comparison between left-side object
   // of type basic_string & right-side object of type basic_string
   if ( s1 <= s2 )
      cout << "The string s1 is less than or equal to "
           << "the string s2." << endl;
   else
      cout << "The string s1 is greater than "
           << "the string s2." << endl;

   // Second member function: comparison between left-side object
   // of type basic_string & right-side object of C-syle string type
   if ( s1 <= s3 )
      cout << "The string s1 is less than or equal to "
           << "the string s3." << endl;
   else
      cout << "The string s1 is greater than "
           << "the string s3." << endl;

   // Third member function: comparison between left-side object
   // of C-syle string type  & right-side object of type basic_string
   if ( s2 <= s3 )
      cout << "The string s2 is less than or equal to "
           << "the string s3." << endl;
   else
      cout << "The string s2 is greater than "
           << "the string s3." << endl;
}
```

```Output
The basic_string s1 = strict.
The basic_string s2 = strum.
The C-style string s3 = strict.
The string s1 is less than or equal to the string s2.
The string s1 is less than or equal to the string s3.
The string s2 is greater than the string s3.
```

## <a name="op_lt_lt"></a> operator&lt;&lt;

Eine Vorlagenfunktion, die eine Zeichenfolge in den Ausgabestream schreibt.

```cpp
template <class CharType, class Traits, class Allocator>
basic_ostream<CharType, Traits>& operator<<(
    basic_ostream<CharType, Traits>& _Ostr,
    const basic_string<CharType, Traits, Allocator>& str);
```

### <a name="parameters"></a>Parameter

_Ostr den Ausgabestream geschrieben wird.

`str` Die Zeichenfolge, die in den Ausgabestream eingegeben werden.

### <a name="return-value"></a>Rückgabewert

Schreibt den Wert der angegebenen Zeichenfolge in den Ausgabestream `_Ostr`.

### <a name="remarks"></a>Hinweise

Die Vorlagenfunktion überlädt **operator<<**, um ein Objekt _ *Str* von Vorlagenklasse [basic_string](../standard-library/basic-string-class.md) in den Stream \_ *Ostr* einzufügen. Die Funktion gibt \_ *Ostr* zurück. **write**( \_ *Str*. [c_str](../standard-library/basic-string-class.md#c_str), \_ *Str*. [size](../standard-library/basic-string-class.md#size)).

## <a name="op_gt"></a> operator&gt;

Testet, ob das Zeichenfolgenobjekt links vom Operator größer als das Zeichenfolgenobjekt rechts vom Operator ist.

```cpp
template <class CharType, class Traits, class Allocator>
bool operator>(
    const basic_string<CharType, Traits, Allocator>& left,
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
bool operator>(
    const basic_string<CharType, Traits, Allocator>& left,
    const CharType* right);

template <class CharType, class Traits, class Allocator>
bool operator>(
    const CharType* left,
    const basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parameter

`left` Eine Zeichenfolge im C-Format oder ein Objekt des Typs `basic_string` verglichen werden soll.

`right` Eine Zeichenfolge im C-Format oder ein Objekt des Typs `basic_string` verglichen werden soll.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn das Zeichenfolgenobjekt links vom Operator lexikografisch größer als das Zeichenfolgenobjekt rechts vom Operator ist, andernfalls **FALSE**.

### <a name="remarks"></a>Hinweise

Ein lexikografischer Vergleich zwischen Zeichenfolgen vergleicht diese zeichenweise, bis:

- Er zwei korrespondierende ungleiche Zeichen findet, und deren Vergleich als Ergebnis des Vergleichs zweier Zeichenfolgen genommen wird.

- Er keine Ungleichheiten findet, aber eine Zeichenfolge mehr Zeichen hat als die andere und die kürzere Zeichenfolge als kleiner als die längere Zeichenfolge betrachtet wird.

- Er keine Ungleichheiten findet und feststellt, dass die Zeichenfolgen die gleiche Anzahl von Zeichen haben und daher gleich sind.

### <a name="example"></a>Beispiel

```cpp
// string_op_gt.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // Declaring an objects of type basic_string<char>
   string s1 ( "strict" );
   string s2 ( "strum" );
   cout << "The basic_string s1 = " << s1 << "." << endl;
   cout << "The basic_string s2 = " << s2 << "." << endl;

   // Declaring a C-style string
   char *s3 = "stricture";
   cout << "The C-style string s3 = " << s3 << "." << endl;

   // First member function: comparison between left-side object
   // of type basic_string & right-side object of type basic_string
   if ( s1 > s2 )
      cout << "The string s1 is greater than "
           << "the string s2." << endl;
   else
      cout << "The string s1 is not greater than "
           << "the string s2." << endl;

   // Second member function: comparison between left-side object
   // of type basic_string & right-side object of C-syle string type
   if ( s3 > s1 )
      cout << "The string s3 is greater than "
           << "the string s1." << endl;
   else
      cout << "The string s3 is not greater than "
           << "the string s1." << endl;

   // Third member function: comparison between left-side object
   // of C-syle string type & right-side object of type basic_string
   if ( s2 > s3 )
      cout << "The string s2 is greater than "
           << "the string s3." << endl;
   else
      cout << "The string s2 is not greater than "
           << "the string s3." << endl;
}
```

```Output
The basic_string s1 = strict.
The basic_string s2 = strum.
The C-style string s3 = stricture.
The string s1 is not greater than the string s2.
The string s3 is greater than the string s1.
The string s2 is greater than the string s3.
```

## <a name="op_gt_eq"></a> operator&gt;=

Testet, ob das Zeichenfolgenobjekt links vom Operator größer als oder gleich dem Zeichenfolgenobjekt rechts vom Operator ist.

```cpp
template <class CharType, class Traits, class Allocator>
bool operator>=(
    const basic_string<CharType, Traits, Allocator>& left,
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
bool operator>=(
    const basic_string<CharType, Traits, Allocator>& left,
    const CharType* right);

template <class CharType, class Traits, class Allocator>
bool operator>=(
    const CharType* left,
    const basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parameter

`left` Eine Zeichenfolge im C-Format oder ein Objekt des Typs `basic_string` verglichen werden soll.

`right` Eine Zeichenfolge im C-Format oder ein Objekt des Typs `basic_string` verglichen werden soll.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn das Zeichenfolgenobjekt links vom Operator lexikografisch größer als oder gleich dem Zeichenfolgenobjekt rechts vom Operator ist, andernfalls **FALSE**.

### <a name="remarks"></a>Hinweise

Ein lexikografischer Vergleich zwischen Zeichenfolgen vergleicht diese zeichenweise, bis:

- Er zwei korrespondierende ungleiche Zeichen findet, und deren Vergleich als Ergebnis des Vergleichs zweier Zeichenfolgen genommen wird.

- Er keine Ungleichheiten findet, aber eine Zeichenfolge mehr Zeichen hat als die andere und die kürzere Zeichenfolge als kleiner als die längere Zeichenfolge betrachtet wird.

- Er keine Ungleichheiten findet und feststellt, dass die Zeichenfolgen die gleiche Anzahl von Zeichen haben und daher gleich sind.

### <a name="example"></a>Beispiel

```cpp
// string_op_ge.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // Declaring an objects of type basic_string<char>
   string s1 ( "strict" );
   string s2 ( "strum" );
   cout << "The basic_string s1 = " << s1 << "." << endl;
   cout << "The basic_string s2 = " << s2 << "." << endl;

   // Declaring a C-style string
   char *s3 = "stricture";
   cout << "The C-style string s3 = " << s3 << "." << endl;

   // First member function: comparison between left-side object
   // of type basic_string & right-side object of type basic_string
   if ( s1 >= s2 )
      cout << "The string s1 is greater than or equal to "
           << "the string s2." << endl;
   else
      cout << "The string s1 is less than "
           << "the string s2." << endl;

   // Second member function: comparison between left-side object
   // of type basic_string & right-side object of C-syle string type
   if ( s3 >= s1 )
      cout << "The string s3 is greater than or equal to "
           << "the string s1." << endl;
   else
      cout << "The string s3 is less than "
           << "the string s1." << endl;

   // Third member function: comparison between left-side object
   // of C-syle string type & right-side object of type basic_string
   if ( s2 >= s3 )
      cout << "The string s2 is greater than or equal to "
           << "the string s3." << endl;
   else
      cout << "The string s2 is less than "
           << "the string s3." << endl;
}
```

```Output
The basic_string s1 = strict.
The basic_string s2 = strum.
The C-style string s3 = stricture.
The string s1 is less than the string s2.
The string s3 is greater than or equal to the string s1.
The string s2 is greater than or equal to the string s3.
```

## <a name="op_gt_gt"></a> operator&gt;&gt;

Eine Vorlagenfunktion, die eine Zeichenfolge aus dem Eingabestream liest.

```cpp
template <class CharType, class Traits, class Allocator>
basic_istream<CharType, Traits>& operator>>(
    basic_istream<CharType, Traits>& _Istr,
    basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parameter

`_Istr` Der Eingabedatenstrom verwendet, um die Sequenz zu extrahieren.

`right` Die Zeichenfolge, die aus dem Eingabestream extrahiert wird.

### <a name="return-value"></a>Rückgabewert

Liest den Wert der angegebenen Zeichenfolge aus `_Istr` und gibt ihn in `right`.

### <a name="remarks"></a>Hinweise

Der Operator überspringt die führenden Leerzeichen, sofern das `skipws`-Flag nicht festgelegt ist. Es liest alle folgenden Zeichen, bis das nächste Zeichen ein Leerzeichen ist oder das Ende der Datei erreicht wird.

Die Vorlagenfunktion überlädt **operator>>**, um die von `right` gesteuerte Sequenz durch eine Sequenz von Elementen zu ersetzen, die aus dem Stream `_Istr` extrahiert wurden. Die Extraktion stoppt:

- Am Ende der Datei.

- Nachdem die Funktion `_Istr` extrahiert hat. **width** Elemente, wenn dieser Wert ungleich null ist.

Nachdem die Funktion `_Istr` extrahiert hat. [max_size](../standard-library/basic-string-class.md#max_size) Elemente.

- Nachdem die Funktion ein Element extrahiert *ch* für die [Use_facet](../standard-library/basic-filebuf-class.md#open)< **Ctype** \< **CharType**> > ( `getloc`). **ist**( **Ctype** \< **CharType**>:: **Speicherplatz**, *ch*) ist "true" in diesem Fall das Zeichen wird zurückgesetzt .

Wenn die Funktion keine Elemente extrahiert, ruft sie [setstate](../standard-library/basic-ios-class.md#setstate)( `ios_base::failbit`) auf. In jedem Fall ruft **Istr**. **Breite**(0) und gibt \* **dies**.

### <a name="example"></a>Beispiel

```cpp
// string_op_read_.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   string c0;
   cout << "Input a string c0 ( try: Fibonacci numbers ): ";
   cin >> c0;
   cout << "The string entered is c0 = " << c0 << endl;
}
```

## <a name="see-also"></a>Siehe auch

[\<string>](../standard-library/string.md)<br/>
