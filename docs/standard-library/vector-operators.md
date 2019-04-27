---
title: '&lt;vector&gt;-Operatoren'
ms.date: 11/04/2016
f1_keywords:
- vector/std::operator!=
- vector/std::operator&gt;
- vector/std::operator&gt;=
- vector/std::operator&lt;
- vector/std::operator&lt;=
- vector/std::operator==
ms.assetid: 1d14f312-6f59-4ec7-88ae-95f89a558823
helpviewer_keywords:
- std::operator!= (vector)
- std::operator&gt; (vector)
- std::operator&gt;= (vector)
- std::operator&lt; (vector)
- std::operator&lt;= (vector)
- std::operator== (vector)
ms.openlocfilehash: f659f1291c4111d83cc8715fd0deb104a9685f4f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62185944"
---
# <a name="ltvectorgt-operators"></a>&lt;vector&gt;-Operatoren

||||
|-|-|-|
|[Operator!=](#op_neq)|[operator&gt;](#op_gt)|[operator&gt;=](#op_gt_eq)|
|[operator&lt;](#op_lt)|[operator&lt;=](#op_lt_eq)|[operator==](#op_eq_eq)|

## <a name="op_neq"></a> operator!=

Testet, ob das Objekt links vom Operator ungleich dem Objekt rechts vom Operator ist.

```cpp
bool operator!=(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Ein Objekt vom Typ `vector`.

*right*<br/>
Ein Objekt vom Typ `vector`.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn die Paare nicht gleich sind; **FALSE**, wenn die Paare gleich sind.

### <a name="remarks"></a>Hinweise

Zwei Vektoren sind gleich, wenn sie über die gleiche Anzahl von Elementen verfügen und die entsprechenden Elemente dieselben Werte aufweisen. Andernfalls sind sie ungleich.

### <a name="example"></a>Beispiel

```cpp
// vector_op_ne.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   vector <int> v1, v2;
   v1.push_back( 1 );
     v2.push_back( 2 );

   if ( v1 != v2 )
      cout << "Vectors not equal." << endl;
   else
      cout << "Vectors equal." << endl;
}
```

```Output
Vectors not equal.
```

## <a name="op_lt"></a> operator&lt;

Testet, ob das Objekt links vom Operator kleiner als das Objekt auf der rechten Seite ist.

```cpp
bool operator<(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Ein Objekt vom Typ `vector`.

*right*<br/>
Ein Objekt vom Typ `vector`.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn der Vektor links vom Operator kleiner als der Vektor rechts vom Operator ist; andernfalls **FALSE**.

### <a name="example"></a>Beispiel

```cpp
// vector_op_lt.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   vector <int> v1, v2;
   v1.push_back( 1 );
   v1.push_back( 2 );
   v1.push_back( 4 );

   v2.push_back( 1 );
   v2.push_back( 3 );

   if ( v1 < v2 )
      cout << "Vector v1 is less than vector v2." << endl;
   else
      cout << "Vector v1 is not less than vector v2." << endl;
}
```

```Output
Vector v1 is less than vector v2.
```

## <a name="op_lt_eq"></a> operator&lt;=

Testet, ob das Objekt links vom Operator kleiner oder gleich dem Objekt auf der rechten Seite ist.

```cpp
bool operator<=(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Ein Objekt vom Typ `vector`.

*right*<br/>
Ein Objekt vom Typ `vector`.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn der Vektor links vom Operator kleiner als oder gleich dem Vektor rechts vom Operator ist; andernfalls **FALSE**.

### <a name="example"></a>Beispiel

```cpp
// vector_op_le.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   vector <int> v1, v2;
   v1.push_back( 1 );
   v1.push_back( 2 );
   v1.push_back( 4 );

   v2.push_back( 1 );
   v2.push_back( 3 );

   if ( v1 <= v2 )
      cout << "Vector v1 is less than or equal to vector v2." << endl;
   else
      cout << "Vector v1 is greater than vector v2." << endl;
}
```

```Output
Vector v1 is less than or equal to vector v2.
```

## <a name="op_eq_eq"></a> operator==

Testet, ob das Objekt links vom Operator gleich dem Objekt rechts vom Operator ist.

```cpp
bool operator==(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Ein Objekt vom Typ `vector`.

*right*<br/>
Ein Objekt vom Typ `vector`.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn der Vektor links vom Operator gleich dem Vektor rechts vom Operator ist; andernfalls **FALSE**.

### <a name="remarks"></a>Hinweise

Zwei Vektoren sind gleich, wenn sie über die gleiche Anzahl von Elementen verfügen und die entsprechenden Elemente dieselben Werte aufweisen. Andernfalls sind sie ungleich.

### <a name="example"></a>Beispiel

```cpp
// vector_op_eq.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   vector <int> v1, v2;
   v1.push_back( 1 );
   v2.push_back( 1 );

   if ( v1 == v2 )
      cout << "Vectors equal." << endl;
   else
      cout << "Vectors not equal." << endl;
}
```

```Output
Vectors equal.
```

## <a name="op_gt"></a> operator&gt;

Testet, ob das Objekt links vom Operator größer als das Objekt auf der rechten Seite ist.

```cpp
bool operator>(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Ein Objekt vom Typ `vector`.

*right*<br/>
Ein Objekt vom Typ `vector`.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn der Vektor links vom Operator größer als der Vektor rechts vom Operator ist; andernfalls **FALSE**.

### <a name="example"></a>Beispiel

```cpp
// vector_op_gt.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   vector <int> v1, v2;
   v1.push_back( 1 );
   v1.push_back( 3 );
   v1.push_back( 1 );

   v2.push_back( 1 );
   v2.push_back( 2 );
   v2.push_back( 2 );

   if ( v1 > v2 )
      cout << "Vector v1 is greater than vector v2." << endl;
   else
      cout << "Vector v1 is not greater than vector v2." << endl;
}
```

```Output
Vector v1 is greater than vector v2.
```

## <a name="op_gt_eq"></a> operator&gt;=

Testet, ob das Objekt links vom Operator größer oder gleich dem Objekt auf der rechten Seite ist.

```cpp
bool operator>=(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Ein Objekt vom Typ `vector`.

*right*<br/>
Ein Objekt vom Typ `vector`.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn der Vektor links vom Operator größer als oder gleich dem Vektor rechts vom Operator ist; andernfalls **FALSE**.

### <a name="example"></a>Beispiel

```cpp
// vector_op_ge.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>

int main( )
{
   using namespace std;

   vector <int> v1, v2;
   v1.push_back( 1 );
   v1.push_back( 3 );
   v1.push_back( 1 );

     v2.push_back( 1 );
   v2.push_back( 2 );
   v2.push_back( 2 );

   if ( v1 >= v2 )
      cout << "Vector v1 is greater than or equal to vector v2." << endl;
   else
      cout << "Vector v1 is less than vector v2." << endl;
}
```

```Output
Vector v1 is greater than or equal to vector v2.
```

## <a name="see-also"></a>Siehe auch

[\<vector>](../standard-library/vector.md)<br/>
