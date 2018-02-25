---
title: '&lt;unordered_map&gt;-Operatoren | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- unordered_map/std::operator!=
- unordered_map/std::operator==
dev_langs:
- C++
ms.assetid: 9d5add0b-84bd-4a79-bd82-3f58b55145ed
caps.latest.revision: 
manager: ghogen
ms.openlocfilehash: d5ee8994367332e6e26d70e166bd0549d16fc965
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="ltunorderedmapgt-operators"></a>&lt;unordered_map&gt;-Operatoren
|||||  
|-|-|-|-|  
|[operator!=](#op_neq)|[operator==](#op_eq_eq)|[operator!=](#op_neq_multimap)|[operator==](#op_eq_eq_multimap)|  
  
##  <a name="op_neq"></a> operator!=  
 Testet, ob das [unordered_map](../standard-library/unordered-map-class.md)-Objekt links vom Operator ungleich dem unordered_map-Objekt rechts vom Operator ist.  
  
```
bool operator!=(const unordered_map <Key, Type, Hash, Pred, Allocator>& left, const unordered_map <Key, Type, Hash, Pred, Allocator>& right);
```  
  
### <a name="parameters"></a>Parameter  
 `left`  
 Ein Objekt vom Typ `unordered_map`.  
  
 `right`  
 Ein Objekt vom Typ `unordered_map`.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn die unordered_map-Objekte ungleich sind; `false`, wenn sie gleich sind.  
  
### <a name="remarks"></a>Hinweise  
 Die beliebige Reihenfolge, in der unordered_map-Objekte ihre Elemente speichern, hat keine Auswirkungen auf den Vergleich der Objekte. Zwei unordered_map-Objekte sind gleich, wenn sie dieselbe Anzahl von Elementen aufweisen und die Elemente in einem Container eine Permutation der Elemente im anderen Container sind. Andernfalls sind sie ungleich.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// unordered_map_op_ne.cpp  
// compile by using: cl.exe /EHsc /nologo /W4 /MTd   
#include <unordered_map>  
#include <iostream>  
#include <ios>  
  
int main( )  
{  
   using namespace std;  
   unordered_map<int, int> um1, um2, um3;  
  
   for ( int i = 0 ; i < 3 ; ++i ) {  
      um1.insert( make_pair( i+1, i ) );  
      um1.insert( make_pair( i, i ) );  
  
      um2.insert( make_pair( i, i+1 ) );  
      um2.insert( make_pair( i, i ) );  
  
      um3.insert( make_pair( i, i ) );  
      um3.insert( make_pair( i+1, i ) );  
   }  
  
   cout << boolalpha;  
   cout << "um1 != um2: " << (um1 != um2) << endl;   
   cout << "um1 != um3: " << (um1 != um3) << endl;   
   cout << "um2 != um3: " << (um2 != um3) << endl;   
}  
  
```  
  
 **Ausgabe:**  
  
 `um1 != um2: true`  
  
 `um1 != um3: false`  
  
 `um2 != um3: true`  
  
##  <a name="op_eq_eq"></a> operator==  
 Testet, ob das [unordered_map](../standard-library/unordered-map-class.md)-Objekt links vom Operator gleich dem unordered_map-Objekt rechts vom Operator ist.  
  
```
bool operator==(const unordered_map <Key, Type, Hash, Pred, Allocator>& left, const unordered_map <Key, Type, Hash, Pred, Allocator>& right);
```  
  
### <a name="parameters"></a>Parameter  
 `left`  
 Ein Objekt vom Typ `unordered_map`.  
  
 `right`  
 Ein Objekt vom Typ `unordered_map`.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn die unordered_map-Objekte gleich sind; `false`, wenn sie ungleich sind.  
  
### <a name="remarks"></a>Hinweise  
 Die beliebige Reihenfolge, in der unordered_map-Objekte ihre Elemente speichern, hat keine Auswirkungen auf den Vergleich der Objekte. Zwei unordered_map-Objekte sind gleich, wenn sie dieselbe Anzahl von Elementen aufweisen und die Elemente in einem Container eine Permutation der Elemente im anderen Container sind. Andernfalls sind sie ungleich.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// unordered_map_op_eq.cpp  
// compile by using: cl.exe /EHsc /nologo /W4 /MTd   
#include <unordered_map>  
#include <iostream>  
#include <ios>  
  
int main( )  
{  
   using namespace std;  
   unordered_map<int, int> um1, um2, um3;  
  
   for ( int i = 0 ; i < 3 ; ++i ) {  
      um1.insert( make_pair( i+1, i ) );  
      um1.insert( make_pair( i, i ) );  
  
      um2.insert( make_pair( i, i+1 ) );  
      um2.insert( make_pair( i, i ) );  
  
      um3.insert( make_pair( i, i ) );  
      um3.insert( make_pair( i+1, i ) );  
   }  
  
   cout << boolalpha;  
   cout << "um1 == um2: " << (um1 == um2) << endl;   
   cout << "um1 == um3: " << (um1 == um3) << endl;   
   cout << "um2 == um3: " << (um2 == um3) << endl;   
}  
  
```  
  
 **Ausgabe:**  
  
 `um1 == um2: false`  
  
 `um1 == um3: true`  
  
 `um2 == um3: false`  
  
##  <a name="op_neq_multimap"></a> operator!=  
 Überprüft, ob das [unordered_multimap](../standard-library/unordered-multimap-class.md)-Objekt links vom Operator ungleich dem unordered_multimap-Objekt rechts vom Operator ist.  
  
```
bool operator!=(const unordered_multimap <Key, Type, Hash, Pred, Allocator>& left, const unordered_multimap <Key, Type, Hash, Pred, Allocator>& right);
```  
  
### <a name="parameters"></a>Parameter  
 `left`  
 Ein Objekt vom Typ `unordered_multimap`.  
  
 `right`  
 Ein Objekt vom Typ `unordered_multimap`.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn die unordered_multimap-Objekte ungleich sind; `false`, wenn sie gleich sind.  
  
### <a name="remarks"></a>Hinweise  
 Die beliebige Reihenfolge, in der unordered_multimap-Objekte ihre Elemente speichern, hat keine Auswirkungen auf den Vergleich der Objekte. Zwei unordered_multimap-Objekte sind gleich, wenn sie dieselbe Anzahl von Elementen aufweisen und die Elemente in einem Container eine Permutation der Elemente im anderen Container sind. Andernfalls sind sie ungleich.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// unordered_multimap_op_ne.cpp  
// compile by using: cl.exe /EHsc /nologo /W4 /MTd   
#include <unordered_map>  
#include <iostream>  
#include <ios>  
  
int main( )  
{  
   using namespace std;  
   unordered_multimap<int, int> um1, um2, um3;  
  
   for ( int i = 0 ; i < 3 ; ++i ) {  
      um1.insert( make_pair( i, i ) );  
      um1.insert( make_pair( i, i ) );  
  
      um2.insert( make_pair( i, i ) );  
      um2.insert( make_pair( i, i ) );  
      um2.insert( make_pair( i, i ) );  
  
      um3.insert( make_pair( i, i ) );  
      um3.insert( make_pair( i, i ) );  
   }  
  
   cout << boolalpha;  
   cout << "um1 != um2: " << (um1 != um2) << endl;   
   cout << "um1 != um3: " << (um1 != um3) << endl;   
   cout << "um2 != um3: " << (um2 != um3) << endl;   
}  
  
```  
  
 **Ausgabe:**  
  
 `um1 != um2: true`  
  
 `um1 != um3: false`  
  
 `um2 != um3: true`  
  
##  <a name="op_eq_eq_multimap"></a> operator==  
 Überprüft, ob das [unordered_multimap](../standard-library/unordered-multimap-class.md)-Objekt links vom Operator gleich dem unordered_multimap-Objekt rechts vom Operator ist.  
  
```
bool operator==(const unordered_multimap <Key, Type, Hash, Pred, Allocator>& left, const unordered_multimap <Key, Type, Hash, Pred, Allocator>& right);
```  
  
### <a name="parameters"></a>Parameter  
 `left`  
 Ein Objekt vom Typ `unordered_multimap`.  
  
 `right`  
 Ein Objekt vom Typ `unordered_multimap`.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn die unordered_multimap-Objekte gleich sind; `false`, wenn sie ungleich sind.  
  
### <a name="remarks"></a>Hinweise  
 Die beliebige Reihenfolge, in der unordered_multimap-Objekte ihre Elemente speichern, hat keine Auswirkungen auf den Vergleich der Objekte. Zwei unordered_multimap-Objekte sind gleich, wenn sie dieselbe Anzahl von Elementen aufweisen und die Elemente in einem Container eine Permutation der Elemente im anderen Container sind. Andernfalls sind sie ungleich.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// unordered_multimap_op_eq.cpp  
// compile by using: cl.exe /EHsc /nologo /W4 /MTd  
#include <unordered_map>  
#include <iostream>  
#include <ios>  
  
int main( )  
{  
   using namespace std;  
   unordered_multimap<int, int> um1, um2, um3;  
  
   for ( int i = 0 ; i < 3 ; ++i ) {  
      um1.insert( make_pair( i, i ) );  
      um1.insert( make_pair( i, i ) );  
  
      um2.insert( make_pair( i, i ) );  
      um2.insert( make_pair( i, i ) );  
      um2.insert( make_pair( i, i ) );  
  
      um3.insert( make_pair( i, i ) );  
      um3.insert( make_pair( i, i ) );  
   }  
  
   cout << boolalpha;  
   cout << "um1 == um2: " << (um1 == um2) << endl;   
   cout << "um1 == um3: " << (um1 == um3) << endl;   
   cout << "um2 == um3: " << (um2 == um3) << endl;   
}  
  
```  
  
 **Ausgabe:**  
  
 `um1 == um2: false`  
  
 `um1 == um3: true`  
  
 `um2 == um3: false`  
  
## <a name="see-also"></a>Siehe auch  
 [<unordered_map>](../standard-library/unordered-map.md)



