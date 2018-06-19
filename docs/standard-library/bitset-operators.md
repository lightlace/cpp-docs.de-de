---
title: '&lt;bitset&gt;-Operatoren | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- bitset/std::operator&amp;
- bitset/std::operator&gt;&gt;
- bitset/std::operator&lt;&lt;
- bitset/std::operator^
- bitset/std::operator|
dev_langs:
- C++
ms.assetid: 84fe6a13-6f6e-4cdc-bf8f-6f65ab1134d4
author: corob-msft
ms.author: corob
helpviewer_keywords:
- std::operator&amp; (bitset)
- std::operator&gt;&gt; (bitset)
- std::operator&lt;&lt; (bitset)
ms.workload:
- cplusplus
ms.openlocfilehash: 3056546e5a543c0058f789e293e0a63a3d53283a
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33850397"
---
# <a name="ltbitsetgt-operators"></a>&lt;bitset&gt;-Operatoren

||||
|-|-|-|
|[operator&amp;](#op_amp)|[operator&gt;&gt;](#op_gt_gt)|[operator&lt;&lt;](#op_lt_lt)|
|[operator^](#op_xor)|[operator|](#op_or)|

## <a name="op_amp"></a> operator&amp;

Führt ein bitweises `AND` zwischen zwei Bitsets aus.

```cpp
template <size_t size>
bitset<size>
operator&(
    const bitset<size>& left,
    const bitset<size>& right);
```

### <a name="parameters"></a>Parameter

`left` Die erste von der zwei bitsets aus, dessen entsprechende Elemente werden mit einer bitweisen Kombination `AND`.

`right` Die zweite von der zwei valarray-Objekten, dessen entsprechende Elemente werden mit einer bitweisen Kombination `AND`.

### <a name="return-value"></a>Rückgabewert

Ein Bitset, dessen Elemente das Ergebnis der Ausführung der `AND`-Operation für die entsprechenden Elemente von `left` und `right` sind.

### <a name="example"></a>Beispiel

```cpp
// bitset_and.cpp
// compile with: /EHsc
#include <bitset>
#include <iostream>
#include <string>

using namespace std;

int main()
{
   bitset<4> b1 ( string("0101") );
   bitset<4> b2 ( string("0011") );
   bitset<4> b3 = b1 & b2;
   cout << "bitset 1: " << b1 << endl;
   cout << "bitset 2: " << b2 << endl;
   cout << "bitset 3: " << b3 << endl;
}
```

```Output
bitset 1: 0101
bitset 2: 0011
bitset 3: 0001
```

## <a name="op_lt_lt"></a> operator&lt;&lt;

Fügt eine Textdarstellung der Bitsequenz in den Ausgabestream ein.

```

template <class CharType, class Traits, size_t N>
basic_ostream<CharType, Traits>& operator<<(
    basic_ostream<CharType, Traits>& ostr,
    const bitset<N>& right);
```

### <a name="parameters"></a>Parameter

`right` Ein Objekt des Typs **Bitset\<N >** , ist in den Ausgabestream als Zeichenfolge eingefügt werden soll.

### <a name="return-value"></a>Rückgabewert

Eine Textdarstellung der Bitsequenz in **ostr**.

### <a name="remarks"></a>Hinweise

Die Vorlagenfunktion überlädt **operator<<**, sodass ein Bitset ausgegeben werden kann, ohne es zuerst in eine Zeichenfolge zu konvertieren. Die Vorlagenfunktion führt Folgendes aus:

**ostr** << _ *Right*. [to_string](bitset-class.md) < **CharType**, **Traits**, **allocator**\< **CharType**> > ( )

### <a name="example"></a>Beispiel

```cpp
// bitset_op_insert.cpp
// compile with: /EHsc
#include <bitset>
#include <iostream>
#include <string>

int main( )
{
   using namespace std;

   bitset<5> b1 ( 9 );

   // bitset inserted into output stream directly
   cout << "The ordered set of bits in the bitset<5> b1(9)"
        << "\n can be output with the overloaded << as: ( "
        << b1 << " )" << endl;

   // Compare converting bitset to a string before
   // inserting it into the output steam
   string s1;
   s1 =  b1.template to_string<char,
      char_traits<char>, allocator<char> >( );
   cout << "The string returned from the bitset b1"
        << "\n by the member function to_string( ) is: "
        << s1 << "." << endl;
}
```

## <a name="op_gt_gt"></a> operator&gt;&gt;

Liest eine Folge von Bitzeichen in ein Bitset aus.

```

template <class CharType, class Traits, size_t Bits>
basic_istream<CharType, Traits>& operator>> (
    basic_istream<CharType, Traits>&
_Istr,
    bitset<N>&
    right);
```

### <a name="parameters"></a>Parameter

`_Istr` Die Zeichenfolge, die in den Eingabestream in der Bitset einzufügenden eingegeben wird.

`right` Die Bitset, mit dem die Bits aus dem Eingabestream empfangen wird.

### <a name="return-value"></a>Rückgabewert

Die Vorlagenfunktion gibt die Zeichenfolge `_Istr` zurück.

### <a name="remarks"></a>Hinweise

Die Vorlagenfunktion überlädt **operator>>**, um im Bitset _ *Right* den Wert bitset( `str`) zu speichern, wobei `str` ein Objekt des Typs [basic_string](basic-string-class.md) < **CharType**, **Traits**, **allocator**\< **CharType**> > **&** ist, das aus `_Istr` extrahiert wurde.

Die Vorlagenfunktion extrahiert Elemente aus `_Istr` und fügt sie so lange in das Bitset ein, bis:

- Alle Bitelemente aus dem Eingabestream extrahiert und im Bitset gespeichert wurden.

- Das Bitset mit Bits aus dem Eingabestream gefüllt wurde.

- Ein Eingabeelement gefunden wird, das weder 0 noch 1 ist.

### <a name="example"></a>Beispiel

```cpp
#include <bitset>
#include <iostream>
#include <string>

using namespace std;
int main()
{

   bitset<5> b1;
   cout << "Enter string of (0 or 1) bits for input into bitset<5>.\n"
        << "Try bit string of length less than or equal to 5,\n"
        << " (for example: 10110): ";
   cin >>  b1;

   cout << "The ordered set of bits entered from the "
        << "keyboard\n has been input into bitset<5> b1 as: ( "
        << b1 << " )" << endl;

   // Truncation due to longer string of bits than length of bitset
   bitset<2> b3;
   cout << "Enter string of bits (0 or 1) for input into bitset<2>.\n"
        << " Try bit string of length greater than 2,\n"
        << " (for example: 1011): ";
   cin >>  b3;

   cout << "The ordered set of bits entered from the "
        << "keyboard\n has been input into bitset<2> b3 as: ( "
        << b3 << " )" << endl;

   // Flushing the input stream
   char buf[100];
   cin.getline(&buf[0], 99);

   // Truncation with non-bit value
   bitset<5> b2;
   cout << "Enter a string for input into  bitset<5>.\n"
        << " that contains a character than is NOT a 0 or a 1,\n "
        << " (for example: 10k01): ";
   cin >>  b2;

   cout << "The string entered from the keyboard\n"
        << " has been input into bitset<5> b2 as: ( "
        << b2 << " )" << endl;
}
```

## <a name="op_xor"></a> operator^

Führt ein bitweises `EXCLUSIVE-OR` zwischen zwei Bitsets aus.

```cpp
template <size_t size>
bitset<size>
operator^(
    const bitset<size>& left,
    const bitset<size>& right);
```

### <a name="parameters"></a>Parameter

`left` Die erste von der zwei bitsets aus, dessen entsprechende Elemente werden mit einer bitweisen Kombination `EXCLUSIVE-OR`.

`right` Die zweite von der zwei valarray-Objekten, dessen entsprechende Elemente werden mit einer bitweisen Kombination `EXCLUSIVE-OR`.

### <a name="return-value"></a>Rückgabewert

Ein Bitset, dessen Elemente das Ergebnis der Ausführung der `EXCLUSIVE-OR`-Operation für die entsprechenden Elemente von `left` und `right` sind.

### <a name="example"></a>Beispiel

```cpp
// bitset_xor.cpp
// compile with: /EHsc
#include <bitset>
#include <iostream>
#include <string>

using namespace std;

int main()
{
   bitset<4> b1 ( string("0101") );
   bitset<4> b2 ( string("0011") );
   bitset<4> b3 = b1 ^ b2;
   cout << "bitset 1: " << b1 << endl;
   cout << "bitset 2: " << b2 << endl;
   cout << "bitset 3: " << b3 << endl;
}
```

```Output
bitset 1: 0101
bitset 2: 0011
bitset 3: 0110
```

## <a name="op_or"></a>  Operator |

Führt ein bitweises `OR` zwischen zwei Bitsets aus.

```cpp
template <size_t size>
bitset<size>
operator|(
    const bitset<size>& left,
    const bitset<size>& right);
```

### <a name="parameters"></a>Parameter

`left` Die erste von der zwei bitsets aus, dessen entsprechende Elemente werden mit einer bitweisen Kombination `OR`.

`right` Die zweite von der zwei valarray-Objekten, dessen entsprechende Elemente werden mit einer bitweisen Kombination `OR`.

### <a name="return-value"></a>Rückgabewert

Ein Bitset, dessen Elemente das Ergebnis der Ausführung der `OR`-Operation für die entsprechenden Elemente von `left` und `right` sind.

### <a name="example"></a>Beispiel

```cpp
// bitset_or.cpp
// compile with: /EHsc
#include <bitset>
#include <iostream>
#include <string>

using namespace std;

int main()
{
   bitset<4> b1 ( string("0101") );
   bitset<4> b2 ( string("0011") );
   bitset<4> b3 = b1 | b2;
   cout << "bitset 1: " << b1 << endl;
   cout << "bitset 2: " << b2 << endl;
   cout << "bitset 3: " << b3 << endl;
}
```

```Output
bitset 1: 0101
bitset 2: 0011
bitset 3: 0111
```

## <a name="see-also"></a>Siehe auch

[\<bitset>](../standard-library/bitset.md)<br/>
