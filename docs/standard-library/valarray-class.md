---
title: valarray-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- valarray/std::valarray
- valarray/std::valarray::value_type
- valarray/std::valarray::apply
- valarray/std::valarray::cshift
- valarray/std::valarray::free
- valarray/std::valarray::max
- valarray/std::valarray::min
- valarray/std::valarray::resize
- valarray/std::valarray::shift
- valarray/std::valarray::size
- valarray/std::valarray::sum
- valarray/std::valarray::swap
dev_langs:
- C++
helpviewer_keywords:
- std::valarray [C++]
- std::valarray [C++], value_type
- std::valarray [C++], apply
- std::valarray [C++], cshift
- std::valarray [C++], free
- std::valarray [C++], max
- std::valarray [C++], min
- std::valarray [C++], resize
- std::valarray [C++], shift
- std::valarray [C++], size
- std::valarray [C++], sum
- std::valarray [C++], swap
ms.assetid: 19b862f9-5d09-4003-8844-6ddd02c1a3a7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9f95c9d85ab3649c1710881c73df1ae325f9cb60
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45724814"
---
# <a name="valarray-class"></a>valarray-Klasse

Die Vorlagenklasse beschreibt ein Objekt, das eine Sequenz von Elementen des Typs steuert `Type` , die als Array gespeichert, für das Ausführen von schnellen mathematischer Operations vorgesehen und für rechenbetonte Leistung optimiert werden.

## <a name="remarks"></a>Hinweise

Die Klasse ist eine Darstellung des mathematischen Konzepts einer sortierten Menge von Werten, und die Elemente werden fortlaufend ab null nummeriert. Die Klasse wird als Fastcontainer beschrieben, da sie einige, aber nicht alle Funktionen unterstützt, die von vollständigen Sequenzcontainern, wie etwa [vector](../standard-library/vector-class.md), unterstützt werden. Die Klasse unterscheidet sich in zwei wichtigen Aspekten von der vector-Vorlagenklasse:

- Sie definiert zahlreiche arithmetische Operationen zwischen entsprechenden Elementen von `valarray<Type>` Objekte desselben Typs und derselben Länge, wie z. B. *Xarr* = cos ( *Yarr*) + sin ( *Zarr*).

- Sie definiert verschiedene interessante Möglichkeiten zu indizieren einer `valarray<Type>` -Objekt durch Überladen [Operator&#91;&#93;](#op_at).

Ein Objekt der Klasse `Type`:

- Es hat einen öffentlichen Standardkonstruktor, Destruktor, Kopierkonstruktor und Zuweisungsoperator mit üblichem Verhalten.

- Es definiert nach Bedarf die arithmetischen Operatoren und mathematischen Funktionen, die für die Gleitkommatypen definiert sind (mit üblichem Verhalten).

Insbesondere dürfen keine feinen Unterschiede zwischen einer Kopierkonstruktion und einer Standardkonstruktion bestehen, auf die eine Zuweisung folgt. Keiner der Vorgänge für Objekte der Klasse `Type` möglicherweise Ausnahmen auslösen.

### <a name="constructors"></a>Konstruktoren

|Konstruktor|Beschreibung|
|-|-|
|[valarray](#valarray)|Erstellt ein `valarray`-Objekt einer bestimmten Größe oder mit Elementen eines bestimmten Werts oder als Kopie eines anderen `valarray`-Objekts oder als Teilmenge eines anderen `valarray`-Objekts.|

### <a name="typedefs"></a>Typedefs

|Typname|Beschreibung|
|-|-|
|[value_type](#value_type)|Ein Typ, der den Typ der in einem `valarray`-Objekt gespeicherten Elemente darstellt.|

### <a name="member-functions"></a>Memberfunktionen

|Member-Funktion|Beschreibung|
|-|-|
|[apply](#apply)|Wendet eine angegebene Funktion auf jedes Element eines `valarray`-Objekts an.|
|[cshift](#cshift)|Verschiebt zyklisch alle Elemente in einem `valarray`-Objekt um eine angegebene Anzahl von Positionen.|
|[free](#free)|Gibt den Arbeitsspeicher frei, der vom `valarray`-Objekt verwendet wird.|
|[max](#max)|Sucht nach dem größten Element in einem `valarray`-Objekt.|
|[min](#min)|Sucht nach dem kleinsten Element in einem `valarray`-Objekt.|
|[resize](#resize)|Ändert die Anzahl von Elementen in einem `valarray`-Objekt in die jeweils angegebene Anzahl, wozu Elemente nach Bedarf hinzugefügt oder entfernt werden.|
|[shift](#shift)|Verschiebt alle Elemente in einem `valarray`-Objekt um eine angegebene Anzahl von Positionen.|
|[size](#size)|Ermittelt die Anzahl von Elementen in einem `valarray`-Objekt.|
|[sum](#sum)|Bestimmt die Summe aller Elemente in einem `valarray`-Objekt mit einer Länge ungleich null.|
|[swap](#swap)||

### <a name="operators"></a>Operatoren

|Operator|Beschreibung|
|-|-|
|[operator!](#op_not)|Ein unärer Operator, der die logischen `NOT`-Werte jedes Elements eines `valarray`-Objekts abruft.|
|[operator%=](#op_mod_eq)|Ruft den Rest der Division der Elemente eines Arrays elementweise entweder entsprechend einem angegebenen `valarray`-Objekt oder entsprechend einem Wert des Elementtyps ab.|
|[operator&=](#op_amp_eq)|Ruft das bitweise `AND`-Ergebnis von Elementen eines Arrays entweder mit den entsprechenden Elementen in einem angegebenen `valarray`-Objekt oder mit einem Wert des Elementtyps ab.|
|[operator>>=](#op_gt_gt_eq)|Verschiebt die Bits für jedes Element eines `valarray`-Operanden um eine angegebene Anzahl von Positionen oder um einen elementweisen Betrag, der durch ein zweites `valarray`-Objekt angegeben ist, nach rechts.|
|[operator<<=](#op_lt_lt_eq)|Verschiebt die Bits für jedes Element eines `valarray`-Operanden um eine angegebene Anzahl von Positionen oder um einen elementweisen Betrag, der durch ein zweites `valarray`-Objekt angegeben ist, nach links.|
|[operator*=](#op_star_eq)|Multipliziert die Elemente eines angegebenen `valarray`-Objekts oder einen Wert des Elementtyps elementweise mit einem `valarray`-Operanden.|
|[operator+](#op_add)|Ein unärer Operator, der ein Pluszeichen auf jedes Element in einem `valarray`-Objekt anwendet.|
|[operator+=](#op_add_eq)|Fügt die Elemente eines angegebenen `valarray`-Objekts oder einen Wert des Elementtyps elementweise einem `valarray`-Operanden hinzu.|
|[operator-](#operator-)|Ein unärer Operator, der ein Minuszeichen auf jedes Element in einem `valarray`-Objekt anwendet.|
|[operator-=](#operator-_eq)|Subtrahiert die Elemente eines angegebenen `valarray`-Objekts oder einen Wert des Elementtyps elementweise von einem `valarray`-Operanden.|
|[operator/=](#op_div_eq)|Dividiert einen `valarray`-Operanden elementweise durch die Elemente eines angegebenen `valarray`-Objekts oder durch einen Wert des Elementtyps.|
|[operator=](#op_eq)|Ordnet einem `valarray`-Objekt Elemente zu, deren Werte entweder direkt oder als Teil eines anderen `valarray`-Objekts oder durch ein `slice_array`-, `gslice_array`-, `mask_array`- oder `indirect_array`-Objekt angegeben sind.|
|[operator[]](#op_at)|Gibt einen Verweis auf ein Element oder auf den Wert zurück, den es am angegebenen Index oder in der angegebenen Teilmenge hat.|
|[operator^=](#op_xor_eq)|Ruft den elementweisen logischen Operator exklusives Oder ( `XOR`) eines Arrays entweder mit einem angegebenen valarray-Objekt oder mit einem Wert des Elementtyps ab.|
|[operator|=](#op_or_eq)|Ruft das bitweise `OR`-Ergebnis von Elementen eines Arrays entweder mit den entsprechenden Elementen in einem angegebenen `valarray`-Objekt oder mit einem Wert des Elementtyps ab.|
|[operator~](#op_dtor)|Ein unärer Operator, der die bitweisen `NOT`-Werte jedes Elements eines `valarray`-Objekts abruft.|

## <a name="requirements"></a>Anforderungen

**Header:** \<valarray>

**Namespace:** std

## <a name="apply"></a> valarray::apply

Wendet eine angegebene Funktion auf jedes Element eines valarray-Objekts an.

```cpp
valarray<Type> apply(Type _Func(Type)) const;

valarray<Type> apply(Type _Func(constType&)) const;
```

### <a name="parameters"></a>Parameter

*_Func(Type)*<br/>
Das Funktionsobjekt, das auf alle Elemente des valarray-Operanden angewendet werden soll.

*_Func(const Type&)*<br/>
Das Funktionsobjekt für const, das auf alle Elemente des valarray-Operanden angewendet werden soll.

### <a name="return-value"></a>Rückgabewert

Ein valarray-Objekt, dessen Elemente `_Func` elementweise auf die Elemente des valarray-Operanden angewendet haben.

### <a name="remarks"></a>Hinweise

Die Memberfunktion gibt ein Objekt der Klasse [Valarray](../standard-library/valarray-class.md)**\<Typ >**, Länge [Größe](#size), jedes, deren Elemente *ich*ist `_Func((*this)[I])`.

### <a name="example"></a>Beispiel

```cpp
// valarray_apply.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

using namespace std;

int __cdecl MyApplyFunc( int n )
{
   return n*2;
}

int main( int argc, char* argv[] )
{
   valarray<int> vaR(10), vaApplied(10);
   int i;

   for ( i = 0; i < 10; i += 3 )
      vaR[i] = i;

   for ( i = 1; i < 10; i += 3 )
      vaR[i] = 0;

   for ( i = 2; i < 10; i += 3 )
      vaR[i] = -i;

   cout << "The initial Right valarray is: (";
   for   ( i=0; i < 10; ++i )
      cout << " " << vaR[i];
   cout << " )" << endl;

   vaApplied = vaR.apply( MyApplyFunc );

   cout << "The element-by-element result of "
       << "applying MyApplyFunc to vaR is the\nvalarray: ( ";
   for ( i = 0; i < 10; ++i )
      cout << " " << vaApplied[i];
   cout << " )" << endl;
}
/* Output:
The initial Right valarray is: ( 0 0 -2 3 0 -5 6 0 -8 9 )
The element-by-element result of applying MyApplyFunc to vaR is the
valarray: (  0 0 -4 6 0 -10 12 0 -16 18 )
*/
```

## <a name="cshift"></a> valarray::cshift

Verschiebt alle Elemente in einem valarray-Objekt zyklisch um eine angegebene Anzahl von Positionen.

```cpp
valarray<Type> cshift(int count) const;
```

### <a name="parameters"></a>Parameter

*count*<br/>
Die Anzahl der Stellen, um die die Elemente nach vorn verschoben werden.

### <a name="return-value"></a>Rückgabewert

Ein neues valarray-Objekt in der alle Elemente verschoben wurden *Anzahl* Positionen zyklisch in Richtung Anfang des valarray-Objekts, in Bezug auf ihre Position im Valarray-Operand nach links.

### <a name="remarks"></a>Hinweise

Ein positiver Wert von *Anzahl* verschiebt die Elemente zyklisch Links *Anzahl* platziert.

Ein negativer Wert von *Anzahl* verschiebt die Elemente zyklisch rechten *Anzahl* platziert.

### <a name="example"></a>Beispiel

```cpp
// valarray_cshift.cpp
// compile with: /EHsc

#include <valarray>
#include <iostream>

int main()
{
    using namespace std;
    int i;

    valarray<int> va1(10), va2(10);
    for (i = 0; i < 10; i+=1)
        va1[i] = i;
    for (i = 0; i < 10; i+=1)
        va2[i] = 10 - i;

    cout << "The operand valarray va1 is: (";
    for (i = 0; i < 10; i++)
        cout << " " << va1[i];
    cout << ")" << endl;

    // A positive parameter shifts elements right
    va1 = va1.cshift(4);
    cout << "The cyclically shifted valarray va1 is:\nva1.cshift (4) = (";
    for (i = 0; i < 10; i++)
        cout << " " << va1[i];
    cout << ")" << endl;

    cout << "The operand valarray va2 is: (";
    for (i = 0; i < 10; i++)
        cout << " " << va2[i];
    cout << ")" << endl;

    // A negative parameter shifts elements left
    va2 = va2.cshift(-4);
    cout << "The cyclically shifted valarray va2 is:\nva2.shift (-4) = (";
    for (i = 0; i < 10; i++)
        cout << " " << va2[i];
    cout << ")" << endl;
}
/* Output:
The operand valarray va1 is: ( 0 1 2 3 4 5 6 7 8 9)
The cyclically shifted valarray va1 is:
va1.cshift (4) = ( 4 5 6 7 8 9 0 1 2 3)
The operand valarray va2 is: ( 10 9 8 7 6 5 4 3 2 1)
The cyclically shifted valarray va2 is:
va2.shift (-4) = ( 4 3 2 1 10 9 8 7 6 5)
*/
```

## <a name="free"></a> valarray::free

Gibt den Arbeitsspeicher frei, der vom valarray-Objekt verwendet wird.

```cpp
void free();
```

### <a name="remarks"></a>Hinweise

Diese nicht dem Standard entsprechende Funktion ist identisch mit der Zuweisung eines leeren valarray-Objekts. Zum Beispiel:

```cpp
valarray<T> v;
v = valarray<T>();

// equivalent to v.free()
```

## <a name="max"></a> valarray::max

Sucht nach dem größten Element in einem valarray-Objekt.

```cpp
Type max() const;
```

### <a name="return-value"></a>Rückgabewert

Der maximale Wert der Elemente im valarray-Operand.

### <a name="remarks"></a>Hinweise

Die Memberfunktion vergleicht Werte durch Anwenden **Operator\<**  oder **Operator >** Elementpaare der Klasse `Type`, für die Operatoren für das Element angegeben werden muss `Type`.

### <a name="example"></a>Beispiel

```cpp
// valarray_max.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i, MaxValue;

   valarray<int> vaR ( 10 );
   for ( i = 0 ; i < 10 ; i += 3 )
      vaR [ i ] =  i;
   for ( i = 1 ; i < 10 ; i += 3 )
      vaR [ i ] =  2*i - 1;
   for ( i = 2 ; i < 10 ; i += 3 )
      vaR [ i ] =  10 - i;

   cout << "The operand valarray is: ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   MaxValue = vaR.max (  );
   cout << "The largest element in the valarray is: "
        << MaxValue  << "." << endl;
}
/* Output:
The operand valarray is: ( 0 1 8 3 7 5 6 13 2 9 ).
The largest element in the valarray is: 13.
*/
```

## <a name="min"></a> valarray::min

Sucht nach dem kleinsten Element in einem valarray-Objekt.

```cpp
Type min() const;
```

### <a name="return-value"></a>Rückgabewert

Der Mindestwert der Elemente im valarray-Operand.

### <a name="remarks"></a>Hinweise

Die Memberfunktion vergleicht Werte durch Anwenden **Operator\<**  oder **Operator >** Elementpaare der Klasse `Type`, für die Operatoren für das Element angegeben werden muss `Type`.

### <a name="example"></a>Beispiel

```cpp
// valarray_min.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i, MinValue;

   valarray<int> vaR ( 10 );
   for ( i = 0 ; i < 10 ; i += 3 )
      vaR [ i ] =  -i;
   for ( i = 1 ; i < 10 ; i += 3 )
      vaR [ i ] =  2*i;
   for ( i = 2 ; i < 10 ; i += 3 )
      vaR [ i ] =  5 - i;

   cout << "The operand valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   MinValue = vaR.min ( );
   cout << "The smallest element in the valarray is: "
        << MinValue  << "." << endl;
}
/* Output:
The operand valarray is: ( 0 2 3 -3 8 0 -6 14 -3 -9 ).
The smallest element in the valarray is: -9.
*/
```

## <a name="op_not"></a> valarray::operator!

Ein unärer Operator, der die logischen **NOT**-Werte jedes Elements eines valarray-Objekts abruft.

```cpp
valarray<bool> operator!() const;
```

### <a name="return-value"></a>Rückgabewert

Das valarray-Objekt von booleschen Werten, die die Negierung der Elementwerte des valarray-Operanden darstellen.

### <a name="remarks"></a>Hinweise

Die logische Operation **NOT** negiert die Elemente, da sie alle Nullen in Einsen umwandelt und alle Werte, die nicht null sind, als Einsen betrachtet und in Nullen umwandelt. Das zurückgegebene valarray-Objekt von booleschen Werten weist dieselbe Größe auf wie der valarray-Operand.

Es gibt auch einen bitweisen **nicht**[valarray:: Operator ~](#op_dtor) , der die Negierung auf der Ebene der einzelbits in die binäre Darstellung von **Char** und **Int**  Elemente eines valarray-Objekts.

### <a name="example"></a>Beispiel

```cpp
// valarray_op_lognot.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 );
   valarray<bool> vaNOT ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  0;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i-1;

   cout << "The initial valarray is:  ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   vaNOT = !vaL;
   cout << "The element-by-element result of "
        << "the logical NOT operator! is the\n valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaNOT [ i ] << " ";
   cout << ")." << endl;
}
/* Output:
The initial valarray is:  ( 0 0 0 2 0 4 0 6 0 8 ).
The element-by-element result of the logical NOT operator! is the
 valarray: ( 1 1 1 0 1 0 1 0 1 0 ).
*/
```

## <a name="op_mod_eq"></a> valarray::operator%=

Ruft den Rest der Division der Elemente eines Arrays elementweise entweder entsprechend einem angegebenen valarray-Objekt oder entsprechend einem Wert des Elementtyps ab.

```cpp
valarray<Type>& operator%=(const valarray<Type>& right);

valarray<Type>& operator%=(const Type& right);
```

### <a name="parameters"></a>Parameter

*right*<br/>
Das valarray-Objekt oder der Wert eines Elementtyps, der mit dem des valarray-Operanden für die elementweise Division des valarray-Operanden identisch ist.

### <a name="return-value"></a>Rückgabewert

Ein valarray-Objekt, dessen Elemente den Rest aus der elementweisen Division des Valarray-Operanden durch *rechts*

### <a name="example"></a>Beispiel

```cpp
// valarray_class_op_rem.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 6 ), vaR ( 6 );
   for ( i = 0 ; i < 6 ; i += 2 )
      vaL [ i ] =  53;
   for ( i = 1 ; i < 6 ; i += 2 )
      vaL [ i ] =  -67;
   for ( i = 0 ; i < 6 ; i++ )
      vaR [ i ] =  3*i+1;

   cout << "The initial valarray is: ( ";
      for ( i = 0 ; i < 6 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial  right valarray is: ( ";
      for ( i = 0 ; i < 6 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaL %= vaR;
   cout << "The remainders from the element-by-element "
        << "division is the\n valarray: ( ";
      for ( i = 0 ; i < 6 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;
}
/* Output:
The initial valarray is: ( 53 -67 53 -67 53 -67 ).
The initial  right valarray is: ( 1 4 7 10 13 16 ).
The remainders from the element-by-element division is the
 valarray: ( 0 -3 4 -7 1 -3 ).
*/
```

## <a name="and_eq"></a> valarray::operator&amp;=

Ruft das bitweise **AND**-Ergebnis von Elementen eines Arrays entweder mit den entsprechenden Elementen in einem angegebenen valarray-Objekt oder mit einem Wert des Elementtyps ab.

```cpp
valarray<Type>& operator&=(const valarray<Type>& right);

valarray<Type>& operator&=(const Type& right);
```

### <a name="parameters"></a>Parameter

*right*<br/>
Das valarray-Objekts oder der Wert eines Elementtyps identisch mit dem des Valarray-Operanden, die kombiniert werden, durch den logischen elementweise `AND` mit dem Valarray-Operanden.

### <a name="return-value"></a>Rückgabewert

Ein valarray-Objekt, dessen Elemente die elementweise logische `AND` des Valarray-Operanden durch *rechts*

### <a name="remarks"></a>Hinweise

Eine bitweise Operation kann nur verwendet werden, um Bits in **Char** und **Int** -Datentypen und-Varianten und nicht in **"float"**, **doppelte**, **Longdouble**, **"void"**, **"bool"**, oder in anderen komplexeren Datentypen.

Der bitweise AND weist dieselbe Wahrheitstabelle wie für die logische `AND` jedoch nur auf den Datentyp auf der Ebene der einzelbits angewendet. Bits angegebenen *b*1 und *b*2, *b*1 `AND` *b*2 **"true"** Wenn beide Bits true sind; sind. **"false"** Wenn mindestens eine "false".

### <a name="example"></a>Beispiel

```cpp
// valarray_class_op_bitand.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  0;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i-1;
   for ( i = 0 ; i < 10 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial valarray is:  ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaL &= vaR;
   cout << "The element-by-element result of "
        << "the logical AND operator&= is the\n valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;
}
/* Output:
The initial valarray is:  ( 0 0 0 2 0 4 0 6 0 8 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 8 9 ).
The element-by-element result of the logical AND operator&= is the
 valarray: ( 0 0 0 2 0 4 0 6 0 8 ).
*/
```

## <a name="op_gt_gt_eq"></a> valarray::operator&gt;&gt;=

Verschiebt die Bits für jedes Element eines valarray-Operanden um eine angegebene Anzahl von Positionen oder um einen elementweisen Betrag, der durch einen zweiten valarray-Operanden angegeben ist, nach rechts.

```cpp
valarray<Type>& operator>>=(const valarray<Type>& right);

valarray<Type>& operator>>=(const Type& right);
```

### <a name="parameters"></a>Parameter

*right*<br/>
Der Wert, der den Betrag angibt, um den die Bits nach rechts verschoben werden, oder das valarray-Objekt, dessen Elemente den elementweisen Betrag angeben, um den die Bits nach rechts verschoben werden.

### <a name="return-value"></a>Rückgabewert

Ein valarray-Objekt, dessen Elemente wurden, nach rechts verschoben in angegebene Menge *rechten*.

### <a name="remarks"></a>Hinweise

Bei Zahlen mit Vorzeichen bleiben die Vorzeichen erhalten.

### <a name="example"></a>Beispiel

```cpp
// valarray_class_op_rs.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 8 ), vaR ( 8 );
   for ( i = 0 ; i < 8 ; i += 2 )
      vaL [ i ] =  64;
   for ( i = 1 ; i < 8 ; i += 2 )
      vaL [ i ] =  -64;
   for ( i = 0 ; i < 8 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial operand valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The  right valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaL >>= vaR;
   cout << "The element-by-element result of "
        << "the right shift is the\n valarray: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;
}
/* Output:
The initial operand valarray is: ( 64 -64 64 -64 64 -64 64 -64 ).
The  right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the right shift is the
 valarray: ( 64 -32 16 -8 4 -2 1 -1 ).
*/
```

## <a name="op_lt_lt_eq"></a> valarray::operator&lt;&lt;=

Verschiebt die Bits für jedes Element eines valarray-Operanden um eine angegebene Anzahl von Positionen oder um einen elementweisen Betrag, der durch einen zweiten valarray-Operanden angegeben ist, nach links.

```cpp
valarray<Type>& operator<<=(const valarray<Type>& right);

valarray<Type>& operator<<=(const Type& right);
```

### <a name="parameters"></a>Parameter

*right*<br/>
Der Wert, der den Betrag angibt, um den die Bits nach links verschoben werden, oder das valarray-Objekt, dessen Elemente den elementweisen Betrag angeben, um den die Bits nach links verschoben werden.

### <a name="return-value"></a>Rückgabewert

Ein valarray-Objekt, dessen Elemente verschoben wurden, bleiben in angegebene Menge *rechten*.

### <a name="remarks"></a>Hinweise

Bei Zahlen mit Vorzeichen bleiben die Vorzeichen erhalten.

### <a name="example"></a>Beispiel

```cpp
// valarray_class_op_ls.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 8 ), vaR ( 8 );
   for ( i = 0 ; i < 8 ; i += 2 )
      vaL [ i ] =  1;
   for ( i = 1 ; i < 8 ; i += 2 )
      vaL [ i ] =  -1;
   for ( i = 0 ; i < 8 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial operand valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The  right valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaL <<= vaR;
   cout << "The element-by-element result of "
        << "the left shift\n on the operand array is the valarray:\n ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;
}
/* Output:
The initial operand valarray is: ( 1 -1 1 -1 1 -1 1 -1 ).
The  right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the left shift
 on the operand array is the valarray:
 ( 1 -2 4 -8 16 -32 64 -128 ).
*/
```

## <a name="op_star_eq"></a> valarray::operator*=

Multipliziert die Elemente eines angegebenen valarray-Objekts oder einen Wert des Elementtyps elementweise mit einem valarray-Operanden.

```cpp
valarray<Type>& operator*=(const valarray<Type>& right);

valarray<Type>& operator*=(const Type& right);
```

### <a name="parameters"></a>Parameter

*right*<br/>
Das valarray-Objekt oder der Wert eines Elementtyps, der mit dem des valarray-Operanden für die elementweise Multiplikation des valarray-Operanden identisch ist.

### <a name="return-value"></a>Rückgabewert

Ein valarray-Objekt, dessen Elemente das elementweise Produkt des Valarray-Operanden und *rechten*.

### <a name="example"></a>Beispiel

```cpp
// valarray_op_emult.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 8 ), vaR ( 8 );
   for ( i = 0 ; i < 8 ; i += 2 )
      vaL [ i ] =  2;
   for ( i = 1 ; i < 8 ; i += 2 )
      vaL [ i ] =  -1;
   for ( i = 0 ; i < 8 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaL *= vaR;
   cout << "The element-by-element result of "
        << "the multiplication is the\n valarray: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;
}
/* Output:
The initial valarray is: ( 2 -1 2 -1 2 -1 2 -1 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the multiplication is the
 valarray: ( 0 -1 4 -3 8 -5 12 -7 ).
*/
```

## <a name="op_add"></a> valarray::operator+

Ein unärer Operator, der ein Pluszeichen auf jedes Element in einem valarray-Objekt anwendet.

```cpp
valarray<Type> operator+() const;
```

### <a name="return-value"></a>Rückgabewert

Ein valarray-Objekt, dessen Elemente mit dem des Operandenarrays addiert wurden.

### <a name="example"></a>Beispiel

```cpp
// valarray_op_eplus.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 );
   valarray<int> vaPLUS ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  -i;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i-1;

   cout << "The initial valarray is:  ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   vaPLUS = +vaL;
   cout << "The element-by-element result of "
        << "the operator+ is the\n valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaPLUS [ i ] << " ";
   cout << ")." << endl;
}
/* Output:
The initial valarray is:  ( 0 0 -2 2 -4 4 -6 6 -8 8 ).
The element-by-element result of the operator+ is the
 valarray: ( 0 0 -2 2 -4 4 -6 6 -8 8 ).
*/
```

## <a name="op_add_eq"></a> valarray::operator+=

Addiert die Elemente eines angegebenen valarray-Objekts oder einen Wert des Elementtyps elementweise mit einem valarray-Operanden.

```cpp
valarray<Type>& operator+=(const valarray<Type>& right);

valarray<Type>& operator+=(const Type& right);
```

### <a name="parameters"></a>Parameter

*right*<br/>
Das valarray-Objekt oder der Wert eines Elementtyps, der mit dem des valarray-Operanden für die elementweise Addition mit dem valarray-Operanden identisch ist.

### <a name="return-value"></a>Rückgabewert

Ein valarray-Objekt, dessen Elemente die elementweise Summe des Valarray-Operanden und *rechten*.

### <a name="example"></a>Beispiel

```cpp
// valarray_op_eadd.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 8 ), vaR ( 8 );
   for ( i = 0 ; i < 8 ; i += 2 )
      vaL [ i ] =  2;
   for ( i = 1 ; i < 8 ; i += 2 )
      vaL [ i ] =  -1;
   for ( i = 0 ; i < 8 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial valarray is: ( ";
      for (i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial  right valarray is: ( ";
      for (i = 0 ; i < 8 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaL += vaR;
   cout << "The element-by-element result of "
        << "the sum is the\n valarray: ( ";
      for (i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;
}
/* Output:
The initial valarray is: ( 2 -1 2 -1 2 -1 2 -1 ).
The initial  right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the sum is the
 valarray: ( 2 0 4 2 6 4 8 6 ).
*/
```

## <a name="valarray__operator-"></a> valarray::operator-

Ein unärer Operator, der ein Minuszeichen auf jedes Element in einem valarray-Objekt anwendet.

```cpp
valarray<Type> operator-() const;
```

### <a name="return-value"></a>Rückgabewert

Ein valarray-Objekt, dessen Elemente mit dem des Operandenarrays subtrahiert wurden.

### <a name="example"></a>Beispiel

```cpp
// valarray_op_eminus.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 );
   valarray<int> vaMINUS ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  -i;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i-1;

   cout << "The initial valarray is:  ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   vaMINUS = -vaL;
   cout << "The element-by-element result of "
        << "the operator+ is the\n valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaMINUS [ i ] << " ";
   cout << ")." << endl;
}
/* Output:
The initial valarray is:  ( 0 0 -2 2 -4 4 -6 6 -8 8 ).
The element-by-element result of the operator+ is the
 valarray: ( 0 0 2 -2 4 -4 6 -6 8 -8 ).
*/
```

## <a name="valarray__operator-_eq"></a> valarray::operator-=

Subtrahiert die Elemente eines angegebenen valarray-Objekts oder einen Wert des Elementtyps elementweise von einem valarray-Operanden.

```cpp
valarray<Type>& operator-=(const valarray<Type>& right);

valarray<Type>& operator-=(const Type& right);
```

### <a name="parameters"></a>Parameter

*right*<br/>
Das valarray-Objekt oder der Wert eines Elementtyps, der mit dem des valarray-Operanden für die elementweise Subtraktion vom valarray-Operanden identisch ist.

### <a name="return-value"></a>Rückgabewert

Ein valarray-Objekt, dessen Elemente die elementweise Differenz des Valarray-Operanden und *rechten*.

### <a name="example"></a>Beispiel

```cpp
// valarray_op_esub.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 8 ), vaR ( 8 );
   for ( i = 0 ; i < 8 ; i += 2 )
      vaL [ i ] =  10;
   for ( i = 1 ; i < 8 ; i += 2 )
      vaL [ i ] =  0;
   for ( i = 0 ; i < 8 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial valarray is: ( ";
      for (i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial  right valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaL -= vaR;
   cout << "The element-by-element result of "
        << "the difference is the\n valarray: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;
}
/* Output:
The initial valarray is: ( 10 0 10 0 10 0 10 0 ).
The initial  right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the difference is the
 valarray: ( 10 -1 8 -3 6 -5 4 -7 ).
*/
```

## <a name="op_div_eq"></a> valarray::operator/=

Dividiert einen valarray-Operanden elementweise durch die Elemente eines angegebenen valarray-Objekts oder einen Wert des Elementtyps.

```cpp
valarray<Type>& operator/=(const valarray<Type>& right);

valarray<Type>& operator/=(const Type& right);
```

### <a name="parameters"></a>Parameter

*right*<br/>
Das valarray-Objekt oder der Wert eines Elementtyps, der mit dem des valarray-Operanden für die elementweise Division durch den valarray-Operanden identisch ist.

### <a name="return-value"></a>Rückgabewert

Ein valarray-Objekt, dessen Elemente den elementweisen Quotienten des Valarray-Operanden dividiert durch *rechten*.

### <a name="example"></a>Beispiel

```cpp
// valarray_op_ediv.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<double> vaL ( 6 ), vaR ( 6 );
   for ( i = 0 ; i < 6 ; i += 2 )
      vaL [ i ] =  100;
   for ( i = 1 ; i < 6 ; i += 2 )
      vaL [ i ] =  -100;
   for ( i = 0 ; i < 6 ; i++ )
      vaR [ i ] =  2*i;

   cout << "The initial valarray is: ( ";
      for (i = 0 ; i < 6 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for (i = 0 ; i < 6 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaL /= vaR;
   cout << "The element-by-element result of "
        << "the quotient is the\n valarray: ( ";
      for (i = 0 ; i < 6 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;
}
/* Output:
The initial valarray is: ( 100 -100 100 -100 100 -100 ).
The initial Right valarray is: ( 0 2 4 6 8 10 ).
The element-by-element result of the quotient is the
 valarray: ( inf -50 25 -16.6667 12.5 -10 ).
*/
```

## <a name="op_eq"></a> valarray::operator=

Weist einem valarray-Objekt Elemente zu, dessen Werte entweder direkt oder als Teil eines anderen valarray-Objekts oder durch ein slice_array-, gslice_array-, mask_array- oder indirect_array-Element angegeben werden.

```cpp
valarray<Type>& operator=(const valarray<Type>& right);

valarray<Type>& operator=(valarray<Type>&& right);

valarray<Type>& operator=(const Type& val);

valarray<Type>& operator=(const slice_array<Type>& _Slicearray);

valarray<Type>& operator=(const gslice_array<Type>& _Gslicearray);

valarray<Type>& operator=(const mask_array<Type>& _Maskarray);

valarray<Type>& operator=(const indirect_array<Type>& _Indarray);
```

### <a name="parameters"></a>Parameter

*right*<br/>
Das valarray-Objekt, das in den valarray-Operanden kopiert wird.

*val*<br/>
Der Wert, der den Elementen des valarray-Operanden zugewiesen wird.

*_Slicearray*<br/>
Das slice_array-Element, das in den valarray-Operanden kopiert wird.

*_Gslicearray*<br/>
Das gslice_array-Element, das in den valarray-Operanden kopiert wird.

*_Maskarray*<br/>
Das mask_array-Element, das in den valarray-Operanden kopiert wird.

*_Indarray*<br/>
Das indirect_array-Element, das in den valarray-Operanden kopiert wird.

### <a name="return-value"></a>Rückgabewert

Der erste Memberoperator ersetzt die kontrollierte Sequenz durch eine Kopie der gesteuerte Sequenz durch *rechten*.

Der zweite Memberoperator ist identisch mit dem ersten, hat aber einen [Rvalue-Verweisdeklarator: &&](../cpp/rvalue-reference-declarator-amp-amp.md).

Der dritte Memberoperator ersetzt jedes Element der gesteuerten Sequenz eine Kopie des *Val*.

Die restlichen Memberoperatoren ersetzen die Elemente der gesteuerten Sequenz, die anhand ihrer Argumente ausgewählt wurden und die nur von [operator&#91;&#93;](#op_at) generiert werden.

Wenn der Wert eines Members in der gesteuerten Ersatzsequenz von einem Member in der gesteuerten Anfangssequenz abhängt, ist das Ergebnis nicht definiert.

### <a name="remarks"></a>Hinweise

Wenn sich die Länge der gesteuerten Sequenz ändert, ist das Ergebnis im Allgemeinen nicht definiert. In dieser Implementierung werden jedoch nur Zeiger oder Verweise auf Elemente in der gesteuerten Sequenz ungültig gemacht.

### <a name="example"></a>Beispiel

```cpp
// valarray_op_assign.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> va ( 10 ), vaR ( 10 );
   for ( i = 0 ; i < 10 ; i += 1 )
      va [ i ] = i;
   for ( i = 0 ; i < 10 ; i+=1 )
      vaR [ i ] = 10 -  i;

   cout << "The operand valarray va is:";
   for ( i = 0 ; i < 10 ; i++ )
      cout << " " << va [ i ];
   cout << endl;

   cout << "The operand valarray vaR is:";
      for ( i = 0 ; i < 10 ; i++ )
         cout << " " << vaR [ i ];
   cout << endl;

   // Assigning vaR to va with the first member functon
   va = vaR;
   cout << "The reassigned valarray va is:";
   for ( i = 0 ; i < 10 ; i++ )
      cout << " " << va [ i ];
   cout << endl;

   // Assigning elements of value 10 to va
   // with the second member functon
   va = 10;
   cout << "The reassigned valarray va is:";
      for ( i = 0 ; i < 10 ; i++ )
         cout << " " << va [ i ];
   cout << endl;
}
/* Output:
The operand valarray va is: 0 1 2 3 4 5 6 7 8 9
The operand valarray vaR is: 10 9 8 7 6 5 4 3 2 1
The reassigned valarray va is: 10 9 8 7 6 5 4 3 2 1
The reassigned valarray va is: 10 10 10 10 10 10 10 10 10 10
*/
```

## <a name="op_at"></a> valarray::operator[]

Gibt einen Verweis auf ein Element oder auf den Wert zurück, den es am angegebenen Index oder in der angegebenen Teilmenge hat.

```cpp
Type& operator[](size_t _Off);

slice_array<Type> operator[](slice _Slicearray);

gslice_array<Type> operator[](const gslice& _Gslicearray);

mask_array<Type> operator[](const valarray<bool>& _Boolarray);

indirect_array<Type> operator[](const valarray<size_t>& _Indarray);

Type operator[](size_t _Off) const;


valarray<Type> operator[](slice _Slice) const;


valarray<Type> operator[](const gslice& _Gslicearray) const;


valarray<Type> operator[](const valarray<bool>& _Boolarray) const;


valarray<Type> operator[](const valarray<size_t>& _Indarray) const;
```

### <a name="parameters"></a>Parameter

*_Off*<br/>
Der Index des Elements, das einem Wert zugewiesen werden soll.

*_Slicearray*<br/>
Ein slice_array-Element eines valarray-Objekts, das eine Teilmenge angibt, die ausgewählt oder an ein neues valarray-Objekt zurückgegeben werden soll.

*_Gslicearray*<br/>
Ein gslice_array-Element eines valarray-Objekts, das eine Teilmenge angibt, die ausgewählt oder an ein neues valarray-Objekt zurückgegeben werden soll.

*_Boolarray*<br/>
Ein bool_array-Element eines valarray-Objekts, das eine Teilmenge angibt, die ausgewählt oder an ein neues valarray-Objekt zurückgegeben werden soll.

*_Indarray*<br/>
Ein indirect_array-Element eines valarray-Objekts, das eine Teilmenge angibt, die ausgewählt oder an ein neues valarray-Objekt zurückgegeben werden soll.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf ein Element oder auf den Wert, den es am angegebenen Index oder in der angegebenen Teilmenge hat.

### <a name="remarks"></a>Hinweise

Der Memberoperator wird überladen, um bieten verschiedene Möglichkeiten zum Auswählen von Sequenzen von Elementsequenzen aus denjenigen von gesteuert  <strong>\*dies</strong>. Die erste Gruppe von fünf Memberoperatoren werden zusammen mit verschiedenen Überladungen von [operator=](#op_eq) (und anderen zuweisenden Operatoren) verwendet, um ein selektives Ersetzen (Slicing) der gesteuerten Sequenz zu ermöglichen. Dabei müssen die ausgewählten Elemente vorhanden sein.

Wenn [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md) beim Kompilieren als 1 oder 2 definiert ist, tritt beim Zugriff auf ein Element außerhalb des valarray-Objekts ein Laufzeitfehler auf.  Weitere Informationen finden Sie unter [Checked Iterators (Überprüfte Iteratoren)](../standard-library/checked-iterators.md).

### <a name="example"></a>Beispiel

Im Beispiel für [slice::slice](../standard-library/slice-class.md#slice) und [gslice::gslice](../standard-library/gslice-class.md#gslice) wird verdeutlicht, wie der Operator deklariert und verwendet wird.

## <a name="op_xor_eq"></a> valarray::operator^=

Ruft den elementweisen logischen Operator exklusives Oder ( **XOR**) eines Arrays entweder mit einem angegebenen valarray-Objekt oder mit einem Wert des Elementtyps ab.

```cpp
valarray<Type>& operator|=(const valarray<Type>& right);

valarray<Type>& operator|=(const Type& right);
```

### <a name="parameters"></a>Parameter

*right*<br/>
Das valarray-Objekt oder der Wert eines Elementtyps, der mit dem valarray-Operanden identisch ist, der durch den logischen **XOR**-Operator mit dem valarray-Operanden elementweise verknüpft werden soll.

### <a name="return-value"></a>Rückgabewert

Ein valarray-Objekt, dessen Elemente die elementweise logische **XOR** des Valarray-Operanden und *rechten*.

### <a name="remarks"></a>Hinweise

Der Operator exklusives Oder, auch als **XOR** bezeichnet, weist die folgende Semantik auf: Wenn die Elemente *e*1 und *e*2 gegeben sind, ist *e*1 **XOR** *e*2 **TRUE**, wenn exakt eines der Element TRUE ist; **FALSE**, wenn beide Elemente FALSE sind oder wenn beide Elemente TRUE sind.

### <a name="example"></a>Beispiel

```cpp
// valarray_op_exor.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
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

   cout << "The initial operand valarray is:  ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The  right valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaL ^= vaR;
   cout << "The element-by-element result of "
        << "the bitwise XOR operator^= is the\n valarray: ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;
}
/* Output:
The initial operand valarray is:  ( 1 0 1 0 1 0 1 0 1 0 ).
The  right valarray is: ( 0 0 1 3 3 4 6 6 7 9 ).
The element-by-element result of the bitwise XOR operator^= is the
 valarray: ( 1 0 0 3 2 4 7 6 6 9 ).
*/
```

## <a name="op_or_eq"></a> valarray::operator|=

Ruft das bitweise `OR`-Ergebnis von Elementen eines Arrays entweder mit den entsprechenden Elementen in einem angegebenen valarray-Objekt oder mit einem Wert des Elementtyps ab.

```cpp
valarray<Type>& operator|=(const valarray<Type>& right);

valarray<Type>& operator|=(const Type& right);
```

### <a name="parameters"></a>Parameter

*right*<br/>
Das valarray-Objekt oder der Wert eines Elementtyps, der mit dem valarray-Operanden identisch ist, der durch den bitweisen `OR`-Operator mit dem valarray-Operanden elementweise verknüpft werden soll.

### <a name="return-value"></a>Rückgabewert

Ein valarray-Objekt, dessen Elemente die elementweise bitweise `OR` des Valarray-Operanden durch *rechten*.

### <a name="remarks"></a>Hinweise

Eine bitweise Operation kann nur verwendet werden, um Bits in **Char** und **Int** -Datentypen und-Varianten und nicht in **"float"**, **doppelte**, **Longdouble**, **"void"**, **"bool"**, oder in anderen komplexeren Datentypen.

Für die bitweise `OR`-Operation gilt dieselbe Wahrheitstabelle wie für die logische `OR`-Operation. Die bitweise OR-Operation wird jedoch nur auf den Datentyp auf der Ebene der Einzelbits angewendet. Wenn die Bits *b*1 und *b*2 gegeben sind, ist *b*1 `OR` *b*2 **TRUE**, wenn mindestens eines der Bits TRUE ist; **FALSE**, wenn beide Bits FALSE sind.

### <a name="example"></a>Beispiel

```cpp
// valarray_class_op_bitor.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
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

   cout << "The initial operand valarray is:\n ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The  right valarray is:\n ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaL |= vaR;
   cout << "The element-by-element result of "
        << "the logical OR\n operator|= is the valarray:\n ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;
}
/* Output:
The initial operand valarray is:
 ( 1 0 1 0 1 0 1 0 1 0 ).
The  right valarray is:
 ( 0 0 1 3 3 4 6 6 7 9 ).
The element-by-element result of the logical OR
 operator|= is the valarray:
 ( 1 0 1 3 3 4 7 6 7 9 ).
*/
```

## <a name="op_dtor"></a> valarray::operator~

Ein unäroperator, der den bitweisen abruft, `NOT` -Werte jedes Elements eines valarray-Objekts.

```cpp
valarray<Type> operator~() const;
```

### <a name="return-value"></a>Rückgabewert

Das valarray-Objekt mit booleschen Werten, die die bitweise `NOT` der Elementwerte des Valarray-Operanden.

### <a name="remarks"></a>Hinweise

Eine bitweise Operation kann nur verwendet werden, um Bits in **Char** und **Int** -Datentypen und-Varianten und nicht in **"float"**, **doppelte**, **Longdouble**, **"void"**, **"bool"** oder in anderen komplexeren Datentypen.

Für die bitweise `NOT`-Operation gilt dieselbe Wahrheitstabelle wie für die logische `NOT`-Operation. Die bitweise OR-Operation wird jedoch nur auf den Datentyp auf der Ebene der Einzelbits angewendet. Wenn das Bit *b* gegeben ist, ist ~ *b* TRUE, wenn *b* FALSE ist und FALSE, wenn *b* TRUE ist. Der logische **NOT**[operator!](#op_not) wird auf Elementebene angewendet, wobei alle Werte, die nicht null sind, als **TRUE** zählen, und das Ergebnis ein valarray-Objekt mit booleschen Werten ist. Der bitweise `NOToperator~`, im Gegensatz dazu kann dazu führen, mit anderen Werten als 0 oder 1 ist, je nach Ergebnis der bitweisen Operation ein valarray-Objekt.

### <a name="example"></a>Beispiel

```cpp
// valarray_op_bitnot.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<unsigned short int> vaL1 ( 10 );
   valarray<unsigned short int> vaNOT1 ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL1 [ i ] =  i;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL1 [ i ] =  5*i;

   cout << "The initial valarray <unsigned short int> is:  ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL1 [ i ] << " ";
   cout << ")." << endl;

   vaNOT1 = ~vaL1;
   cout << "The element-by-element result of "
        << "the bitwise NOT operator~ is the\n valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaNOT1 [ i ] << " ";
   cout << ")." << endl << endl;

   valarray<int> vaL2 ( 10 );
   valarray<int> vaNOT2 ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL2 [ i ] =  i;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL2 [ i ] =  -2 * i;

   cout << "The initial valarray <int> is:  ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL2 [ i ] << " ";
   cout << ")." << endl;

   vaNOT2 = ~vaL2;
   cout << "The element-by-element result of "
        << "the bitwise NOT operator~ is the\n valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaNOT2 [ i ] << " ";
   cout << ")." << endl;

   // The negative numbers are represented using
   // the two's complement approach, so adding one
   // to the flipped bits returns the negative elements
   vaNOT2 = vaNOT2 + 1;
   cout << "The element-by-element result of "
        << "adding one\n is the negative of the "
        << "original elements the\n valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaNOT2 [ i ] << " ";
   cout << ")." << endl;
}

/* Output:
The initial valarray <unsigned short int> is:  ( 0 5 2 15 4 25 6 35 8 45 ).
The element-by-element result of the bitwise NOT operator~ is the
 valarray: ( 65535 65530 65533 65520 65531 65510 65529 65500 65527 65490 ).

The initial valarray <int> is:  ( 0 -2 2 -6 4 -10 6 -14 8 -18 ).
The element-by-element result of the bitwise NOT operator~ is the
 valarray: ( -1 1 -3 5 -5 9 -7 13 -9 17 ).
The element-by-element result of adding one
 is the negative of the original elements the
 valarray: ( 0 2 -2 6 -4 10 -6 14 -8 18 ).
*/
```

## <a name="resize"></a> valarray::resize

Ändert die Anzahl der Elemente in einem „valarray“ auf eine bestimmte Anzahl.

```cpp
void resize(
    size_t _Newsize);

void resize(
    size_t _Newsize,
    const Type val);
```

### <a name="parameters"></a>Parameter

*_Newsize*<br/>
Die Anzahl der Elemente im „valarray“, dessen Größe angepasst wird.

*val*<br/>
Der Wert, der an die Elemente des „valarray“ übergeben wird, dessen Größe angepasst wird.

### <a name="remarks"></a>Hinweise

Die erste Memberfunktion initialisiert Elemente mit ihrem standardmäßigen Konstruktor.

Zeiger oder Verweise auf Elemente in der kontrollierten Sequenz werden ungültig.

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird die Verwendung der Memberfunktion „valarray::resize“ gezeigt.

```cpp
// valarray_resize.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main()
{
    using namespace std;
    int i;
    size_t size1, sizeNew;

    valarray<int> va1(10);
    for (i = 0; i < 10; i+=1)
        va1[i] = i;

    cout << "The valarray contains ( ";
        for (i = 0; i < 10; i++)
            cout << va1[i] << " ";
    cout << ")." << endl;

    size1 = va1.size();
    cout << "The number of elements in the valarray is: "
         << size1  << "." <<endl << endl;

    va1.resize(15, 10);

    cout << "The valarray contains ( ";
        for (i = 0; i < 15; i++)
            cout << va1[i] << " ";
    cout << ")." << endl;
    sizeNew = va1.size();
    cout << "The number of elements in the resized valarray is: "
         << sizeNew  << "." <<endl << endl;
}
```

```Output
The valarray contains ( 0 1 2 3 4 5 6 7 8 9 ).
The number of elements in the valarray is: 10.

The valarray contains ( 10 10 10 10 10 10 10 10 10 10 10 10 10 10 10 ).
The number of elements in the resized valarray is: 15.
```

## <a name="shift"></a> valarray::shift

Verschiebt alle Elemente in einem valarray-Objekt um eine angegebene Anzahl von Stellen.

```cpp
valarray<Type> shift(int count) const;
```

### <a name="parameters"></a>Parameter

*count*<br/>
Die Anzahl der Stellen, um die die Elemente nach vorn verschoben werden.

### <a name="return-value"></a>Rückgabewert

Ein neues valarray-Objekt in der alle Elemente verschoben wurden *Anzahl* Positionen in Richtung Anfang des valarray-Objekts, in Bezug auf ihre Position im Valarray-Operand nach links.

### <a name="remarks"></a>Hinweise

Ein positiver Wert von *Anzahl* verschiebt die Elemente werden Links *Anzahl* platziert werden, füllt mit Nullen.

Ein negativer Wert von *Anzahl* verschiebt die Elemente nach rechts *Anzahl* platziert werden, füllt mit Nullen.

### <a name="example"></a>Beispiel

```cpp
// valarray_shift.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> va1 ( 10 ), va2 ( 10 );
   for ( i = 0 ; i < 10 ; i += 1 )
      va1 [ i ] =  i;
   for ( i = 0 ; i < 10 ; i += 1 )
      va2 [ i ] = 10 -  i;

   cout << "The operand valarray va1(10) is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << va1 [ i ] << " ";
   cout << ")." << endl;

   // A positive parameter shifts elements left
   va1 = va1.shift ( 4 );
   cout << "The shifted valarray va1 is: va1.shift (4) = ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << va1 [ i ] << " ";
   cout << ")." << endl;

   cout << "The operand valarray va2(10) is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << va2 [ i ] << " ";
   cout << ")." << endl;

   // A negative parameter shifts elements right
   va2 = va2.shift ( - 4 );
   cout << "The shifted valarray va2 is: va2.shift (-4) = ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << va2 [ i ] << " ";
   cout << ")." << endl;
}
/* Output:
The operand valarray va1(10) is: ( 0 1 2 3 4 5 6 7 8 9 ).
The shifted valarray va1 is: va1.shift (4) = ( 4 5 6 7 8 9 0 0 0 0 ).
The operand valarray va2(10) is: ( 10 9 8 7 6 5 4 3 2 1 ).
The shifted valarray va2 is: va2.shift (-4) = ( 0 0 0 0 10 9 8 7 6 5 ).
*/
```

## <a name="size"></a> valarray::size

Gibt die Anzahl von Elementen in einem Wertarray zurück.

```cpp
size_t size() const;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Elemente im Operandenwertarray.

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird die Verwendung der Memberfunktion „valarray::size“ gezeigt.

```cpp
// valarray_size.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main()
{
    using namespace std;
    int i;
    size_t size1, size2;

    valarray<int> va1(10), va2(12);
    for (i = 0; i < 10; i += 1)
        va1[i] =  i;
    for (i = 0; i < 10; i += 1)
        va2[i] =  i;

    cout << "The operand valarray va1(10) is: ( ";
        for (i = 0; i < 10; i++)
            cout << va1[i] << " ";
    cout << ")." << endl;

    size1 = va1.size();
    cout << "The number of elements in the valarray va1 is: va1.size = "
         << size1  << "." <<endl << endl;

    cout << "The operand valarray va2(12) is: ( ";
        for (i = 0; i < 10; i++)
            cout << va2[i] << " ";
    cout << ")." << endl;

    size2 = va2.size();
    cout << "The number of elements in the valarray va2 is: va2.size = "
         << size2  << "." << endl << endl;

    // Initializing two more elements to va2
    va2[10] = 10;
    va2[11] = 11;
    cout << "After initializing two more elements,\n "
         << "the operand valarray va2(12) is now: ( ";
        for (i = 0; i < 12; i++)
            cout << va2[i] << " ";
    cout << ")." << endl;
    cout << "The number of elements in the valarray va2 is still: "
         << size2  << "." << endl;
}
```

```Output
The operand valarray va1(10) is: ( 0 1 2 3 4 5 6 7 8 9 ).
The number of elements in the valarray va1 is: va1.size = 10.

The operand valarray va2(12) is: ( 0 1 2 3 4 5 6 7 8 9 ).
The number of elements in the valarray va2 is: va2.size = 12.

After initializing two more elements,
 the operand valarray va2(12) is now: ( 0 1 2 3 4 5 6 7 8 9 10 11 ).
The number of elements in the valarray va2 is still: 12.
```

## <a name="sum"></a> valarray::sum

Bestimmt die Summe aller Elemente in einem valarray-Objekt mit einer Länge ungleich null.

```cpp
Type sum() const;
```

### <a name="return-value"></a>Rückgabewert

Die Summe der Elemente des valarray-Operanden.

### <a name="remarks"></a>Hinweise

Wenn die Länge größer als eins ist, addiert die Memberfunktion Werte zur Summe durch Anwenden von `operator+=` Elementpaare der Klasse `Type`, welcher Operator, daher muss angegeben werden für Elemente des Typs `Type`.

### <a name="example"></a>Beispiel

```cpp
// valarray_sum.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;
   int sumva = 0;

   valarray<int> va ( 10 );
   for ( i = 0 ; i < 10 ; i+=1 )
      va [ i ] =  i;

   cout << "The operand valarray va (10) is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << va [ i ] << " ";
   cout << ")." << endl;

   sumva = va.sum ( );
   cout << "The sum of elements in the valarray is: "
        << sumva  << "." <<endl;
}
/* Output:
The operand valarray va (10) is: ( 0 1 2 3 4 5 6 7 8 9 ).
The sum of elements in the valarray is: 45.
*/
```

## <a name="swap"></a> valarray::swap

Tauscht die Elemente zweier `valarray`n.

```cpp
void swap(valarray& right);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*right*|Ein `valarray`-Objekt, das die auszutauschenden Elemente bereitgestellt.|

### <a name="remarks"></a>Hinweise

Die Memberfunktion tauscht die kontrollierten Sequenzen zwischen `*this` und *rechten*. Sie führt dies in einer konstanten Zeit aus, sie löst keine Ausnahmen aus, und sie macht keine Verweise, Zeiger oder Iteratoren ungültig, die Elemente in den beiden kontrollierten Sequenzen bestimmen.

## <a name="valarray"></a> valarray::valarray

Erstellt ein Wertarray einer bestimmten Größe bzw. eins mit Elementen eines bestimmten Werts oder als Kopie eines anderen Wertarrays oder als Teilmenge eines anderen Wertarrays.

```cpp
valarray();

explicit valarray(
    size_t Count);

valarray(
    const Type& Val,
    size_t Count);

valarray(
    const Type* Ptr,
    size_t Count);

valarray(
    const valarray<Type>& Right);

valarray(
    const slice_array<Type>& SliceArray);

valarray(
    const gslice_array<Type>& GsliceArray);

valarray(
    const mask_array<Type>& MaskArray);

valarray(
    const indirect_array<Type>& IndArray);

valarray(
    valarray<Type>&& Right);

valarray(
    initializer_list<Type> IList);
```

### <a name="parameters"></a>Parameter

*Anzahl*<br/>
Die Anzahl von Elementen im Wertarray.

*val*<br/>
Der beim Initialisieren der Elemente im Wertarray zu verwendende Wert.

*PTR*<br/>
Zeiger auf die beim Initialisieren der Elemente im Wertarray zu verwendenden Werte.

*Rechts*<br/>
Ein vorhandenes Wertarray, mit dem das neue Wertarray initialisiert wird.

*SliceArray*<br/>
Ein slice_array-Element, dessen Elementwerte beim Initialisieren der Elemente des zu erstellenden Wertarrays verwendet werden sollen.

*GsliceArray*<br/>
Ein gslice_array-Element, dessen Elementwerte beim Initialisieren der Elemente des zu erstellenden Wertarrays verwendet werden sollen.

*MaskArray*<br/>
Ein mask_array-Element, dessen Elementwerte beim Initialisieren der Elemente des zu erstellenden Wertarrays verwendet werden sollen.

*IndArray*<br/>
Ein indirect_array-Element, dessen Elementwerte beim Initialisieren der Elemente des zu erstellenden Wertarrays verwendet werden sollen.

*IList*<br/>
Das initializer_list-Element, in dem die zu kopierenden Elemente enthalten sind.

### <a name="remarks"></a>Hinweise

Der erste (standardmäßige) Konstruktor initialisiert das Objekt in ein leeres Array. Die nächsten drei Konstruktoren wird jeweils initialisieren Sie das Objekt in ein Array von *Anzahl* Elemente wie folgt:

- Bei expliziten `valarray(size_t Count)` wird jedes Element mit dem Standardkonstruktor initialisiert.

- Für `valarray(const Type& Val, Count)`, jedes Element wird mit initialisiert *Val*.

- Bei `valarray(const Type* Ptr, Count)` wird das Element an Position `I` mit `Ptr`[ `I`] initialisiert.

Jeder verbleibende Konstruktor initialisiert das Objekt in einem valarray\<Type>-Objekt, das durch die im Argument angegebene Teilmenge bestimmt wird.

Der letzte Konstruktor ist identisch mit dem neben dem letzten, hat aber einen [Rvalue-Verweisdeklarator: &&](../cpp/rvalue-reference-declarator-amp-amp.md).

### <a name="example"></a>Beispiel

```cpp
// valarray_ctor.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main()
{
    using namespace std;
    int i;

    // The second member function
    valarray<int> va(10);
    for (auto i : va){
        va[i] = 2 * (i + 1);
    }

    cout << "The operand valarray va is:\n(";
    for (auto i : va) {
        cout << " " << va[i];
    }
    cout << " )" << endl;

    slice Slice(2, 4, 3);

    // The fifth member function
    valarray<int> vaSlice = va[Slice];

    cout << "The new valarray initialized from the slice is vaSlice ="
        << "\nva[slice( 2, 4, 3)] = (";
    for (int i = 0; i < 3; i++) {
        cout << " " << vaSlice[i];
    }
    cout << " )" << endl;

    valarray<int> va2{{ 1, 2, 3, 4 }};
    for (auto& v : va2){
        cout << v << " ";
    }
    cout << endl;
}

```

```Output
The operand valarray va is:( 0 2 2 2 2 2 2 2 2 2 )The new valarray initialized from the slice is vaSlice =va[slice( 2, 4, 3)] = ( 0 0 0 )1 2 3 4
```

## <a name="value_type"></a> valarray::value_type

Ein Typ, der den Typ des in einem valarray-Objekt gespeicherten Elements darstellt.

```cpp
typedef Type value_type;
```

### <a name="remarks"></a>Hinweise

Der Type stellt ein Synonym für den Vorlagenparameter `Type` dar.

### <a name="example"></a>Beispiel

```cpp
// valarray_value_type.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;
   valarray<int> va ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      va [ i ] =  i;
   for ( i = 1 ; i < 10 ; i += 2 )
      va [ i ] =  -1;

   cout << "The initial operand valarray is:  ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << va [ i ] << " ";
   cout << ")." << endl;

   // value_type declaration and initialization:
   valarray<int>::value_type Right = 10;

   cout << "The decalared value_type Right is: "
           << Right << endl;
   va *= Right;
   cout << "The resulting valarray is:  ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << va [ i ] << " ";
   cout << ")." << endl;
}
/* Output:
The initial operand valarray is:  ( 0 -1 2 -1 4 -1 6 -1 8 -1 ).
The decalared value_type Right is: 10
The resulting valarray is:  ( 0 -10 20 -10 40 -10 60 -10 80 -10 ).
*/
```

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
