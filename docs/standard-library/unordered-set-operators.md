---
title: '&lt;unordered_set&gt;-Operatoren | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- unordered_set/std::operator!=
- unordered_set/std::operator==
dev_langs: C++
ms.assetid: 8653eea6-12f2-4dd7-aa2f-db38a71599a0
caps.latest.revision: "7"
manager: ghogen
ms.openlocfilehash: 615e2f69a45a17b34b38190ac1c7def1de09d8c8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="ltunorderedsetgt-operators"></a>&lt;unordered_set&gt;-Operatoren
|||||  
|-|-|-|-|  
|[operator!=](#op_neq)|[operator==](#op_eq_eq)|[operator!=](#op_neq_unordered_multiset)|[operator==](#op_eq_eq_unordered_multiset)|  
  
##  <a name="op_neq"></a> operator!=  
 Testet, ob das [unordered_set](../standard-library/unordered-set-class.md)-Objekt links vom Operator ungleich dem unordered_set-Objekt rechts vom Operator ist.  
  
```
bool operator!=(const unordered_set <Key, Hash, Pred, Allocator>& left, const unordered_set <Key, Hash, Pred, Allocator>& right);
```  
  
### <a name="parameters"></a>Parameter  
 `left`  
 Ein Objekt vom Typ `unordered_set`.  
  
 `right`  
 Ein Objekt vom Typ `unordered_set`.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn die unordered_set-Objekte ungleich sind; `false`, wenn sie gleich sind.  
  
### <a name="remarks"></a>Hinweise  
 Die beliebige Reihenfolge, in der unordered_set-Objekte ihre Elemente speichern, hat keine Auswirkungen auf den Vergleich der Objekte. Zwei unordered_set-Objekte sind gleich, wenn sie dieselbe Anzahl von Elementen aufweisen und die Elemente in einem Container eine Permutation der Elemente im anderen Container sind. Andernfalls sind sie ungleich.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// unordered_set_ne.cpp   
// compile by using: cl.exe /EHsc /nologo /W4 /MTd   
#include <unordered_set>   
#include <iostream>   
#include <ios>  
  
int main()   
{   
    using namespace std;  
  
    unordered_set<char> c1, c2, c3;  
  
    c1.insert('a');   
    c1.insert('b');   
    c1.insert('c');   
  
    c2.insert('c');   
    c2.insert('a');   
    c2.insert('d');   
  
    c3.insert('c');   
    c3.insert('a');   
    c3.insert('b');   
  
   cout << boolalpha;  
   cout << "c1 != c2: " << (c1 != c2) << endl;   
   cout << "c1 != c3: " << (c1 != c3) << endl;   
   cout << "c2 != c3: " << (c2 != c3) << endl;   
  
    return (0);   
}  
  
```  
  
 **Ausgabe:**  
  
 `c1 != c2: true`  
  
 `c1 != c3: false`  
  
 `c2 != c3: true`  
  
##  <a name="op_eq_eq"></a> operator==  
 Testet, ob das [unordered_set](../standard-library/unordered-set-class.md)-Objekt links vom Operator gleich dem unordered_set-Objekt rechts vom Operator ist.  
  
```
bool operator==(const unordered_set <Key, Hash, Pred, Allocator>& left, const unordered_set <Key, Hash, Pred, Allocator>& right);
```  
  
### <a name="parameters"></a>Parameter  
 `left`  
 Ein Objekt vom Typ `unordered_set`.  
  
 `right`  
 Ein Objekt vom Typ `unordered_set`.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn die unordered_set-Objekte gleich sind; `false`, wenn sie ungleich sind.  
  
### <a name="remarks"></a>Hinweise  
 Die beliebige Reihenfolge, in der unordered_set-Objekte ihre Elemente speichern, hat keine Auswirkungen auf den Vergleich der Objekte. Zwei unordered_set-Objekte sind gleich, wenn sie dieselbe Anzahl von Elementen aufweisen und die Elemente in einem Container eine Permutation der Elemente im anderen Container sind. Andernfalls sind sie ungleich.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// unordered_set_eq.cpp   
// compile by using: cl.exe /EHsc /nologo /W4 /MTd   
#include <unordered_set>   
#include <iostream>   
#include <ios>  
  
int main()   
{   
    using namespace std;  
  
    unordered_set<char> c1, c2, c3;  
  
    c1.insert('a');   
    c1.insert('b');   
    c1.insert('c');   
  
    c2.insert('c');   
    c2.insert('a');   
    c2.insert('d');   
  
    c3.insert('c');   
    c3.insert('a');   
    c3.insert('b');   
  
   cout << boolalpha;  
   cout << "c1 == c2: " << (c1 == c2) << endl;   
   cout << "c1 == c3: " << (c1 == c3) << endl;   
   cout << "c2 == c3: " << (c2 == c3) << endl;   
  
    return (0);   
}  
  
```  
  
 **Ausgabe:**  
  
 `c1 == c2: false`  
  
 `c1 == c3: true`  
  
 `c2 == c3: false`  
  
##  <a name="op_neq_unordered_multiset"></a> operator!=  
 Überprüft, ob das [unordered_multiset](../standard-library/unordered-multiset-class.md)-Objekt links vom Operator ungleich dem unordered_multiset-Objekt rechts vom Operator ist.  
  
```
bool operator!=(const unordered_multiset <Key, Hash, Pred, Allocator>& left, const unordered_multiset <Key, Hash, Pred, Allocator>& right);
```  
  
### <a name="parameters"></a>Parameter  
 `left`  
 Ein Objekt vom Typ `unordered_multiset`.  
  
 `right`  
 Ein Objekt vom Typ `unordered_multiset`.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn die unordered_multiset-Objekte ungleich sind; `false`, wenn sie gleich sind.  
  
### <a name="remarks"></a>Hinweise  
 Die beliebige Reihenfolge, in der unordered_multiset-Objekte ihre Elemente speichern, hat keine Auswirkungen auf den Vergleich der Objekte. Zwei unordered_multiset-Objekte sind gleich, wenn sie dieselbe Anzahl von Elementen aufweisen und die Elemente in einem Container eine Permutation der Elemente im anderen Container sind. Andernfalls sind sie ungleich.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// unordered_multiset_ne.cpp   
// compile by using: cl.exe /EHsc /nologo /W4 /MTd   
#include <unordered_set>   
#include <iostream>   
#include <ios>  
  
int main()   
{   
    using namespace std;  
  
    unordered_multiset<char> c1, c2, c3;  
  
    c1.insert('a');   
    c1.insert('b');   
    c1.insert('c');   
    c1.insert('c');   
  
    c2.insert('c');   
    c2.insert('c');   
    c2.insert('a');   
    c2.insert('d');   
  
    c3.insert('c');   
    c3.insert('c');   
    c3.insert('a');   
    c3.insert('b');   
  
   cout << boolalpha;  
   cout << "c1 != c2: " << (c1 != c2) << endl;   
   cout << "c1 != c3: " << (c1 != c3) << endl;   
   cout << "c2 != c3: " << (c2 != c3) << endl;   
  
    return (0);   
}  
  
```  
  
 **Ausgabe:**  
  
 `c1 != c2: true`  
  
 `c1 != c3: false`  
  
 `c2 != c3: true`  
  
##  <a name="op_eq_eq_unordered_multiset"></a> operator==  
 Überprüft, ob das [unordered_multiset](../standard-library/unordered-multiset-class.md)-Objekt links vom Operator gleich dem unordered_multiset-Objekt rechts vom Operator ist.  
  
```
bool operator==(const unordered_multiset <Key, Hash, Pred, Allocator>& left, const unordered_multiset <Key, Hash, Pred, Allocator>& right);
```  
  
### <a name="parameters"></a>Parameter  
 `left`  
 Ein Objekt vom Typ `unordered_multiset`.  
  
 `right`  
 Ein Objekt vom Typ `unordered_multiset`.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn die unordered_multiset-Objekte gleich sind; `false`, wenn sie ungleich sind.  
  
### <a name="remarks"></a>Hinweise  
 Die beliebige Reihenfolge, in der unordered_multiset-Objekte ihre Elemente speichern, hat keine Auswirkungen auf den Vergleich der Objekte. Zwei unordered_multiset-Objekte sind gleich, wenn sie dieselbe Anzahl von Elementen aufweisen und die Elemente in einem Container eine Permutation der Elemente im anderen Container sind. Andernfalls sind sie ungleich.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// unordered_multiset_eq.cpp   
// compile by using: cl.exe /EHsc /nologo /W4 /MTd   
#include <unordered_set>   
#include <iostream>   
#include <ios>  
  
int main()   
{   
    using namespace std;  
  
    unordered_multiset<char> c1, c2, c3;  
  
    c1.insert('a');   
    c1.insert('b');   
    c1.insert('c');   
    c1.insert('c');   
  
    c2.insert('c');   
    c2.insert('c');   
    c2.insert('a');   
    c2.insert('d');   
  
    c3.insert('c');   
    c3.insert('c');   
    c3.insert('a');   
    c3.insert('b');   
  
   cout << boolalpha;  
   cout << "c1 == c2: " << (c1 == c2) << endl;   
   cout << "c1 == c3: " << (c1 == c3) << endl;   
   cout << "c2 == c3: " << (c2 == c3) << endl;   
  
    return (0);   
}  
  
```  
  
 **Ausgabe:**  
  
 `c1 == c2: false`  
  
 `c1 == c3: true`  
  
 `c2 == c3: false`  
  
## <a name="see-also"></a>Siehe auch  
 [<unordered_set>](../standard-library/unordered-set.md)



