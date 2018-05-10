---
title: '&lt;iterator&gt;-Operatoren | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- xutility/std::operator!=
- xutility/std::operator&gt;
- xutility/std::operator&gt;=
- xutility/std::operator&lt;
- xutility/std::operator&lt;=
- xutility/std::operator+
- xutility/std::operator-
- xutility/std::operator==
dev_langs:
- C++
ms.assetid: b7c664f0-49d4-4993-b5d1-9ac4859fdddc
helpviewer_keywords:
- std::operator!= (iterator)
- std::operator&gt; (iterator)
- std::operator&gt;= (iterator)
- std::operator&lt; (iterator)
- std::operator&lt;= (iterator), std::operator== (iterator)
ms.openlocfilehash: 411fcf8969ba13c4f50360c3db151f0801fd5a28
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="ltiteratorgt-operators"></a>&lt;iterator&gt;-Operatoren

||||
|-|-|-|
|[operator!=](#op_neq)|[operator&gt;](#op_gt)|[operator&gt;=](#op_gt_eq)|
|[operator&lt;](#op_lt)|[operator&lt;=](#op_lt_eq)|[operator+](#op_add)|
|[operator-](#operator-)|[operator==](#op_eq_eq)|

## <a name="op_neq"></a> operator!=

Testet, ob das Iterator-Objekt links vom Operator ungleich dem Iterator-Objekt rechts vom Operator ist.

```cpp
template <class RandomIterator>
bool operator!=(const reverse_iterator<RandomIterator>& left, const reverse_iterator<RandomIterator>& right);

template <class Type, class CharType, class Traits, class Distance>
bool operator!=(const istream_iterator<Type, CharType, Traits, Distance>& left, const istream_iterator<Type, CharType, Traits, Distance>& right);

template <class CharType, class Tr>
bool operator!=(const istreambuf_iterator<CharType, Traits>& left, const istreambuf_iterator<CharType, Traits>& right);
```

### <a name="parameters"></a>Parameter

`left` Ein Objekt des Typs **Iterator**.

`right` Ein Objekt des Typs **Iterator**.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn die Iterator-Objekte gleich sind; **FALSE**, wenn die Iterator-Objekte nicht gleich sind.

### <a name="remarks"></a>Hinweise

Ein Iterator-Objekt entspricht einem anderen, wenn sie sich auf dieselben Elemente in einem Container beziehen. Wenn zwei Iteratoren auf verschiedene Elemente in einem Container zeigen, sind sie nicht gleich.

### <a name="example"></a>Beispiel

```cpp
// iterator_op_ne.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for ( i = 1 ; i < 9 ; ++i )
   {
      vec.push_back ( i );
   }

   vector <int>::iterator vIter;

   cout << "The vector vec is: ( ";
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++ )
      cout << *vIter << " ";
   cout << ")." << endl;

   // Initializing reverse_iterators to the last element
   vector <int>::reverse_iterator rVPOS1 = vec.rbegin ( ),
           rVPOS2 = vec.rbegin ( );

   cout << "The iterator rVPOS1 initially points to the first "
        << "element\n in the reversed sequence: "
        << *rVPOS1 << "." << endl;

   if ( rVPOS1 != rVPOS2 )
      cout << "The iterators are not equal." << endl;
   else
      cout << "The iterators are equal." << endl;

   rVPOS1++;
   cout << "The iterator rVPOS1 now points to the second "
        << "element\n in the reversed sequence: "
        << *rVPOS1 << "." << endl;

   if ( rVPOS1 != rVPOS2 )
      cout << "The iterators are not equal." << endl;
   else
      cout << "The iterators are equal." << endl;
}
```

```Output
The vector vec is: ( 1 2 3 4 5 6 7 8 ).
The iterator rVPOS1 initially points to the first element
 in the reversed sequence: 8.
The iterators are equal.
The iterator rVPOS1 now points to the second element
 in the reversed sequence: 7.
The iterators are not equal.
```

## <a name="op_eq_eq"></a> operator==

Testet, ob das Iterator-Objekt links vom Operator gleich dem Iterator-Objekt rechts vom Operator ist.

```cpp
template <class RandomIterator1, class RandomIterator2>
bool operator==(
    const move_iterator<RandomIterator1>& left,
    const move_iterator<RandomIterator2>& right);

template <class RandomIterator1, class RandomIterator2>
bool operator==(
    const reverse_iterator<RandomIterator1>& left,
    const reverse_iterator<RandomIterator2>& right);

template <class Type, class CharType, class Traits, class Distance>
bool operator==(
    const istream_iterator<Type, CharType, Traits, Distance>& left,
    const istream_iterator<Type, CharType, Traits, Distance>& right);

template <class CharType, class Tr>
bool operator==(
    const istreambuf_iterator<CharType, Traits>& left,
    const istreambuf_iterator<CharType, Traits>& right);
```

### <a name="parameters"></a>Parameter

`left` Ein Objekt des Typs Iterator.

`right` Ein Objekt des Typs Iterator.

### <a name="return-value"></a>Rückgabewert

`true`, wenn die Iterator-Objekte gleich sind; `false`, wenn die Iterator-Objekte nicht gleich sind.

### <a name="remarks"></a>Hinweise

Ein Iterator-Objekt entspricht einem anderen, wenn sie sich auf dieselben Elemente in einem Container beziehen. Wenn zwei Iteratoren auf verschiedene Elemente in einem Container zeigen, sind sie nicht gleich.

Die ersten zwei Vorlagenoperatoren geben nur TRUE zurück, wenn sowohl `left` als auch `right` den gleichen Iterator speichern. Der dritte Vorlagenoperator gibt TRUE nur zurück, wenn sowohl `left` als auch `right` den gleichen Streamzeiger speichern. Der vierte Vorlagenoperator gibt ` left.equal ( right)` zurück.

### <a name="example"></a>Beispiel

```cpp
// iterator_op_eq.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for ( i = 1 ; i < 6 ; ++i )
   {
      vec.push_back ( 2 * i );
   }

   vector <int>::iterator vIter;

   cout << "The vector vec is: ( ";
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)
      cout << *vIter << " ";
   cout << ")." << endl;

   // Initializing reverse_iterators to the last element
   vector <int>::reverse_iterator rVPOS1 = vec.rbegin ( ),
           rVPOS2 = vec.rbegin ( );

   cout << "The iterator rVPOS1 initially points to the first "
        << "element\n in the reversed sequence: "
        << *rVPOS1 << "." << endl;

   if ( rVPOS1 == rVPOS2 )
      cout << "The iterators are equal." << endl;
   else
      cout << "The iterators are not equal." << endl;

   rVPOS1++;
   cout << "The iterator rVPOS1 now points to the second "
        << "element\n in the reversed sequence: "
        << *rVPOS1 << "." << endl;

   if ( rVPOS1 == rVPOS2 )
      cout << "The iterators are equal." << endl;
   else
      cout << "The iterators are not equal." << endl;
}
```

```Output
The vector vec is: ( 2 4 6 8 10 ).
The iterator rVPOS1 initially points to the first element
 in the reversed sequence: 10.
The iterators are equal.
The iterator rVPOS1 now points to the second element
 in the reversed sequence: 8.
The iterators are not equal.
```

## <a name="op_lt"></a> operator&lt;

Testet, ob das Iterator-Objekt links vom Operator kleiner ist als das Iterator-Objekt rechts vom Operator.

```cpp
template <class RandomIterator>
bool operator<(const reverse_iterator<RandomIterator>& left, const reverse_iterator<RandomIterator>& right);
```

### <a name="parameters"></a>Parameter

`left` Ein Objekt des Typs **Iterator**.

`right` Ein Objekt des Typs **Iterator**.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn der Iterator auf der linken Seite des Ausdrucks kleiner als der Iterator auf der rechten Seite des Ausdrucks ist; **FALSE**, wenn er größer als oder gleich dem Iterator auf der rechten Seite ist.

### <a name="remarks"></a>Hinweise

Ein Iterator-Objekt ist kleiner als ein anderes, wenn es sich auf ein Element bezieht, das früher im Container auftritt, als das Element, das vom anderen Iterator-Objekt adressiert wurde. Ein Iterator-Objekt ist nicht kleiner als ein anderes, wenn es sich entweder auf das gleiche Element wie das andere Iterator-Objekt bezieht, oder auf ein Element, das später im Container auftritt, als das Element, das vom anderen Iterator-Objekt adressiert wurde.

### <a name="example"></a>Beispiel

```cpp
// iterator_op_lt.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for ( i = 0 ; i < 6 ; ++i )
   {
      vec.push_back ( 2 * i );
   }

   vector <int>::iterator vIter;

   cout << "The initial vector vec is: ( ";
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)
      cout << *vIter << " ";
   cout << ")." << endl;

   // Initializing reverse_iterators to the last element
   vector <int>::reverse_iterator rVPOS1 = vec.rbegin ( ),
           rVPOS2 = vec.rbegin ( );

   cout << "The iterators rVPOS1& rVPOS2 initially point to the "
           << "first element\n in the reversed sequence: "
           << *rVPOS1 << "." << endl;

   if ( rVPOS1 < rVPOS2 )
      cout << "The iterator rVPOS1 is less than"
              << " the iterator rVPOS2." << endl;
   else
      cout << "The iterator rVPOS1 is not less than"
              << " the iterator rVPOS2." << endl;

   rVPOS2++;
   cout << "The iterator rVPOS2 now points to the second "
           << "element\n in the reversed sequence: "
           << *rVPOS2 << "." << endl;

   if ( rVPOS1 < rVPOS2 )
      cout << "The iterator rVPOS1 is less than"
              << " the iterator rVPOS2." << endl;
   else
      cout << "The iterator rVPOS1 is not less than"
              << " the iterator rVPOS2." << endl;
}
```

```Output
The initial vector vec is: ( 0 2 4 6 8 10 ).
The iterators rVPOS1& rVPOS2 initially point to the first element
 in the reversed sequence: 10.
The iterator rVPOS1 is not less than the iterator rVPOS2.
The iterator rVPOS2 now points to the second element
 in the reversed sequence: 8.
The iterator rVPOS1 is less than the iterator rVPOS2.
```

## <a name="op_lt_eq"></a> operator&lt;=

Testet, ob das Iterator-Objekt links vom Operator kleiner als oder gleich dem Iterator-Objekt rechts vom Operator ist.

```cpp
template <class RandomIterator>
bool operator<=(const reverse_iterator<RandomIterator>& left, const reverse_iterator<RandomIterator>& right);
```

### <a name="parameters"></a>Parameter

`left` Ein Objekt des Typs Iterator.

`right` Ein Objekt des Typs Iterator.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn der Iterator auf der linken Seite des Ausdrucks kleiner als oder gleich dem Iterator auf der rechten Seite des Ausdrucks ist; **FALSE**, wenn er größer als der Iterator auf der rechten Seite ist.

### <a name="remarks"></a>Hinweise

Ein Iterator-Objekt ist kleiner als oder gleich einem anderen, wenn es sich auf das gleiche Element oder ein Element bezieht, das früher im Container auftritt, als das Element, das vom anderen Iterator-Objekt adressiert wurde. Ein Iterator-Objekt ist größer als ein anderes, wenn es sich auf ein Element bezieht, das später im Container auftritt, als das Element, das vom anderen Iterator-Objekt adressiert wurde.

### <a name="example"></a>Beispiel

```cpp
// iterator_op_le.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for (i = 0 ; i < 6 ; ++i )  {
      vec.push_back ( 2 * i );
      }

   vector <int>::iterator vIter;

   cout << "The initial vector vec is: ( ";
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)
      cout << *vIter << " ";
   cout << ")." << endl;

   vector <int>::reverse_iterator rVPOS1 = vec.rbegin ( ) + 1,
           rVPOS2 = vec.rbegin ( );

   cout << "The iterator rVPOS1 initially points to the "
           << "second element\n in the reversed sequence: "
           << *rVPOS1 << "." << endl;

   cout << "The iterator rVPOS2 initially points to the "
           << "first element\n in the reversed sequence: "
           << *rVPOS2 << "." << endl;

   if ( rVPOS1 <= rVPOS2 )
      cout << "The iterator rVPOS1 is less than or "
              << "equal to the iterator rVPOS2." << endl;
   else
      cout << "The iterator rVPOS1 is greater than "
              << "the iterator rVPOS2." << endl;

   rVPOS2++;
   cout << "The iterator rVPOS2 now points to the second "
           << "element\n in the reversed sequence: "
           << *rVPOS2 << "." << endl;

   if ( rVPOS1 <= rVPOS2 )
      cout << "The iterator rVPOS1 is less than or "
              << "equal to the iterator rVPOS2." << endl;
   else
      cout << "The iterator rVPOS1 is greater than "
              << "the iterator rVPOS2." << endl;
}
```

```Output
The initial vector vec is: ( 0 2 4 6 8 10 ).
The iterator rVPOS1 initially points to the second element
 in the reversed sequence: 8.
The iterator rVPOS2 initially points to the first element
 in the reversed sequence: 10.
The iterator rVPOS1 is greater than the iterator rVPOS2.
The iterator rVPOS2 now points to the second element
 in the reversed sequence: 8.
The iterator rVPOS1 is less than or equal to the iterator rVPOS2.
```

## <a name="op_gt"></a> operator&gt;

Testet, ob das Iterator-Objekt links vom Operator größer als das Iterator-Objekt rechts vom Operator ist.

```cpp
template <class RandomIterator>
bool operator>(const reverse_iterator<RandomIterator>& left, const reverse_iterator<RandomIterator>& right);
```

### <a name="parameters"></a>Parameter

`left` Ein Objekt des Typs Iterator.

`right` Ein Objekt des Typs Iterator.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn der Iterator auf der linken Seite des Ausdrucks größer ist als der Iterator auf der rechten Seite des Ausdrucks ist; **FALSE**, wenn er kleiner als oder gleich dem Iterator auf der rechten Seite ist.

### <a name="remarks"></a>Hinweise

Ein Iterator-Objekt ist größer als ein anderes, wenn es sich auf ein Element bezieht, das später im Container auftritt, als das Element, das vom anderen Iterator-Objekt adressiert wurde. Ein Iterator-Objekt ist nicht größer als ein anderes, wenn es sich entweder auf das gleiche Element bezieht, wie das andere Iterator-Objekt, oder ein Element, das früher im Container auftritt, als das Element, das vom anderen Iterator-Objekt adressiert wurde.

### <a name="example"></a>Beispiel

```cpp
// iterator_op_gt.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for (i = 0 ; i < 6 ; ++i )  {
      vec.push_back ( 2 * i );
      }

   vector <int>::iterator vIter;

   cout << "The initial vector vec is: ( ";
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)
      cout << *vIter << " ";
   cout << ")." << endl;

   vector <int>::reverse_iterator rVPOS1 = vec.rbegin ( ),
           rVPOS2 = vec.rbegin ( );

   cout << "The iterators rVPOS1 & rVPOS2 initially point to "
           << "the first element\n in the reversed sequence: "
           << *rVPOS1 << "." << endl;

   if ( rVPOS1 > rVPOS2 )
      cout << "The iterator rVPOS1 is greater than "
              << "the iterator rVPOS2." << endl;
   else
      cout << "The iterator rVPOS1 is less than or "
              << "equal to the iterator rVPOS2." << endl;

   rVPOS1++;
   cout << "The iterator rVPOS1 now points to the second "
           << "element\n in the reversed sequence: "
           << *rVPOS1 << "." << endl;

   if ( rVPOS1 > rVPOS2 )
      cout << "The iterator rVPOS1 is greater than "
              << "the iterator rVPOS2." << endl;
   else
      cout << "The iterator rVPOS1 is less than or "
              << "equal to the iterator rVPOS2." << endl;
}
```

```Output
The initial vector vec is: ( 0 2 4 6 8 10 ).
The iterators rVPOS1 & rVPOS2 initially point to the first element
 in the reversed sequence: 10.
The iterator rVPOS1 is less than or equal to the iterator rVPOS2.
The iterator rVPOS1 now points to the second element
 in the reversed sequence: 8.
The iterator rVPOS1 is greater than the iterator rVPOS2.
```

## <a name="op_gt_eq"></a> operator&gt;=

Testet, ob das Iterator-Objekt links vom Operator größer als oder gleich dem Iterator-Objekt rechts vom Operator ist.

```cpp
template <class RandomIterator>
bool operator>=(const reverse_iterator<RandomIterator>& left, const reverse_iterator<RandomIterator>& right);
```

### <a name="parameters"></a>Parameter

`left` Ein Objekt des Typs Iterator.

`right` Ein Objekt des Typs Iterator.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn der Iterator auf der linken Seite des Ausdrucks größer als oder gleich dem Iterator auf der rechten Seite des Ausdrucks ist; **FALSE**, wenn er kleiner als der Iterator auf der rechten Seite ist.

### <a name="remarks"></a>Hinweise

Ein Iterator-Objekt ist größer als oder gleich einem anderen, wenn es sich auf das gleiche Element oder ein Element bezieht, das später im Container auftritt, als das Element, das vom anderen Iterator-Objekt adressiert wurde. Ein Iterator-Objekt ist kleiner als ein anderes, wenn es sich auf ein Element bezieht, das früher im Container auftritt, als das Element, das vom anderen Iterator-Objekt adressiert wurde.

### <a name="example"></a>Beispiel

```cpp
// iterator_op_ge.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for (i = 0 ; i < 6 ; ++i )  {
      vec.push_back ( 2 * i );
      }

   vector <int>::iterator vIter;

   cout << "The initial vector vec is: ( ";
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)
      cout << *vIter << " ";
   cout << ")." << endl;

   vector <int>::reverse_iterator rVPOS1 = vec.rbegin ( ),
           rVPOS2 = vec.rbegin ( ) + 1;

   cout << "The iterator rVPOS1 initially points to the "
           << "first element\n in the reversed sequence: "
           << *rVPOS1 << "." << endl;

   cout << "The iterator rVPOS2 initially points to the "
           << "second element\n in the reversed sequence: "
           << *rVPOS2 << "." << endl;

   if ( rVPOS1 >= rVPOS2 )
      cout << "The iterator rVPOS1 is greater than or "
              << "equal to the iterator rVPOS2." << endl;
   else
      cout << "The iterator rVPOS1 is less than "
              << "the iterator rVPOS2." << endl;

   rVPOS1++;
   cout << "The iterator rVPOS1 now points to the second "
           << "element\n in the reversed sequence: "
           << *rVPOS1 << "." << endl;

   if ( rVPOS1 >= rVPOS2 )
      cout << "The iterator rVPOS1 is greater than or "
              << "equal to the iterator rVPOS2." << endl;
   else
      cout << "The iterator rVPOS1 is less than "
              << "the iterator rVPOS2." << endl;
}
```

```Output
The initial vector vec is: ( 0 2 4 6 8 10 ).
The iterator rVPOS1 initially points to the first element
 in the reversed sequence: 10.
The iterator rVPOS2 initially points to the second element
 in the reversed sequence: 8.
The iterator rVPOS1 is less than the iterator rVPOS2.
The iterator rVPOS1 now points to the second element
 in the reversed sequence: 8.
The iterator rVPOS1 is greater than or equal to the iterator rVPOS2.
```

## <a name="op_add"></a> operator+

Fügt einen Offset zu einem Iterator hinzu und gibt `move_iterator` oder `reverse_iterator` zurück, das auf das eingefügte Element an der neuen Offsetposition zeigt.

```cpp
template <class RandomIterator, class Diff>
move_iterator<RandomIterator>
operator+(
    Diff _Off,
    const move_iterator<RandomIterator>& right);

template <class RandomIterator>
reverse_iterator<RandomIterator>
operator+(
    Diff _Off,
    const reverse_iterator<RandomIterator>& right);
```

### <a name="parameters"></a>Parameter

`_Off` Die Anzahl von Positionen, dass das Move_iterator-Konstante oder const Reverse_iterator besteht darin, versetzt werden.

`right` Der Iterator versetzt werden soll.

### <a name="return-value"></a>Rückgabewert

Gibt die Summe `right` + `_Off` zurück.

### <a name="example"></a>Beispiel

```cpp
// iterator_op_insert.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for (i = 0 ; i < 6 ; ++i )  {
      vec.push_back ( 2 * i );
      }

   vector <int>::iterator vIter;

   cout << "The initial vector vec is: ( ";
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)
      cout << *vIter << " ";
   cout << ")." << endl;

   vector <int>::reverse_iterator rVPOS1 = vec.rbegin ( );

   cout << "The iterator rVPOS1 initially points to "
           << "the first element\n in the reversed sequence: "
           << *rVPOS1 << "." << endl;

   vector<int>::difference_type diff = 4;
   rVPOS1 = diff +rVPOS1;

   cout << "The iterator rVPOS1 now points to the fifth "
           << "element\n in the reversed sequence: "
           << *rVPOS1 << "." << endl;
}
```

```Output
The initial vector vec is: ( 0 2 4 6 8 10 ).
The iterator rVPOS1 initially points to the first element
 in the reversed sequence: 10.
The iterator rVPOS1 now points to the fifth element
 in the reversed sequence: 2.
```

## <a name="operator-"></a> operator-

Subtrahiert einen Iterator von einem anderen und gibt die Differenz zurück.

```cpp
template <class RandomIterator1, class RandomIterator2>
Tdiff operator-(
    const move_iterator<RandomIterator1>& left,
    const move_iterator<RandomIterator2>& right);

template <class RandomIterator1, class RandomIterator2>
Tdiff operator-(
    const reverse_iterator<RandomIterator1>& left,
    const reverse_iterator<RandomIterator2>& right);
```

### <a name="parameters"></a>Parameter

`left` Ein Iterator.

`right` Ein Iterator.

### <a name="return-value"></a>Rückgabewert

Der Unterschied zwischen zwei Iteratoren `.`

### <a name="remarks"></a>Hinweise

Der erste Vorlagenoperator gibt `left.base() - right.base()` zurück.

Der zweite Vorlagenoperator gibt `right.current - left.current` zurück.

`Tdiff` wird durch den Typ des zurückgegebenen Ausdrucks bestimmt. Andernfalls ist der Wert `RandomIterator1::difference_type`.

### <a name="example"></a>Beispiel

```cpp
// iterator_op_sub.cpp
// compile with: /EHsc
#include <iterator>
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   vector<int> vec;
   for (i = 0 ; i < 6 ; ++i )
   {
      vec.push_back ( 2 * i );
   }

   vector <int>::iterator vIter;

   cout << "The initial vector vec is: ( ";
   for ( vIter = vec.begin( ) ; vIter != vec.end( ); vIter++)
      cout << *vIter << " ";
   cout << ")." << endl;

   vector <int>::reverse_iterator rVPOS1 = vec.rbegin ( ),
          rVPOS2 = vec.rbegin ( );

   cout << "The iterators rVPOS1 & rVPOS2 initially point to "
        << "the first element\n in the reversed sequence: "
        << *rVPOS1 << "." << endl;

   for (i = 1; i < 5; ++i)
   {
      rVPOS2++;
   }
   cout << "The iterator rVPOS2 now points to the fifth "
        << "element\n in the reversed sequence: "
        << *rVPOS2 << "." << endl;

   vector<int>::difference_type diff = rVPOS2 - rVPOS1;
   cout << "The difference: rVPOS2 - rVPOS1= "
        << diff << "." << endl;
}
```

```Output
The initial vector vec is: ( 0 2 4 6 8 10 ).
The iterators rVPOS1 & rVPOS2 initially point to the first element
 in the reversed sequence: 10.
The iterator rVPOS2 now points to the fifth element
 in the reversed sequence: 2.
The difference: rVPOS2 - rVPOS1= 4.
```

## <a name="see-also"></a>Siehe auch

[\<iterator>](../standard-library/iterator.md)<br/>
