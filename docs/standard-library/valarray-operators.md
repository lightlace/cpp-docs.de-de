---
title: '&lt;valarray&gt;-Operatoren | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- valarray/std::operator!=
- valarray/std::operator%
- valarray/std::operator&amp;
- valarray/std::operator&amp;&amp;
- valarray/std::operator&gt;
- valarray/std::operator&gt;&gt;
- valarray/std::operator&gt;=
- valarray/std::operator&lt;
- valarray/std::operator&lt;&lt;
- valarray/std::operator&lt;=
- valarray/std::operator*
- valarray/std::operator+
- valarray/std::operator-
- valarray/std::operator/
- valarray/std::operator==
- valarray/std::operator^
- valarray/std::operator|
- valarray/std::operator||
dev_langs:
- C++
ms.assetid: 8a53562c-90ab-4eb3-85d3-ada5259d90b0
helpviewer_keywords:
- std::operator!= (valarray), std::operator&amp; (valarray)
- std::operator&amp;&amp; (valarray)
- std::operator&gt; (valarray)
- std::operator&gt;&gt; (valarray)
- std::operator&gt;= (valarray)
- std::operator&lt; (valarray)
- std::operator&lt;&lt; (valarray)
- std::operator&lt;= (valarray), std::operator== (valarray)
ms.openlocfilehash: 83958ee300143463a1da9b10d2edb6eb1707ec4f
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45703559"
---
# <a name="ltvalarraygt-operators"></a>&lt;valarray&gt;-Operatoren

||||
|-|-|-|
|[operator!=](#op_neq)|[operator%](#op_mod)|[operator&amp;](#op_amp)|
|[operator&amp;&amp;](#op_amp_amp)|[operator&gt;](#op_gt)|[operator&gt;&gt;](#op_gt_gt)|
|[operator&gt;=](#op_gt_eq)|[operator&lt;](#op_lt)|[operator&lt;&lt;](#op_lt_lt)|
|[operator&lt;=](#op_lt_eq)|[operator*](#op_star)|[operator+](#op_add)|
|[operator-](#operator-)|[operator/](#op_div)|[operator==](#op_eq_eq)|
|[operator^](#op_xor)|[operator|](#op_or)|[operator||](#op_lor)|

## <a name="op_neq"></a> operator!=

Überprüft, ob die entsprechenden Elemente von zwei gleich großen valarray-Objekten ungleich sind oder ob alle Elemente eines valarray-Objekts entsprechend einem angegebenen Wert ungleich sind.

```cpp
template <class Type>
valarray<bool>
operator!=(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<bool>
operator!=(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<bool>
operator!=(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Das erste der beiden valarray-Objekte, deren Elemente auf Ungleichheit getestet werden sollen.

*right*<br/>
Das zweite der beiden valarray-Objekte, deren Elemente auf Ungleichheit getestet werden sollen.

### <a name="return-value"></a>Rückgabewert

Ein valarray-Objekt mit booleschen Werten, für die Folgendes gilt:

- **TRUE**, wenn die entsprechenden Elemente ungleich sind.

- **FALSE**, wenn die entsprechenden Elemente nicht ungleich sind.

### <a name="remarks"></a>Hinweise

Der erste Vorlagenoperator gibt ein Objekt der Klasse [Valarray\<Bool >](../standard-library/valarray-bool-class.md), jedes, deren Elemente `I` ist `left[I] != right[I]`.

Der zweite Vorlagenoperator speichert in Element `I` `left[I] != right`.

Der dritte Vorlagenoperator speichert in Element `I` `left != right[I]`.

### <a name="example"></a>Beispiel

```cpp
// valarray_op_ne.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   valarray<bool> vaNE ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  -i;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i;
   for ( i = 0 ; i < 10 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial Left valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL != vaR );
   cout << "The element-by-element result of "
        << "the not equal comparison test is the\n valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
/* Output:
The initial Left valarray is: ( 0 1 -2 3 -4 5 -6 7 -8 9 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 8 9 ).
The element-by-element result of the not equal comparison test is the
 valarray: ( 0 0 1 0 1 0 1 0 1 0 ).
*/
```

## <a name="op_mod"></a> operator%

Ruft den Rest der Division der entsprechenden Elemente von zwei gleich großen valarray-Objekten oder der Division eines valarray-Objekts durch einen angegebenen Wert oder der Division eines angegebenen Werts durch ein valarray-Objekt ab.

```cpp
template <class Type>
valarray<Type>
operator%(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<Type>
operator%(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<Type>
operator%(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Ein Wert oder ein valarray-Objekt, der bzw. das als Dividend dient, durch den ein anderer Wert oder ein anderes valarray-Objekt dividiert wird.

*right*<br/>
Ein Wert oder ein valarray-Objekt, der bzw. das als Divisor dient und der einen anderen Wert oder ein anderes valarray-Objekt dividiert.

### <a name="return-value"></a>Rückgabewert

Ein valarray-Objekt, dessen Elemente den elementweisen Reste der *linken* geteilt durch *rechten*.

### <a name="example"></a>Beispiel

```cpp
// valarray_op_rem.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 6 ), vaR ( 6 );
   valarray<int> vaREM ( 6 );
   for ( i = 0 ; i < 6 ; i += 2 )
      vaL [ i ] =  53;
   for ( i = 1 ; i < 6 ; i += 2 )
      vaL [ i ] =  -67;
   for ( i = 0 ; i < 6 ; i++ )
      vaR [ i ] =  3*i+1;

   cout << "The initial Left valarray is: ( ";
      for ( i = 0 ; i < 6 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 6 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaREM = ( vaL % vaR );
   cout << "The remainders from the element-by-element "
        << "division is the\n valarray: ( ";
      for ( i = 0 ; i < 6 ; i++ )
         cout << vaREM [ i ] << " ";
   cout << ")." << endl;
}
/* Output:
The initial Left valarray is: ( 53 -67 53 -67 53 -67 ).
The initial Right valarray is: ( 1 4 7 10 13 16 ).
The remainders from the element-by-element division is the
 valarray: ( 0 -3 4 -7 1 -3 ).
*/
```

## <a name="op_amp"></a> operator&amp;

Ruft das bitweise **AND** zwischen den entsprechenden Elementen von zwei gleich großen valarray-Objekten oder zwischen einem valarray-Objekt und einem angegebenen Wert des Elementtyps ab.

```cpp
template <class Type>
valarray<Type>
operator&(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<Type>
operator&(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<Type>
operator&(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Das erste der beiden valarray-Objekte, deren Elemente jeweils mit dem bitweisen `AND`-Operator verknüpft werden soll, oder ein angegebener Wert des Elementtyps, der bitweise mit den Elementen eines valarray-Objekts verknüpft werden soll.

*right*<br/>
Das zweite der beiden valarray-Objekte, deren Elemente jeweils mit dem bitweisen `AND`-Operator verknüpft werden soll, oder ein angegebener Wert des Elementtyps, der bitweise mit den Elementen eines valarray-Objekts verknüpft werden soll.

### <a name="return-value"></a>Rückgabewert

Ein valarray-Objekt, dessen Elemente die elementweise Verknüpfung der bitweisen AND-Operation von *linken* und *rechten*.

### <a name="remarks"></a>Hinweise

Eine bitweise Operation kann nur verwendet werden, um Bits in **Char** und **Int** -Datentypen und-Varianten und nicht in **"float"**, **doppelte**, **Longdouble**, **"void"**, **"bool"** oder in anderen komplexeren Datentypen.

Für die bitweise `AND`-Operation gilt dieselbe Wahrheitstabelle wie für die logische `AND`-Operation. Die bitweise OR-Operation wird jedoch nur auf den Datentyp auf der Ebene der Einzelbits angewendet. Der [operator&&](../standard-library/valarray-operators.md#amp) wird auf Elementebene angewendet, wobei alle Werte, die nicht null sind, als TRUE zählen, und das Ergebnis ein valarray-Objekt mit booleschen Werten ist. Der bitweise **ANDoperator&** kann dagegen je nach dem Ergebnis der bitweisen Operation ein valarray-Objekt mit anderen Werten als 0 und 1 ergeben.

### <a name="example"></a>Beispiel

```cpp
// valarray_op_bitand.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   valarray<int> vaBWA ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  0;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i+1;
   for ( i = 0 ; i < 10 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial Left valarray is:  ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaBWA = ( vaL & vaR );
   cout << "The element-by-element result of "
        << "the bitwise operator & is the\n valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaBWA [ i ] << " ";
   cout << ")." << endl;
}
/* Output:
The initial Left valarray is:  ( 0 2 0 4 0 6 0 8 0 10 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 8 9 ).
The element-by-element result of the bitwise operator & is the
 valarray: ( 0 0 0 0 0 4 0 0 0 8 ).
*/
```

## <a name="op_amp_amp"></a> operator&amp;&amp;

Ruft das logische **AND** zwischen den entsprechenden Elementen von zwei gleich großen valarray-Objekten oder zwischen einem valarray-Objekt und einem angegebenen Wert des Elementtyps des valarray-Objekts ab.

```cpp
template <class Type>
valarray<bool>
operator&&(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<bool>
operator&&(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<bool>
operator&&(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Das erste der beiden valarray-Objekte, deren Elemente jeweils mit dem logischen `AND`-Operator verknüpft werden soll, oder ein angegebener Wert des Elementtyps, der mit den Elementen eines valarray-Objekts verknüpft werden soll.

*right*<br/>
Das zweite der beiden valarray-Objekte, deren Elemente jeweils mit dem logischen `AND`-Operator verknüpft werden soll, oder ein angegebener Wert des Elementtyps, der mit den Elementen eines valarray-Objekts verknüpft werden soll.

### <a name="return-value"></a>Rückgabewert

Ein valarray-Objekt, dessen Elemente vom Typ "bool" und die elementweise Verknüpfung der logischen `AND` Vorgang *linken* und *rechten*.

### <a name="remarks"></a>Hinweise

Die logische `ANDoperator&&` gilt auf Elementebene, zählen alle Werte als "true", und das Ergebnis ein valarray-Objekt mit booleschen Werten ist. Die bitweise Version von `AND`, [Operator &,](../standard-library/valarray-operators.md#op_amp), im Gegensatz dazu kann dazu führen, mit anderen Werten als 0 oder 1, abhängig vom Ergebnis der bitweisen Operation ein valarray-Objekt.

### <a name="example"></a>Beispiel

```cpp
// valarray_op_logand.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   valarray<bool> vaLAA ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  0;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i-1;
   for ( i = 0 ; i < 10 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial Left valarray is:  ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaLAA = ( vaL && vaR );
   cout << "The element-by-element result of "
        << "the logical AND operator&& is the\n valarray: ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaLAA [ i ] << " ";
   cout << ")." << endl;
}
/* Output:
The initial Left valarray is:  ( 0 0 0 2 0 4 0 6 0 8 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 8 9 ).
The element-by-element result of the logical AND operator&& is the
 valarray: ( 0 0 0 1 0 1 0 1 0 1 ).
*/
```

## <a name="op_gt"></a> operator&gt;

Überprüft, ob die Elemente eines valarray-Objekts größer sind als die Elemente eines gleich großen valarray-Objekts oder ob alle Elemente eines valarray-Objekts größer oder kleiner sind als ein angegebener Wert.

```cpp
template <class Type>
valarray<bool>
operator>(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<bool>
operator>(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<bool>
operator>(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Das erste der beiden valarray-Objekte, deren Elemente verglichen werden sollen, oder ein angegebener Wert, der mit den Elementen eines valarray-Objekts verglichen werden sollen.

*right*<br/>
Das zweite der beiden valarray-Objekte, deren Elemente verglichen werden sollen, oder ein angegebener Wert, der mit den Elementen eines valarray-Objekts verglichen werden sollen.

### <a name="return-value"></a>Rückgabewert

Ein valarray-Objekt mit booleschen Werten, für die Folgendes gilt:

- **"true"** Wenn die *linken* -Element oder der Wert ist größer als die entsprechende *rechten* -Element oder Wert.

- **"false"** Wenn die *linken* -Element oder der Wert ist nicht größer als die entsprechende *rechten* -Element oder Wert.

### <a name="remarks"></a>Hinweise

Wenn die Anzahl von Elementen in zwei valarray-Objekten nicht übereinstimmt, ist das Ergebnis nicht definiert.

### <a name="example"></a>Beispiel

```cpp
// valarray_op_gt.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   valarray<bool> vaNE ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  -i;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i;
   for ( i = 0 ; i < 10 ; i++ )
      vaR [ i ] =  i - 1;

   cout << "The initial Left valarray is: ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL > vaR );
   cout << "The element-by-element result of "
        << "the greater than comparison test is the\n valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
/* Output:
The initial Left valarray is: ( 0 1 -2 3 -4 5 -6 7 -8 9 ).
The initial Right valarray is: ( -1 0 1 2 3 4 5 6 7 8 ).
The element-by-element result of the greater than comparison test is the
 valarray: ( 1 1 0 1 0 1 0 1 0 1 ).
*/
```

## <a name="op_gt_eq"></a> operator&gt;=

Überprüft, ob die Elemente eines valarray-Objekts größer gleich den Elementen eines gleich großen valarray-Objekts oder ob alle Elemente eines valarray-Objekts größer gleich oder kleiner gleich einem angegebenen Wert sind.

```cpp
template <class Type>
valarray<bool>
operator>=(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<bool>
operator>=(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<bool>
operator>=(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Das erste der beiden valarray-Objekte, deren Elemente verglichen werden sollen, oder ein angegebener Wert, der mit den Elementen eines valarray-Objekts verglichen werden sollen.

*right*<br/>
Das zweite der beiden valarray-Objekte, deren Elemente verglichen werden sollen, oder ein angegebener Wert, der mit den Elementen eines valarray-Objekts verglichen werden sollen.

### <a name="return-value"></a>Rückgabewert

Ein valarray-Objekt mit booleschen Werten, für die Folgendes gilt:

- **"true"** Wenn die *linken* -Element oder der Wert ist größer als oder gleich dem entsprechenden *rechten* -Element oder Wert.

- **"false"** Wenn die *linken* -Element oder der Wert ist kleiner als die entsprechende *rechten* -Element oder Wert.

### <a name="remarks"></a>Hinweise

Wenn die Anzahl von Elementen in zwei valarray-Objekten nicht übereinstimmt, ist das Ergebnis nicht definiert.

### <a name="example"></a>Beispiel

```cpp
// valarray_op_ge.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   valarray<bool> vaNE ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  -i;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i;
   for ( i = 0 ; i < 10 ; i++ )
      vaR [ i ] =  i - 1;

   cout << "The initial Left valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL >= vaR );
   cout << "The element-by-element result of "
        << "the greater than or equal test is the\n valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
/* Output:
The initial Left valarray is: ( 0 1 -2 3 -4 5 -6 7 -8 9 ).
The initial Right valarray is: ( -1 0 1 2 3 4 5 6 7 8 ).
The element-by-element result of the greater than or equal test is the
 valarray: ( 1 1 0 1 0 1 0 1 0 1 ).
*/
```

## <a name="op_gt_gt"></a> operator&gt;&gt;

Verschiebt die Bits für jedes Element eines valarray-Objekts um eine angegebene Anzahl von Positionen oder um einen elementweisen Betrag, der durch ein zweites valarray-Objekt angegeben ist, nach rechts.

```cpp
template <class Type>
valarray<Type>
operator>>(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<Type>
operator>>(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<Type>
operator>>(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Der Wert, der verschoben werden soll, oder das valarray-Objekt, dessen Elemente verschoben werden sollen.

*right*<br/>
Der Wert, der den Betrag angibt, um den die Bits nach rechts verschoben werden, oder das valarray-Objekt, dessen Elemente den elementweisen Betrag angeben, um den die Bits nach rechts verschoben werden.

### <a name="return-value"></a>Rückgabewert

Ein valarray-Objekt, dessen Elemente um den angegebenen Betrag nach rechts verschoben wurden.

### <a name="remarks"></a>Hinweise

Bei Zahlen mit Vorzeichen bleiben die Vorzeichen erhalten.

### <a name="example"></a>Beispiel

```cpp
// valarray_op_rs.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 8 ), vaR ( 8 );
   valarray<int> vaNE ( 8 );
   for ( i = 0 ; i < 8 ; i += 2 )
      vaL [ i ] =  64;
   for ( i = 1 ; i < 8 ; i += 2 )
      vaL [ i ] =  -64;
   for ( i = 0 ; i < 8 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial Left valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL >> vaR );
   cout << "The element-by-element result of "
        << "the right shift is the\n valarray: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
/* Output:
The initial Left valarray is: ( 64 -64 64 -64 64 -64 64 -64 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the right shift is the
 valarray: ( 64 -32 16 -8 4 -2 1 -1 ).
*/
```

## <a name="op_lt"></a> operator&lt;

Überprüft, ob die Elemente eines valarray-Objekts kleiner sind als die Elemente eines gleich großen valarray-Objekts oder ob alle Elemente eines valarray-Objekts größer oder kleiner sind als ein angegebener Wert.

```cpp
template <class Type>
valarray<bool>
operator<(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<bool>
operator<(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<bool>
operator<(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Das erste der beiden valarray-Objekte, deren Elemente verglichen werden sollen, oder ein angegebener Wert, der mit den Elementen eines valarray-Objekts verglichen werden sollen.

*right*<br/>
Das zweite der beiden valarray-Objekte, deren Elemente verglichen werden sollen, oder ein angegebener Wert, der mit den Elementen eines valarray-Objekts verglichen werden sollen.

### <a name="return-value"></a>Rückgabewert

Ein valarray-Objekt mit booleschen Werten, für die Folgendes gilt:

- **"true"** Wenn die *linken* -Element oder der Wert ist kleiner als die entsprechende *rechten* -Element oder Wert.

- **"false"** Wenn die *linken* -Element oder der Wert ist nicht kleiner als die entsprechende *rechten* -Element oder Wert.

### <a name="remarks"></a>Hinweise

Wenn die Anzahl von Elementen in zwei valarray-Objekten nicht übereinstimmt, ist das Ergebnis nicht definiert.

### <a name="example"></a>Beispiel

```cpp
// valarray_op_lt.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   valarray<bool> vaNE ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  -i;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i;
   for ( i = 0 ; i < 10 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial Left valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL < vaR );
   cout << "The element-by-element result of "
        << "the less-than comparson test is the\n valarray: ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
/* Output:
The initial Left valarray is: ( 0 1 -2 3 -4 5 -6 7 -8 9 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 8 9 ).
The element-by-element result of the less-than comparson test is the
 valarray: ( 0 0 1 0 1 0 1 0 1 0 ).
*/
```

## <a name="op_lt_eq"></a> operator&lt;=

Überprüft, ob die Elemente eines valarray-Objekts kleiner gleich den Elementen eines gleich großen valarray-Objekts oder ob alle Elemente eines valarray-Objekts größer gleich oder kleiner gleich einem angegebenen Wert sind.

```cpp
template <class Type>
valarray<bool>
operator<=(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<bool>
operator<=(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<bool>
operator<=(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Das erste der beiden valarray-Objekte, deren Elemente verglichen werden sollen, oder ein angegebener Wert, der mit den Elementen eines valarray-Objekts verglichen werden sollen.

*right*<br/>
Das zweite der beiden valarray-Objekte, deren Elemente verglichen werden sollen, oder ein angegebener Wert, der mit den Elementen eines valarray-Objekts verglichen werden sollen.

### <a name="return-value"></a>Rückgabewert

Ein valarray-Objekt mit booleschen Werten, für die Folgendes gilt:

- **"true"** Wenn die *linken* -Element oder der Wert ist kleiner oder gleich dem entsprechenden *rechten* -Element oder Wert.

- **"false"** Wenn die *linken* -Element oder der Wert ist größer als die entsprechende *rechten* -Element oder Wert.

### <a name="remarks"></a>Hinweise

Wenn die Anzahl von Elementen in zwei valarray-Objekten nicht übereinstimmt, ist das Ergebnis nicht definiert.

### <a name="example"></a>Beispiel

```cpp
// valarray_op_le.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   valarray<bool> vaNE ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  -i;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i;
   for ( i = 0 ; i < 10 ; i++ )
      vaR [ i ] =  i - 1;

   cout << "The initial Left valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL <= vaR );
   cout << "The element-by-element result of "
        << "the less than or equal test is the\n valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
/* Output:
The initial Left valarray is: ( 0 1 -2 3 -4 5 -6 7 -8 9 ).
The initial Right valarray is: ( -1 0 1 2 3 4 5 6 7 8 ).
The element-by-element result of the less than or equal test is the
 valarray: ( 0 0 1 0 1 0 1 0 1 0 ).
*/
```

## <a name="op_lt_lt"></a> operator&lt;&lt;

Verschiebt die Bits für jedes Element eines valarray-Objekts um eine angegebene Anzahl von Positionen oder um einen elementweisen Betrag, der durch ein zweites valarray-Objekt angegeben ist, nach links.

```cpp
template <class Type>
valarray<Type>
operator<<(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<Type>
operator<<(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<Type>
operator<<(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Der Wert, der verschoben werden soll, oder das valarray-Objekt, dessen Elemente verschoben werden sollen.

*right*<br/>
Der Wert, der den Betrag angibt, um den die Bits nach links verschoben werden, oder das valarray-Objekt, dessen Elemente den elementweisen Betrag angeben, um den die Bits nach links verschoben werden.

### <a name="return-value"></a>Rückgabewert

Ein valarray-Objekt, dessen Elemente um den angegebenen Betrag nach links verschoben wurden.

### <a name="remarks"></a>Hinweise

Bei Zahlen mit Vorzeichen bleiben die Vorzeichen erhalten.

### <a name="example"></a>Beispiel

```cpp
// valarray_op_ls.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 8 ), vaR ( 8 );
   valarray<int> vaNE ( 8 );
   for ( i = 0 ; i < 8 ; i += 2 )
      vaL [ i ] =  1;
   for ( i = 1 ; i < 8 ; i += 2 )
      vaL [ i ] =  -1;
   for ( i = 0 ; i < 8 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial Left valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL << vaR );
   cout << "The element-by-element result of "
        << "the left shift is the\n valarray: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
/* Output:
The initial Left valarray is: ( 1 -1 1 -1 1 -1 1 -1 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the left shift is the
 valarray: ( 1 -2 4 -8 16 -32 64 -128 ).
*/
```

## <a name="op_star"></a> operator*

Ruft das elementweise Produkt zwischen den entsprechenden Elementen von zwei gleich großen valarray-Objekten oder zwischen einem valarray-Objekt und einem angegebenen Wert ab.

```cpp
template <class Type>
valarray<Type>
operator*(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<Type>
operator*(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<Type>
operator*(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Das erste der beiden valarray-Objekte, deren Elemente multipliziert werden sollen, oder ein angegebener Wert, der mit den Elementen eines valarray-Objekts multipliziert werden sollen.

*right*<br/>
Das zweite der beiden valarray-Objekte, deren Elemente multipliziert werden sollen, oder ein angegebener Wert, der mit den Elementen eines valarray-Objekts multipliziert werden sollen.

### <a name="return-value"></a>Rückgabewert

Ein valarray-Objekt, dessen Elemente das elementweise Produkt der *linken* und *rechten*.

### <a name="example"></a>Beispiel

```cpp
// valarray_op_eprod.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 8 ), vaR ( 8 );
   valarray<int> vaNE ( 8 );
   for ( i = 0 ; i < 8 ; i += 2 )
      vaL [ i ] =  2;
   for ( i = 1 ; i < 8 ; i += 2 )
      vaL [ i ] =  -1;
   for ( i = 0 ; i < 8 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial Left valarray is: ( ";
      for (i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for (i = 0 ; i < 8 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL * vaR );
   cout << "The element-by-element result of "
        << "the multiplication is the\n valarray: ( ";
      for (i = 0 ; i < 8 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
/* Output:
The initial Left valarray is: ( 2 -1 2 -1 2 -1 2 -1 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the multiplication is the
 valarray: ( 0 -1 4 -3 8 -5 12 -7 ).
*/
```

## <a name="op_add"></a> operator+

Ruft die elementweise Summe zwischen den entsprechenden Elementen von zwei gleich großen valarray-Objekten oder zwischen einem valarray-Objekt und einem angegebenen Wert ab.

```cpp
template <class Type>
valarray<Type>
operator+(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<Type>
operator+(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<Type>
operator+(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Das erste der beiden valarray-Objekte, deren Elemente addiert werden sollen, oder ein angegebener Wert, der mit den Elementen eines valarray-Objekts addiert werden sollen.

*right*<br/>
Das zweite der beiden valarray-Objekte, deren Elemente addiert werden sollen, oder ein angegebener Wert, der mit den Elementen eines valarray-Objekts addiert werden sollen.

### <a name="return-value"></a>Rückgabewert

Ein valarray-Objekt, dessen Elemente die elementweise Summe der *linken* und *rechten*.

### <a name="example"></a>Beispiel

```cpp
// valarray_op_esum.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 8 ), vaR ( 8 );
   valarray<int> vaNE ( 8 );
   for ( i = 0 ; i < 8 ; i += 2 )
      vaL [ i ] =  2;
   for ( i = 1 ; i < 8 ; i += 2 )
      vaL [ i ] =  -1;
   for ( i = 0 ; i < 8 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial Left valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL + vaR );
   cout << "The element-by-element result of "
        << "the sum is the\n valarray: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
/* Output:
The initial Left valarray is: ( 2 -1 2 -1 2 -1 2 -1 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the sum is the
 valarray: ( 2 0 4 2 6 4 8 6 ).
*/
```

## <a name="operator-"></a> operator-

Ruft die elementweise Differenz zwischen den entsprechenden Elementen von zwei gleich großen valarray-Objekten oder zwischen einem valarray-Objekt und einem angegebenen Wert ab.

```cpp
template <class Type>
valarray<Type>
operator-(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<Type>
operator-(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<Type>
operator-(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Ein Wert oder ein valarray-Objekt, das als Minuend dient, von dem andere Werte oder valarray-Objekte subtrahiert werden und so eine Differenz ergeben.

*right*<br/>
Ein Wert oder ein valarray-Objekt, das als Subtrahend dient, der von anderen Werten oder valarray-Objekten subtrahiert wird und so eine Differenz ergibt.

### <a name="return-value"></a>Rückgabewert

Ein valarray-Objekt, dessen Elemente die elementweise Differenz der *linken* und *rechten*.

### <a name="remarks"></a>Hinweise

Die arithmetische Terminologie, die zum Beschreiben einer Subtraktion verwendet wird:

Differenz = Minuend - Subtrahend

### <a name="example"></a>Beispiel

```cpp
// valarray_op_ediff.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 8 ), vaR ( 8 );
   valarray<int> vaNE ( 8 );
   for ( i = 0 ; i < 8 ; i += 2 )
      vaL [ i ] =  10;
   for ( i = 1 ; i < 8 ; i += 2 )
      vaL [ i ] =  0;
   for ( i = 0 ; i < 8 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial Left valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL - vaR );
   cout << "The element-by-element result of "
        << "the difference is the\n valarray: ( ";
      for (i = 0 ; i < 8 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
/* Output:
The initial Left valarray is: ( 10 0 10 0 10 0 10 0 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the difference is the
 valarray: ( 10 -1 8 -3 6 -5 4 -7 ).
*/
```

## <a name="op_div"></a> operator/

Ruft den elementweise Quotienten zwischen den entsprechenden Elementen von zwei gleich großen valarray-Objekten oder zwischen einem valarray-Objekt und einem angegebenen Wert ab.

```cpp
template <class Type>
valarray<Type>
operator/(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<Type>
operator/(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<Type>
operator/(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Ein Wert oder ein valarray-Objekt, der bzw. das als Dividend dient, durch den ein anderer Wert oder ein anderes valarray-Objekt dividiert wird und so den Quotienten ergibt.

*right*<br/>
Ein Wert oder ein valarray-Objekt, der bzw. das als Divisor dient und der einen anderen Wert oder ein anderes valarray-Objekt dividiert und so den Quotienten ergibt.

### <a name="return-value"></a>Rückgabewert

Ein valarray-Objekt, dessen Elemente den elementweisen Quotienten von *linken* geteilt durch *rechten*.

### <a name="remarks"></a>Hinweise

Die arithmetische Terminologie, die zum Beschreiben einer Division verwendet wird:

Quotient = Dividend/Divisor

### <a name="example"></a>Beispiel

```cpp
// valarray_op_equo.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<double> vaL ( 6 ), vaR ( 6 );
   valarray<double> vaNE ( 6 );
   for ( i = 0 ; i < 6 ; i += 2 )
      vaL [ i ] =  100;
   for ( i = 1 ; i < 6 ; i += 2 )
      vaL [ i ] =  -100;
   for ( i = 0 ; i < 6 ; i++ )
      vaR [ i ] =  2*i;

   cout << "The initial Left valarray is: ( ";
      for ( i = 0 ; i < 6 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 6 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL / vaR );
   cout << "The element-by-element result of "
        << "the quotient is the\n valarray: ( ";
      for ( i = 0 ; i < 6 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
/* Output:
The initial Left valarray is: ( 100 -100 100 -100 100 -100 ).
The initial Right valarray is: ( 0 2 4 6 8 10 ).
The element-by-element result of the quotient is the
 valarray: ( inf -50 25 -16.6667 12.5 -10 ).
*/
```

## <a name="op_eq_eq"></a> operator==

Überprüft, ob die entsprechenden Elemente von zwei gleich großen valarray-Objekten gleich sind oder ob alle Elemente eines valarray-Objekts entsprechend einem angegebenen Wert gleich sind.

```cpp
template <class Type>
valarray<bool>
operator==(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<bool>
operator==(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<bool>
operator==(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Das erste der beiden valarray-Objekte, deren Elemente auf Gleichheit getestet werden sollen.

*right*<br/>
Das zweite der beiden valarray-Objekte, deren Elemente auf Gleichheit getestet werden sollen.

### <a name="return-value"></a>Rückgabewert

Ein valarray-Objekt mit booleschen Werten, für die Folgendes gilt:

- **TRUE**, wenn die entsprechenden Elemente gleich sind.

- **FALSE**, wenn die entsprechenden Elemente nicht gleich sind.

### <a name="remarks"></a>Hinweise

Der erste Vorlagenoperator gibt ein Objekt der Klasse [Valarray\<Bool >](../standard-library/valarray-bool-class.md), jedes, deren Elemente `I` ist `left[I] == right[I]`. Der zweite Vorlagenoperator speichert in Element `I` `left[I] == right`. Der dritte Vorlagenoperator speichert in Element `I` `left == right[I]`.

### <a name="example"></a>Beispiel

```cpp
// valarray_op_eq.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   valarray<bool> vaNE ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  -i;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i;
   for ( i = 0 ; i < 10 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial Left valarray is: ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL == vaR );
   cout << "The element-by-element result of "
        << "the equality comparison test is the\n valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
/* Output:
The initial Left valarray is: ( 0 1 -2 3 -4 5 -6 7 -8 9 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 8 9 ).
The element-by-element result of the equality comparison test is the
 valarray: ( 1 1 0 1 0 1 0 1 0 1 ).
*/
```

## <a name="op_xor"></a> operator^

Ruft das bitweise exklusive `OR` ( **XOR**) zwischen den entsprechenden Elementen von zwei gleich großen valarray-Objekten oder zwischen einem valarray-Objekt und einem angegebenen Wert des Elementtyps ab.

```cpp
template <class Type>
valarray<Type>
operator^(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<Type>
operator^(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<Type>
operator^(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Das erste der beiden valarray-Objekte, deren Elemente jeweils mit dem bitweisen **XOR**-Operator verknüpft werden soll, oder ein angegebener Wert des Elementtyps, der bitweise mit den Elementen eines valarray-Objekts verknüpft werden soll.

*right*<br/>
Das zweite der beiden valarray-Objekte, deren Elemente jeweils mit dem bitweisen **XOR**-Operator verknüpft werden soll, oder ein angegebener Wert des Elementtyps, der bitweise mit den Elementen eines valarray-Objekts verknüpft werden soll.

### <a name="return-value"></a>Rückgabewert

Ein valarray-Objekt, dessen Elemente die elementweise Verknüpfung der bitweisen **XOR** Vorgang *linken* und *rechten*.

### <a name="remarks"></a>Hinweise

Eine bitweise Operation kann nur verwendet werden, um Bits in **Char** und **Int** -Datentypen und-Varianten und nicht in **"float"**, **doppelte**, **long double**, **"void"**, **"bool"** oder in anderen komplexeren Datentypen.

Der Operator exklusives `OR` ( **XOR**) weist die folgende Semantik auf: Wenn die Bits *b*1 und *b*2 gegeben sind, ist *b*1 **XOR** *b*2 **TRUE**, wenn exakt eines der Bits TRUE ist; **FALSE**, wenn beide Bits FALSE sind oder beide Bits TRUE sind.

### <a name="example"></a>Beispiel

```cpp
// valarray_op_xor.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   valarray<int> vaLAA ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  1;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  0;
   for ( i = 0 ; i < 10 ; i += 3 )
      vaR [ i ] =  i;
   for ( i = 1 ; i < 10 ; i += 3 )
      vaR [ i ] =  i-1;
   for ( i = 2 ; i < 10 ; i += 3 )
      vaR [ i ] =  i-1;

   cout << "The initial Left valarray is:  ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaLAA = ( vaL ^ vaR );
   cout << "The element-by-element result of "
        << "the bitwise XOR operator^ is the\n valarray: ( ";
           for ( i = 0 ; i < 10 ; i++ )
         cout << vaLAA [ i ] << " ";
   cout << ")." << endl;
}
/* Output:
The initial Left valarray is:  ( 1 0 1 0 1 0 1 0 1 0 ).
The initial Right valarray is: ( 0 0 1 3 3 4 6 6 7 9 ).
The element-by-element result of the bitwise XOR operator^ is the
 valarray: ( 1 0 0 3 2 4 7 6 6 9 ).
*/
```

## <a name="op_or"></a> operator|

Ruft das bitweise `OR` zwischen den entsprechenden Elementen von zwei gleich großen valarray-Objekten oder zwischen einem valarray-Objekt und einem angegebenen Wert des Elementtyps ab.

```cpp
template <class Type>
valarray<Type>
operator|(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<Type>
operator|(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<Type>
operator|(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Das erste der beiden valarray-Objekte, deren Elemente jeweils mit dem bitweisen `OR`-Operator verknüpft werden soll, oder ein angegebener Wert des Elementtyps, der bitweise mit den Elementen eines valarray-Objekts verknüpft werden soll.

*right*<br/>
Das zweite der beiden valarray-Objekte, deren Elemente jeweils mit dem bitweisen `OR`-Operator verknüpft werden soll, oder ein angegebener Wert des Elementtyps, der bitweise mit den Elementen eines valarray-Objekts verknüpft werden soll.

### <a name="return-value"></a>Rückgabewert

Ein valarray-Objekt, dessen Elemente die elementweise Verknüpfung der bitweisen `OR` Vorgang *linken* und *rechten*.

### <a name="remarks"></a>Hinweise

Eine bitweise Operation kann nur verwendet werden, um Bits in **Char** und **Int** -Datentypen und-Varianten und nicht in **"float"**, **doppelte**, **Longdouble**, **"void"**, **"bool"** oder in anderen komplexeren Datentypen.

Für die bitweise OR-Operation gilt dieselbe Wahrheitstabelle wie für die logische `OR`-Operation. Die bitweise OR-Operation wird jedoch nur auf den Datentyp auf der Ebene der Einzelbits angewendet. Wenn die Bits *b*1 und *b*2 gegeben sind, ist *b*1 `OR` *b*2 **TRUE**, wenn mindestens eines der Bits TRUE ist; **FALSE**, wenn beide Bits FALSE sind. Der logische `OR`[operator&#124;&#124;](../standard-library/valarray-operators.md#op_lor) wird auf Elementebene angewendet, wobei alle Werte, die nicht null sind, als **TRUE** zählen, und das Ergebnis ein valarray-Objekt mit booleschen Werten ist. Der bitweise OR `operator|` kann dagegen je nach dem Ergebnis der bitweisen Operation ein valarray-Objekt mit anderen Werten als 0 und 1 ergeben.

### <a name="example"></a>Beispiel

```cpp
// valarray_op_bitor.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   valarray<int> vaLAA ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  1;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  0;
   for ( i = 0 ; i < 10 ; i += 3 )
      vaR [ i ] =  i;
   for ( i = 1 ; i < 10 ; i += 3 )
      vaR [ i ] =  i-1;
   for ( i = 2 ; i < 10 ; i += 3 )
      vaR [ i ] =  i-1;

   cout << "The initial Left valarray is:  ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaLAA = ( vaL | vaR );
   cout << "The element-by-element result of "
        << "the bitwise OR operator| is the\n valarray: ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaLAA [ i ] << " ";
   cout << ")." << endl;
}
/* Output:
The initial Left valarray is:  ( 1 0 1 0 1 0 1 0 1 0 ).
The initial Right valarray is: ( 0 0 1 3 3 4 6 6 7 9 ).
The element-by-element result of the bitwise OR operator| is the
 valarray: ( 1 0 1 3 3 4 7 6 7 9 ).
*/
```

## <a name="op_lor"></a> operator||

Ruft das logische `OR` zwischen den entsprechenden Elementen von zwei gleich großen valarray-Objekten oder zwischen einem valarray-Objekt und einem angegebenen Wert des Elementtyps des valarray-Objekts ab.

```cpp
template <class Type>
valarray<bool>
operator||(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<bool>
operator||(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<bool>
operator||(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Parameter

*left*<br/>
Das erste der beiden valarray-Objekte, deren Elemente jeweils mit dem logischen `OR`-Operator verknüpft werden soll, oder ein angegebener Wert des Elementtyps, der mit den Elementen eines valarray-Objekts verknüpft werden soll.

*right*<br/>
Das zweite der beiden valarray-Objekte, deren Elemente jeweils mit dem logischen `OR`-Operator verknüpft werden soll, oder ein angegebener Wert des Elementtyps, der mit den Elementen eines valarray-Objekts verknüpft werden soll.

### <a name="return-value"></a>Rückgabewert

Ein valarray-Objekt, dessen Elemente vom Typ **"bool"** und die elementweise Verknüpfung der logischen OR-Operation von *linken* und *rechten*.

### <a name="remarks"></a>Hinweise

Die logische `OR` `operator||` wendet auf Elementebene, zählen alle ungleich NULL-Werte als **"true"**, und das Ergebnis ein valarray-Objekt mit booleschen Werten. Die bitweise Version von `OR`, [operator&#124;](../standard-library/valarray-operators.md#op_or) kann dagegen je nach dem Ergebnis der bitweisen Operation ein valarray-Objekt mit anderen Werten als 0 und 1 ergeben.

### <a name="example"></a>Beispiel

```cpp
// valarray_op_logor.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   valarray<bool> vaLOR ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  0;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i-1;
   for ( i = 0 ; i < 10 ; i += 3 )
      vaR [ i ] =  i;
   for ( i = 1 ; i < 10 ; i += 3 )
      vaR [ i ] =  0;
   for ( i = 2 ; i < 10 ; i += 3 )
      vaR [ i ] =  0;

   cout << "The initial Left valarray is:  ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaLOR = ( vaL || vaR );
   cout << "The element-by-element result of "
        << "the logical OR operator|| is the\n valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaLOR [ i ] << " ";
   cout << ")." << endl;
}
/* Output:
The initial Left valarray is:  ( 0 0 0 2 0 4 0 6 0 8 ).
The initial Right valarray is: ( 0 0 0 3 0 0 6 0 0 9 ).
The element-by-element result of the logical OR operator|| is the
 valarray: ( 0 0 0 1 0 1 1 1 0 1 ).
*/
```

## <a name="see-also"></a>Siehe auch

[\<valarray>](../standard-library/valarray.md)<br/>
