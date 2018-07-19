---
title: '&lt;list&gt;-Operatoren | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- list/std::operator!=
- list/std::operator&gt;
- list/std::operator&gt;=
- list/std::operator&lt;
- list/std::operator&lt;=
- list/std::operator==
dev_langs:
- C++
ms.assetid: 8103d8f2-c30f-49ad-ac50-b3ba6a907ebe
helpviewer_keywords:
- std::operator!= (list)
- std::operator&gt; (list)
- std::operator&gt;= (list)
- std::operator&lt; (list)
- std::operator&lt;= (list)
- std::operator== (list)
ms.openlocfilehash: ba77722abb28f246d305b44fb78379b2297ccc14
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38965716"
---
# <a name="ltlistgt-operators"></a>&lt;list&gt;-Operatoren

||||
|-|-|-|
|[operator!=](#op_neq)|[operator&gt;](#op_gt)|[operator&gt;=](#op_gt_eq)|
|[operator&lt;](#op_lt)|[operator&lt;=](#op_lt_eq)|[operator==](#op_eq_eq)|

## <a name="op_neq"></a> operator!=

Testet, ob das Listenobjekt links vom Operator ungleich dem Listenobjekt rechts vom Operator ist.

```cpp
bool operator!=(
    const list<Type, Allocator>& left,
    const list<Type, Allocator>& right);
```

### <a name="parameters"></a>Parameter

*linken* ein Objekt des Typs `list`.

*richtige* ein Objekt des Typs `list`.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn die Listen ungleich sind; **FALSE**, wenn die Listen gleich sind.

### <a name="remarks"></a>Hinweise

Der Vergleich zwischen den Listenobjekten basiert auf einem paarweisen Vergleich der entsprechenden Elemente. Zwei Listen sind gleich, wenn sie über die gleiche Anzahl von Elementen verfügen und die entsprechenden Elemente dieselben Werte aufweisen. Andernfalls sind sie ungleich.

### <a name="example"></a>Beispiel

```cpp
// list_op_ne.cpp
// compile with: /EHsc
#include <list>
#include <iostream>

int main( )
{
using namespace std;
list <int> c1, c2;
c1.push_back( 1 );
c2.push_back( 2 );

if ( c1 != c2 )
cout << "Lists not equal." << endl;
else
cout << "Lists equal." << endl;
}
\* Output:
Lists not equal.
*\
```

## <a name="op_lt"></a> operator&lt;

Testet, ob das Listenobjekt links vom Operator kleiner als das Listenobjekt auf der rechten Seite ist.

```cpp
bool operator<(
    const list<Type, Allocator>& left,
    const list<Type, Allocator>& right);
```

### <a name="parameters"></a>Parameter

*linken* ein Objekt des Typs `list`.

*richtige* ein Objekt des Typs `list`.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn die Liste links vom Operator kleiner als, aber ungleich der Liste rechts vom Operator ist; andernfalls **FALSE**.

### <a name="remarks"></a>Hinweise

Der Vergleich zwischen den Listenobjekten basiert auf einem paarweisen Vergleich der entsprechenden Elemente. Die Beziehung "kleiner als" zwischen zwei Objekten basiert auf einem Vergleich des ersten Paares mit ungleichen Elementen.

### <a name="example"></a>Beispiel

```cpp
// list_op_lt.cpp
// compile with: /EHsc
#include <list>
#include <iostream>

int main( )
{
   using namespace std;
   list <int> c1, c2;
   c1.push_back( 1 );
   c1.push_back( 2 );
   c1.push_back( 4 );

   c2.push_back( 1 );
   c2.push_back( 3 );

   if ( c1 < c2 )
      cout << "List c1 is less than list c2." << endl;
   else
      cout << "List c1 is not less than list c2." << endl;
}
\* Output:
List c1 is less than list c2.
*\
```

## <a name="op_lt_eq"></a> operator&lt;=

Testet, ob das Listenobjekt links vom Operator kleiner als oder gleich dem Listenobjekt rechts vom Operator ist.

```cpp
bool operator<=(
    const list<Type, Allocator>& left,
    const list<Type, Allocator>& right);
```

### <a name="parameters"></a>Parameter

*linken* ein Objekt des Typs `list`.

*richtige* ein Objekt des Typs `list`.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn die Liste links vom Operator kleiner als oder gleich der Liste rechts vom Operator ist; andernfalls **FALSE**.

### <a name="remarks"></a>Hinweise

Der Vergleich zwischen den Listenobjekten basiert auf einem paarweisen Vergleich der entsprechenden Elemente. Die Beziehung "kleiner als oder gleich" zwischen zwei Objekten basiert auf einem Vergleich des ersten Paares mit ungleichen Elementen.

### <a name="example"></a>Beispiel

```cpp
// list_op_le.cpp
// compile with: /EHsc
#include <list>
#include <iostream>

int main( )
{
   using namespace std;
   list <int> c1, c2;
   c1.push_back( 1 );
   c1.push_back( 2 );
   c1.push_back( 4 );

   c2.push_back( 1 );
   c2.push_back( 3 );

   if ( c1 <= c2 )
      cout << "List c1 is less than or equal to list c2." << endl;
   else
      cout << "List c1 is greater than list c2." << endl;
}
\* Output:
List c1 is less than or equal to list c2.
*\
```

## <a name="op_eq_eq"></a> operator==

Testet, ob das Listenobjekt links vom Operator gleich dem Listenobjekt rechts vom Operator ist.

```cpp
bool operator==(
    const list<Type, Allocator>& left,
    const list<Type, Allocator>& right);
```

### <a name="parameters"></a>Parameter

*linken* ein Objekt des Typs `list`.

*richtige* ein Objekt des Typs `list`.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn die Liste links vom Operator gleich der Liste rechts vom Operator ist; andernfalls **FALSE**.

### <a name="remarks"></a>Hinweise

Der Vergleich zwischen den Listenobjekten basiert auf einem paarweisen Vergleich der entsprechenden Elemente. Zwei Listen sind gleich, wenn sie über die gleiche Anzahl von Elementen verfügen und die entsprechenden Elemente dieselben Werte aufweisen. Andernfalls sind sie ungleich.

### <a name="example"></a>Beispiel

```cpp
// list_op_eq.cpp
// compile with: /EHsc
#include <list>
#include <iostream>
int main( )
{
   using namespace std;

   list <int> c1, c2;
   c1.push_back( 1 );
   c2.push_back( 1 );

   if ( c1 == c2 )
      cout << "The lists are equal." << endl;
   else
      cout << "The lists are not equal." << endl;
}
\* Output:
The lists are equal.
*\
```

## <a name="op_gt"></a> operator&gt;

Testet, ob das Listenobjekt links vom Operator größer als das Listenobjekt auf der rechten Seite ist.

```cpp
bool operator>(
    const list<Type, Allocator>& left,
    const list<Type, Allocator>& right);
```

### <a name="parameters"></a>Parameter

*linken* ein Objekt des Typs `list`.

*richtige* ein Objekt des Typs `list`.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn die Liste links vom Operator größer als die Liste rechts vom Operator ist; andernfalls **FALSE**.

### <a name="remarks"></a>Hinweise

Der Vergleich zwischen den Listenobjekten basiert auf einem paarweisen Vergleich der entsprechenden Elemente. Die Beziehung "größer als" zwischen zwei Objekten basiert auf einem Vergleich des ersten Paares mit ungleichen Elementen.

### <a name="example"></a>Beispiel

```cpp
// list_op_gt.cpp
// compile with: /EHsc
#include <list>
#include <iostream>
int main( )
{
   using namespace std;
   list <int> c1, c2;
   c1.push_back( 1 );
   c1.push_back( 3 );
   c1.push_back( 1 );

   c2.push_back( 1 );
   c2.push_back( 2 );
   c2.push_back( 2 );

   if ( c1 > c2 )
      cout << "List c1 is greater than list c2." << endl;
   else
      cout << "List c1 is not greater than list c2." << endl;
}
\* Output:
List c1 is greater than list c2.
*\
```

## <a name="op_gt_eq"></a> operator&gt;=

Testet, ob das Listenobjekt links vom Operator größer als oder gleich dem Listenobjekt rechts vom Operator ist.

```cpp
bool operator>=(
    const list<Type, Allocator>& left,
    const list<Type, Allocator>& right);
```

### <a name="parameters"></a>Parameter

*linken* ein Objekt des Typs `list`.

*richtige* ein Objekt des Typs `list`.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn die Liste links vom Operator größer als oder gleich der Liste rechts vom Operator ist; andernfalls **FALSE**.

### <a name="remarks"></a>Hinweise

Der Vergleich zwischen den Listenobjekten basiert auf einem paarweisen Vergleich der entsprechenden Elemente. Die Beziehung "größer als oder gleich" zwischen zwei Objekten basiert auf einem Vergleich des ersten Paares mit ungleichen Elementen.

### <a name="example"></a>Beispiel

```cpp
// list_op_ge.cpp
// compile with: /EHsc
#include <list>
#include <iostream>

int main( )
{
   using namespace std;
   list <int> c1, c2;
   c1.push_back( 1 );
   c1.push_back( 3 );
   c1.push_back( 1 );

   c2.push_back( 1 );
   c2.push_back( 2 );
   c2.push_back( 2 );

   if ( c1 >= c2 )
      cout << "List c1 is greater than or equal to list c2." << endl;
   else
      cout << "List c1 is less than list c2." << endl;
}
\* Output:
List c1 is greater than or equal to list c2.
*\
```

## <a name="see-also"></a>Siehe auch

[\<list>](../standard-library/list.md)<br/>
