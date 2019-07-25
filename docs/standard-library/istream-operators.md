---
title: '&lt;iStream&gt;-Operatoren'
ms.date: 11/04/2016
f1_keywords:
- istream/std::operator&gt;&gt;
ms.assetid: 7174da41-f301-4a34-b631-0ab918b188d2
ms.openlocfilehash: c10692194c80051b10ecbe776c7d23a03860d508
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68447786"
---
# <a name="ltistreamgt-operators"></a>&lt;iStream&gt;-Operatoren

## <a name="op_gt_gt"></a> Operator&gt;&gt;

Extrahiert von Zeichenfolgen und Zeichen aus dem Stream.

```cpp
template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr,
    Elem* str);

template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr,
    Elem& Ch);

template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,
    signed char* str);

template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,
    signed char& Ch);

template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,
    unsigned char* str);

template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,
    unsigned char& Ch);

template <class Elem, class Tr, class Type>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<char, Tr>&& Istr,
    Type& val);
```

### <a name="parameters"></a>Parameter

*Ch*\
Ein Zeichen.

*ISTR*\
Ein Stream.

*SRT*\
Eine Zeichenfolge.

*ster*\
Ein Typ.

### <a name="return-value"></a>Rückgabewert

Ein Stream

### <a name="remarks"></a>Hinweise

Die `basic_istream`-Klasse definiert außerdem mehrere Extraktionsoperatoren. Weitere Informationen finden Sie unter [basic_istream::operator>>](../standard-library/basic-istream-class.md#op_gt_gt).

Die Vorlagenfunktion:

```cpp
template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr, Elem* str);
```

extrahiert bis zu *N*-1-Elemente und speichert sie in das Array, beginnend mit _*Str*. Wenn `Istr`. [Breite](../standard-library/ios-base-class.md#width) ist größer als 0 (  null) `Istr`, N ist. **Breite**; Andernfalls ist es die Größe des größten Arrays von `Elem` , das deklariert werden kann. Die Funktion speichert den Wert `Elem()` immer nach allen extrahierten Elementen, die er speichert. Die Extraktion hält früh am Ende der Datei, an einem Zeichen mit dem Wert **Elem**(0) (das nicht extrahiert wurde), oder an einem beliebigen Element (das nicht extrahiert wurde), welches von [ws](../standard-library/istream-functions.md#ws) verworfen werden würde. Wenn die Funktion keine Elemente extrahiert, ruft `Istr`Sie auf. [SetState](../standard-library/basic-ios-class.md#setstate) (**Failbit**). In jedem Fall ruft `Istr`Sie auf. **Breite** (0) und gibt *ISTR*zurück.

**Sicherheitshinweis** Die aus dem Eingabestream extrahierte aus null endenden Zeichenfolge darf die Größe des Ziel Puffers *Str*nicht überschreiten. Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](/windows/desktop/SecBP/avoiding-buffer-overruns).

Die Vorlagenfunktion:

```cpp
template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr, Elem& Ch);
```

extrahiert ein Element, sofern möglich, und speichert es in *ch*. Andernfalls **wird**aufgerufen. [setstate](../standard-library/basic-ios-class.md#setstate)( **failbit**) auf. In jedem Fall wird *ISTR*zurückgegeben.

Die Vorlagenfunktion:

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, signed char* str);
```

`Istr >> ( char * ) str` wird zurückgegeben.

Die Vorlagenfunktion:

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, signed char& Ch);
```

`Istr >> ( char& ) Ch` wird zurückgegeben.

Die Vorlagenfunktion:

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, unsigned char* str);
```

`Istr >> ( char * ) str` wird zurückgegeben.

Die Vorlagenfunktion:

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, unsigned char& Ch);
```

`Istr >> ( char& ) Ch` wird zurückgegeben.

Die Vorlagenfunktion:

```cpp
template <class Elem, class Tr, class Type>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<char, Tr>&& Istr,
    Type& val);
```

gibt `Istr >> val` zurück (und konvertiert einen Rvalue- `Istr` Verweis in einen lvalue im Prozess).

### <a name="example"></a>Beispiel

```cpp
// istream_op_extract.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main( )
{
   ws( cin );
   char c[10];

   cin.width( 9 );
   cin >> c;
   cout << c << endl;
}
```

## <a name="see-also"></a>Siehe auch

[\<istream>](../standard-library/istream.md)
