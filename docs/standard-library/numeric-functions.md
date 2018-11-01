---
title: '&lt;numeric&gt;-Funktionen'
ms.date: 11/04/2016
f1_keywords:
- numeric/std::accumulate
- numeric/std::adjacent_difference
- numeric/std::inner_product
- numeric/std::iota
- numeric/std::partial_sum
ms.assetid: a4b0449a-c80c-4a1d-8d9f-d7fcd0058f8b
helpviewer_keywords:
- std::accumulate [C++]
- std::adjacent_difference [C++]
- std::inner_product [C++]
- std::iota [C++]
- std::partial_sum [C++]
ms.openlocfilehash: 6df37cf4f6c8afe09f25550d4fc0d9acb553ac52
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50475100"
---
# <a name="ltnumericgt-functions"></a>&lt;numeric&gt;-Funktionen

||||
|-|-|-|
|[accumulate](#accumulate)|[adjacent_difference](#adjacent_difference)|[inner_product](#inner_product)|
|[iota](#iota)|[partial_sum](#partial_sum)|

## <a name="accumulate"></a> accumulate

Berechnet die Summe aller Elemente in einem angegebenen Bereich, einschließlich einigen Anfangswerten, indem aufeinander folgende Teilsummen berechnet werden, oder berechnet das Ergebnis der aufeinander folgenden Teilergebnisse, die auf ähnliche Weise mithilfe eines angegebenen binären Vorgangs (außer Summe) abgerufen werden.

```cpp
template <class InputIterator, class Type>
Type accumulate(InputIterator first, InputIterator last, Type val);

template <class InputIterator, class Type, class BinaryOperation>
Type accumulate(
    InputIterator first,
    InputIterator last,
    Type val,
    BinaryOperation binary_op);
```

### <a name="parameters"></a>Parameter

*Erste*<br/>
Ein Eingabeiterator, der das erste Element in dem Bereich adressiert, der entsprechend eines angegebenen binären Vorgangs summiert oder kombiniert werden soll.

*last*<br/>
Ein Eingabeiterator, der das letzte Element im Bereich adressiert, der entsprechend eines angegebenen binären Vorgangs summiert oder kombiniert werden soll. Dieser Vorgang befindet sich eine Position nach dem letzten Element, das tatsächlich im iterierten Sammelbereich enthalten ist.

*val*<br/>
Ein anfänglicher Wert, zu oder mit dem jedes Element hinzugefügt oder kombiniert wird, entsprechend eines angegebenen binären Vorgangs.

*binary_op*<br/>
Der binäre Vorgang, der auf jedes Element im angegebenen Bereich angewendet wird und das Ergebnis der vorherigen Anwendung.

### <a name="return-value"></a>Rückgabewert

Die Summe der *Val* und alle Elemente im angegebenen Bereich für die erste Vorlagenfunktion oder, für die zweite Vorlagenfunktion, das Ergebnis des Anwendens der binären Operation angegeben ist, anstelle von der Summenvorgang, um (  *PartialResult, \*Iter*), wobei *PartialResult* ist das Ergebnis des vorherigen Anwendungen des Vorgangs und `Iter` ist ein Iterator, der auf ein Element im Bereich zeigt.

### <a name="remarks"></a>Hinweise

Der Anfangswert stellt sicher, dass es ein klar definiertes Ergebnis sein wird, wenn der Bereich leer ist, in diesem Fall wird *Val* zurückgegeben wird. Der binäre Vorgang muss nicht assoziativ oder kommutativ sein. Das Ergebnis wird auf den ursprünglichen Wert initialisiert *Val* und dann *Ergebnis*  =  `binary_op` ( *Ergebnis*, <strong>\*</strong> `Iter`) iterativ über den Bereich berechnet wird, in denen `Iter` ist ein Iterator, der auf nachfolgende Element im Bereich zeigt. Der Bereich muss gültig sein und die Komplexität ist linear mit der Größe des Bereichs. Der Rückgabetyp des binären Operators muss in **Typ** konvertierbar sein, um Closure während der Iteration sicherzustellen.

### <a name="example"></a>Beispiel

```cpp
// numeric_accum.cpp
// compile with: /EHsc
#include <vector>
#include <numeric>
#include <functional>
#include <iostream>

int main( )
{
   using namespace std;

   vector <int> v1, v2(20);
   vector <int>::iterator iter1, iter2;

   int i;
   for (i = 1; i < 21; i++)
   {
      v1.push_back(i);
   }

   cout << "The original vector v1 is:\n ( " ;
   for (iter1 = v1.begin(); iter1 != v1.end(); iter1++)
      cout << *iter1 << " ";
   cout << ")." << endl;

   // The first member function for the accumulated sum
   int total;
   total = accumulate(v1.begin(), v1.end(), 0);

   cout << "The sum of the integers from 1 to 20 is: "
        << total << "." << endl;

   // Constructing a vector of partial sums
   int j = 0, partotal;
   for (iter1 = v1.begin(); iter1 != v1.end(); iter1++)
   {
      partotal = accumulate(v1.begin(), iter1 + 1, 0);
      v2[j] = partotal;
      j++;
   }

   cout << "The vector of partial sums is:\n ( " ;
   for (iter2 = v2.begin(); iter2 != v2.end(); iter2++)
      cout << *iter2 << " ";
   cout << ")." << endl << endl;

   // The second member function for the accumulated product
   vector <int> v3, v4(10);
   vector <int>::iterator iter3, iter4;

   int s;
   for (s = 1; s < 11; s++)
   {
      v3.push_back(s);
   }

   cout << "The original vector v3 is:\n ( " ;
   for (iter3 = v3.begin(); iter3 != v3.end(); iter3++)
      cout << *iter3 << " ";
   cout << ")." << endl;

   int ptotal;
   ptotal = accumulate(v3.begin(), v3.end(), 1, multiplies<int>());

   cout << "The product of the integers from 1 to 10 is: "
        << ptotal << "." << endl;

   // Constructing a vector of partial products
   int k = 0, ppartotal;
   for (iter3 = v3.begin(); iter3 != v3.end(); iter3++) {
      ppartotal = accumulate(v3.begin(), iter3 + 1, 1, multiplies<int>());
      v4[k] = ppartotal;
      k++;
   }

   cout << "The vector of partial products is:\n ( " ;
   for (iter4 = v4.begin(); iter4 != v4.end(); iter4++)
      cout << *iter4 << " ";
   cout << ")." << endl;
}
```

```Output
The original vector v1 is:
( 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 ).
The sum of the integers from 1 to 20 is: 210.
The vector of partial sums is:
( 1 3 6 10 15 21 28 36 45 55 66 78 91 105 120 136 153 171 190 210 ).

The original vector v3 is:
( 1 2 3 4 5 6 7 8 9 10 ).
The product of the integers from 1 to 10 is: 3628800.
The vector of partial products is:
( 1 2 6 24 120 720 5040 40320 362880 3628800 ).
```

## <a name="adjacent_difference"></a> adjacent_difference

Berechnet die aufeinander folgenden Unterschiede zwischen einem Element und seinem Vorgänger in einem Eingabebereich und gibt die Ergebnisse in einem Zielbereich aus oder berechnet das Ergebnis einer allgemeinen Prozedur, in der der Vorgang zum Feststellen von Unterschieden durch einen anderen angegebenen binären Vorgang ersetzt wird.

```cpp
template <class InputIterator, class OutIterator>
OutputIterator adjacent_difference(
    InputIterator first,
    InputIterator last,
    OutputIterator result);

template <class InputIterator, class OutIterator, class BinaryOperation>
OutputIterator adjacent_difference(
    InputIterator first,
    InputIterator last,
    OutputIterator result,
    BinaryOperation binary_op);
```

### <a name="parameters"></a>Parameter

*Erste*<br/>
Ein Eingabeiterator, der das erste Element im Eingabebereich adressiert, dessen Elemente mit ihren jeweiligen Vorgängern differenziert werden sollen oder in dem die Wertpaare durch einen anderen angegebenen binären Vorgang verarbeitet werden sollen.

*last*<br/>
Ein Eingabeiterator, der das letzte Element im Eingabebereich adressiert, dessen Elemente mit ihren jeweiligen Vorgängern differenziert werden sollen oder in dem die Wertpaare durch einen anderen angegebenen binären Vorgang verarbeitet werden sollen.

*Ergebnis*<br/>
Ein Ausgabeiterator, der das erste Element eines Zielbereichs adressiert, in dem die Reihe von Differenzen oder die Ergebnisse des angegebenen Vorgangs gespeichert werden sollen.

*binary_op*<br/>
Der binäre Vorgang, der im allgemeinen Vorgang angewendet werden soll, der den Vorgang der Subtraktion im Differenzierungsverfahren ersetzt.

### <a name="return-value"></a>Rückgabewert

Ein Ausgabeiterator, der das Ende des Zielbereichs adressiert: `result` + (`last` - `first`).

### <a name="remarks"></a>Hinweise

Der Ausgabeiterator _ *Ergebnis* darf derselbe Iterator sein wie der eingabeiterator * erste, *, damit `adjacent_difference`direktes berechnet werden können.

Für eine Sequenz von Werten *eine*1 *eine*2, *eine*3 in einem Eingabebereich die erste Vorlagenfunktion aufeinander folgende speichert `partial_difference`s *eine*1 , *eine*2 – *eine*1, a3 – *eine*2 im Zielbereich.

Für eine Sequenz von Werten *eine*1 *eine*2, *eine*3 in einem Eingabebereich, die zweite Vorlagenfunktion aufeinander folgende speichert `partial_difference`s *eine* 1, *eine*2 `binary_op` *eine*1 *eine*3 `binary_op` *eine*2 im Zielbereich.

Der binäre Vorgang `binary_op` muss weder assoziativ noch kommutativ sein, da die Reihenfolge der Vorgänge vollständig angegeben wird.

### <a name="example"></a>Beispiel

```cpp
// numeric_adj_diff.cpp
// compile with: /EHsc
#include <vector>
#include <list>
#include <numeric>
#include <functional>
#include <iostream>

int main( )
{
   using namespace std;

   vector<int> V1( 10 ), V2( 10 );
   vector<int>::iterator VIter1, VIter2, VIterend, VIterend2;

   list <int> L1;
   list <int>::iterator LIter1, LIterend, LIterend2;

   int t;
   for ( t = 1 ; t <= 10 ; t++ )
   {
      L1.push_back( t * t );
   }

   cout << "The input list L1 is:\n ( " ;
   for ( LIter1 = L1.begin( ) ; LIter1 != L1.end( ) ; LIter1++ )
      cout << *LIter1 << " ";
   cout << ")." << endl;

   // The first member function for the adjacent_differences of
   // elements in a list output to a vector
   VIterend = adjacent_difference ( L1.begin ( ) , L1.end ( ) ,
      V1.begin ( ) );

   cout << "Output vector containing adjacent_differences is:\n ( " ;
   for ( VIter1 = V1.begin( ) ; VIter1 != VIterend ; VIter1++ )
      cout << *VIter1 << " ";
   cout << ")." << endl;

   // The second member function used to compute
   // the adjacent products of the elements in a list
   VIterend2 = adjacent_difference ( L1.begin ( ) , L1.end ( ) , V2.begin ( ) ,
      multiplies<int>( ) );

   cout << "The output vector with the adjacent products is:\n ( " ;
   for ( VIter2 = V2.begin( ) ; VIter2 != VIterend2 ; VIter2++ )
      cout << *VIter2 << " ";
   cout << ")." << endl;

   // Computation of adjacent_differences in place
   LIterend2 = adjacent_difference ( L1.begin ( ) , L1.end ( ) , L1.begin ( ) );
   cout << "In place output adjacent_differences in list L1 is:\n ( " ;
   for ( LIter1 = L1.begin( ) ; LIter1 != LIterend2 ; LIter1++ )
      cout << *LIter1 << " ";
   cout << ")." << endl;
}
```

## <a name="inner_product"></a> inner_product

Berechnet die Summe des elementweisen Produkts von zwei Bereichen und fügt sie einem angegebenen Anfangswert hinzu oder berechnet das Ergebnis einer allgemeinen Prozedur, in der die Summen- und Produktvorgänge durch andere angegebene binäre Vorgänge ersetzt werden.

```cpp
template <class InputIterator1, class InputIterator2, class Type>
Type inner_product(
    InputIterator1   first1,
    InputIterator1   last1,
    InputIterator2   first2,
    Type             val);

template <class InputIterator1, class InputIterator2, class Type, class BinaryOperation1, class BinaryOperation2>
Type inner_product(
    InputIterator1   first1,
    InputIterator1   last1,
    InputIterator2   first2,
    Type             val,
    BinaryOperation1  binary_op1,
    BinaryOperation2  binary_op2);
```

### <a name="parameters"></a>Parameter

*first1*<br/>
Ein Eingabeiterator, der das erste Element im ersten Bereich adressiert, dessen inneres oder generalisiertes inneres Produkt mit dem zweiten Bereich neu zu berechnen ist.

*Last1*<br/>
Ein Eingabeiterator, der das letzte Element im ersten Bereich adressiert, dessen inneres oder generalisiertes inneres Produkt mit dem zweiten Bereich neu zu berechnen ist.

*first2*<br/>
Ein Eingabeiterator, der das erste Element im zweiten Bereich adressiert, dessen inneres oder generalisiertes inneres Produkt mit dem ersten Bereich neu zu berechnen ist.

*val*<br/>
Einen Anfangswert für den das innere oder generalisierte innere Produkt zwischen den Bereichen hinzugefügt wird.

*binary_op1*<br/>
Der binäre Vorgang, der das innere Produkt des Summenvorgangs ersetzt, wird auf die elementweisen Produkte in der Generalisierung des inneren Produkts angewendet.

*binary_op2*<br/>
Der binäre Vorgang, der das innere Produkt des elementweisen Produkt des Multiplizierungsvorgangs in der Generalisierung des inneren Produkts ersetzt.

### <a name="return-value"></a>Rückgabewert

Der erste Memberfunktion gibt die Summe des elementweisen Produkts zurück und fügt den angegebenen Anfangswert hinzu. Für Wertebereiche *a*i und *b*i wird folgendes zurückgegeben:

`val` + ( *eine*1 \* *b*1) + ( *eine*2 \* *b*2) +... + ( *eine*n \* *b*n)

durch iterativen Ersatz *Val* mit `val` + ( *eine*ich \* *b*ich).

Die zweite Memberfunktion gibt folgendes zurück:

`val` *binary_op1* ( *a*1 *binary_op2* *b*1 ) *binary_op1* ( *a*2 *binary_op2* *b*2 ) *binary_op1* ... *binary_op1* ( *a*n *binary_op2* *b*n )

durch iterativen Ersatz *Val* mit `val` *binary_op1* ( *eine*ich *binary_op2* *b* i).

### <a name="remarks"></a>Hinweise

Der Anfangswert stellt sicher, dass es ein klar definiertes Ergebnis sein wird, wenn der Bereich leer ist, in diesem Fall wird *Val* zurückgegeben wird. Der binäre Vorgang muss nicht assoziativ oder kommutativ sein. Der Bereich muss gültig sein und die Komplexität ist linear mit der Größe des Bereichs. Der Rückgabetyp des binären Operators muss in **Typ** konvertierbar sein, um Closure während der Iteration sicherzustellen.

### <a name="example"></a>Beispiel

```cpp
// numeric_inner_prod.cpp
// compile with: /EHsc
#include <vector>
#include <list>
#include <numeric>
#include <functional>
#include <iostream>

int main()
{
   using namespace std;

   vector <int> v1, v2(7), v3(7);
   vector <int>::iterator iter1, iter2, iter3;

   int i;
   for (i = 1; i <= 7; i++)
   {
      v1.push_back(i);
   }

   cout << "The original vector v1 is:\n ( " ;
   for (iter1 = v1.begin(); iter1 != v1.end(); iter1++)
      cout << *iter1 << " ";
   cout << ")." << endl;

   list <int> l1, l2(7);
   list <int>::iterator lIter1, lIter2;

   int t;
   for (t = 1; t <= 7; t++)
   {
      l1.push_back(t);
   }

   cout << "The original list l1 is:\n ( " ;
   for (lIter1 = l1.begin(); lIter1 != l1.end(); lIter1++)
      cout << *lIter1 << " ";
   cout << ")." << endl;

   // The first member function for the inner product
   int inprod;
   inprod = inner_product(v1.begin(), v1.end(), l1.begin(), 0);

   cout << "The inner_product of the vector v1 and the list l1 is: "
        << inprod << "." << endl;

   // Constructing a vector of partial inner_products between v1 & l1
   int j = 0, parinprod;
   for (iter1 = v1.begin(); iter1 != v1.end(); iter1++) {
      parinprod = inner_product(v1.begin(), iter1 + 1, l1.begin(), 0);
      v2[j] = parinprod;
      j++;
   }

   cout << "Vector of partial inner_products between v1 & l1 is:\n ( " ;
   for (iter2 = v2.begin(); iter2 != v2.end(); iter2++)
      cout << *iter2 << " ";
   cout << ")." << endl << endl;

   // The second member function used to compute
   // the product of the element-wise sums
   int inprod2;
   inprod2 = inner_product (v1.begin(), v1.end(),
      l1.begin(), 1, multiplies<int>(), plus<int>());

   cout << "The sum of the element-wise products of v1 and l1 is: "
        << inprod2 << "." << endl;

   // Constructing a vector of partial sums of element-wise products
   int k = 0, parinprod2;
   for (iter1 = v1.begin(); iter1 != v1.end(); iter1++)
   {
      parinprod2 =
         inner_product(v1.begin(), iter1 + 1, l1.begin(), 1,
         multiplies<int>(), plus<int>());
      v3[k] = parinprod2;
      k++;
   }

   cout << "Vector of partial sums of element-wise products is:\n ( " ;
   for (iter3 = v3.begin(); iter3 != v3.end(); iter3++)
      cout << *iter3 << " ";
   cout << ")." << endl << endl;
}
```

## <a name="iota"></a> iota

Speichert einen Startwert, beginnend mit dem ersten Element und füllt ihn mit aufeinander folgenden Schritten des Werts (` value++`) in jedem der Elemente im Intervall `[ first,  last)`.

```cpp
template <class ForwardIterator, class Type>
void iota(ForwardIterator first, ForwardIterator last, Type value);
```

### <a name="parameters"></a>Parameter

*Erste*<br/>
Ein Eingabeiterator, der das erste Element im aufzufüllenden Bereich adressiert.

*last*<br/>
Ein Eingabeiterator, der das letzte Element im aufzufüllenden Bereich adressiert.

*Wert*<br/>
Der Anfangswert, der im ersten Element gespeichert und schrittweise für nachfolgende Elemente erhöht werden soll.

### <a name="remarks"></a>Hinweise

### <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht einige Verwendungsmöglichkeiten für die `iota`-Funktion durch Ausfüllen einer [list](../standard-library/list.md) von ganzen Zahlen und Ausfüllen eines [vector](../standard-library/vector.md) mit `list`, damit die [random_shuffle](../standard-library/algorithm-functions.md#random_shuffle)-Funktion verwendet werden kann.

```cpp
// compile by using: cl /EHsc /nologo /W4 /MTd
#include <algorithm>
#include <numeric>
#include <list>
#include <vector>
#include <iostream>

using namespace std;

int main(void)
{
    list <int> intList(10);
    vector <list<int>::iterator> intVec(intList.size());

    // Fill the list
    iota(intList.begin(), intList.end(), 0);

    // Fill the vector with the list so we can shuffle it
    iota(intVec.begin(), intVec.end(), intList.begin());

    random_shuffle(intVec.begin(), intVec.end());

    // Output results
    cout << "Contents of the integer list: " << endl;
    for (auto i: intList) {
        cout << i << ' ';
    }
    cout << endl << endl;

    cout << "Contents of the integer list, shuffled by using a vector: " << endl;
    for (auto i: intVec) {
        cout << *i << ' ';
    }
    cout << endl;
}
```

## <a name="partial_sum"></a> partial_sum

Berechnet eine Reihe von Summen in einem Eingabebereich vom ersten Element bis zum *i*.-Element und speichert das Ergebnis jeder Summe im *i*.-Element eines Zielbereichs oder berechnet das Ergebnis einer allgemeinen Prozedur, in der der Summenvorgang durch einen anderen angegebenen binären Vorgang ersetzt wird.

```cpp
template <class InputIterator, class OutIt>
OutputIterator partial_sum(
    InputIterator first,
    InputIterator last,
    OutputIterator result);

template <class InputIterator, class OutIt, class Fn2>
OutputIterator partial_sum(
    InputIterator first,
    InputIterator last,
    OutputIterator result,
    BinaryOperation binary_op);
```

### <a name="parameters"></a>Parameter

*Erste*<br/>
Ein Eingabeiterator, der das erste Element in dem Bereich adressiert, der entsprechend eines angegebenen binären Vorgangs teilweise summiert oder kombiniert werden soll.

*last*<br/>
Ein Eingabeiterator, der das letzte Element in dem Bereich adressiert, der entsprechend eines angegebenen binären Vorgangs teilweise summiert oder kombiniert werden soll und eine Position nach dem letzten Element folgt, das tatsächlich im iterierten Sammelbereich enthalten ist.

*Ergebnis*<br/>
Ein Ausgabeiterator, der das erste Element eines Zielbereichs adressiert, in dem die Reihe von Teilsummen oder die Ergebnisse des angegebenen Vorgangs gespeichert werden sollen.

*binary_op*<br/>
Der binäre Vorgang, der im allgemeinen Vorgang angewendet werden soll, der den Vorgang der Summierung im Teilsummenverfahren ersetzt.

### <a name="return-value"></a>Rückgabewert

Ein Ausgabeiterator, der das Ende des Zielbereichs adressiert: `result` + (`last` - `first`),

### <a name="remarks"></a>Hinweise

Der Ausgabeiterator *Ergebnis* darf derselbe Iterator sein wie der eingabeiterator *erste*, sodass Teilsummen direkt berechnet werden können.

Bei einer Sequenz der Werte *a*1, *a*2, *a*3 in einem Eingabebereich speichert die erste Vorlagenfunktion aufeinander folgende Teilsummen im Zielbereich, in dem das *i*.-Element durch (  ( (*a*1 + *a*2) + *a*3) *a*i) angegeben ist.

Für eine Sequenz von Werten *eine*1, *eine*2, *eine*3, in einem Eingabebereich die zweite Vorlagenfunktion speichert aufeinander folgende Teilsummen im Zielbereich, das IT-Element steht Angabe durch ((( *eine*1 `binary_op` *eine* (2)`binary_op` *eine* (3)*eine*ich).

Der binäre Vorgang *Binary_op* muss nicht assoziativ oder kommutativ sein, da die Reihenfolge der Vorgänge vollständig angegeben wird.

### <a name="example"></a>Beispiel

```cpp
// numeric_partial_sum.cpp
// compile with: /EHsc
#include <vector>
#include <list>
#include <numeric>
#include <functional>
#include <iostream>

int main( )
{
   using namespace std;
   vector<int> V1( 10 ), V2( 10 );
   vector<int>::iterator VIter1, VIter2, VIterend, VIterend2;

   list <int> L1;
   list <int>::iterator LIter1, LIterend;

   int t;
   for ( t = 1 ; t <= 10 ; t++ )
   {
      L1.push_back( t );
   }

   cout << "The input list L1 is:\n ( " ;
   for ( LIter1 = L1.begin( ) ; LIter1 != L1.end( ) ; LIter1++ )
      cout << *LIter1 << " ";
   cout << ")." << endl;

   // The first member function for the partial sums of
   // elements in a list output to a vector
   VIterend = partial_sum ( L1.begin ( ) , L1.end ( ) ,
      V1.begin ( ) );

   cout << "The output vector containing the partial sums is:\n ( " ;
   for ( VIter1 = V1.begin( ) ; VIter1 != VIterend ; VIter1++ )
      cout << *VIter1 << " ";
   cout << ")." << endl;

   // The second member function used to compute
   // the partial product of the elements in a list
   VIterend2 = partial_sum ( L1.begin ( ) , L1.end ( ) , V2.begin ( ) ,
      multiplies<int>( ) );

   cout << "The output vector with the partial products is:\n ( " ;
   for ( VIter2 = V2.begin( ) ; VIter2 != VIterend2 ; VIter2++ )
      cout << *VIter2 << " ";
   cout << ")." << endl;

   // Computation of partial sums in place
   LIterend = partial_sum ( L1.begin ( ) , L1.end ( ) , L1.begin ( ) );
   cout << "The in place output partial_sum list L1 is:\n ( " ;
   for ( LIter1 = L1.begin( ) ; LIter1 != LIterend ; LIter1++ )
      cout << *LIter1 << " ";
   cout << ")." << endl;
}
```

## <a name="see-also"></a>Siehe auch

[\<numeric>](../standard-library/numeric.md)<br/>
