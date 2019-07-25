---
title: iterator_traits-Struktur
ms.date: 11/04/2016
f1_keywords:
- xutility/std::iterator_traits
helpviewer_keywords:
- iterator_traits struct
- iterator_traits class
ms.assetid: 8b92c2c5-f658-402f-8ca1-e7ae301b8514
ms.openlocfilehash: 9d2f9d79d200579f539f7d9edc49d4a907e6cdb2
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68455579"
---
# <a name="iteratortraits-struct"></a>iterator_traits-Struktur

Eine Vorlagenhilfsstruktur wird verwendet, um alle wichtigen Typdefinitionen anzugeben, die ein Iterator haben sollte.

## <a name="syntax"></a>Syntax

```cpp
struct iterator_traits {
   typedef typename Iterator::iterator_category iterator_category;
   typedef typename Iterator::value_type value_type;
   typedef typename Iterator::difference_type difference_type;
   typedef difference_type distance_type;
   typedef typename Iterator::pointer pointer;
   typedef typename Iterator::reference reference;
   };
```

## <a name="remarks"></a>Hinweise

Die Vorlagenstruktur definiert die Membertypen.

- `iterator_category`: ein Synonym für `Iterator::iterator_category`.

- `value_type`: ein Synonym für `Iterator::value_type`.

- `difference_type`: ein Synonym für `Iterator::difference_type`.

- `distance_type`: ein Synonym für`Iterator::difference_type.`

- `pointer`: ein Synonym für `Iterator::pointer`.

- `reference`: ein Synonym für `Iterator::reference`.

Die partiellen Spezialisierungs Typen bestimmen die kritischen Typen, die einem Objekt Zeiger vom Typ <strong>\*</strong> **Type oder dem** **Konstanten Typ** <strong>\*</strong>zugeordnet sind.

In dieser Implementierung können Sie auch mehrere Vorlagenfunktionen verwenden, die keine Teilspezialisierung benutzen:

```cpp
template <class Category, class Type, class Diff>
C _Iter_cat(const iterator<Category, Ty, Diff>&);

template <class Ty>
random_access_iterator_tag _Iter_cat(const Ty *);

template <class Category, class Ty, class Diff>
Ty *val_type(const iterator<Category, Ty, Diff>&);

template <class Ty>
Ty *val_type(const Ty *);

template <class Category, class Ty, class Diff>
Diff *_Dist_type(const iterator<Category, Ty, Diff>&);

template <class Ty>
ptrdiff_t *_Dist_type(const Ty *);
```

welche mehrere der gleichen Typen indirekter bestimmen. Sie verwenden diese Funktionen als Argumente in einem Funktionsaufruf. Ihr einziger Zweck ist es, einen hilfreichen Vorlagenklassenparameter an die aufgerufene Funktion anzugeben.

## <a name="example"></a>Beispiel

```cpp
// iterator_traits.cpp
// compile with: /EHsc
#include <iostream>
#include <iterator>
#include <vector>
#include <list>

using namespace std;

template< class it >
void
function( it i1, it i2 )
{
   iterator_traits<it>::iterator_category cat;
   cout << typeid( cat ).name( ) << endl;
   while ( i1 != i2 )
   {
      iterator_traits<it>::value_type x;
      x = *i1;
      cout << x << " ";
      i1++;
   };
   cout << endl;
};

int main( )
{
   vector<char> vc( 10,'a' );
   list<int> li( 10 );
   function( vc.begin( ), vc.end( ) );
   function( li.begin( ), li.end( ) );
}
/* Output:
struct std::random_access_iterator_tag
a a a a a a a a a a
struct std::bidirectional_iterator_tag
0 0 0 0 0 0 0 0 0 0
*/
```

## <a name="requirements"></a>Anforderungen

**Header:** \<iterator>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[\<iterator>](../standard-library/iterator.md)\
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)
