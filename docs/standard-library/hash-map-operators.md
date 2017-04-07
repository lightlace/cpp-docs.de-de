---
title: '&lt;hash_map&gt;-Operatoren | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24b9bb9e-e983-4060-bce5-2c7c8161ee61
caps.latest.revision: 13
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 6960d7dfc3a6f36f803ae765ad4cbeb77038401c
ms.lasthandoff: 02/24/2017

---
# <a name="lthashmapgt-operators"></a>&lt;hash_map&gt;-Operatoren
||||  
|-|-|-|  
|[operator!=](#operator_neq)|[operator!= (hash_map)](#operator_neq__hash_map_)|[operator==](#operator_eq_eq)|  
|[operator== (hash_map)](#operator_eq_eq__hash_map_)|  
  
##  <a name="operator_neq__hash_map_"></a> operator!= (hash_map)  
  
> [!NOTE]
>  Diese API ist veraltet. Die Alternative ist die [unordered_map-Klasse](../standard-library/unordered-map-class.md).  
  
 Testet, ob das hash_map-Objekt links vom Operator ungleich dem hash_map-Objekt rechts vom Operator ist.  
  
```  
bool operator!=(const hash_map <Key, Type, Traits, Allocator>& left, const hash_map <Key, Type, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Parameter  
 `left`  
 Ein Objekt vom Typ `hash_map`.  
  
 `right`  
 Ein Objekt vom Typ `hash_map`.  
  
### <a name="return-value"></a>Rückgabewert  
 **TRUE**, wenn die hash_maps ungleich sind; **FALSE**, wenn hash_maps gleich sind.  
  
### <a name="remarks"></a>Hinweise  
 Der Vergleich zwischen den hash_map-Objekten basiert auf einem paarweisen Vergleich der entsprechenden Elemente. Zwei hash_maps sind gleich, wenn sie über die gleiche Anzahl von Elementen verfügen, und die entsprechenden Elemente dieselben Werte aufweisen. Andernfalls sind sie ungleich.  
  
 In Visual C++ .NET 2003 sind Member der [<hash_map>](../standard-library/hash-map.md)- und [<hash_set>](../standard-library/hash-set.md)-Headerdateien nicht mehr im STD-Namespace enthalten. Sie wurden stattdessen in den stdext-Namespace verschoben. Weitere Informationen finden Sie unter [Der stdext-Namespace](../standard-library/stdext-namespace.md).  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// hash_map_op_ne.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_map <int, int> hm1, hm2, hm3;  
   int i;  
   typedef pair <int, int> Int_Pair;  
  
   for ( i = 0 ; i < 3 ; i++ )  
   {  
      hm1.insert ( Int_Pair ( i, i ) );  
      hm2.insert ( Int_Pair ( i, i * i ) );  
      hm3.insert ( Int_Pair ( i, i ) );  
   }  
  
   if ( hm1 != hm2 )  
      cout << "The hash_maps hm1 and hm2 are not equal." << endl;  
   else  
      cout << "The hash_maps hm1 and hm2 are equal." << endl;  
  
   if ( hm1 != hm3 )  
      cout << "The hash_maps hm1 and hm3 are not equal." << endl;  
   else  
      cout << "The hash_maps hm1 and hm3 are equal." << endl;  
}  
```  
  
```Output  
The hash_maps hm1 and hm2 are not equal.  
The hash_maps hm1 and hm3 are equal.  
```  
  
##  <a name="operator_eq_eq__hash_map_"></a> operator== (hash_map)  
  
> [!NOTE]
>  Diese API ist veraltet. Die Alternative ist die [unordered_map-Klasse](../standard-library/unordered-map-class.md).  
  
 Testet, ob das hash_map-Objekt links vom Operator gleich dem hash_map-Objekt rechts vom Operator ist.  
  
```  
bool operator==(const hash_map <Key, Type, Traits, Allocator>& left, const hash_map <Key, Type, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Parameter  
 `left`  
 Ein Objekt vom Typ `hash_map`.  
  
 `right`  
 Ein Objekt vom Typ `hash_map`.  
  
### <a name="return-value"></a>Rückgabewert  
 **TRUE**, wenn die hash_map links vom Operator gleich der hash_map rechts vom Operator ist; andernfalls **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Der Vergleich zwischen den hash_map-Objekten basiert auf einem paarweisen Vergleich der entsprechenden Elemente. Zwei hash_maps sind gleich, wenn sie über die gleiche Anzahl von Elementen verfügen, und die entsprechenden Elemente dieselben Werte aufweisen. Andernfalls sind sie ungleich.  
  
 In Visual C++ .NET 2003 sind Member der [<hash_map>](../standard-library/hash-map.md)- und [<hash_set>](../standard-library/hash-set.md)-Headerdateien nicht mehr im STD-Namespace enthalten. Sie wurden stattdessen in den stdext-Namespace verschoben. Weitere Informationen finden Sie unter [Der stdext-Namespace](../standard-library/stdext-namespace.md).  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// hash_map_op_eq.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_map <int, int> hm1, hm2, hm3;  
   int i;  
   typedef pair <int, int> Int_Pair;  
  
   for ( i = 0 ; i < 3 ; i++ )  
   {  
      hm1.insert ( Int_Pair ( i, i ) );  
      hm2.insert ( Int_Pair ( i, i * i ) );  
      hm3.insert ( Int_Pair ( i, i ) );  
   }  
  
   if ( hm1 == hm2 )  
      cout << "The hash_maps hm1 and hm2 are equal." << endl;  
   else  
      cout << "The hash_maps hm1 and hm2 are not equal." << endl;  
  
   if ( hm1 == hm3 )  
      cout << "The hash_maps hm1 and hm3 are equal." << endl;  
   else  
      cout << "The hash_maps hm1 and hm3 are not equal." << endl;  
}  
```  
  
```Output  
The hash_maps hm1 and hm2 are not equal.  
The hash_maps hm1 and hm3 are equal.  
```  
  
##  <a name="operator_neq"></a> operator!=  
  
> [!NOTE]
>  Diese API ist veraltet. Die Alternative ist [unordered_multimap Class](../standard-library/unordered-multimap-class.md).  
  
 Überprüft, ob das hash_multimap-Objekt links vom Operator ungleich dem hash_multimap-Objekt rechts vom Operator ist.  
  
```  
bool operator!=(const hash_multimap <Key, Type, Traits, Allocator>& left, const hash_multimap <Key, Type, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Parameter  
 `left`  
 Ein Objekt vom Typ `hash_multimap`.  
  
 `right`  
 Ein Objekt vom Typ `hash_multimap`.  
  
### <a name="return-value"></a>Rückgabewert  
 **TRUE**, wenn die hash_multimaps ungleich sind; **FALSE**, wenn hash_multimaps gleich sind.  
  
### <a name="remarks"></a>Hinweise  
 Der Vergleich zwischen den hash_multimap-Objekten basiert auf einem paarweisen Vergleich der entsprechenden Elemente. Zwei hash_multimaps sind gleich, wenn sie über die gleiche Anzahl von Elementen verfügen und die entsprechenden Elemente dieselben Werte aufweisen. Andernfalls sind sie ungleich.  
  
 In Visual C++ .NET 2003 sind Member der [<hash_map>](../standard-library/hash-map.md)- und [<hash_set>](../standard-library/hash-set.md)-Headerdateien nicht mehr im STD-Namespace enthalten. Sie wurden stattdessen in den stdext-Namespace verschoben. Weitere Informationen finden Sie unter [Der stdext-Namespace](../standard-library/stdext-namespace.md).  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// hash_multimap_op_ne.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_multimap <int, int> hm1, hm2, hm3;  
   int i;  
   typedef pair <int, int> Int_Pair;  
  
   for ( i = 0 ; i < 3 ; i++ )  
   {  
      hm1.insert ( Int_Pair ( i, i ) );  
      hm2.insert ( Int_Pair ( i, i * i ) );  
      hm3.insert ( Int_Pair ( i, i ) );  
   }  
  
   if ( hm1 != hm2 )  
      cout << "The hash_multimaps hm1 and hm2 are not equal." << endl;  
   else  
      cout << "The hash_multimaps hm1 and hm2 are equal." << endl;  
  
   if ( hm1 != hm3 )  
      cout << "The hash_multimaps hm1 and hm3 are not equal." << endl;  
   else  
      cout << "The hash_multimaps hm1 and hm3 are equal." << endl;  
}  
```  
  
```Output  
The hash_multimaps hm1 and hm2 are not equal.  
The hash_multimaps hm1 and hm3 are equal.  
```  
  
##  <a name="operator_eq_eq"></a> operator==  
  
> [!NOTE]
>  Diese API ist veraltet. Die Alternative ist [unordered_multimap Class](../standard-library/unordered-multimap-class.md).  
  
 Überprüft, ob das hash_multimap-Objekt links vom Operator gleich dem hash_multimap-Objekt rechts vom Operator ist.  
  
```  
bool operator==(const hash_multimap <Key, Type, Traits, Allocator>& left, const hash_multimap <Key, Type, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Parameter  
 `left`  
 Ein Objekt vom Typ `hash_multimap`.  
  
 `right`  
 Ein Objekt vom Typ `hash_multimap`.  
  
### <a name="return-value"></a>Rückgabewert  
 **TRUE**, wenn die hash_multimap links vom Operator gleich der hash_multimap rechts vom Operator ist; andernfalls **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Der Vergleich zwischen den hash_multimap-Objekten basiert auf einem paarweisen Vergleich der entsprechenden Elemente. Zwei hash_multimaps sind gleich, wenn sie über die gleiche Anzahl von Elementen verfügen und die entsprechenden Elemente dieselben Werte aufweisen. Andernfalls sind sie ungleich.  
  
 In Visual C++ .NET 2003 sind Member der [<hash_map>](../standard-library/hash-map.md)- und [<hash_set>](../standard-library/hash-set.md)-Headerdateien nicht mehr im STD-Namespace enthalten. Sie wurden stattdessen in den stdext-Namespace verschoben. Weitere Informationen finden Sie unter [Der stdext-Namespace](../standard-library/stdext-namespace.md).  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// hash_multimap_op_eq.cpp  
// compile with: /EHsc  
#include <hash_map>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_multimap<int, int> hm1, hm2, hm3;  
   int i;  
   typedef pair<int, int> Int_Pair;  
  
   for (i = 0; i < 3; i++)  
   {  
      hm1.insert(Int_Pair(i, i));  
      hm2.insert(Int_Pair(i, i*i));  
      hm3.insert(Int_Pair(i, i));  
   }  
  
   if ( hm1 == hm2 )  
      cout << "The hash_multimaps hm1 and hm2 are equal." << endl;  
   else  
      cout << "The hash_multimaps hm1 and hm2 are not equal." << endl;  
  
   if ( hm1 == hm3 )  
      cout << "The hash_multimaps hm1 and hm3 are equal." << endl;  
   else  
      cout << "The hash_multimaps hm1 and hm3 are not equal." << endl;  
}  
```  
  
```Output  
The hash_multimaps hm1 and hm2 are not equal.  
The hash_multimaps hm1 and hm3 are equal.  
```  
  
## <a name="see-also"></a>Siehe auch  
 [<hash_map>](../standard-library/hash-map.md)


