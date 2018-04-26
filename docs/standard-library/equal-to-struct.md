---
title: equal_to-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- xfunctional/std::equal_to
dev_langs:
- C++
helpviewer_keywords:
- equal_to function
- equal_to struct
ms.assetid: 8e4f2b50-b2db-48e3-b4cc-6cc03362c2a6
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cc80add30616b35a0d0c22ad3f84bfb5187b3495
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="equalto-struct"></a>equal_to-Struktur

Ein binäres Prädikat, mit dem der Gleichheitsvorgang (`operator==`) auf den Argumenten ausgeführt wird.

## <a name="syntax"></a>Syntax

```cpp
template <class Type = void>
struct equal_to : public binary_function<Type, Type, bool>
 {
    bool operator()(const Type& Left, const Type& Right) const;
 };

// specialized transparent functor for operator==
template <>
struct equal_to<void>
 {
    template <class T, class U>
    auto operator()(T&& Left, U&& Right) const
      ->  decltype(std::forward<T>(Left) == std::forward<U>(Right));
 };
```

### <a name="parameters"></a>Parameter

`Type`, `T`, `U` Jeder Typ, der unterstützt ein `operator==` , das Operanden angegebenen oder abgeleiteten Typen akzeptiert.

`Left` Der linke Operand des gleichheitsvorgangs. Die nicht spezialisierte Vorlage besitzt ein lvalue-Verweisargument vom Typ `Type`. Die spezialisierte Vorlage vervollkommnet die Weiterleitung von lvalue und rvalue-Verweisargumenten des abgeleiteten Typs `T`.

`Right` Der Rechte Operand des gleichheitsvorgangs. Die nicht spezialisierte Vorlage besitzt ein lvalue-Verweisargument vom Typ `Type`. Die spezialisierte Vorlage vervollkommnet die Weiterleitung von lvalue und rvalue-Verweisargumenten des abgeleiteten Typs `U`.

## <a name="return-value"></a>Rückgabewert

Das Ergebnis von `Left == Right`. Die spezialisierte Vorlage vervollkommnet die Weiterleitung des Ergebnisses mit dem von `operator==` zurückgegebenen Typs.

## <a name="remarks"></a>Hinweise

Die Objekte vom Typ `Type` müssen auf Gleichheit vergleichbar sein. Das erfordert, dass das mit dem `operator==`-Element, das im Satz von Objekten definiert wird, die Eigenschaften einer mathematischen Äquivalenzrelation erfüllt werden. Alle integrierten numerischen Typen und Zeigertypen erfüllen diese Anforderung.

## <a name="example"></a>Beispiel

```cpp
// functional_equal_to.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

int main( )
{
   vector <double> v1, v2, v3 ( 6 );
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
   transform ( v1.begin( ),  v1.end( ), v2.begin( ), v3.begin ( ),
      equal_to<double>( ) );

   cout << "The result of the element-wise equal_to comparison\n"
      << "between v1 & v2 is: ( " ;
   for ( Iter3 = v3.begin( ) ; Iter3 != v3.end( ) ; Iter3++ )
      cout << *Iter3 << " ";
   cout << ")" << endl;
}
```

```Output
The vector v1 = ( 0 1 4 5 8 9 )
The vector v2 = ( -0 1 -4 5 -8 9 )
The result of the element-wise equal_to comparison
between v1 & v2 is: ( 1 1 0 1 0 1 )
```

