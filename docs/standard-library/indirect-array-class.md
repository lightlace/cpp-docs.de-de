---
title: indirect_array-Klasse
ms.date: 11/04/2016
f1_keywords:
- valarray/std::indirect_array
helpviewer_keywords:
- indirect_array class
ms.assetid: 10e1eaea-ba5a-405c-a25e-7bdd3eee7fc7
ms.openlocfilehash: 43c54bf3dae02eb117b15cae0dd7de9bb4a9db51
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50448879"
---
# <a name="indirectarray-class"></a>indirect_array-Klasse

Eine interne zusätzliche Vorlagenklasse, die allgemeine Objekte, die Teilmengen von valarray-Objekten sind, unterstützt, indem sie Vorgänge zwischen Teilmengenarrays bereitstellt, die durch Angeben einer Teilmenge von Indizes eines übergeordneten valarray-Objekts definiert sind.

## <a name="syntax"></a>Syntax

## <a name="remarks"></a>Hinweise

Die Klasse beschreibt ein Objekt, das einen Verweis auf ein Objekt speichert `va` Klasse [Valarray](../standard-library/valarray-class.md)**\<Typ >**, zusammen mit einem Objekt `xa` Klasse `valarray<size_t>`, Beschreibt, die die Sequenz von Elementen aus der `valarray<Type>` Objekt.

Sie erstellen eine `indirect_array<Type>` -Objekt nur, indem Sie das Schreiben eines Ausdrucks des Formulars `va[xa]`. Die Memberfunktionen der Indirect_array-Klasse Verhalten sich dann wie die entsprechenden Funktionssignaturen für definiert `valarray<Type>`, außer dass nur die Reihenfolge der ausgewählten Elemente betroffen ist.

Die Sequenz besteht aus **Xa.** [Größe](../standard-library/valarray-class.md#size) Elemente, in dem Element `I` wird der Index **Xa**[ `I`] innerhalb von `va`.

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

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
