---
title: pair-Struktur
ms.date: 11/04/2016
f1_keywords:
- utility/std::pair
helpviewer_keywords:
- pair class
ms.assetid: 539d3d67-80a2-4170-b347-783495d42109
ms.openlocfilehash: 2b7f2b736d24961376db4317d6d53e06153283c2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50443237"
---
# <a name="pair-structure"></a>pair-Struktur

Eine Struktur, die die Möglichkeit bietet, zwei Objekte als ein einzelnes Objekt zu behandeln.

## <a name="syntax"></a>Syntax

```cpp
struct pair
{
    typedef T1 first_type;
    typedef T2 second_type;
    T1 first;
    T2 second;
    constexpr pair();
    constexpr pair(
        const T1& Val1,
        const T2& Val2);

    template <class Other1, class Other2>
    constexpr pair(const pair<Other1, Other2>& Right);

    template <class Other1, class Other2>
    constexpr pair(const pair <Other1 Val1, Other2 Val2>&& Right);

    template <class Other1, class Other2>
    constexpr pair(Other1&& Val1, Other2&& Val2);
};
```

### <a name="parameters"></a>Parameter

*Wert1*<br/>
Der Wert, der das erste Element von `pair` initialisiert.

*Wert2*<br/>
Der Wert, der das zweite Element von `pair` initialisiert.

*Rechts*<br/>
Ein Paar, dessen Werte verwendet werden, um die Elemente eines anderen Paars zu initialisieren.

## <a name="return-value"></a>Rückgabewert

Der erste Konstruktor (Standardkonstruktor) initialisiert das erste Element des Paars auf den Standardwert des Typs `T1` und zweite Element auf den Standardwert des Typs `T2`.

Der zweite Konstruktor initialisiert das erste Element des Paars auf *Val1* und das zweite auf *Val2.*

Der dritte Konstruktor (Vorlagenkonstruktor) initialisiert das erste Element des Paars auf `Right`. **first** und das zweite auf `Right`. **second**.

Der vierte Konstruktor initialisiert das erste Element des Paars auf *Val1* und das zweite auf *Val2* mit [Rvalue-Verweisdeklarator: & &](../cpp/rvalue-reference-declarator-amp-amp.md).

## <a name="remarks"></a>Hinweise

Die Vorlagenstruktur speichert ein Paar von Objekten des Typs `T1` und `T2`bzw. Der Typ `first_type` ist identisch mit dem Vorlagenparameter `T1` und welche `second_type` ist identisch mit dem Vorlagenparameter `T2`. `T1` und `T2` müssen jeweils nur einen Standardkonstruktor, einen Einzelargumentkonstruktor und einen Destruktor bereitstellen. Alle Member des Typs `pair` sind öffentlich, da der Typ als `struct` statt als **Klasse** deklariert ist. Die beiden häufigsten Einsatzfälle für ein Paar sind, es als Rückgabetyp für eine Funktion zu verwenden, die zwei Werte zurückgibt, oder es als Element für die assoziativen Containerklassen [map-Klasse](../standard-library/map-class.md) und [multimap-Klasse](../standard-library/multimap-class.md) zu verwenden, die beide einen Schlüssel und einen Werttyp haben, die jedem Element zugeordnet sind. Die zweite Verwendung erfüllt die Anforderungen für einen paarweise assoziativen Container und hat einen Werttyp der Form `pair`< **const**`key_type`, `mapped_type`>.

## <a name="example"></a>Beispiel

```cpp
// utility_pair.cpp
// compile with: /EHsc
#include <utility>
#include <map>
#include <iomanip>
#include <iostream>

int main( )
{
   using namespace std;

   // Using the constructor to declare and initialize a pair
   pair <int, double> p1 ( 10, 1.1e-2 );

   // Compare using the helper function to declare and initialize a pair
   pair <int, double> p2;
   p2 = make_pair ( 10, 2.22e-1 );

   // Making a copy of a pair
   pair <int, double> p3 ( p1 );

   cout.precision ( 3 );
   cout << "The pair p1 is: ( " << p1.first << ", "
        << p1.second << " )." << endl;
   cout << "The pair p2 is: ( " << p2.first << ", "
        << p2.second << " )." << endl;
   cout << "The pair p3 is: ( " << p3.first << ", "
        << p3.second << " )." << endl;

   // Using a pair for a map element
   map <int, int> m1;
   map <int, int>::iterator m1_Iter;

   typedef pair <int, int> Map_Int_Pair;

   m1.insert ( Map_Int_Pair ( 1, 10 ) );
   m1.insert ( Map_Int_Pair ( 2, 20 ) );
   m1.insert ( Map_Int_Pair ( 3, 30 ) );

   cout << "The element pairs of the map m1 are:";
   for ( m1_Iter = m1.begin( ); m1_Iter != m1.end( ); m1_Iter++ )
      cout << " ( " << m1_Iter -> first << ", "
           << m1_Iter -> second << " )";
   cout   << "." << endl;

   // Using pair as a return type for a function
   pair< map<int,int>::iterator, bool > pr1, pr2;
   pr1 = m1.insert ( Map_Int_Pair ( 4, 40 ) );
   pr2 = m1.insert ( Map_Int_Pair (1, 10 ) );

   if( pr1.second == true )
   {
      cout << "The element (4,40) was inserted successfully in m1."
           << endl;
   }
   else
   {
      cout << "The element with a key value of\n"
           << " ( (pr1.first) -> first ) = " << ( pr1.first ) -> first
           << " is already in m1,\n so the insertion failed." << endl;
   }

   if( pr2.second == true )
   {
      cout << "The element (1,10) was inserted successfully in m1."
           << endl;
   }
   else
   {
      cout << "The element with a key value of\n"
           << " ( (pr2.first) -> first ) = " << ( pr2.first ) -> first
           << " is already in m1,\n so the insertion failed." << endl;
   }
}
/* Output:
The pair p1 is: ( 10, 0.011 ).
The pair p2 is: ( 10, 0.222 ).
The pair p3 is: ( 10, 0.011 ).
The element pairs of the map m1 are: ( 1, 10 ) ( 2, 20 ) ( 3, 30 ).
The element (4,40) was inserted successfully in m1.
The element with a key value of
( (pr2.first) -> first ) = 1 is already in m1,
so the insertion failed.
*/
```

## <a name="requirements"></a>Anforderungen

**Header:** \<utility>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
