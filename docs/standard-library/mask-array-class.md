---
title: mask_array-Klasse
ms.date: 11/04/2016
f1_keywords:
- valarray/std::mask_array
helpviewer_keywords:
- mask_array class
ms.assetid: c49bed6a-3000-4f39-bff6-cb9a453acb0b
ms.openlocfilehash: 12398203d61f2c3ea155b5f6e6e7b118d4a13c75
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689408"
---
# <a name="mask_array-class"></a>mask_array-Klasse

Eine interne, zusätzliche Klassen Vorlage, die Objekte unterstützt, die Teilmengen von übergeordneten Valarray-Objekten sind, die mit einem booleschen Ausdruck angegeben werden, indem Vorgänge zwischen den Teilmengen Arrays bereitgestellt werden.

## <a name="syntax"></a>Syntax

## <a name="remarks"></a>Hinweise

Die Klasse beschreibt ein Objekt, das einen Verweis auf ein Objekt `va` der Klasse [Valarray](../standard-library/valarray-class.md)  **\<Type >** zusammen mit einem Objekt `ba` der Klasse [Valarray \<bool >](../standard-library/valarray-bool-class.md)speichert, das die Reihenfolge der Elemente beschreibt, die ausgewählt werden sollen. aus dem `valarray<Type>`-Objekt.

Sie erstellen nur dann ein `mask_array<Type>` Objekt, indem Sie einen Ausdruck der [Form&#91;VA&#93;BA](../standard-library/valarray-class.md#op_at)schreiben. Die Element Funktionen der Klasse Mask_array Verhalten sich dann wie die entsprechenden Funktions Signaturen, die für `valarray<Type>` definiert sind, mit dem Unterschied, dass nur die Reihenfolge der ausgewählten Elemente betroffen ist.

Die Sequenz besteht aus höchstens `ba.size` Elementen. Ein Element *J* ist nur enthalten, wenn **ba**[ *J*] gleich „true“ ist. Folglich gibt es so viele Elemente in der Sequenz, wie echte Elemente in `ba` vorhanden sind. Wenn `I` der Index des niedrigsten true-Elements in `ba` ist, dann ist **VA**[`I`] das Element 0 (null) in der ausgewählten Sequenz.

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

[Thread Safety in the C++ Standard Library (Threadsicherheit in der C++-Standardbibliothek)](../standard-library/thread-safety-in-the-cpp-standard-library.md)
