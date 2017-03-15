---
title: '&lt;hash_set&gt;-Operatoren | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 403d8e4e-0b3f-43fb-bc5a-8100c4f331c5
caps.latest.revision: 13
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 031904042e81f5ec9c8b54bbc3e2bfa9e9a365cf
ms.lasthandoff: 02/24/2017

---
# <a name="lthashsetgt-operators"></a>&lt;hash_set&gt;-Operatoren
||||  
|-|-|-|  
|[operator!=](#operator_neq)|[operator!= (hash_multiset)](#operator_neq__hash_multiset_)|[operator==](#operator_eq_eq)|  
|[operator== (hash_multiset)](#operator_eq_eq__hash_multiset_)|  
  
##  <a name="a-nameoperatorneqa--operator"></a><a name="operator_neq"></a> operator!=  
  
> [!NOTE]
>  Diese API ist veraltet. Die Alternative ist [unordered_set-Klasse](../standard-library/unordered-set-class.md).  
  
 Testet, ob das hash_set-Objekt links vom Operator ungleich dem hash_set-Objekt rechts vom Operator ist.  
  
```  
bool operator!=(const hash_set <Key, Traits, Allocator>& left, const hash_set <Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Parameter  
 ` left`  
 Ein Objekt vom Typ `hash_set`.  
  
 ` right`  
 Ein Objekt vom Typ `hash_set`.  
  
### <a name="return-value"></a>Rückgabewert  
 **TRUE**, wenn die hash_sets ungleich sind; **FALSE**, wenn sie gleich sind.  
  
### <a name="remarks"></a>Hinweise  
 Der Vergleich zwischen den hash_set-Objekten basiert auf einem paarweisen Vergleich zwischen deren Elemente. Zwei hash_sets sind gleich, wenn sie über die gleiche Anzahl von Elementen verfügen und die entsprechenden Elemente dieselben Werte aufweisen. Andernfalls sind sie ungleich.  
  
 In Visual C++ .NET 2003 sind Member der [<hash_map>](../standard-library/hash-map.md)- und [<hash_set>](../standard-library/hash-set.md)-Headerdateien nicht mehr im STD-Namespace enthalten. Sie wurden stattdessen in den stdext-Namespace verschoben. Weitere Informationen finden Sie unter [Der stdext-Namespace](../standard-library/stdext-namespace.md).  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// hash_set_op_ne.cpp  
// compile with: /EHsc  
#include <hash_set>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   using namespace stdext;  
   hash_set <int> hs1, hs2, hs3;  
   int i;  
  
   for ( i = 0 ; i < 3 ; i++ )  
   {  
      hs1.insert ( i );  
      hs2.insert ( i * i );  
      hs3.insert ( i );  
   }  
  
   if ( hs1 != hs2 )  
      cout << "The hash_sets hs1 and hs2 are not equal." << endl;  
   else  
      cout << "The hash_sets hs1 and hs2 are equal." << endl;  
  
   if ( hs1 != hs3 )  
      cout << "The hash_sets hs1 and hs3 are not equal." << endl;  
   else  
      cout << "The hash_sets hs1 and hs3 are equal." << endl;  
}  
```  
  
```Output  
The hash_sets hs1 and hs2 are not equal.  
The hash_sets hs1 and hs3 are equal.  
```  
  
##  <a name="a-nameoperatoreqeqa--operator"></a><a name="operator_eq_eq"></a> operator==  
  
> [!NOTE]
>  Diese API ist veraltet. Die Alternative ist [unordered_set-Klasse](../standard-library/unordered-set-class.md).  
  
 Testet, ob das hash_set-Objekt links vom Operator gleich dem hash_set-Objekt rechts vom Operator ist.  
  
```  
bool operator!==(const hash_set <Key, Traits, Allocator>& left, const hash_set <Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Parameter  
 ` left`  
 Ein Objekt vom Typ `hash_set`.  
  
 ` right`  
 Ein Objekt vom Typ `hash_set`.  
  
### <a name="return-value"></a>Rückgabewert  
 **TRUE**, wenn das hash_set links vom Operator gleich des hash_set rechts vom Operator ist; andernfalls **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Der Vergleich zwischen den hash_set-Objekten basiert auf einem paarweisen Vergleich der entsprechenden Elemente. Zwei hash_sets sind gleich, wenn sie über die gleiche Anzahl von Elementen verfügen und die entsprechenden Elemente dieselben Werte aufweisen. Andernfalls sind sie ungleich.  
  
 In Visual C++ .NET 2003 sind Member der [<hash_map>](../standard-library/hash-map.md)- und [<hash_set>](../standard-library/hash-set.md)-Headerdateien nicht mehr im STD-Namespace enthalten. Sie wurden stattdessen in den stdext-Namespace verschoben. Weitere Informationen finden Sie unter [Der stdext-Namespace](../standard-library/stdext-namespace.md).  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// hash_set_op_eq.cpp  
// compile with: /EHsc  
#include <hash_set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_set <int> s1, s2, s3;  
   int i;  
  
   for ( i = 0 ; i < 3 ; i++ )  
   {  
      s1.insert ( i );  
      s2.insert ( i * i );  
      s3.insert ( i );  
   }  
  
   if ( s1 == s2 )  
      cout << "The hash_sets s1 and s2 are equal." << endl;  
   else  
      cout << "The hash_sets s1 and s2 are not equal." << endl;  
  
   if ( s1 == s3 )  
      cout << "The hash_sets s1 and s3 are equal." << endl;  
   else  
      cout << "The hash_sets s1 and s3 are not equal." << endl;  
}  
```  
  
```Output  
The hash_sets s1 and s2 are not equal.  
The hash_sets s1 and s3 are equal.  
```  
  
##  <a name="a-nameoperatorneqhashmultiseta--operator-hashmultiset"></a><a name="operator_neq__hash_multiset_"></a> operator!= (hash_multiset)  
  
> [!NOTE]
>  Diese API ist veraltet. Die Alternative ist [unordered_set-Klasse](../standard-library/unordered-set-class.md).  
  
 Überprüft, ob das hash_multiset-Objekt links vom Operator ungleich dem hash_multiset-Objekt rechts vom Operator ist.  
  
```  
bool operator!=(const hash_multiset <Key, Traits, Allocator>& left, const hash_multiset <Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Parameter  
 ` left`  
 Ein Objekt vom Typ `hash_multiset`.  
  
 ` right`  
 Ein Objekt vom Typ `hash_multiset`.  
  
### <a name="return-value"></a>Rückgabewert  
 **TRUE**, wenn die hash_multisets ungleich sind; **FALSE**, wenn sie gleich sind.  
  
### <a name="remarks"></a>Hinweise  
 Der Vergleich zwischen den hash_multiset-Objekten basiert auf einem paarweisen Vergleich zwischen deren Elemente. Zwei hash_multisets sind gleich, wenn sie über die gleiche Anzahl von Elementen verfügen und die entsprechenden Elemente dieselben Werte aufweisen. Andernfalls sind sie ungleich.  
  
 In Visual C++ .NET 2003 sind Member der [<hash_map>](../standard-library/hash-map.md)- und [<hash_set>](../standard-library/hash-set.md)-Headerdateien nicht mehr im STD-Namespace enthalten. Sie wurden stattdessen in den stdext-Namespace verschoben. Weitere Informationen finden Sie unter [Der stdext-Namespace](../standard-library/stdext-namespace.md).  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// hashset_op_ne.cpp  
// compile with: /EHsc  
#include <hash_set>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   using namespace stdext;  
   hash_multiset <int> hs1, hs2, hs3;  
   int i;  
  
   for ( i = 0 ; i < 3 ; i++ )  
   {  
      hs1.insert ( i );  
      hs2.insert ( i * i );  
      hs3.insert ( i );  
   }  
  
   if ( hs1 != hs2 )  
      cout << "The hash_multisets hs1 and hs2 are not equal." << endl;  
   else  
      cout << "The hash_multisets hs1 and hs2 are equal." << endl;  
  
   if ( hs1 != hs3 )  
      cout << "The hash_multisets hs1 and hs3 are not equal." << endl;  
   else  
      cout << "The hash_multisets hs1 and hs3 are equal." << endl;  
}  
```  
  
```Output  
The hash_multisets hs1 and hs2 are not equal.  
The hash_multisets hs1 and hs3 are equal.  
```  
  
##  <a name="a-nameoperatoreqeqhashmultiseta--operator-hashmultiset"></a><a name="operator_eq_eq__hash_multiset_"></a> operator== (hash_multiset)  
  
> [!NOTE]
>  Diese API ist veraltet. Die Alternative ist [unordered_set-Klasse](../standard-library/unordered-set-class.md).  
  
 Überprüft, ob das hash_multiset-Objekt links vom Operator gleich dem hash_multiset-Objekt rechts vom Operator ist.  
  
```  
bool operator!==(const hash_multiset <Key, Traits, Allocator>& left, const hash_multiset <Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Parameter  
 ` left`  
 Ein Objekt vom Typ `hash_multiset`.  
  
 ` right`  
 Ein Objekt vom Typ `hash_multiset`.  
  
### <a name="return-value"></a>Rückgabewert  
 **TRUE**, wenn das hash_multiset links vom Operator gleich des hash_multiset rechts vom Operator ist; andernfalls **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Der Vergleich zwischen den hash_multiset-Objekten basiert auf einem paarweisen Vergleich der entsprechenden Elemente. Zwei hash_multisets sind gleich, wenn sie über die gleiche Anzahl von Elementen verfügen und die entsprechenden Elemente dieselben Werte aufweisen. Andernfalls sind sie ungleich.  
  
 In Visual C++ .NET 2003 sind Member der [<hash_map>](../standard-library/hash-map.md)- und [<hash_set>](../standard-library/hash-set.md)-Headerdateien nicht mehr im STD-Namespace enthalten. Sie wurden stattdessen in den stdext-Namespace verschoben. Weitere Informationen finden Sie unter [Der stdext-Namespace](../standard-library/stdext-namespace.md).  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// hash_multiset_op_eq.cpp  
// compile with: /EHsc  
#include <hash_set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_multiset <int> s1, s2, s3;  
   int i;  
  
   for ( i = 0 ; i < 3 ; i++ )  
   {  
      s1.insert ( i );  
      s2.insert ( i * i );  
      s3.insert ( i );  
   }  
  
   if ( s1 == s2 )  
      cout << "The hash_multisets s1 and s2 are equal." << endl;  
   else  
      cout << "The hash_multisets s1 and s2 are not equal." << endl;  
  
   if ( s1 == s3 )  
      cout << "The hash_multisets s1 and s2 are equal." << endl;  
   else  
      cout << "The hash_multisets s1 and s2 are not equal." << endl;  
}  
```  
  
```Output  
The hash_multisets s1 and s2 are not equal.  
The hash_multisets s1 and s2 are equal.  
```  
  
## <a name="see-also"></a>Siehe auch  
 [<hash_set>](../standard-library/hash-set.md)


