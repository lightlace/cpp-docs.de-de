---
title: '&lt;deque&gt;-Operatoren | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- deque/std::operator!=
- deque/std::operator&gt;
- deque/std::operator&gt;=
- deque/std::operator&lt;
- deque/std::operator&lt;=
- deque/std::operator==
dev_langs:
- C++
ms.assetid: 482d7c92-54c7-493b-99e6-2a73617481a5
helpviewer_keywords:
- std::operator!= (deque)
- std::operator&gt; (deque)
- std::operator&gt;= (deque)
- std::operator&lt; (deque)
- std::operator&lt;= (deque)
- std::operator== (deque)
ms.openlocfilehash: 21fdf5e624634a29d8ed32e004e7fb0d653b86f1
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38955214"
---
# <a name="ltdequegt-operators"></a>&lt;deque&gt;-Operatoren

||||
|-|-|-|
|[operator!=](#op_neq)|[operator&gt;](#op_gt)|[operator&gt;=](#op_gt_eq)|
|[operator&lt;](#op_lt)|[operator&lt;=](#op_lt_eq)|[operator==](#op_eq_eq)|

## <a name="op_neq"></a> operator!=

Überprüft, ob das deque-Objekt links vom Operator ungleich dem deque-Objekt rechts vom Operator ist.

```cpp
bool operator!=(const deque<Type, Allocator>& left, const deque<Type, Allocator>& right);
```

### <a name="parameters"></a>Parameter

*linken* ein Objekt des Typs `deque`.

*richtige* ein Objekt des Typs `deque`.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn die deque-Objekte nicht gleich sind; **FALSE**, wenn die deque-Objekte gleich sind.

### <a name="remarks"></a>Hinweise

Der Vergleich zwischen den deque-Objekten basiert auf einem paarweisen Vergleich der entsprechenden Elemente. Zwei deque-Objekte sind gleich, wenn sie über die gleiche Anzahl von Elementen verfügen und die entsprechenden Elemente dieselben Werte aufweisen. Andernfalls sind sie ungleich.

### <a name="example"></a>Beispiel

```cpp
// deque_op_ne.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1, c2;

   c1.push_back( 1 );
   c2.push_back( 2 );

   if ( c1 != c2 )
      cout << "The deques are not equal." << endl;
   else
      cout << "The deques are equal." << endl;
}
\* Output:
The deques are not equal.
*\
```

## <a name="op_lt"></a> operator&lt;

Überprüft, ob das deque-Objekt links vom Operator kleiner als das deque-Objekt rechts vom Operator ist.

```cpp
bool operator<(const deque<Type, Allocator>& left, const deque<Type, Allocator>& right);
```

### <a name="parameters"></a>Parameter

*linken* ein Objekt des Typs `deque`.

*richtige* ein Objekt des Typs `deque`.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn die Doppelschlange links vom Operator kleiner als, aber ungleich der Doppelschlange rechts vom Operator ist; andernfalls **FALSE**.

### <a name="remarks"></a>Hinweise

Der Vergleich zwischen den deque-Objekten basiert auf einem paarweisen Vergleich der entsprechenden Elemente. Die Beziehung "kleiner als" zwischen zwei Objekten basiert auf einem Vergleich des ersten Paares mit ungleichen Elementen.

### <a name="example"></a>Beispiel

```cpp
// deque_op_lt.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1, c2;

   c1.push_back( 1 );
   c1.push_back( 2 );
   c1.push_back( 4 );

   c2.push_back( 1 );
   c2.push_back( 3 );

   if ( c1 < c2 )
      cout << "Deque c1 is less than deque c2." << endl;
   else
      cout << "Deque c1 is not less than deque c2." << endl;
}
\* Output:
Deque c1 is less than deque c2.
*\
```

## <a name="op_lt_eq"></a> operator&lt;=

Überprüft, ob das deque-Objekt links vom Operator kleiner gleich dem deque-Objekt rechts vom Operator ist.

```cpp
bool operator<=(const deque<Type, Allocator>& left, const deque<Type, Allocator>& right);
```

### <a name="parameters"></a>Parameter

*linken* ein Objekt des Typs `deque`.

*richtige* ein Objekt des Typs `deque`.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn die Doppelschlange links vom Operator kleiner als oder gleich der Doppelschlange rechts vom Operator ist; andernfalls **FALSE**.

### <a name="remarks"></a>Hinweise

Der Vergleich zwischen den deque-Objekten basiert auf einem paarweisen Vergleich der entsprechenden Elemente. Die Beziehung "kleiner als oder gleich" zwischen zwei Objekten basiert auf einem Vergleich des ersten Paares mit ungleichen Elementen.

### <a name="example"></a>Beispiel

```cpp
// deque_op_le.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1, c2;

   c1.push_back( 1 );
   c1.push_back( 2 );
   c1.push_back( 4 );

   c2.push_back( 1 );
   c2.push_back( 3 );

   if ( c1 <= c2 )
      cout << "Deque c1 is less than or equal to deque c2." << endl;
   else
      cout << "Deque c1 is greater than deque c2." << endl;
}
\* Output:
Deque c1 is less than or equal to deque c2.
*\

```

## <a name="op_eq_eq"></a> operator==

Überprüft, ob das deque-Objekt links vom Operator gleich dem deque-Objekt rechts vom Operator ist.

```cpp
bool operator==(const deque<Type, Allocator>& left, const deque<Type, Allocator>& right);
```

### <a name="parameters"></a>Parameter

*linken* ein Objekt des Typs `deque`.

*richtige* ein Objekt des Typs `deque`.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn die Doppelschlange links vom Operator gleich der Doppelschlange rechts vom Operator ist; andernfalls **FALSE**.

### <a name="remarks"></a>Hinweise

Der Vergleich zwischen den deque-Objekten basiert auf einem paarweisen Vergleich der entsprechenden Elemente. Zwei Doppelschlangen sind gleich, wenn sie über die gleiche Anzahl von Elementen verfügen und die entsprechenden Elemente dieselben Werte aufweisen. Andernfalls sind sie ungleich.

### <a name="example"></a>Beispiel

```cpp
// deque_op_eq.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1, c2;

   c1.push_back( 1 );
   c2.push_back( 1 );

   if ( c1 == c2 )
      cout << "The deques are equal." << endl;
   else
      cout << "The deques are not equal." << endl;

   c1.push_back( 1 );
   if ( c1 == c2 )
      cout << "The deques are equal." << endl;
   else
      cout << "The deques are not equal." << endl;
}
\* Output:
The deques are equal.
The deques are not equal.
*\

```

## <a name="op_gt"></a> operator&gt;

Überprüft, ob das deque-Objekt links vom Operator größer als das deque-Objekt rechts vom Operator ist.

```cpp
bool operator>(const deque<Type, Allocator>& left, const deque<Type, Allocator>& right);
```

### <a name="parameters"></a>Parameter

*linken* ein Objekt des Typs `deque`.

*richtige* ein Objekt des Typs `deque`.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn die Doppelschlange links vom Operator größer als die Doppelschlange rechts vom Operator ist; andernfalls **FALSE**.

### <a name="remarks"></a>Hinweise

Der Vergleich zwischen den deque-Objekten basiert auf einem paarweisen Vergleich der entsprechenden Elemente. Die Beziehung "größer als" zwischen zwei Objekten basiert auf einem Vergleich des ersten Paares mit ungleichen Elementen.

### <a name="example"></a>Beispiel

```cpp
// deque_op_gt.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1, c2;

   c1.push_back( 1 );
   c1.push_back( 3 );
   c1.push_back( 1 );

   c2.push_back( 1 );
   c2.push_back( 2 );
   c2.push_back( 2 );

   if ( c1 > c2 )
      cout << "Deque c1 is greater than deque c2." << endl;
   else
      cout << "Deque c1 is not greater than deque c2." << endl;
}
\* Output:
Deque c1 is greater than deque c2.
*\

```

## <a name="op_gt_eq"></a> operator&gt;=

Überprüft, ob das deque-Objekt links vom Operator größer gleich dem deque-Objekt rechts vom Operator ist.

```cpp
bool operator>=(const deque<Type, Allocator>& left, const deque<Type, Allocator>& right);
```

### <a name="parameters"></a>Parameter

*linken* ein Objekt des Typs `deque`.

*richtige* ein Objekt des Typs `deque`.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn die Doppelschlange links vom Operator größer als oder gleich der Doppelschlange rechts vom Operator ist; andernfalls **FALSE**.

### <a name="remarks"></a>Hinweise

Der Vergleich zwischen den deque-Objekten basiert auf einem paarweisen Vergleich der entsprechenden Elemente. Die Beziehung "größer als oder gleich" zwischen zwei Objekten basiert auf einem Vergleich des ersten Paares mit ungleichen Elementen.

### <a name="example"></a>Beispiel

```cpp
// deque_op_ge.cpp
// compile with: /EHsc
#include <deque>
#include <iostream>

int main( )
{
   using namespace std;
   deque <int> c1, c2;

   c1.push_back( 1 );
   c1.push_back( 3 );
   c1.push_back( 1 );

   c2.push_back( 1 );
   c2.push_back( 2 );
   c2.push_back( 2 );

   if ( c1 >= c2 )
      cout << "Deque c1 is greater than or equal to deque c2." << endl;
   else
      cout << "Deque c1 is less than deque c2." << endl;
}
\* Output:
Deque c1 is greater than or equal to deque c2.
*\
```

## <a name="see-also"></a>Siehe auch

[\<deque>](../standard-library/deque.md)<br/>
