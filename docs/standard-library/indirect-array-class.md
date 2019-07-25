---
title: indirect_array-Klasse
ms.date: 11/04/2016
f1_keywords:
- valarray/std::indirect_array
helpviewer_keywords:
- indirect_array class
ms.assetid: 10e1eaea-ba5a-405c-a25e-7bdd3eee7fc7
ms.openlocfilehash: 5db5f2ce60038267b70ae8e77d9dd929d972af6a
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456329"
---
# <a name="indirectarray-class"></a>indirect_array-Klasse

Eine interne zusätzliche Vorlagenklasse, die allgemeine Objekte, die Teilmengen von valarray-Objekten sind, unterstützt, indem sie Vorgänge zwischen Teilmengenarrays bereitstellt, die durch Angeben einer Teilmenge von Indizes eines übergeordneten valarray-Objekts definiert sind.

## <a name="syntax"></a>Syntax

## <a name="remarks"></a>Hinweise

Die Klasse beschreibt ein Objekt, das einen Verweis auf ein Objekt `va` der Klasse [Valarray](../standard-library/valarray-class.md) **\<Type >** speichert, zusammen mit einem `xa` Objekt der `valarray<size_t>`Klasse, das die Reihenfolge der Elemente beschreibt, aus denen Sie auswählen können. Das `valarray<Type>` -Objekt.

Sie erstellen ein `indirect_array<Type>` -Objekt nur, indem Sie einen Ausdruck der `va[xa]`Form schreiben. Die Member-Funktionen der-Klasse Indirect_array Verhalten sich dann wie die entsprechenden Funktions `valarray<Type>`Signaturen, die für definiert sind, mit dem Unterschied, dass nur die Sequenz ausgewählter Elemente betroffen ist.

Die Sequenz besteht aus **XA.** [size](../standard-library/valarray-class.md#size) -Elemente, wobei `I` Element der Index **XA**[ `I`] innerhalb `va`von wird.

## <a name="example"></a>Beispiel:

```cpp
// indirect_array.cpp
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

   // Select 2nd, 4th & 6th elements
   // and assign a value of 10 to them
   valarray<size_t> indx ( 3 );
   indx [0] = 2;
   indx [1] = 4;
   indx [2] = 6;
   va[indx] = 10;

   cout << "The modified operand valarray is:  ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << va [ i ] << " ";
   cout << ")." << endl;
}
```

### <a name="output"></a>Ausgabe

```cpp
The initial operand valarray is:  (0 -1 2 -1 4 -1 6 -1 8 -1).
The modified operand valarray is:  (0 -1 10 -1 10 -1 10 -1 8 -1).
```

## <a name="requirements"></a>Anforderungen

**Header:** \<valarray>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)
