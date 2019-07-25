---
title: mask_array-Klasse
ms.date: 11/04/2016
f1_keywords:
- valarray/std::mask_array
helpviewer_keywords:
- mask_array class
ms.assetid: c49bed6a-3000-4f39-bff6-cb9a453acb0b
ms.openlocfilehash: 9da5e3593288be02819330e11b60e306784054dc
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68460138"
---
# <a name="maskarray-class"></a>mask_array-Klasse

Eine interne zusätzliche Vorlagenklasse, die Objekte, die Teilmengen von übergeordneten valarray-Objekten und mit einem booleschen Ausdruck angegeben sind, dadurch unterstützt, dass sie Vorgänge zwischen den Teilmengenarrays bereitstellt.

## <a name="syntax"></a>Syntax

## <a name="remarks"></a>Hinweise

Die Klasse beschreibt ein Objekt, das einen Verweis auf ein Objekt `va` der Klasse [Valarray](../standard-library/valarray-class.md) **\<Type >** speichert, zusammen mit einem `ba` Objekt der Klasse [Valarray\<bool >](../standard-library/valarray-bool-class.md), das das Sequenz von Elementen, die aus dem `valarray<Type>` -Objekt ausgewählt werden sollen.

Sie erstellen ein `mask_array<Type>` -Objekt nur, indem Sie einen Ausdruck der [Form&#91;VA&#93;BA](../standard-library/valarray-class.md#op_at)schreiben. Die Member-Funktionen der-Klasse Mask_array Verhalten sich dann wie die entsprechenden Funktions `valarray<Type>`Signaturen, die für definiert sind, mit dem Unterschied, dass nur die Sequenz ausgewählter Elemente betroffen ist.

Die Sequenz besteht aus `ba.size` höchstens Elementen. Ein Element *J* ist nur enthalten, wenn **ba**[ *J*] gleich „true“ ist. Folglich gibt es so viele Elemente in der Sequenz, wie echte Elemente in `ba`vorhanden sind. Wenn `I` der Index des niedrigsten true-Elements in `ba`ist, dann ist **VA**[] das Element 0 ( `I`null) in der ausgewählten Sequenz.

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

### <a name="output"></a>Ausgabe

```Output
The initial operand valarray is:  (0 -1 2 -1 4 -1 6 -1 8 -1).
The modified operand valarray is:  (0 -1 2 -1 10 -1 10 -1 10 -1).
```

## <a name="requirements"></a>Anforderungen

**Header:** \<valarray>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)
