---
title: ostream_iterator-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- iterator/std::ostream_iterator
- iterator/std::ostream_iterator::char_type
- iterator/std::ostream_iterator::ostream_type
- iterator/std::ostream_iterator::traits_type
dev_langs:
- C++
helpviewer_keywords:
- std::ostream_iterator [C++]
- std::ostream_iterator [C++], char_type
- std::ostream_iterator [C++], ostream_type
- std::ostream_iterator [C++], traits_type
ms.assetid: 24d842d3-9f45-4bf6-a697-62f5968f5a03
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4ee931abb2273ab3119fa62b9219ad69448b2048
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38963523"
---
# <a name="ostreamiterator-class"></a>ostream_iterator-Klasse

Die Vorlagenklasse Ostream_iterator beschreibt ein ausgabeiteratorobjekt, das aufeinander folgende Elemente in den Ausgabestream mit der Extraktion schreibt `operator <<`.

## <a name="syntax"></a>Syntax

```cpp
template <class Type class CharType = char class Traits = char_traits <CharType>>
class ostream_iterator
```

### <a name="parameters"></a>Parameter

*Typ* den Typ des Objekts in den Ausgabestream eingefügt werden soll.

*CharType* der Typ, der den Zeichentyp für das `ostream_iterator`. Dieses Argument ist optional, und der Standardwert ist **Char**.

*"Traits"* der Typ, der den Zeichentyp für das `ostream_iterator`. Dieses Argument ist optional, und der Standardwert ist `char_traits`\< *CharType>.*

Die ostream_iterator-Klasse muss den Anforderungen für einen Ausgabeiterator entsprechen. Algorithmen können mit `ostream_iterator` direkt in Ausgabestreams geschrieben werden.

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[ostream_iterator](#ostream_iterator)|Erstellt einen `ostream_iterator`, der initialisiert und zum Schreiben in den Ausgabestream begrenzt wird.|

### <a name="typedefs"></a>Typedefs

|Typname|Beschreibung|
|-|-|
|[char_type](#char_type)|Ein Typ, der für den Zeichentyp von `ostream_iterator` bereitgestellt wird.|
|[ostream_type](#ostream_type)|Ein Typ, der für den Streamtyp von `ostream_iterator` bereitgestellt wird.|
|[traits_type](#traits_type)|Ein Typ, der für den Merkmaltyp von `ostream_iterator` bereitgestellt wird.|

### <a name="operators"></a>Operatoren

|Operator|Beschreibung|
|-|-|
|[operator*](#op_star)|Der Dereferenzierungsoperator, der zum Implementieren des Ausgabeiteratorausdrucks *`i` = `x` verwendet wird.|
|[operator++](#op_add_add)|Ein nicht funktionaler Inkrementoperator, der einen `ostream_iterator` zum gleichen Objekt zurückgibt, das er adressiert hat, bevor der Vorgang aufgerufen wurde.|
|[operator=](#op_eq)|Ein Zuweisungsoperator, der zum Implementieren des Ausgabeiteratorausdrucks *`i` = `x` zum Schreiben in einen Ausgabestream verwendet wird.|

## <a name="requirements"></a>Anforderungen

**Header:** \<iterator>

**Namespace:** std

## <a name="char_type"></a> ostream_iterator::char_type

Ein Typ, der für den Zeichentyp des Iterators bereitgestellt wird.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Hinweise

Der Type stellt ein Synonym für den Vorlagenparameter `CharType` dar.

### <a name="example"></a>Beispiel

```cpp
// ostream_iterator_char_type.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   typedef ostream_iterator<int>::char_type CHT1;
   typedef ostream_iterator<int>::traits_type CHTR1;

   // ostream_iterator for stream cout
   // with new line delimiter:
    ostream_iterator<int, CHT1, CHTR1> intOut ( cout , "\n" );

   // Standard iterator interface for writing
   // elements to the output stream:
   cout << "The integers written to the output stream\n"
        << "by intOut are:" << endl;
 *intOut = 10;
 *intOut = 20;
 *intOut = 30;
}
\* Output:
The integers written to the output stream
by intOut are:
10
20
30
*\
```

## <a name="op_star"></a> ostream_iterator::operator*

Der Dereferenzierungsoperator, der zum Implementieren des Ausgabeiteratorausdrucks \* *ii* = *x* verwendet wird.

```cpp
ostream_iterator<Type, CharType, Traits>& operator*();
```

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf `ostream_iterator`.

### <a name="remarks"></a>Hinweise

Die Anforderungen für einen Ausgabeiterator, der `ostream_iterator` erfüllen muss, benötigen nur den gültigen Ausdruck \* *ii* = *t*, und sagen nichts über den **operator** oder `operator=` selbst. Der Memberoperator in dieser Implementierung gibt **\*this** zurück.

### <a name="example"></a>Beispiel

```cpp
// ostream_iterator_op_deref.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   // ostream_iterator for stream cout
   // with new line delimiter
   ostream_iterator<int> intOut ( cout , "\n" );

   // Standard iterator interface for writing
   // elements to the output stream
   cout << "Elements written to output stream:" << endl;
 *intOut = 10;
   intOut++;      // No effect on iterator position
 *intOut = 20;
 *intOut = 30;
}
\* Output:
Elements written to output stream:
10
20
30
*\
```

## <a name="op_add_add"></a> ostream_iterator::operator++

Ein nicht funktionaler Inkrementoperator, der einen `ostream_iterator` zum gleichen Objekt zurückgibt, das er adressiert hat, bevor der Vorgang aufgerufen wurde.

```cpp
ostream_iterator<Type, CharType, Traits>& operator++();
ostream_iterator<Type, CharType, Traits> operator++(int);
```

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf `ostream_iterator`.

### <a name="remarks"></a>Hinweise

Diese Memberoperatoren geben beide **\*this** zurück.

### <a name="example"></a>Beispiel

```cpp
// ostream_iterator_op_incr.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   // ostream_iterator for stream cout
   // with new line delimiter
   ostream_iterator<int> intOut ( cout , "\n" );

   // standard iterator interface for writing
   // elements to the output stream
   cout << "Elements written to output stream:" << endl;
 *intOut = 10;
   intOut++;      // No effect on iterator position
 *intOut = 20;
 *intOut = 30;
}
\* Output:
Elements written to output stream:
10
20
30
*\
```

## <a name="op_eq"></a> ostream_iterator::operator=

Ein Zuweisungsoperator, der zum Implementieren des Ausgabeiteratorausdrucks *`i` = `x` zum Schreiben in einen Ausgabestream verwendet wird.

```cpp
ostream_iterator<Type, CharType, Traits>& operator=(const Type& val);
```

### <a name="parameters"></a>Parameter

*Val* den Wert des Objekts vom Typ `Type` in den Ausgabestream eingefügt werden soll.

### <a name="return-value"></a>Rückgabewert

Der Operator fügt *Val* in den Ausgabestream, der dem Objekt zugeordnet wird, gefolgt von dem Trennzeichen den [Ostream_iterator-Konstruktor](#ostream_iterator) (sofern vorhanden), und klicken Sie dann einen Verweis auf die zurückgibt`ostream_iterator`.

### <a name="remarks"></a>Hinweise

Die Anforderungen für einen Ausgabeiterator, der `ostream_iterator` erfüllen muss, benötigen nur den gültigen Ausdruck * `ii` = `t`, und sagen nichts über den operator oder den operator= selbst. Dieser Memberoperator gibt `*this` zurück.

### <a name="example"></a>Beispiel

```cpp
// ostream_iterator_op_assign.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   // ostream_iterator for stream cout
   // with new line delimiter
   ostream_iterator<int> intOut ( cout , "\n" );

   // Standard iterator interface for writing
   // elements to the output stream
   cout << "Elements written to output stream:" << endl;
 *intOut = 10;
   intOut++;      // No effect on iterator position
 *intOut = 20;
 *intOut = 30;
}
\* Output:
Elements written to output stream:
10
20
30
*\
```

## <a name="ostream_iterator"></a> ostream_iterator::ostream_iterator

Erstellt einen `ostream_iterator`, der initialisiert und zum Schreiben in den Ausgabestream begrenzt wird.

```cpp
ostream_iterator(
    ostream_type& _Ostr);

ostream_iterator(
    ostream_type& _Ostr,
    const CharType* _Delimiter);
```

### <a name="parameters"></a>Parameter

*_Ostr* der Ausgabestream vom Typ [ostream_iterator:: ostream_type](#ostream_type) durchlaufen werden soll.

*_Delimiter* das Trennzeichen, das in den Ausgabestream zwischen Werten eingefügt wird.

### <a name="remarks"></a>Hinweise

Der erste Konstruktor initialisiert den Ausgabestreamzeiger mit `&_Ostr`. Der Zeiger für Zeichenfolgentrennzeichen kennzeichnet eine leere Zeichenfolge.

Der zweite Konstruktor initialisiert den ausgabestreamzeiger mit `&_Ostr` und der Zeiger für Zeichenfolgentrennzeichen mit *_Delimiter*.

### <a name="example"></a>Beispiel

```cpp
// ostream_iterator_ostream_iterator.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   // ostream_iterator for stream cout
   ostream_iterator<int> intOut ( cout , "\n" );
 *intOut = 10;
   intOut++;
 *intOut = 20;
   intOut++;

   int i;
   vector<int> vec;
   for ( i = 1 ; i < 7 ; ++i )
   {
      vec.push_back (  i );
   }

   // Write elements to standard output stream
   cout << "Elements output without delimiter: ";
   copy ( vec.begin ( ), vec.end ( ),
          ostream_iterator<int> ( cout ) );
   cout << endl;

   // Write elements with delimiter " : " to output stream
   cout << "Elements output with delimiter: ";
   copy ( vec.begin ( ), vec.end ( ),
          ostream_iterator<int> ( cout, " : " ) );
   cout << endl;
}
\* Output:
10
20
Elements output without delimiter: 123456
Elements output with delimiter: 1 : 2 : 3 : 4 : 5 : 6 :
*\
```

## <a name="ostream_type"></a> ostream_iterator::ostream_type

Ein Typ, der für den Streamtyp des Iteraotrs bereitgestellt wird.

```cpp
typedef basic_ostream<CharType, Traits> ostream_type;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für [basic_ostream](../standard-library/basic-ostream-class.md)< `CharType`, `Traits`>, eine Stream-Klasse der iostream-Hierarchie, die Objekte definiert, die zum Schreiben verwendet werden können.

### <a name="example"></a>Beispiel

Unter [ostream_iterator](#ostream_iterator) finden Sie ein Beispiel für das Deklarieren und Verwenden von `ostream_type`.

## <a name="traits_type"></a> ostream_iterator::traits_type

Ein Typ, der für den Zeichenmerkmaltyp des Iterators bereitgestellt wird.

```cpp
typedef Traits traits_type;
```

### <a name="remarks"></a>Hinweise

Der Type stellt ein Synonym für den Vorlagenparameter `Traits` dar.

### <a name="example"></a>Beispiel

```cpp
// ostream_iterator_traits_type.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   // The following not OK, but are just the default values:
   typedef ostream_iterator<int>::char_type CHT1;
   typedef ostream_iterator<int>::traits_type CHTR1;

   // ostream_iterator for stream cout
   // with new line delimiter:
    ostream_iterator<int, CHT1, CHTR1> intOut ( cout , "\n" );

   // Standard iterator interface for writing
   // elements to the output stream:
   cout << "The integers written to output stream\n"
        << "by intOut are:" << endl;
 *intOut = 1;
 *intOut = 10;
 *intOut = 100;
}
\* Output:
The integers written to output stream
by intOut are:
1
10
100
*\
```

## <a name="see-also"></a>Siehe auch

[\<iterator>](../standard-library/iterator.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)<br/>
