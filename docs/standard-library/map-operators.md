---
title: '&lt;map&gt;-Operatoren'
ms.date: 03/27/2019
f1_keywords:
- map/std::operator!=
- map/std::operator&gt;
- map/std::operator&gt;=
- map/std::operator&lt;
- map/std::operator&lt;=
- map/std::operator==
ms.assetid: 7df02b9f-701c-44ed-834a-a819badc5bd0
helpviewer_keywords:
- std::operator!= (map)
- std::operator&gt; (map)
- std::operator&gt;= (map)
- std::operator&lt; (map)
- std::operator&lt;= (map)
- std::operator== (map)
ms.openlocfilehash: b6d2ac108652e33fdd76abaac9b982840d4fce7f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62413020"
---
# <a name="ltmapgt-operators"></a>&lt;map&gt;-Operatoren

||||
|-|-|-|
|[Operator!=](#op_neq)|[operator&gt;](#op_gt)|[operator&gt;=](#op_gt_eq)|
|[operator&lt;](#op_lt)|[operator&lt;=](#op_lt_eq)|[operator==](#op_eq_eq)|
|[operator!= (multimap)](#op_neq_multimap)|[operator&gt; (multimap)](#op_gt_multimap)|[operator&gt;= (multimap)](#op_gt_eq_multimap)|
|[operator&lt; (multimap)](#op_lt_multimap)|[operator&lt;= (multimap)](#op_lt_eq_multimap)|[operator== (multimap)](#op_eq_eq_multimap)|

## <a name="op_neq"></a> operator!=

Testet, ob das Zuordnungsobjekt links vom Operator ungleich dem Zuordnungsobjekt rechts vom Operator ist.

```cpp
bool operator!=(
      const map <Key, Type, Traits, Allocator>& left,
      const map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Ein Objekt vom Typ `map`.

*right*<br/>
Ein Objekt vom Typ `map`.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn die Zuordnungen ungleich sind; **FALSE**, wenn diese gleich sind.

### <a name="remarks"></a>Hinweise

Der Vergleich zwischen den map-Objekten basiert auf einem paarweisen Vergleich der entsprechenden Elemente. Zwei Zuordnungen sind gleich, wenn sie über die gleiche Anzahl von Elementen verfügen und die entsprechenden Elemente dieselben Werte aufweisen. Andernfalls sind sie ungleich.

### <a name="example"></a>Beispiel

```cpp
// map_op_ne.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map <int, int> m1, m2, m3;
   int i;
   typedef pair <int, int> Int_Pair;

   for ( i = 0 ; i < 3 ; i++ )
   {
      m1.insert ( Int_Pair ( i, i ) );
      m2.insert ( Int_Pair ( i, i * i ) );
      m3.insert ( Int_Pair ( i, i ) );
   }

   if ( m1 != m2 )
      cout << "The maps m1 and m2 are not equal." << endl;
   else
      cout << "The maps m1 and m2 are equal." << endl;

   if ( m1 != m3 )
      cout << "The maps m1 and m3 are not equal." << endl;
   else
      cout << "The maps m1 and m3 are equal." << endl;
}
/* Output:
The maps m1 and m2 are not equal.
The maps m1 and m3 are equal.
*/
```

## <a name="op_lt"></a> operator&lt;

Testet, ob das Zuordnungsobjekt links vom Operator kleiner als das Zuordnungsobjekt auf der rechten Seite ist.

```cpp
bool operator<(
      const map <Key, Type, Traits, Allocator>& left,
      const map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Ein Objekt vom Typ `map`.

*right*<br/>
Ein Objekt vom Typ `map`.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn die Zuordnung links vom Operator strikt kleiner als die Zuordnung rechts vom Operator ist; andernfalls **FALSE**.

### <a name="remarks"></a>Hinweise

Der Vergleich zwischen den Zuordnungsobjekten basiert auf einem paarweisen Vergleich der entsprechenden Elemente. Die Beziehung "kleiner als" zwischen zwei Objekten basiert auf einem Vergleich des ersten Paares mit ungleichen Elementen.

### <a name="example"></a>Beispiel

```cpp
// map_op_lt.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map<int, int> m1, m2, m3;
   int i;
   typedef pair<int, int> Int_Pair;

   for ( i = 1 ; i < 3 ; i++ )
   {
      m1.insert ( Int_Pair ( i, i ) );
      m2.insert ( Int_Pair ( i, i * i ) );
      m3.insert ( Int_Pair ( i, i - 1 ) );
   }

   if ( m1 < m2 )
      cout << "The map m1 is less than the map m2." << endl;
   else
      cout << "The map m1 is not less than the map m2." << endl;

   if ( m1 < m3 )
      cout << "The map m1 is less than the map m3." << endl;
   else
      cout << "The map m1 is not less than the map m3." << endl;
}
/* Output:
The map m1 is less than the map m2.
The map m1 is not less than the map m3.
*/
```

## <a name="op_lt_eq"></a> operator&lt;=

Testet, ob das map-Objekt links vom Operator kleiner als das map-Objekt oder gleich diesem Objekt auf der rechten Seite ist.

```cpp
bool operator<=(
      const map <Key, Type, Traits, Allocator>& left,
      const map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Ein Objekt vom Typ `map`.

*right*<br/>
Ein Objekt vom Typ `map`.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn die Zuordnung links vom Operator kleiner als die Zuordnung rechts vom Operator oder gleich ist; andernfalls **FALSE**.

### <a name="example"></a>Beispiel

```cpp
// map_op_le.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map <int, int> m1, m2, m3, m4;
   int i;
   typedef pair <int, int> Int_Pair;

   for ( i = 1 ; i < 3 ; i++ )
   {
      m1.insert ( Int_Pair ( i, i ) );
      m2.insert ( Int_Pair ( i, i * i ) );
      m3.insert ( Int_Pair ( i, i - 1 ) );
      m4.insert ( Int_Pair ( i, i ) );
   }

   if ( m1 <= m2 )
      cout << "The map m1 is less than or equal to the map m2." << endl;
   else
      cout << "The map m1 is greater than the map m2." << endl;

   if ( m1 <= m3 )
      cout << "The map m1 is less than or equal to the map m3." << endl;
   else
      cout << "The map m1 is greater than the map m3." << endl;

   if ( m1 <= m4 )
      cout << "The map m1 is less than or equal to the map m4." << endl;
   else
      cout << "The map m1 is greater than the map m4." << endl;
}
/* Output:
The map m1 is less than or equal to the map m2.
The map m1 is greater than the map m3.
The map m1 is less than or equal to the map m4.
*/
```

## <a name="op_eq_eq"></a> operator==

Testet, ob das map-Objekt links vom Operator gleich dem map-Objekt rechts vom Operator ist.

```cpp
bool operator==(
      const map <Key, Type, Traits, Allocator>& left,
      const map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Ein Objekt vom Typ `map`.

*right*<br/>
Ein Objekt vom Typ `map`.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn die Zuordnung links vom Operator gleich der Zuordnung rechts vom Operator ist; andernfalls **FALSE**.

### <a name="remarks"></a>Hinweise

Der Vergleich zwischen den map-Objekten basiert auf einem paarweisen Vergleich der entsprechenden Elemente. Zwei Zuordnungen sind gleich, wenn sie über die gleiche Anzahl von Elementen verfügen und die entsprechenden Elemente dieselben Werte aufweisen. Andernfalls sind sie ungleich.

### <a name="example"></a>Beispiel

```cpp
// map_op_eq.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map < int, int > m1, m2, m3;
   int i;
   typedef pair < int, int > Int_Pair;

   for ( i = 0 ; i < 3 ; i++ )
   {
      m1.insert ( Int_Pair ( i, i ) );
      m2.insert ( Int_Pair ( i, i * i ) );
      m3.insert ( Int_Pair ( i, i ) );
   }

   if ( m1 == m2 )
      cout << "The maps m1 and m2 are equal." << endl;
   else
      cout << "The maps m1 and m2 are not equal." << endl;

   if ( m1 == m3 )
      cout << "The maps m1 and m3 are equal." << endl;
   else
      cout << "The maps m1 and m3 are not equal." << endl;
}
/* Output:
The maps m1 and m2 are not equal.
The maps m1 and m3 are equal.
*/
```

## <a name="op_gt"></a> operator&gt;

Testet, ob das map-Objekt links vom Operator größer als das map-Objekt auf der rechten Seite ist.

```cpp
bool operator>(
      const map <Key, Type, Traits, Allocator>& left,
      const map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Ein Objekt vom Typ `map`.

*right*<br/>
Ein Objekt vom Typ `map`.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn die map links vom Operator größer als die map rechts vom Operator ist; andernfalls **FALSE**.

### <a name="remarks"></a>Hinweise

Der Vergleich zwischen den map-Objekten basiert auf einem paarweisen Vergleich der entsprechenden Elemente. Die Beziehung "größer als" zwischen zwei Objekten basiert auf einem Vergleich des ersten Paares mit ungleichen Elementen.

### <a name="example"></a>Beispiel

```cpp
// map_op_gt.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map < int, int > m1, m2, m3;
   int i;
   typedef pair < int, int > Int_Pair;

   for ( i = 0 ; i < 3 ; i++ )
   {
      m1.insert ( Int_Pair ( i, i ) );
      m2.insert ( Int_Pair ( i, i * i ) );
      m3.insert ( Int_Pair ( i, i - 1 ) );
   }

   if ( m1 > m2 )
      cout << "The map m1 is greater than the map m2." << endl;
   else
      cout << "The map m1 is not greater than the map m2." << endl;

   if ( m1 > m3 )
      cout << "The map m1 is greater than the map m3." << endl;
   else
      cout << "The map m1 is not greater than the map m3." << endl;
}
/* Output:
The map m1 is not greater than the map m2.
The map m1 is greater than the map m3.
*/
```

## <a name="op_gt_eq"></a>operator&gt;=

Testet, ob das map-Objekt links vom Operator größer als das map-Objekt auf der rechten Seite ist oder diesem entspricht.

```cpp
bool operator>=(
      const map <Key, Type, Traits, Allocator>& left,
      const map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Ein Objekt vom Typ `map`.

*right*<br/>
Ein Objekt vom Typ `map`.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn die map links vom Operator größer als die map rechts von der Liste ist oder dieser entspricht; andernfalls **FALSE**.

### <a name="example"></a>Beispiel

```cpp
// map_op_ge.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   map < int, int > m1, m2, m3, m4;
   int i;
   typedef pair < int, int > Int_Pair;

   for ( i = 1 ; i < 3 ; i++ )
   {
      m1.insert ( Int_Pair ( i, i ) );
      m2.insert ( Int_Pair ( i, i * i ) );
      m3.insert ( Int_Pair ( i, i - 1 ) );
      m4.insert ( Int_Pair ( i, i ) );
   }

   if ( m1 >= m2 )
      cout << "Map m1 is greater than or equal to map m2." << endl;
   else
      cout << "The map m1 is less than the map m2." << endl;

   if ( m1 >= m3 )
      cout << "Map m1 is greater than or equal to map m3." << endl;
   else
      cout << "The map m1 is less than the map m3." << endl;

   if ( m1 >= m4 )
      cout << "Map m1 is greater than or equal to map m4." << endl;
   else
      cout << "The map m1 is less than the map m4." << endl;
}
/* Output:
The map m1 is less than the map m2.
Map m1 is greater than or equal to map m3.
Map m1 is greater than or equal to map m4.
*/
```

## <a name="op_neq_multimap"></a> operator!= (multimap)

Überprüft, ob das multimap-Objekt links vom Operator ungleich dem multimap-Objekt rechts vom Operator ist.

```cpp
bool operator!=(
      const multimap <Key, Type, Traits, Allocator>& left,
      const multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Ein Objekt vom Typ `multimap`.

*right*<br/>
Ein Objekt vom Typ `multimap`.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn die Mehrfachzuordnungen nicht gleich sind; **FALSE**, wenn die Mehrwachzuordnungen gleich sind.

### <a name="remarks"></a>Hinweise

Der Vergleich zwischen den multimap-Objekten basiert auf einem paarweisen Vergleich der entsprechenden Elemente. Zwei Mehrfachzuordnungen sind gleich, wenn sie über die gleiche Anzahl von Elementen verfügen und die entsprechenden Elemente dieselben Werte aufweisen. Andernfalls sind sie ungleich.

### <a name="example"></a>Beispiel

```cpp
// multimap_op_ne.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   multimap <int, int> m1, m2, m3;
   int i;
   typedef pair <int, int> Int_Pair;

   for ( i = 0 ; i < 3 ; i++ )
   {
      m1.insert ( Int_Pair ( i, i ) );
      m2.insert ( Int_Pair ( i, i * i ) );
      m3.insert ( Int_Pair ( i, i ) );
   }

   if ( m1 != m2 )
      cout << "The multimaps m1 and m2 are not equal." << endl;
   else
      cout << "The multimaps m1 and m2 are equal." << endl;

   if ( m1 != m3 )
      cout << "The multimaps m1 and m3 are not equal." << endl;
   else
      cout << "The multimaps m1 and m3 are equal." << endl;
}
/* Output:
The multimaps m1 and m2 are not equal.
The multimaps m1 and m3 are equal.
*/
```

## <a name="op_lt_multimap"></a> operator&lt;

Überprüft, ob das multimap-Objekt links vom Operator ungleich dem multimap-Objekt rechts vom Operator ist.

```cpp
bool operator<(
      const multimap <Key, Type, Traits, Allocator>& left,
      const multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Ein Objekt vom Typ `multimap`.

*right*<br/>
Ein Objekt vom Typ `multimap`.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn die Mehrfachzuordnung links vom Operator strikt kleiner als die Mehrfachzuordnung rechts vom Operator ist; andernfalls **FALSE**.

### <a name="remarks"></a>Hinweise

Der Vergleich zwischen den multimap-Objekten basiert auf einem paarweisen Vergleich der entsprechenden Elemente. Die Beziehung "kleiner als" zwischen zwei Objekten basiert auf einem Vergleich des ersten Paares mit ungleichen Elementen.

### <a name="example"></a>Beispiel

```cpp
// multimap_op_lt.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   multimap < int, int > m1, m2, m3;
   int i;
   typedef pair < int, int > Int_Pair;

   for ( i = 1 ; i < 3 ; i++ )
   {
      m1.insert ( Int_Pair ( i, i ) );
      m2.insert ( Int_Pair ( i, i * i ) );
      m3.insert ( Int_Pair ( i, i - 1 ) );
   }

   if ( m1 < m2 )
      cout << "The multimap m1 is less than the multimap m2." << endl;
   else
      cout << "The multimap m1 is not less than the multimap m2." << endl;

   if ( m1 < m3 )
      cout << "The multimap m1 is less than the multimap m3." << endl;
   else
      cout << "The multimap m1 is not less than the multimap m3." << endl;
}
/* Output:
The multimap m1 is less than the multimap m2.
The multimap m1 is not less than the multimap m3.
*/
```

## <a name="op_lt_eq_multimap"></a> operator&lt;=

Überprüft, ob das multimap-Objekt links vom Operator kleiner als das multimap-Objekt rechts vom Operator ist oder diesem entspricht.

```cpp
bool operator<=(
      const multimap <Key, Type, Traits, Allocator>& left,
      const multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Ein Objekt vom Typ `multimap`.

*right*<br/>
Ein Objekt vom Typ `multimap`.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn die Mehrfachzuordnung links vom Operator kleiner als die Mehrfachzuordnung rechts vom Operator oder gleich ist; andernfalls **FALSE**.

### <a name="example"></a>Beispiel

```cpp
// multimap_op_le.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   multimap <int, int> m1, m2, m3, m4;
   int i;
   typedef pair <int, int> Int_Pair;

   for ( i = 1 ; i < 3 ; i++ )
   {
      m1.insert ( Int_Pair ( i, i ) );
      m2.insert ( Int_Pair ( i, i * i ) );
      m3.insert ( Int_Pair ( i, i - 1 ) );
      m4.insert ( Int_Pair ( i, i ) );
   }

   if ( m1 <= m2 )
      cout << "m1 is less than or equal to m2" << endl;
   else
      cout << "m1 is greater than m2" << endl;

   if ( m1 <= m3 )
      cout << "m1 is less than or equal to m3" << endl;
   else
      cout << "m1 is greater than m3" << endl;

   if ( m1 <= m4 )
      cout << "m1 is less than or equal to m4" << endl;
   else
      cout << "m1 is greater than m4" << endl;
}
/* Output:
m1 is less than or equal to m2
m1 is greater than m3
m1 is less than or equal to m4
*/
```

## <a name="op_eq_eq_multimap"></a> operator==

Überprüft, ob das multimap-Objekt links vom Operator dem multimap-Objekt rechts vom Operator entspricht.

```cpp
bool operator==(
      const multimap <Key, Type, Traits, Allocator>& left,
      const multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Ein Objekt vom Typ `multimap`.

*right*<br/>
Ein Objekt vom Typ `multimap`.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn die Mehrfachzuordnung links vom Operator der Mehrfachzuordnung rechts vom Operator entspricht; andernfalls **FALSE**.

### <a name="remarks"></a>Hinweise

Der Vergleich zwischen den multimap-Objekten basiert auf einem paarweisen Vergleich der entsprechenden Elemente. Zwei Mehrfachzuordnungen sind gleich, wenn sie über die gleiche Anzahl von Elementen verfügen und die entsprechenden Elemente dieselben Werte aufweisen. Andernfalls sind sie ungleich.

### <a name="example"></a>Beispiel

```cpp
// multimap_op_eq.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   multimap<int, int> m1, m2, m3;
   int i;
   typedef pair<int, int> Int_Pair;

   for (i = 0; i < 3; i++)
   {
      m1.insert(Int_Pair(i, i));
      m2.insert(Int_Pair(i, i*i));
      m3.insert(Int_Pair(i, i));
   }

   if ( m1 == m2 )
      cout << "m1 and m2 are equal" << endl;
   else
      cout << "m1 and m2 are not equal" << endl;

   if ( m1 == m3 )
      cout << "m1 and m3 are equal" << endl;
   else
      cout << "m1 and m3 are not equal" << endl;
}
/* Output:
m1 and m2 are not equal
m1 and m3 are equal
*/
```

## <a name="op_gt_multimap"></a> operator&gt;

Überprüft, ob das multimap-Objekt links vom Operator größer als das multimap-Objekt rechts vom Operator ist.

```cpp
bool operator>(
      const multimap <Key, Type, Traits, Allocator>& left,
      const multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Ein Objekt vom Typ `multimap`.

*right*<br/>
Ein Objekt vom Typ `multimap`.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn die Mehrfachzuordnung links vom Operator größer als die Mehrfachzuordnung rechts vom Operator ist; andernfalls **FALSE**.

### <a name="remarks"></a>Hinweise

Der Vergleich zwischen den multimap-Objekten basiert auf einem paarweisen Vergleich der entsprechenden Elemente. Die Beziehung "größer als" zwischen zwei Objekten basiert auf einem Vergleich des ersten Paares mit ungleichen Elementen.

### <a name="example"></a>Beispiel

```cpp
// multimap_op_gt.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   multimap < int, int > m1, m2, m3;
   int i;
   typedef pair < int, int > Int_Pair;

   for ( i = 0 ; i < 3 ; i++ )
   {
      m1.insert ( Int_Pair ( i, i ) );
      m2.insert ( Int_Pair ( i, i * i ) );
      m3.insert ( Int_Pair ( i, i - 1 ) );
   }

   if ( m1 > m2 )
      cout << "The multimap m1 is greater than the multimap m2." << endl;
   else
      cout << "Multimap m1 is not greater than multimap m2." << endl;

   if ( m1 > m3 )
      cout << "The multimap m1 is greater than the multimap m3." << endl;
   else
      cout << "The multimap m1 is not greater than the multimap m3." << endl;
}
/* Output:
Multimap m1 is not greater than multimap m2.
The multimap m1 is greater than the multimap m3.
*/
```

## <a name="op_gt_eq_multimap"></a> operator&gt;=

Überprüft, ob das multimap-Objekt links vom Operator größer als das multimap-Objekt rechts vom Operator ist oder diesem entspricht.

```cpp
bool operator>=(
      const multimap <Key, Type, Traits, Allocator>& left,
      const multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Ein Objekt vom Typ `multimap`.

*right*<br/>
Ein Objekt vom Typ `multimap`.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn die Mehrfachzuordnung links vom Operator größer als die Mehrfachzuordnung rechts vom Operator ist; andernfalls **FALSE**.

### <a name="example"></a>Beispiel

```cpp
// multimap_op_ge.cpp
// compile with: /EHsc
#include <map>
#include <iostream>

int main( )
{
   using namespace std;
   multimap < int, int > m1, m2, m3, m4;
   int i;
   typedef pair < int, int > Int_Pair;

   for ( i = 1 ; i < 3 ; i++ )
   {
      m1.insert ( Int_Pair ( i, i ) );
      m2.insert ( Int_Pair ( i, i * i ) );
      m3.insert ( Int_Pair ( i, i - 1 ) );
      m4.insert ( Int_Pair ( i, i ) );
   }

   if ( m1 >= m2 )
      cout << "The multimap m1 is greater than or equal to the multimap m2." << endl;
   else
      cout << "The multimap m1 is less than the multimap m2." << endl;

   if ( m1 >= m3 )
      cout << "The multimap m1 is greater than or equal to the multimap m3." << endl;
   else
      cout << "The multimap m1 is less than the multimap m3." << endl;

   if ( m1 >= m4 )
      cout << "The multimap m1 is greater than or equal to the multimap m4." << endl;
   else
      cout << "The multimap m1 is less than the multimap m4." << endl;
}
/* Output:
The multimap m1 is less than the multimap m2.
The multimap m1 is greater than or equal to the multimap m3.
The multimap m1 is greater than or equal to the multimap m4.
*/
```

## <a name="see-also"></a>Siehe auch

[\<map>](../standard-library/map.md)<br/>
