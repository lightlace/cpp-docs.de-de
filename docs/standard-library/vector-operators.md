---
title: '&lt;vector&gt;-Operatoren | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d14f312-6f59-4ec7-88ae-95f89a558823
caps.latest.revision: 13
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 14308c0789851af423fd687f88acfe9177d89aff
ms.lasthandoff: 02/24/2017

---
# <a name="ltvectorgt-operators"></a>&lt;vector&gt;-Operatoren
||||  
|-|-|-|  
|[operator!=](#operator_neq)|[operator&gt;](#operator_gt_)|[operator&gt;=](#operator_gt__eq)|  
|[operator&lt;](#operator_lt_)|[operator&lt;=](#operator_lt__eq)|[operator==](#operator_eq_eq)|  
  
##  <a name="operator_neq"></a> operator!=  
 Testet, ob das Objekt links vom Operator ungleich dem Objekt rechts vom Operator ist.  
  
```  
bool operator!=(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Parameter  
 `left`  
 Ein Objekt vom Typ **vector**.  
  
 `right`  
 Ein Objekt vom Typ **vector**.  
  
### <a name="return-value"></a>Rückgabewert  
 **TRUE**, wenn die Paare nicht gleich sind; **FALSE**, wenn die Paare gleich sind.  
  
### <a name="remarks"></a>Hinweise  
 Zwei Vektoren sind gleich, wenn sie über die gleiche Anzahl von Elementen verfügen und die entsprechenden Elemente dieselben Werte aufweisen. Andernfalls sind sie ungleich.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// vector_op_ne.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;   
  
   vector <int> v1, v2;  
   v1.push_back( 1 );  
     v2.push_back( 2 );  
  
   if ( v1 != v2 )  
      cout << "Vectors not equal." << endl;  
   else  
      cout << "Vectors equal." << endl;  
}  
```  
  
```Output  
Vectors not equal.  
```  
  
##  <a name="operator_lt_"></a> operator&lt;  
 Testet, ob das Objekt links vom Operator kleiner als das Objekt auf der rechten Seite ist.  
  
```  
bool operator<(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Parameter  
 `left`  
 Ein Objekt vom Typ **vector**.  
  
 `right`  
 Ein Objekt vom Typ **vector**.  
  
### <a name="return-value"></a>Rückgabewert  
 **TRUE**, wenn der Vektor links vom Operator kleiner als der Vektor rechts vom Operator ist; andernfalls **FALSE**.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// vector_op_lt.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;   
  
   vector <int> v1, v2;  
   v1.push_back( 1 );  
   v1.push_back( 2 );  
   v1.push_back( 4 );  
  
   v2.push_back( 1 );  
   v2.push_back( 3 );  
  
   if ( v1 < v2 )  
      cout << "Vector v1 is less than vector v2." << endl;  
   else  
      cout << "Vector v1 is not less than vector v2." << endl;  
}  
```  
  
```Output  
Vector v1 is less than vector v2.  
```  
  
##  <a name="operator_lt__eq"></a> operator&lt;=  
 Testet, ob das Objekt links vom Operator kleiner oder gleich dem Objekt auf der rechten Seite ist.  
  
```  
bool operator<=(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Parameter  
 `left`  
 Ein Objekt vom Typ **vector**.  
  
 `right`  
 Ein Objekt vom Typ **vector**.  
  
### <a name="return-value"></a>Rückgabewert  
 **TRUE**, wenn der Vektor links vom Operator kleiner als oder gleich dem Vektor rechts vom Operator ist; andernfalls **FALSE**.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// vector_op_le.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;   
  
   vector <int> v1, v2;  
   v1.push_back( 1 );  
   v1.push_back( 2 );  
   v1.push_back( 4 );  
  
   v2.push_back( 1 );  
   v2.push_back( 3 );  
  
   if ( v1 <= v2 )  
      cout << "Vector v1 is less than or equal to vector v2." << endl;  
   else  
      cout << "Vector v1 is greater than vector v2." << endl;  
}  
```  
  
```Output  
Vector v1 is less than or equal to vector v2.  
```  
  
##  <a name="operator_eq_eq"></a> operator==  
 Testet, ob das Objekt links vom Operator gleich dem Objekt rechts vom Operator ist.  
  
```  
bool operator==(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Parameter  
 `left`  
 Ein Objekt vom Typ **vector**.  
  
 `right`  
 Ein Objekt vom Typ **vector**.  
  
### <a name="return-value"></a>Rückgabewert  
 **TRUE**, wenn der Vektor links vom Operator gleich dem Vektor rechts vom Operator ist; andernfalls **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Zwei Vektoren sind gleich, wenn sie über die gleiche Anzahl von Elementen verfügen und die entsprechenden Elemente dieselben Werte aufweisen. Andernfalls sind sie ungleich.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// vector_op_eq.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;   
  
   vector <int> v1, v2;  
   v1.push_back( 1 );  
   v2.push_back( 1 );  
  
   if ( v1 == v2 )  
      cout << "Vectors equal." << endl;  
   else  
      cout << "Vectors not equal." << endl;  
}  
```  
  
```Output  
Vectors equal.  
```  
  
##  <a name="operator_gt_"></a> operator&gt;  
 Testet, ob das Objekt links vom Operator größer als das Objekt auf der rechten Seite ist.  
  
```  
bool operator>(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Parameter  
 `left`  
 Ein Objekt vom Typ **vector**.  
  
 `right`  
 Ein Objekt vom Typ **vector**.  
  
### <a name="return-value"></a>Rückgabewert  
 **TRUE**, wenn der Vektor links vom Operator größer als der Vektor rechts vom Operator ist; andernfalls **FALSE**.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// vector_op_gt.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;   
  
   vector <int> v1, v2;  
   v1.push_back( 1 );  
   v1.push_back( 3 );  
   v1.push_back( 1 );  
  
   v2.push_back( 1 );  
   v2.push_back( 2 );  
   v2.push_back( 2 );  
  
   if ( v1 > v2 )  
      cout << "Vector v1 is greater than vector v2." << endl;  
   else  
      cout << "Vector v1 is not greater than vector v2." << endl;  
}  
```  
  
```Output  
Vector v1 is greater than vector v2.  
```  
  
##  <a name="operator_gt__eq"></a> operator&gt;=  
 Testet, ob das Objekt links vom Operator größer oder gleich dem Objekt auf der rechten Seite ist.  
  
```  
bool operator>=(const vector<Type, Allocator>& left, const vector<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Parameter  
 `left`  
 Ein Objekt vom Typ **vector**.  
  
 `right`  
 Ein Objekt vom Typ **vector**.  
  
### <a name="return-value"></a>Rückgabewert  
 **TRUE**, wenn der Vektor links vom Operator größer als oder gleich dem Vektor rechts vom Operator ist; andernfalls **FALSE**.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// vector_op_ge.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;   
  
   vector <int> v1, v2;  
   v1.push_back( 1 );  
   v1.push_back( 3 );  
   v1.push_back( 1 );  
  
     v2.push_back( 1 );  
   v2.push_back( 2 );  
   v2.push_back( 2 );  
  
   if ( v1 >= v2 )  
      cout << "Vector v1 is greater than or equal to vector v2." << endl;  
   else  
      cout << "Vector v1 is less than vector v2." << endl;  
}  
```  
  
```Output  
Vector v1 is greater than or equal to vector v2.  
```  
  
## <a name="see-also"></a>Siehe auch  
 [\<vector>](../standard-library/vector.md)


