---
title: not_equal_to-Struktur
ms.date: 11/04/2016
f1_keywords:
- functional/std::not_equal_to
helpviewer_keywords:
- not_equal_to function
- not_equal_to struct
ms.assetid: 333fce09-4f51-44e0-ba26-533bccffd485
ms.openlocfilehash: 8dc0e5710790714bab2c0109db3a4aa41f0acbaf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62223596"
---
# <a name="notequalto-struct"></a>not_equal_to-Struktur

Ein binäres Prädikat, mit dem der Ungleichheitsvorgang (`operator!=`) auf den Argumenten ausgeführt wird.

## <a name="syntax"></a>Syntax

```
template <class Type = void>
struct not_equal_to : public binary_function<Type, Type, bool>
{
    bool operator()(const Type& Left, const Type& Right) const;
};

// specialized transparent functor for operator!=
template <>
struct not_equal_to<void>
{
  template <class T, class U>
  auto operator()(T&& Left, U&& Right) const`
    -> decltype(std::forward<T>(Left) != std::forward<U>(Right));
};
```

### <a name="parameters"></a>Parameter

*Typ*, *T*, *U* jeder Typ, unterstützt eine `operator!=` , das Operanden angegebener oder abgeleiteter Typen akzeptiert.

*Links*<br/>
Der linke Operand des Ungleichheitsvorgangs. Die nicht spezialisierte Vorlage besitzt ein Lvalue-Verweisargument vom Typ *Typ*. Die spezialisierte Vorlage vervollkommnet die Weiterleitung von Lvalue und Rvalue-verweisargumenten des abgeleiteten Typs *T*.

*Rechts*<br/>
Der rechte Operand des Ungleichheitsvorgangs. Die nicht spezialisierte Vorlage besitzt ein Lvalue-Verweisargument vom Typ *Typ*. Die spezialisierte Vorlage vervollkommnet die Weiterleitung von Lvalue und Rvalue-verweisargumenten des abgeleiteten Typs *U*.

## <a name="return-value"></a>Rückgabewert

Das Ergebnis von `Left != Right`. Die spezialisierte Vorlage vervollkommnet die Weiterleitung des Ergebnisses mit dem von `operator!=` zurückgegebenen Typs.

## <a name="remarks"></a>Hinweise

Die Objekte vom Typ *Typ* müssen auf Gleichheit vergleichbar sein. Das erfordert, dass das mit dem `operator!=`-Element, das im Satz von Objekten definiert wird, die Eigenschaften einer mathematischen Äquivalenzrelation erfüllt werden. Alle integrierten numerischen Typen und Zeigertypen erfüllen diese Anforderung.

## <a name="example"></a>Beispiel

```cpp
// functional_not_equal_to.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

int main( )
{
   vector <double> v1, v2, v3 (6);
   vector <double>::iterator Iter1, Iter2, Iter3;

   int i;
   for ( i = 0 ; i <= 5 ; i+=2 )
   {
      v1.push_back( 2.0 *i );
      v1.push_back( 2.0 * i + 1.0 );
   }

   int j;
   for ( j = 0 ; j <= 5 ; j+=2 )
   {
      v2.push_back( - 2.0 * j );
      v2.push_back( 2.0 * j + 1.0 );
   }

   cout << "The vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   cout << "The vector v2 = ( " ;
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )
      cout << *Iter2 << " ";
   cout << ")" << endl;

   // Testing for the element-wise equality between v1 & v2
   transform ( v1.begin( ), v1.end( ), v2.begin( ), v3.begin ( ),
      not_equal_to<double>( ) );

   cout << "The result of the element-wise not_equal_to comparsion\n"
      << "between v1 & v2 is: ( " ;
   for ( Iter3 = v3.begin( ) ; Iter3 != v3.end( ) ; Iter3++ )
      cout << *Iter3 << " ";
   cout << ")" << endl;
}
/* Output:
The vector v1 = ( 0 1 4 5 8 9 )
The vector v2 = ( -0 1 -4 5 -8 9 )
The result of the element-wise not_equal_to comparsion
between v1 & v2 is: ( 0 0 1 0 1 0 )
*/
```

## <a name="requirements"></a>Anforderungen

**Header:** \<functional>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)<br/>
