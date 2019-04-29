---
title: mask_array-Klasse
ms.date: 11/04/2016
f1_keywords:
- valarray/std::mask_array
helpviewer_keywords:
- mask_array class
ms.assetid: c49bed6a-3000-4f39-bff6-cb9a453acb0b
ms.openlocfilehash: 108c942bef33e44b515d46e953c9d99274e3ce8d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412981"
---
# <a name="maskarray-class"></a>mask_array-Klasse

Eine interne zusätzliche Vorlagenklasse, die Objekte, die Teilmengen von übergeordneten valarray-Objekten und mit einem booleschen Ausdruck angegeben sind, dadurch unterstützt, dass sie Vorgänge zwischen den Teilmengenarrays bereitstellt.

## <a name="syntax"></a>Syntax

## <a name="remarks"></a>Hinweise

Die Klasse beschreibt ein Objekt, das einen Verweis auf ein Objekt speichert `va` Klasse [Valarray](../standard-library/valarray-class.md)**\<Typ >**, zusammen mit einem Objekt `ba` Klasse [ valarray-Objekt\<Bool >](../standard-library/valarray-bool-class.md), die beschreibt, der Reihenfolge der Elemente aus der `valarray<Type>` Objekt.

Sie erstellen eine `mask_array<Type>` -Objekt nur, indem Sie das Schreiben eines Ausdrucks des Formulars [va&#91;Ba&#93;](../standard-library/valarray-class.md#op_at). Die Memberfunktionen der Mask_array-Klasse Verhalten sich dann wie die entsprechenden Funktionssignaturen für definiert `valarray<Type>`, außer dass nur die Reihenfolge der ausgewählten Elemente betroffen ist.

Die Sequenz besteht aus höchstens `ba.size` Elemente. Ein Element *J* ist nur enthalten, wenn **ba**[ *J*] gleich „true“ ist. Es gibt also beliebig viele Elemente in der Sequenz vorhanden sind "true"-Elemente in `ba`. Wenn `I` ist der Index des kleinsten "true"-Elements in `ba`, klicken Sie dann **va**[ `I`] ist Element 0 (null) in der ausgewählten Reihenfolge.

## <a name="example"></a>Beispiel

```cpp
// mask_array.cpp
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

   // Use masked subsets to assign a value of 10
   // to all elements grrater than 3 in value
   va [va > 3 ] = 10;
   cout << "The modified operand valarray is:  ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << va [ i ] << " ";
   cout << ")." << endl;
}
```

### <a name="output"></a>Output

```Output
The initial operand valarray is:  (0 -1 2 -1 4 -1 6 -1 8 -1).
The modified operand valarray is:  (0 -1 2 -1 10 -1 10 -1 10 -1).
```

## <a name="requirements"></a>Anforderungen

**Header:** \<valarray>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
