---
title: indirect_array-Klasse
ms.date: 11/04/2016
f1_keywords:
- valarray/std::indirect_array
helpviewer_keywords:
- indirect_array class
ms.assetid: 10e1eaea-ba5a-405c-a25e-7bdd3eee7fc7
ms.openlocfilehash: 6be0c5153cbc94d09b414fc9e14fa498c7a4cfa7
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2019
ms.locfileid: "72687918"
---
# <a name="indirect_array-class"></a>indirect_array-Klasse

Eine interne, zusätzliche Klassen Vorlage, die Objekte unterstützt, die Teilmengen von Valarray sind, indem Vorgänge zwischen Teilmengen Arrays bereitgestellt werden, die durch Angeben einer Teilmenge von Indizes eines übergeordneten Valarray-Objekts definiert werden.

## <a name="syntax"></a>Syntax

## <a name="remarks"></a>Hinweise

Die Klasse beschreibt ein Objekt, das einen Verweis auf ein Objekt `va` der Klasse [Valarray](../standard-library/valarray-class.md)  **\<Type >** zusammen mit einem Objekt `xa` der Klasse `valarray<size_t>` speichert, das die Reihenfolge der Elemente beschreibt, die aus dem `valarray<Type>` Objekt ausgewählt werden sollen.

Sie erstellen nur dann ein `indirect_array<Type>` Objekt, indem Sie einen Ausdruck der Form `va[xa]` schreiben. Die Element Funktionen der Klasse Indirect_array Verhalten sich dann wie die entsprechenden Funktions Signaturen, die für `valarray<Type>` definiert sind, mit dem Unterschied, dass nur die Reihenfolge der ausgewählten Elemente betroffen ist.

Die Sequenz besteht aus **XA.** [size](../standard-library/valarray-class.md#size) -Elemente, wobei Element `I` zum Index **XA**[`I`] innerhalb `va` wird.

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

### <a name="output"></a>Output

```cpp
The initial operand valarray is:  (0 -1 2 -1 4 -1 6 -1 8 -1).
The modified operand valarray is:  (0 -1 10 -1 10 -1 10 -1 8 -1).
```

## <a name="requirements"></a>Anforderungen

**Header:** \<valarray>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Thread Safety in the C++ Standard Library (Threadsicherheit in der C++-Standardbibliothek)](../standard-library/thread-safety-in-the-cpp-standard-library.md)
