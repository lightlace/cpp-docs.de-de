---
title: logical_not-Struktur
ms.date: 11/04/2016
f1_keywords:
- functional/std::logical_not
helpviewer_keywords:
- logical_not class
- logical_not struct
ms.assetid: 892db678-31da-4540-974b-17b05efc0849
ms.openlocfilehash: 7fd554a28775a6b625332ac250a46171dd369f50
ms.sourcegitcommit: 4299caac2dc9e806c74ac833d856a3838b0f52a1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "57006564"
---
# <a name="logicalnot-struct"></a>logical_not-Struktur

Ein vordefiniertes Funktionsobjekt, mit dem der logische NOT-Vorgang (`operator!`) auf das Argument ausgeführt werden kann.

## <a name="syntax"></a>Syntax

```
template <class Type = void>
struct logical_not : public unary_function<Type, bool>
{
    bool operator()(const Type& Left) const;
};

// specialized transparent functor for operator!
template <>
struct logical_not<void>
{
  template <class Type>
  auto operator()(Type&& Left) const`
     -> decltype(!std::forward<Type>(Left));
};
```

### <a name="parameters"></a>Parameter

*Type*<br/>
Jeder Typ, der ein `operator!`-Element unterstützt, das einen Operanden des angegebenen oder abgeleiteten Typs akzeptiert.

*Links*<br/>
Der Operand des logischen NOT-Vorgangs. Die nicht spezialisierte Vorlage besitzt ein Lvalue-Verweisargument vom Typ *Typ*. Die spezialisierte Vorlage vervollkommnet die Weiterleitung von Lvalue und Rvalue-verweisargumenten des abgeleiteten Typs *Typ*.

## <a name="return-value"></a>Rückgabewert

Das Ergebnis von `!Left`. Die spezialisierte Vorlage vervollkommnet die Weiterleitung des Ergebnisses mit dem von `operator!` zurückgegebenen Typs.

## <a name="example"></a>Beispiel

```cpp
// functional_logical_not.cpp
// compile with: /EHsc
#include <deque>
#include <algorithm>
#include <functional>
#include <iostream>

int main( )
{
   using namespace std;
   deque<bool> d1, d2 ( 7 );
   deque<bool>::iterator iter1, iter2;

   int i;
   for ( i = 0 ; i < 7 ; i++ )
   {
      d1.push_back((bool)((i % 2) != 0));
   }

   cout << boolalpha;    // boolalpha I/O flag on

   cout << "Original deque:\n d1 = ( " ;
   for ( iter1 = d1.begin( ) ; iter1 != d1.end( ) ; iter1++ )
      cout << *iter1 << " ";
   cout << ")" << endl;

   // To flip all the truth values of the elements,
   // use the logical_not function object
   transform( d1.begin( ), d1.end( ), d2.begin( ),logical_not<bool>( ) );
   cout << "The deque with its values negated is:\n d2 = ( " ;
   for ( iter2 = d2.begin( ) ; iter2 != d2.end( ) ; iter2++ )
      cout << *iter2 << " ";
   cout << ")" << endl;
}
/* Output:
Original deque:
d1 = ( false true false true false true false )
The deque with its values negated is:
d2 = ( true false true false true false true )
*/
```

## <a name="requirements"></a>Anforderungen

**Header:** \<functional>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)<br/>
