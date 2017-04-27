---
title: less_equal-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- xfunctional/std::less_equal
- less_equal
dev_langs:
- C++
helpviewer_keywords:
- less_equal function
- less_equal struct
ms.assetid: 32085782-c7e0-4310-9b40-8aa3c1bff211
caps.latest.revision: 23
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 2d05749ba2837a3879c91886b9266de47dd2ece6
ms.openlocfilehash: 58e188cc830140ace78777a03959a7f4e170f328
ms.lasthandoff: 02/24/2017

---
# <a name="lessequal-struct"></a>less_equal-Struktur
Ein binäres Prädikat, das den kleiner-oder-gleich-Vorgang (`operator<=`) mit den Argumenten ausführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class Type = void>
struct less_equal : public binary_function <Type, Type, bool>  
{
    bool operator()(const Type& Left, const Type& Right) const;
};

// specialized transparent functor for operator<=
template <>
struct less_equal<void>  
{
  template <class T, class U>
  auto operator()(T&& Left, U&& Right) const`
    -> decltype(std::forward<T>(Left) <= std::forward<U>(Right));
};
```  
  
#### <a name="parameters"></a>Parameter  
 `Type`, `T`, `U`  
 Jeder Typ, der ein `operator<=`-Element unterstützt, das Operanden angegebener oder abgeleiteter Typen akzeptiert.  
  
 `Left`  
 Der linke Operand des kleiner-oder-gleich-Vorgangs. Die nicht spezialisierte Vorlage besitzt ein lvalue-Verweisargument vom Typ `Type`. Die spezialisierte Vorlage vervollkommnet die Weiterleitung von lvalue und rvalue-Verweisargumenten des abgeleiteten Typs `T`.  
  
 `Right`  
 Der rechte Operand des kleiner-oder-gleich-Vorgangs. Die nicht spezialisierte Vorlage besitzt ein lvalue-Verweisargument vom Typ `Type`. Die spezialisierte Vorlage vervollkommnet die Weiterleitung von lvalue und rvalue-Verweisargumenten des abgeleiteten Typs `U`.  
  
## <a name="return-value"></a>Rückgabewert  
 Das Ergebnis von `Left``<=``Right`. Die spezialisierte Vorlage vervollkommnet die Weiterleitung des Ergebnisses mit dem von `operator<=` zurückgegebenen Typs.  
  
## <a name="remarks"></a>Hinweise  
 Das binäre Prädikat `less_equal`< `Type`> stellt eine strenge, schwache Sortierung eines Satzes von Elementwerten vom Typ `Type` in Äquivalenzklassen bereit, wenn und nur wenn dieser Typ den mathematischen Standardanforderungen für eine solche Sortierung entspricht. Die Spezialisierungen für einen Zeigertyp ergeben eine gesamte Sortierung von Elementen, insofern, dass alle Elemente unterschiedlicher Werte zueinander in Beziehung stehend sortiert werden.  
  
## <a name="example"></a>Beispiel  
  
```cpp  
// functional_less_equal.cpp  
// compile with: /EHsc  
#define _CRT_RAND_S  
#include <stdlib.h>  
#include <vector>  
#include <algorithm>  
#include <functional>  
#include <cstdlib>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   vector <int> v1;  
   vector <int>::iterator Iter1;  
   vector <int>::reverse_iterator rIter1;  
   unsigned int randomNumber;  
  
   int i;  
   for ( i = 0 ; i < 5 ; i++ )  
   {  
      if ( rand_s( &randomNumber ) == 0 )  
      {  
         // Convert the random number to be between 1 - 50000  
         // This is done for readability purposes  
         randomNumber = ( unsigned int) ((double)randomNumber /   
            (double) UINT_MAX * 50000) + 1;  
  
         v1.push_back( randomNumber );  
      }  
   }  
   for ( i = 0 ; i < 3 ; i++ )  
   {  
      v1.push_back( 2836 );  
   }  
  
   cout << "Original vector v1 = ( " ;  
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )  
      cout << *Iter1 << " ";  
   cout << ")" << endl;  
  
   // To sort in ascending order,  
   // use the binary predicate less_equal<int>( )  
   sort( v1.begin( ), v1.end( ), less_equal<int>( ) );  
   cout << "Sorted vector v1 = ( " ;  
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )  
      cout << *Iter1 << " ";  
   cout << ")" << endl;  
}  
```  
  
## <a name="sample-output"></a>Beispielausgabe  
  
```
Original vector v1 = (31247 37154 48755 15251 6205 2836 2836 2836)
Sorted vector v1 = (2836 2836 2836 6205 15251 31247 37154 48755)
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<functional>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)




