---
title: modulus-Struktur
ms.date: 11/04/2016
f1_keywords:
- xfunctional/std::modulus
helpviewer_keywords:
- modulus class
- modulus struct
ms.assetid: 86d342f7-b7b1-46a4-b0bb-6b7ae827369b
ms.openlocfilehash: e5ab03cf51a001e6e62d3bc09c2899b8a319456b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50478623"
---
# <a name="modulus-struct"></a>modulus-Struktur

Ein vordefiniertes Funktionsobjekt, das den Modulusdivisionsvorgang (`operator%`) auf den Argumenten ausführt.

## <a name="syntax"></a>Syntax

```
template <class Type = void>
struct modulus : public binary_function <Type, Type, Type>
{
    Type operator()(const Type& Left, const Type& Right) const;
};

// specialized transparent functor for operator%
template <>
struct modulus<void>
{
  template <class T, class U>
  auto operator()(T&& Left, U&& Right) const`
    -> decltype(std::forward<T>(Left) % std::forward<U>(Right));
};
```

### <a name="parameters"></a>Parameter

*Typ*, *T*, *U* jeder Typ, unterstützt eine `operator%` , das Operanden angegebener oder abgeleiteter Typen akzeptiert.

*Links*<br/>
Der linke Operand des Modulusvorgangs. Die nicht spezialisierte Vorlage besitzt ein Lvalue-Verweisargument vom Typ *Typ*. Die spezialisierte Vorlage vervollkommnet die Weiterleitung von Lvalue und Rvalue-verweisargumenten des abgeleiteten Typs *T*.

*Rechts*<br/>
Der rechte Operand des Modulusvorgangs. Die nicht spezialisierte Vorlage besitzt ein Lvalue-Verweisargument vom Typ *Typ*. Die spezialisierte Vorlage vervollkommnet die Weiterleitung von Lvalue und Rvalue-verweisargumenten des abgeleiteten Typs *U*.

## <a name="return-value"></a>Rückgabewert

Das Ergebnis von `Left % Right`. Die spezialisierte Vorlage vervollkommnet die Weiterleitung des Ergebnisses mit dem von `operator%` zurückgegebenen Typs.

## <a name="remarks"></a>Hinweise

Das `modulus`-Funktionselement wird auf Ganzzahltypen für die grundlegenden Datentypen oder benutzerdefinierte Typen beschränkt, die `operator%` implementieren.

## <a name="example"></a>Beispiel

```cpp
// functional_modulus.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

int main( )
{
   vector <int> v1, v2, v3 ( 6 );
   vector <int>::iterator Iter1, Iter2, Iter3;

   int i;
   for ( i = 1 ; i <= 6 ; i++ )
   {
      v1.push_back( 5 * i );
   }

   int j;
   for ( j = 1 ; j <= 6 ; j++ )
   {
      v2.push_back( 3 * j );
   }

   cout << "The vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   cout << "The vector v2 = ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )
      cout << *Iter2 << " ";
   cout << ")" << endl;

   // Finding the element-wise remainders of the elements of v1 & v2
   transform (v1.begin( ),  v1.end( ), v2.begin( ), v3.begin ( ),
      modulus<int>() );

   cout << "The element-wise remainders of the modular division\n are: ( " ;
   for ( Iter3 = v3.begin( ) ; Iter3 != v3.end( ) ; Iter3++ )
      cout << *Iter3 << " ";
   cout << ")" << endl;
}
/* Output:
The vector v1 = ( 5 10 15 20 25 30 )
The vector v2 = ( 3 6 9 12 15 18 )
The element-wise remainders of the modular division
are: ( 2 4 6 8 10 12 )
*/
```

## <a name="requirements"></a>Anforderungen

**Header:** \<functional>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)<br/>
