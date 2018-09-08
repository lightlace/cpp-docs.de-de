---
title: istreambuf_iterator-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- streambuf/std::istreambuf_iterator
- iterator/std::istreambuf_iterator::char_type
- iterator/std::istreambuf_iterator::int_type
- iterator/std::istreambuf_iterator::istream_type
- iterator/std::istreambuf_iterator::streambuf_type
- iterator/std::istreambuf_iterator::traits_type
- iterator/std::istreambuf_iterator::equal
dev_langs:
- C++
helpviewer_keywords:
- std::istreambuf_iterator [C++]
- std::istreambuf_iterator [C++], char_type
- std::istreambuf_iterator [C++], int_type
- std::istreambuf_iterator [C++], istream_type
- std::istreambuf_iterator [C++], streambuf_type
- std::istreambuf_iterator [C++], traits_type
- std::istreambuf_iterator [C++], equal
ms.assetid: 39002da2-61a6-48a5-9d0c-5df8271f6038
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 381316cd7b05f62ba8b730c376e266e5fd0a70cb
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44109281"
---
# <a name="istreambufiterator-class"></a>istreambuf_iterator-Klasse

Die Vorlagenklasse „istreambuf_iterator“ beschreibt ein Eingabeiteratorobjekt, das Zeichenelemente aus einem Eingabestreampuffer extrahiert, auf den es durch ein gespeichertes Objekt zugreift, des Zeigers auf `basic_streambuf`\< **CharType**, **Traits**>.

## <a name="syntax"></a>Syntax

```cpp
template <class CharType class Traits = char_traits <CharType>>
class istreambuf_iterator
: public iterator<input_iterator_tag, CharType, typename Traits ::off_type, CharType*, CharType&>
```

### <a name="parameters"></a>Parameter

*CharType*<br/>
Der Typ, der den Zeichentyp für das istreambuf_iterator-Objekt darstellt.

*Merkmale*<br/>
Der Typ, der den Zeichentyp für das istreambuf_iterator-Objekt darstellt. Dieses Argument ist optional, und der Standardwert ist `char_traits`\< *CharType>.*

## <a name="remarks"></a>Hinweise

Die istreambuf_iterator-Klasse muss die Anforderungen für einen Eingabeiterator erfüllen.

Nachdem ein Objekt der istreambuf_iterator-Klasse mit einem als nicht null gespeicherten Zeiger erstellt oder inkrementiert wurde, versucht das Objekt effektiv, ein Objekt vom Typ *CharType* aus dem zugeordneten Eingabestream zu extrahieren und zu speichern. Die Extraktion kann jedoch verzögert werden, bis das Objekt tatsächlich dereferenziert oder kopiert wurde. Wenn die Extraktion fehlschlägt, ersetzt das Objekt den gespeicherten Zeiger durch einen NULL-Zeiger und erstellt so einen Indikator für das Ende der Sequenz.

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[istreambuf_iterator](#istreambuf_iterator)|Erstellt ein `istreambuf_iterator`-Objekt, das initialisiert wird, um Zeichen aus dem Eingabestream zu lesen.|

### <a name="typedefs"></a>Typedefs

|Typname|Beschreibung|
|-|-|
|[char_type](#char_type)|Ein Typ, der für den Zeichentyp von `ostreambuf_iterator` bereitgestellt wird.|
|[int_type](#int_type)|Ein Typ, der einen Ganzzahltyp für ein `istreambuf_iterator`-Objekt bereitstellt.|
|[istream_type](#istream_type)|Ein Typ, der für den Streamtyp von `istream_iterator` bereitgestellt wird.|
|[streambuf_type](#streambuf_type)|Ein Typ, der für den Streamtyp von `istreambuf_iterator` bereitgestellt wird.|
|[traits_type](../standard-library/istream-iterator-class.md#traits_type)|Ein Typ, der für den Merkmaltyp von `istream_iterator` bereitgestellt wird.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[equal](#equal)|Testet zwei Eingabestreampufferiteratoren auf Gleichheit.|

### <a name="operators"></a>Operatoren

|Operator|Beschreibung|
|-|-|
|[operator*](#op_star)|Der Dereferenzierungsoperator gibt das folgende Zeichen im Stream zurück.|
|[operator++](#op_add_add)|Gibt entweder das folgende Zeichen im Eingabestream zurück oder kopiert das Objekt vor dem Inkrementieren und gibt die Kopie zurück.|
|[operator->](#op_arrow)|Gibt den Wert eines Members zurück, falls vorhanden.|

## <a name="requirements"></a>Anforderungen

**Header:** \<iterator>

**Namespace:** std

## <a name="char_type"></a> istreambuf_iterator::char_type

Ein Typ, der für den Zeichentyp von `ostreambuf_iterator` bereitgestellt wird.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Hinweise

Der Typ stellt ein Synonym für den Vorlagenparameter *CharType* dar.

### <a name="example"></a>Beispiel

```cpp
// istreambuf_iterator_char_type.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>
#include <algorithm>

int main( )
{
   using namespace std;

   typedef istreambuf_iterator<char>::char_type CHT1;
   typedef istreambuf_iterator<char>::traits_type CHTR1;

   cout << "(Try the example: 'So many dots to be done'\n"
        << " then an Enter key to insert into the output,\n"
        << " & use a ctrl-Z Enter key combination to exit): ";

   // istreambuf_iterator for input stream
   istreambuf_iterator< CHT1, CHTR1> charInBuf ( cin );
   ostreambuf_iterator<char> charOut ( cout );

   // Used in conjunction with replace_copy algorithm
   // to insert into output stream and replace spaces
   // with dot-separators
   replace_copy ( charInBuf , istreambuf_iterator<char>( ),
        charOut , ' ' , '.' );
}
```

## <a name="equal"></a> istreambuf_iterator::equal

Testet zwei Eingabestream-Pufferiteratoren auf Äquivalenz.

```cpp
bool equal(const istreambuf_iterator<CharType, Traits>& right) const;
```

### <a name="parameters"></a>Parameter

*right*<br/>
Der Iterator für die Durchführung von Gleichheitsüberprüfungen.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn die Iteratoren `istreambuf_iterator` End-of-Stream-Iteratoren sind oder wenn keiner von beiden ein End-of-Stream-Iterator ist; andernfalls **FALSE**.

### <a name="remarks"></a>Hinweise

Wird eine Reihe von definiert die `istreambuf_iterator` Iteratoren sind äquivalent, um die aktuelle Position und die End-of-Stream-Iterator; da aber alle nicht-End-of-Stream der `equal` Member-Funktion, es ist nicht möglich, alle Unterbereiche mit definieren `istreambuf_iterator`s. Die `==`- und `!=`-Operatoren weisen die gleiche Semantik auf.

### <a name="example"></a>Beispiel

```cpp
// istreambuf_iterator_equal.cpp
// compile with: /EHsc
#include <iterator>
#include <iostream>

int main( )
{
   using namespace std;

   cout << "(Try the example: 'Hello world!'\n"
        << " then an Enter key to insert into the output,\n"
        << " & use a ctrl-Z Enter key combination to exit): ";

   istreambuf_iterator<char> charReadIn1 ( cin );
   istreambuf_iterator<char> charReadIn2 ( cin );

   bool b1 = charReadIn1.equal ( charReadIn2 );

   if (b1)
      cout << "The iterators are equal." << endl;
   else
      cout << "The iterators are not equal." << endl;
}
```

## <a name="int_type"></a> istreambuf_iterator::int_type

Ein Typ, der einen Ganzzahltyp für ein `istreambuf_iterator`-Objekt bereitstellt.

```cpp
typedef typename traits_type::int_type int_type;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für `Traits::int_type`.

### <a name="example"></a>Beispiel

```cpp
// istreambuf_iterator_int_type.cpp
// compile with: /EHsc
#include <iterator>
#include <iostream>

int main( )
{
   using namespace std;
   istreambuf_iterator<char>::int_type inttype1 = 100;
   cout << "The inttype1 = " << inttype1 << "." << endl;
}
\* Output:
The inttype1 = 100.
*\
```

## <a name="istream_type"></a> istreambuf_iterator::istream_type

Ein Typ, der für den Streamtyp von `istreambuf_iterator` bereitgestellt wird.

```cpp
typedef basic_istream<CharType, Traits> istream_type;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für `basic_istream`\< **CharType**, **Traits**>.

### <a name="example"></a>Beispiel

Unter [istreambuf_iterator](#istreambuf_iterator) finden Sie ein Beispiel für das Deklarieren und Verwenden von `istream_type`.

## <a name="istreambuf_iterator"></a> istreambuf_iterator::istreambuf_iterator

Erstellt einen istreambuf_iterator, der initialisiert wird, um Zeichen aus dem Eingabestream zu lesen.

```cpp
istreambuf_iterator(streambuf_type* strbuf = 0) throw();
istreambuf_iterator(istream_type& _Istr) throw();
```

### <a name="parameters"></a>Parameter

*strbuf*<br/>
Der Eingabestreampuffer, dem der `istreambuf_iterator` angefügt wird.

*_Istr*<br/>
Der Eingabestream, dem der `istreambuf_iterator` angefügt wird.

### <a name="remarks"></a>Hinweise

Der erste Konstruktor initialisiert den Eingabestream-Pufferzeiger mit *Strbuf*. Der zweite Konstruktor initialisiert den Eingabestream-Pufferzeiger mit *_Istr*. `rdbuf`, und anschließend zum Extrahieren und speichern ein Objekt vom Typ versucht `CharType`.

### <a name="example"></a>Beispiel

```cpp
// istreambuf_iterator_istreambuf_iterator.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <algorithm>
#include <iostream>

int main( )
{
   using namespace std;

   // Following declarations will not compile:
   istreambuf_iterator<char>::istream_type &istrm = cin;
   istreambuf_iterator<char>::streambuf_type *strmbf = cin.rdbuf( );

   cout << "(Try the example: 'Oh what a world!'\n"
      << " then an Enter key to insert into the output,\n"
      << " & use a ctrl-Z Enter key combination to exit): ";
   istreambuf_iterator<char> charReadIn ( cin );
   ostreambuf_iterator<char> charOut ( cout );

   // Used in conjunction with replace_copy algorithm
   // to insert into output stream and replace spaces
   // with hyphen-separators
   replace_copy ( charReadIn , istreambuf_iterator<char>( ),
      charOut , ' ' , '-' );
}
```

## <a name="op_star"></a> istreambuf_iterator::operator*

Der Dereferenzierungsoperator gibt das folgende Zeichen im Stream zurück.

```cpp
CharType operator*() const;
```

### <a name="return-value"></a>Rückgabewert

Das nächste Zeichen im Stream.

### <a name="example"></a>Beispiel

```cpp
// istreambuf_iterator_operator_deref.cpp
// compile with: /EHsc
#include <iterator>
#include <iostream>

int main( )
{
   using namespace std;

   cout << "Type string of characters & enter to output it,\n"
      << " with stream buffer iterators,(try: 'I'll be back.')\n"
      << " repeat as many times as desired,\n"
      << " then keystroke ctrl-Z Enter to exit program: ";
   istreambuf_iterator<char> inpos ( cin );
   istreambuf_iterator<char> endpos;
   ostreambuf_iterator<char> outpos ( cout );
   while ( inpos != endpos )
   {
*outpos = *inpos;   //Put value of outpos equal to inpos
      ++inpos;
      ++outpos;
   }
}
```

## <a name="op_add_add"></a> istreambuf_iterator::operator++

Gibt entweder das folgende Zeichen im Eingabestream zurück oder kopiert das Objekt vor dem Inkrementieren und gibt die Kopie zurück.

```cpp
istreambuf_iterator<CharType, Traits>& operator++();
istreambuf_iterator<CharType, Traits> operator++(int);
```

### <a name="return-value"></a>Rückgabewert

Ein `istreambuf_iterator` oder ein Verweis auf `istreambuf_iterator`.

### <a name="remarks"></a>Hinweise

Der erste Operator versucht schließlich zum Extrahieren und speichern ein Objekt des Typs `CharType` aus dem zugeordneten Eingabestream. Der zweite Operator erstellt eine Kopie des Objekts, inkrementiert das Objekt und gibt dann die Kopie zurück.

### <a name="example"></a>Beispiel

```cpp
// istreambuf_iterator_operator_incr.cpp
// compile with: /EHsc
#include <iterator>
#include <iostream>

int main( )
{
   using namespace std;

   cout << "Type string of characters & enter to output it,\n"
      << " with stream buffer iterators,(try: 'I'll be back.')\n"
      << " repeat as many times as desired,\n"
      << " then keystroke ctrl-Z Enter to exit program: ";
   istreambuf_iterator<char> inpos ( cin );
   istreambuf_iterator<char> endpos;
   ostreambuf_iterator<char> outpos ( cout );
   while ( inpos != endpos )
   {
*outpos = *inpos;
      ++inpos;   //Increment istreambuf_iterator
      ++outpos;
   }
}
```

## <a name="op_arrow"></a> istreambuf_iterator::operator-&gt;

Gibt den Wert eines Members zurück, falls vorhanden.

```cpp
const Elem* operator->() const;
```

### <a name="return-value"></a>Rückgabewert

Der Operator gibt **&\*\*this** zurück.

## <a name="streambuf_type"></a> istreambuf_iterator::streambuf_type

Ein Typ, der für den Streamtyp von „istreambuf_iterator“ bereitgestellt wird.

```cpp
typedef basic_streambuf<CharType, Traits> streambuf_type;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für `basic_streambuf`\< **CharType**, **Traits**>.

### <a name="example"></a>Beispiel

Unter [istreambuf_iterator](#istreambuf_iterator) finden Sie ein Beispiel für das Deklarieren und Verwenden von `istreambuf_type`.

## <a name="traits_type"></a> istreambuf_iterator::traits_type

Ein Typ, der für den Merkmaltyp von `istream_iterator` bereitgestellt wird.

```cpp
typedef Traits traits_type;
```

### <a name="remarks"></a>Hinweise

Der Typ stellt ein Synonym für den Vorlagenparameter *Merkmale* dar.

### <a name="example"></a>Beispiel

```cpp
// istreambuf_iterator_traits_type.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>
#include <algorithm>

int main( )
{
   using namespace std;

   typedef istreambuf_iterator<char>::char_type CHT1;
   typedef istreambuf_iterator<char>::traits_type CHTR1;

   cout << "(Try the example: 'So many dots to be done'\n"
        << " then an Enter key to insert into the output,\n"
        << " & use a ctrl-Z Enter key combination to exit): ";

   // istreambuf_iterator for input stream
   istreambuf_iterator< CHT1, CHTR1> charInBuf ( cin );
   ostreambuf_iterator<char> charOut ( cout );

   // Used in conjunction with replace_copy algorithm
   // to insert into output stream and replace spaces
   // with dot-separators
   replace_copy ( charInBuf , istreambuf_iterator<char>( ),
        charOut , ' ' , '.' );
}
```

## <a name="see-also"></a>Siehe auch

[iterator-Struktur](../standard-library/iterator-struct.md)<br/>
[\<iterator>](../standard-library/iterator.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)<br/>
