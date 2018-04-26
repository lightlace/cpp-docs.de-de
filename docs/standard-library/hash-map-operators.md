---
title: '&lt;hash_map&gt;-Operatoren | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- hash_map/std::operator!=
- hash_map/std::operator==
dev_langs:
- C++
ms.assetid: 24b9bb9e-e983-4060-bce5-2c7c8161ee61
caps.latest.revision: 13
manager: ghogen
ms.openlocfilehash: 0b4b2a2c98e47752dbfb30afb2a0de522bcbb9f7
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="lthashmapgt-operators"></a>&lt;hash_map&gt;-Operatoren

|||
|-|-|
|[operator!=](#op_neq)|[operator!= (multimap)](#op_neq_mm)|
|[operator==](#op_eq_eq)|[operator== (multimap)](#op_eq_eq_mm)|

## <a name="op_neq"></a> operator!=

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist die [unordered_map-Klasse](unordered-map-class.md).

Testet, ob das hash_map-Objekt links vom Operator ungleich dem hash_map-Objekt rechts vom Operator ist.

```cpp
bool operator!=(const hash_map <Key, Type, Traits, Allocator>& left, const hash_map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parameter

`left` Ein Objekt vom Typ `hash_map`.

`right` Ein Objekt vom Typ `hash_map`.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn die hash_maps ungleich sind; **FALSE**, wenn hash_maps gleich sind.

### <a name="remarks"></a>Hinweise

Der Vergleich zwischen den hash_map-Objekten basiert auf einem paarweisen Vergleich der entsprechenden Elemente. Zwei hash_maps sind gleich, wenn sie über die gleiche Anzahl von Elementen verfügen, und die entsprechenden Elemente dieselben Werte aufweisen. Andernfalls sind sie ungleich.

Mitglieder der [< Hash_map >](hash-map.md) und [< Hash_set >](hash-set.md) Headerdateien der [ Stdext-Namespace](stdext-namespace.md).

### <a name="example"></a>Beispiel

```cpp
// hash_map_op_ne.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1, hm2, hm3;
   int i;
   typedef pair <int, int> Int_Pair;

   for ( i = 0 ; i < 3 ; i++ )
   {
      hm1.insert ( Int_Pair ( i, i ) );
      hm2.insert ( Int_Pair ( i, i * i ) );
      hm3.insert ( Int_Pair ( i, i ) );
   }

   if ( hm1 != hm2 )
      cout << "The hash_maps hm1 and hm2 are not equal." << endl;
   else
      cout << "The hash_maps hm1 and hm2 are equal." << endl;

   if ( hm1 != hm3 )
      cout << "The hash_maps hm1 and hm3 are not equal." << endl;
   else
      cout << "The hash_maps hm1 and hm3 are equal." << endl;
}
```

```Output
The hash_maps hm1 and hm2 are not equal.
The hash_maps hm1 and hm3 are equal.
```

## <a name="op_eq_eq"></a> operator==

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist die [unordered_map-Klasse](unordered-map-class.md).

Testet, ob das hash_map-Objekt links vom Operator gleich dem hash_map-Objekt rechts vom Operator ist.

```cpp
bool operator==(const hash_map <Key, Type, Traits, Allocator>& left, const hash_map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parameter

`left` Ein Objekt vom Typ `hash_map`.

`right` Ein Objekt vom Typ `hash_map`.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn die hash_map links vom Operator gleich der hash_map rechts vom Operator ist; andernfalls **FALSE**.

### <a name="remarks"></a>Hinweise

Der Vergleich zwischen den hash_map-Objekten basiert auf einem paarweisen Vergleich der entsprechenden Elemente. Zwei hash_maps sind gleich, wenn sie über die gleiche Anzahl von Elementen verfügen, und die entsprechenden Elemente dieselben Werte aufweisen. Andernfalls sind sie ungleich.

### <a name="example"></a>Beispiel

```cpp
// hash_map_op_eq.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_map <int, int> hm1, hm2, hm3;
   int i;
   typedef pair <int, int> Int_Pair;

   for ( i = 0 ; i < 3 ; i++ )
   {
      hm1.insert ( Int_Pair ( i, i ) );
      hm2.insert ( Int_Pair ( i, i * i ) );
      hm3.insert ( Int_Pair ( i, i ) );
   }

   if ( hm1 == hm2 )
      cout << "The hash_maps hm1 and hm2 are equal." << endl;
   else
      cout << "The hash_maps hm1 and hm2 are not equal." << endl;

   if ( hm1 == hm3 )
      cout << "The hash_maps hm1 and hm3 are equal." << endl;
   else
      cout << "The hash_maps hm1 and hm3 are not equal." << endl;
}
```

```Output
The hash_maps hm1 and hm2 are not equal.
The hash_maps hm1 and hm3 are equal.
```

## <a name="op_neq_mm"></a>  Operator! = (Hash_multimap)

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist [unordered_multimap Class](unordered-multimap-class.md).

Überprüft, ob das hash_multimap-Objekt links vom Operator ungleich dem hash_multimap-Objekt rechts vom Operator ist.

```cpp
bool operator!=(const hash_multimap <Key, Type, Traits, Allocator>& left, const hash_multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parameter

`left` Ein Objekt vom Typ `hash_multimap`.

`right` Ein Objekt vom Typ `hash_multimap`.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn die hash_multimaps ungleich sind; **FALSE**, wenn hash_multimaps gleich sind.

### <a name="remarks"></a>Hinweise

Der Vergleich zwischen den hash_multimap-Objekten basiert auf einem paarweisen Vergleich der entsprechenden Elemente. Zwei hash_multimaps sind gleich, wenn sie über die gleiche Anzahl von Elementen verfügen und die entsprechenden Elemente dieselben Werte aufweisen. Andernfalls sind sie ungleich.

### <a name="example"></a>Beispiel

```cpp
// hash_multimap_op_ne.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multimap <int, int> hm1, hm2, hm3;
   int i;
   typedef pair <int, int> Int_Pair;

   for ( i = 0 ; i < 3 ; i++ )
   {
      hm1.insert ( Int_Pair ( i, i ) );
      hm2.insert ( Int_Pair ( i, i * i ) );
      hm3.insert ( Int_Pair ( i, i ) );
   }

   if ( hm1 != hm2 )
      cout << "The hash_multimaps hm1 and hm2 are not equal." << endl;
   else
      cout << "The hash_multimaps hm1 and hm2 are equal." << endl;

   if ( hm1 != hm3 )
      cout << "The hash_multimaps hm1 and hm3 are not equal." << endl;
   else
      cout << "The hash_multimaps hm1 and hm3 are equal." << endl;
}
```

```Output
The hash_multimaps hm1 and hm2 are not equal.
The hash_multimaps hm1 and hm3 are equal.
```

## <a name="op_eq_eq_mm"></a>  Operator == (Hash_multimap)

> [!NOTE]
> Diese API ist veraltet. Die Alternative ist die [unordered_multimap-Klasse](unordered-multimap-class.md).

Überprüft, ob das hash_multimap-Objekt links vom Operator gleich dem hash_multimap-Objekt rechts vom Operator ist.

```cpp
bool operator==(const hash_multimap <Key, Type, Traits, Allocator>& left, const hash_multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parameter

`left` Ein Objekt vom Typ `hash_multimap`.

`right` Ein Objekt vom Typ `hash_multimap`.

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn die hash_multimap links vom Operator gleich der hash_multimap rechts vom Operator ist; andernfalls **FALSE**.

### <a name="remarks"></a>Hinweise

Der Vergleich zwischen den hash_multimap-Objekten basiert auf einem paarweisen Vergleich der entsprechenden Elemente. Zwei hash_multimaps sind gleich, wenn sie über die gleiche Anzahl von Elementen verfügen und die entsprechenden Elemente dieselben Werte aufweisen. Andernfalls sind sie ungleich.

### <a name="example"></a>Beispiel

```cpp
// hash_multimap_op_eq.cpp
// compile with: /EHsc
#include <hash_map>
#include <iostream>

int main( )
{
   using namespace std;
   using namespace stdext;
   hash_multimap<int, int> hm1, hm2, hm3;
   int i;
   typedef pair<int, int> Int_Pair;

   for (i = 0; i < 3; i++)
   {
      hm1.insert(Int_Pair(i, i));
      hm2.insert(Int_Pair(i, i*i));
      hm3.insert(Int_Pair(i, i));
   }

   if ( hm1 == hm2 )
      cout << "The hash_multimaps hm1 and hm2 are equal." << endl;
   else
      cout << "The hash_multimaps hm1 and hm2 are not equal." << endl;

   if ( hm1 == hm3 )
      cout << "The hash_multimaps hm1 and hm3 are equal." << endl;
   else
      cout << "The hash_multimaps hm1 and hm3 are not equal." << endl;
}
```

```Output
The hash_multimaps hm1 and hm2 are not equal.
The hash_multimaps hm1 and hm3 are equal.
```

## <a name="see-also"></a>Siehe auch

[<hash_map>](hash-map.md)<br/>
