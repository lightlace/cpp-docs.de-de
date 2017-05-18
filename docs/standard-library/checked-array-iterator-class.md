---
title: checked_array_iterator-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- iterator/checked_array_iterator
- checked_array_iterator
- iterator/stdext::checked_array_iterator::difference_type
- iterator/stdext::checked_array_iterator::pointer
- iterator/stdext::checked_array_iterator::reference
- iterator/stdext::checked_array_iterator::base
dev_langs:
- C++
helpviewer_keywords:
- checked_array_iterator, syntax
- checked_array_iterator class
- checked_array_iterator
ms.assetid: 7f07185e-d588-4ae3-9c4f-84ec4aa25a28
caps.latest.revision: 28
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: a53cc2a5bb7bd50e41e9e01d3953465706554017
ms.contentlocale: de-de
ms.lasthandoff: 04/29/2017

---
# <a name="checkedarrayiterator-class"></a>checked_array_iterator-Klasse
Die `checked_array_iterator`-Klasse ermöglicht es Ihnen, ein Array oder einen Zeiger in einen überprüfter Iterator zu transformieren. Verwenden Sie diese Klasse (mithilfe der [make_checked_array_iterator](../standard-library/iterator-functions.md#make_checked_array_iterator)-Funktion) als Wrapper für unformatierte Zeiger oder Arrays. So erhalten Sie eine zielgerichtete Methode für Überprüfungen und zum Verwalten von Warnungen für ungeprüfte Zeiger, anstatt diese Warnungen global zu deaktivieren. Bei Bedarf können Sie die ungeprüfte Version dieser Klasse, [unchecked_array_iterator](../standard-library/unchecked-array-iterator-class.md), verwenden.  
  
> [!NOTE]
>  Bei dieser Klasse handelt es sich um eine Microsoft-Erweiterung der C++-Standardbibliothek. Der Code, der mit dieser Funktion implementiert wird, ist nicht auf C++-Standardbuildumgebungen übertragbar, die die Microsoft-Erweiterung nicht unterstützen. Ein Beispiel, in dem das Schreiben von Code veranschaulicht wird, bei dem die Verwendung dieser Klasse nicht erforderlich ist, finden Sie im zweiten Beispiel weiter unten.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class _Iterator>  
class checked_array_iterator;
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse wird im [stdext](../standard-library/stdext-namespace.md)-Namespace definiert.  
  
 Weitere Informationen und Beispielcode zu überprüften Iteratoren finden Sie unter [Überprüfte Iteratoren](../standard-library/checked-iterators.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird das Definieren und Verwenden eines überprüften Arrayiterators veranschaulicht.  
  
 Wenn die Größe des Ziel nicht ausreicht, um alle kopierten Elemente zu halten, wie es bei Änderung der folgenden Zeile der Fall wäre:  
  
```cpp  
copy(a, a + 5, checked_array_iterator<int*>(b, 5));
```  
  
 bis  
  
```cpp  
copy(a, a + 5, checked_array_iterator<int*>(b, 4));
```  
  
 Ein Laufzeitfehler tritt auf.  
  
```cpp  
// compile with: /EHsc /W4 /MTd  
#include <algorithm>  
#include <iostream>  
  
using namespace std;  
using namespace stdext;  
  
int main() {  
   int a[]={0, 1, 2, 3, 4};  
   int b[5];  
   copy(a, a + 5, checked_array_iterator<int*>(b, 5));  
  
   cout << "(";  
   for (int i = 0 ; i < 5 ; i++)  
      cout << " " << b[i];  
   cout << " )" << endl;  
  
   // constructor example  
   checked_array_iterator<int*> checked_out_iter(b, 5);  
   copy(a, a + 5, checked_out_iter);  
  
   cout << "(";  
   for (int i = 0 ; i < 5 ; i++)  
      cout << " " << b[i];  
   cout << " )" << endl;  
}  
\* Output:   
( 0 1 2 3 4 )  
( 0 1 2 3 4 )  
*\  
```  
  
## <a name="example"></a>Beispiel  
 Um bei der Verwendung von C++-Standardbibliotheksalgorithmen keine `checked_array_iterator`-Klasse zu benötigen, könnten Sie anstelle eines dynamisch zugeordneten Arrays `vector` verwenden. Im folgenden Beispiel wird die dafür erforderliche Vorgehensweise veranschaulicht.  
  
```cpp  
// compile with: /EHsc /W4 /MTd  
  
#include <algorithm>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
int main()  
{  
    std::vector<int> v(10);  
    int *arr = new int[10];  
    for (int i = 0; i < 10; ++i)  
    {  
        v[i] = i;  
        arr[i] = i;  
    }  
  
    // std::copy(v.begin(), v.end(), arr); will result in  
    // warning C4996. To avoid this warning while using int *,  
    // use the Microsoft extension checked_array_iterator.  
    std::copy(v.begin(), v.end(),  
              stdext::checked_array_iterator<int *>(arr, 10));  
  
    // Instead of using stdext::checked_array_iterator and int *,  
    // consider using std::vector to encapsulate the array. This will  
    // result in no warnings, and the code will be portable.  
    std::vector<int> arr2(10);    // Similar to int *arr = new int[10];  
    std::copy(v.begin(), v.end(), arr2.begin());  
  
    for (int j = 0; j < arr2.size(); ++j)  
    {  
        cout << " " << arr2[j];  
    }  
    cout << endl;  
  
    return 0;  
}  
\* Output:   
 0 1 2 3 4 5 6 7 8 9  
*\  
```  
  
### <a name="constructors"></a>Konstruktoren  
  
|||  
|-|-|  
|[checked_array_iterator](#checked_array_iterator)|Erstellt aus einem zugrunde liegenden Iterator einen standardmäßigen `checked_array_iterator` oder `checked_array_iterator`.|  
  
### <a name="typedefs"></a>TypeDefs  
  
|||  
|-|-|  
|[difference_type](#difference_type)|Ein Typ, mit dem der Unterschied zwischen zwei `checked_array_iterator`en bereitgestellt wird, die auf Elemente innerhalb desselben Containers verweisen.|  
|[pointer](#pointer)|Ein Typ, mit dem ein Zeiger auf ein Element bereitgestellt wird, die von `checked_array_iterator` adressiert werden.|  
|[Verweis](#reference)|Ein Typ, mit dem ein Verweis auf ein Element bereitgestellt wird, die von `checked_array_iterator` adressiert werden.|  
  
### <a name="member-functions"></a>Memberfunktionen  
  
|||  
|-|-|  
|[base](#base)|Stellt den zugrunde liegenden Iterator aus `checked_array_iterator` wieder her.|  
  
### <a name="operators"></a>Operatoren  
  
|||  
|-|-|  
|[operator==](#op_eq_eq)|Prüft zwei `checked_array_iterator`en auf Gleichheit.|  
|[operator!=](#op_neq)|Prüft zwei `checked_array_iterator`en auf Ungleichheit.|  
|[operator<](#op_lt)|Testet, ob `checked_array_iterator` links vom Operator kleiner als `checked_array_iterator` auf der rechten Seite ist.|  
|[operator>](#op_gt)|Testet, ob `checked_array_iterator` links vom Operator größer als `checked_array_iterator` auf der rechten Seite ist.|  
|[operator<=](#op_lt_eq)|Testet, ob `checked_array_iterator` links vom Operator kleiner oder gleich `checked_array_iterator` auf der rechten Seite ist.|  
|[operator>=](#op_gt_eq)|Testet, ob `checked_array_iterator` links vom Operator größer oder gleich `checked_array_iterator` auf der rechten Seite ist.|  
|[operator*](#op_star)|Gibt das Element zurück, das ein `checked_array_iterator` adressiert.|  
|[operator->](#operator-_gt)|Gibt einen Zeiger auf das Element zurück, das von `checked_array_iterator` adressiert wird.|  
|[operator++](#op_add_add)|Erhöht `checked_array_iterator` zum nächsten Element.|  
|[operator--](#operator--)|Verringert `checked_array_iterator` zum vorherigen Element.|  
|[operator+=](#op_add_eq)|Fügt `checked_array_iterator` einem angegebenen Offset hinzu.|  
|[operator+](#op_add)|Fügt einen Offset zu einem Iterator hinzu und gibt den neuen `checked_array_iterator` zurück, der auf das eingefügte Element an der neuen Offsetposition zeigt.|  
|[operator-=](#operator-_eq)|Verringert einen angegebenen Offset von `checked_array_iterator`.|  
|[operator-](#operator-)|Verringert einen Offset von einem Iterator und gibt den neuen `checked_array_iterator` zurück, der auf das eingefügte Element an der neuen Offsetposition zeigt.|  
|[operator&#91;&#93;](#op_at)|Gibt einen Verweis auf ein Elementoffset aus dem Element zurück, das von `checked_array_iterator` mithilfe der angegebenen Anzahl von Positionen adressiert wird.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<iterator>  
  
 **Namespace:** stdext  
  
##  <a name="base"></a> checked_array_iterator::base  
 Stellt den zugrunde liegenden Iterator aus `checked_array_iterator` wieder her.  
  
```
_Iterator base() const;
```  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [Überprüfte Iteratoren](../standard-library/checked-iterators.md).  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// checked_array_iterators_base.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main() {  
   using namespace std;  
  
   int V1[10];  
  
   for (int i = 0; i < 10 ; i++)  
      V1[i] = i;  
  
   int* bpos;  
  
   stdext::checked_array_iterator<int*> rpos(V1, 10);  
   rpos++;  
  
   bpos = rpos.base ( );  
   cout << "The iterator underlying rpos is bpos & it points to: "   
        << *bpos << "." << endl;  
}  
\* Output:   
The iterator underlying rpos is bpos & it points to: 1.  
*\  
```  
  
##  <a name="checked_array_iterator"></a> checked_array_iterator::checked_array_iterator  
 Erstellt aus einem zugrunde liegenden Iterator einen standardmäßigen `checked_array_iterator` oder `checked_array _iterator`.  
  
```
checked_array_iterator();

checked_array_iterator(
    ITerator ptr,
    size_t size,
    size_t index = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `ptr`  
 Ein Zeiger auf den Array.  
  
 `size`  
 Die Größe des Arrays.  
  
 `index`  
 (Optional) Ein Element im Array zur Initialisierung des Iterators.  Der Iterator wird standardmäßig mit dem ersten Element im Array initialisiert.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [Überprüfte Iteratoren](../standard-library/checked-iterators.md).  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// checked_array_iterators_ctor.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <iostream>   
  
using namespace std;  
using namespace stdext;  
  
int main() {  
   int a[] = {0, 1, 2, 3, 4};  
   int b[5];  
   copy(a, a + 5, checked_array_iterator<int*>(b,5));  
  
   for (int i = 0 ; i < 5 ; i++)  
      cout << b[i] << " ";  
   cout << endl;  
  
   checked_array_iterator<int*> checked_output_iterator(b,5);  
   copy (a, a + 5, checked_output_iterator);  
   for (int i = 0 ; i < 5 ; i++)  
      cout << b[i] << " ";  
   cout << endl;  
  
   checked_array_iterator<int*> checked_output_iterator2(b,5,3);  
   cout << *checked_output_iterator2 << endl;  
}  
\* Output:   
0 1 2 3 4   
0 1 2 3 4   
3  
*\  
```  
  
##  <a name="difference_type"></a> checked_array_iterator::difference_type  
 Ein Typ, mit dem der Unterschied zwischen zwei `checked_array_iterator`en bereitgestellt wird, die auf Elemente innerhalb desselben Containers verweisen.  
  
```
typedef typename iterator_traits<_Iterator>::difference_type difference_type;
```  
  
### <a name="remarks"></a>Hinweise  
 Der `checked_array_iterator`-Differenztyp ist identisch mit den Differenztyp des Iterators.  
  
 Siehe [checked_array_iterator::operator[]](#op_at) für ein Codebeispiel.  
  
 Weitere Informationen finden Sie unter [Überprüfte Iteratoren](../standard-library/checked-iterators.md).  
  
##  <a name="op_eq_eq"></a> checked_array_iterator::operator==  
 Prüft zwei `checked_array_iterator`en auf Gleichheit.  
  
```
bool operator==(const checked_array_iterator<_Iterator>& right) const;
```  
  
### <a name="parameters"></a>Parameter  
 `right`  
 Der `checked_array_iterator` für die Durchführung von Gleichheitsüberprüfungen.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [Überprüfte Iteratoren](../standard-library/checked-iterators.md).  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// checked_array_iterators_opeq.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <iostream>   
  
using namespace std;  
using namespace stdext;  
  
int main() {  
   int a[] = {0, 1, 2, 3, 4};  
   int b[5];  
   copy(a, a + 5, checked_array_iterator<int*>(b,5));  
   copy(a, a + 5, checked_array_iterator<int*>(b,5));  
  
   checked_array_iterator<int*> checked_output_iterator(b,5);  
   checked_array_iterator<int*> checked_output_iterator2(b,5);  
  
   if (checked_output_iterator2 == checked_output_iterator)  
      cout << "checked_array_iterators are equal" << endl;  
   else  
      cout << "checked_array_iterators are not equal" << endl;  
  
   copy (a, a + 5, checked_output_iterator);  
   checked_output_iterator++;  
  
   if (checked_output_iterator2 == checked_output_iterator)  
      cout << "checked_array_iterators are equal" << endl;  
   else  
      cout << "checked_array_iterators are not equal" << endl;  
}  
\* Output:   
checked_array_iterators are equal  
checked_array_iterators are not equal  
*\  
```  
  
##  <a name="op_neq"></a> checked_array_iterator::operator!=  
 Prüft zwei `checked_array_iterator`en auf Ungleichheit.  
  
```
bool operator!=(const checked_array_iterator<_Iterator>& right) const;
```  
  
### <a name="parameters"></a>Parameter  
 `right`  
 Der `checked_array_iterator` für die Durchführung von Ungleichheitsüberprüfungen.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [Überprüfte Iteratoren](../standard-library/checked-iterators.md).  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// checked_array_iterators_opneq.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <iostream>   
  
using namespace std;  
using namespace stdext;  
  
int main() {  
   int a[] = {0, 1, 2, 3, 4};  
   int b[5];  
   copy(a, a + 5, checked_array_iterator<int*>(b,5));  
   copy(a, a + 5, checked_array_iterator<int*>(b,5));  
  
   checked_array_iterator<int*> checked_output_iterator(b,5);  
   checked_array_iterator<int*> checked_output_iterator2(b,5);  
  
   if (checked_output_iterator2 != checked_output_iterator)  
      cout << "checked_array_iterators are not equal" << endl;  
   else  
      cout << "checked_array_iterators are equal" << endl;  
  
   copy (a, a + 5, checked_output_iterator);  
   checked_output_iterator++;  
  
   if (checked_output_iterator2 != checked_output_iterator)  
      cout << "checked_array_iterators are not equal" << endl;  
   else  
      cout << "checked_array_iterators are equal" << endl;  
}  
\* Output:   
checked_array_iterators are equal  
checked_array_iterators are not equal  
*\  
```  
  
##  <a name="op_lt"></a> checked_array_iterator::operator&lt;  
 Testet, ob `checked_array_iterator` links vom Operator kleiner als `checked_array_iterator` auf der rechten Seite ist.  
  
```
bool operator<(const checked_array_iterator<_Iterator>& right) const;
```  
  
### <a name="parameters"></a>Parameter  
 `right`  
 Der `checked_array_iterator` für die Durchführung von Ungleichheitsüberprüfungen.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [Überprüfte Iteratoren](../standard-library/checked-iterators.md).  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// checked_array_iterators_oplt.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <iostream>   
  
using namespace std;  
using namespace stdext;  
  
int main() {  
   int a[] = {0, 1, 2, 3, 4};  
   int b[5];  
   copy(a, a + 5, checked_array_iterator<int*>(b,5));  
   copy(a, a + 5, checked_array_iterator<int*>(b,5));  
  
   checked_array_iterator<int*> checked_output_iterator(b,5);  
   checked_array_iterator<int*> checked_output_iterator2(b,5);  
  
   if (checked_output_iterator2 < checked_output_iterator)  
      cout << "checked_output_iterator2 is less than checked_output_iterator" << endl;  
   else  
      cout << "checked_output_iterator2 is not less than checked_output_iterator" << endl;  
  
   copy (a, a + 5, checked_output_iterator);  
   checked_output_iterator++;  
  
   if (checked_output_iterator2 < checked_output_iterator)  
      cout << "checked_output_iterator2 is less than checked_output_iterator" << endl;  
   else  
      cout << "checked_output_iterator2 is not less than checked_output_iterator" << endl;  
}  
\* Output:   
checked_output_iterator2 is not less than checked_output_iterator  
checked_output_iterator2 is less than checked_output_iterator  
*\  
```  
  
##  <a name="op_gt"></a> checked_array_iterator::operator&gt;  
 Testet, ob `checked_array_iterator` links vom Operator größer als `checked_array_iterator` auf der rechten Seite ist.  
  
```
bool operator>(const checked_array_iterator<_Iterator>& right) const;
```  
  
### <a name="parameters"></a>Parameter  
 `right`  
 `checked_array_iterator` für den Vergleich.  
  
### <a name="remarks"></a>Hinweise  
 Siehe [checked_array_iterator::operator&lt;](#op_lt) für ein Codebeispiel.  
  
 Weitere Informationen finden Sie unter [Überprüfte Iteratoren](../standard-library/checked-iterators.md).  
  
##  <a name="lt_eq"></a> checked_array_iterator::operator&lt;=  
 Testet, ob `checked_array_iterator` links vom Operator kleiner oder gleich `checked_array_iterator` auf der rechten Seite ist.  
  
```
bool operator<=(const checked_array_iterator<_Iterator>& right) const;
```  
  
### <a name="parameters"></a>Parameter  
 `right`  
 `checked_array_iterator` für den Vergleich.  
  
### <a name="remarks"></a>Hinweise  
 Siehe [checked_array_iterator::operator&gt;=](#op_gt_eq) für ein Codebeispiel.  
  
 Weitere Informationen finden Sie unter [Überprüfte Iteratoren](../standard-library/checked-iterators.md).  
  
##  <a name="gt_eq"></a> checked_array_iterator::operator&gt;=  
 Testet, ob `checked_array_iterator` links vom Operator größer oder gleich `checked_array_iterator` auf der rechten Seite ist.  
  
```
bool operator>=(const checked_array_iterator<_Iterator>& right) const;
```  
  
### <a name="parameters"></a>Parameter  
 `right`  
 `checked_array_iterator` für den Vergleich.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [Überprüfte Iteratoren](../standard-library/checked-iterators.md).  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// checked_array_iterators_opgteq.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <iostream>   
  
using namespace std;  
using namespace stdext;  
  
int main() {  
   int a[] = {0, 1, 2, 3, 4};  
   int b[5];  
   copy(a, a + 5, checked_array_iterator<int*>(b,5));  
   copy(a, a + 5, checked_array_iterator<int*>(b,5));  
  
   checked_array_iterator<int*> checked_output_iterator(b,5);  
   checked_array_iterator<int*> checked_output_iterator2(b,5);  
  
   if (checked_output_iterator2 >= checked_output_iterator)  
      cout << "checked_output_iterator2 is greater than or equal to checked_output_iterator" << endl;  
   else  
      cout << "checked_output_iterator2 is less than checked_output_iterator" << endl;  
  
   copy (a, a + 5, checked_output_iterator);  
   checked_output_iterator++;  
  
   if (checked_output_iterator2 >= checked_output_iterator)  
      cout << "checked_output_iterator2 is greater than or equal to checked_output_iterator" << endl;  
   else  
      cout << "checked_output_iterator2 is less than checked_output_iterator" << endl;  
}  
\* Output:   
checked_output_iterator2 is greater than or equal to checked_output_iterator  
checked_output_iterator2 is less than checked_output_iterator  
*\  
```  
  
##  <a name="op_star"></a> checked_array_iterator::operator*  
 Gibt das Element zurück, das ein `checked_array_iterator` adressiert.  
  
```
reference operator*() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert des von `checked_array_iterator` adressierten Elements.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [Überprüfte Iteratoren](../standard-library/checked-iterators.md).  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// checked_array_iterator_pointer.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <algorithm>  
#include <vector>  
#include <utility>  
#include <iostream>  
  
using namespace std;  
using namespace stdext;  
  
int main() {  
   int a[] = {0, 1, 2, 3, 4};  
   int b[5];  
   pair<int, int> c[1];  
   copy(a, a + 5, checked_array_iterator<int*>(b,5));  
  
   for (int i = 0 ; i < 5 ; i++)  
      cout << b[i] << endl;  
  
    c[0].first = 10;  
    c[0].second = 20;  
  
   checked_array_iterator<int*> checked_output_iterator(b,5);  
   checked_array_iterator<int*>::pointer p = &(*checked_output_iterator);  
   checked_array_iterator<pair<int, int>*> chk_c(c, 1);  
   checked_array_iterator<pair<int, int>*>::pointer p_c = &(*chk_c);  
  
   cout << "b[0] = " << *p << endl;  
   cout << "c[0].first = " << p_c->first << endl;  
}  
\* Output:   
0  
1  
2  
3  
4  
b[0] = 0  
c[0].first = 10  
*\  
```  
  
##  <a name="checked_array_iterator__operator-_gt"></a> checked_array_iterator::operator-&gt;  
 Gibt einen Zeiger auf das Element zurück, das von `checked_array_iterator` adressiert wird.  
  
```
pointer operator->() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das von `checked_array_iterator` adressierte Element.  
  
### <a name="remarks"></a>Hinweise  
 Siehe [checked_array_iterator::pointer](#pointer) für ein Codebeispiel.  
  
 Weitere Informationen finden Sie unter [Überprüfte Iteratoren](../standard-library/checked-iterators.md).  
  
##  <a name="op_add_add"></a> checked_array_iterator::operator++  
 Erhöht `checked_array_iterator` zum nächsten Element.  
  
```
checked_array_iterator& operator++();

checked_array_iterator<_Iterator> operator++(int);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der erste Operator gibt den präinkrementierten `checked_array_iterator` zurück, der zweite Postinkrementoperator gibt eine Kopie des inkrementierten `checked_array_iterator` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [Überprüfte Iteratoren](../standard-library/checked-iterators.md).  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// checked_array_iterators_op_plus_plus.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main() {  
   using namespace stdext;  
   using namespace std;  
   int a[] = {6, 3, 77, 199, 222};  
   int b[5];  
   copy(a, a + 5, checked_array_iterator<int*>(b,5));  
  
   checked_array_iterator<int*> checked_output_iterator(b,5);  
  
   cout << *checked_output_iterator << endl;  
   ++checked_output_iterator;  
   cout << *checked_output_iterator << endl;  
   checked_output_iterator++;  
   cout << *checked_output_iterator << endl;  
}  
\* Output:   
6  
3  
77  
*\  
```  
  
##  <a name="checked_array_iterator__operator--"></a> checked_array_iterator::operator--  
 Verringert `checked_array_iterator` zum vorherigen Element.  
  
```
checked_array_iterator<_Iterator>& operator--();

checked_array_iterator<_Iterator> operator--(int);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der erste Operator gibt den prädekrementierten `checked_array_iterator` zurück, der zweite Postdekrementoperator gibt eine Kopie des dekrementierten `checked_array_iterator` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [Überprüfte Iteratoren](../standard-library/checked-iterators.md).  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// checked_array_iterators_op_minus_minus.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main() {  
   using namespace stdext;  
   using namespace std;  
   int a[] = {6, 3, 77, 199, 222};  
   int b[5];  
   copy(a, a + 5, checked_array_iterator<int*>(b,5));  
  
   checked_array_iterator<int*> checked_output_iterator(b,5);  
  
   cout << *checked_output_iterator << endl;  
   checked_output_iterator++;  
   cout << *checked_output_iterator << endl;  
   checked_output_iterator--;  
   cout << *checked_output_iterator << endl;  
}  
\* Output:   
6  
3  
6  
*\  
```  
  
##  <a name="op_add_eq"></a> checked_array_iterator::operator+=  
 Fügt `checked_array_iterator` einem angegebenen Offset hinzu.  
  
```
checked_array_iterator<_Iterator>& operator+=(difference_type _Off);
```  
  
### <a name="parameters"></a>Parameter  
 `_Off`  
 Der Offset, um den der Iterator inkrementiert werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf das von `checked_array_iterator` adressierte Element.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [Überprüfte Iteratoren](../standard-library/checked-iterators.md).  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// checked_array_iterators_op_plus_eq.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main() {  
   using namespace stdext;  
   using namespace std;  
   int a[] = {6, 3, 77, 199, 222};  
   int b[5];  
   copy(a, a + 5, checked_array_iterator<int*>(b,5));  
  
   checked_array_iterator<int*> checked_output_iterator(b,5);  
  
   cout << *checked_output_iterator << endl;  
   checked_output_iterator += 3;  
   cout << *checked_output_iterator << endl;  
}  
\* Output:   
6  
199  
*\  
```  
  
##  <a name="op_add"></a> checked_array_iterator::operator+  
 Fügt einen Offset zu einem Iterator hinzu und gibt den neuen `checked_array_iterator` zurück, der auf das eingefügte Element an der neuen Offsetposition zeigt.  
  
```
checked_array_iterator<_Iterator> operator+(difference_type _Off) const;
```  
  
### <a name="parameters"></a>Parameter  
 `_Off`  
 Der zum `checked_array_iterator` hinzuzufügende Offset.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `checked_array_iterator`, der das Offsetelement adressiert.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [Überprüfte Iteratoren](../standard-library/checked-iterators.md).  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// checked_array_iterators_op_plus.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main() {  
   using namespace stdext;  
   using namespace std;  
   int a[] = {6, 3, 77, 199, 222};  
   int b[5];  
   copy(a, a + 5, checked_array_iterator<int*>(b,5));  
  
   checked_array_iterator<int*> checked_output_iterator(b,5);  
  
   cout << *checked_output_iterator << endl;  
   checked_output_iterator = checked_output_iterator + 3;  
   cout << *checked_output_iterator << endl;  
}  
\* Output:   
6  
199  
*\  
```  
  
##  <a name="checked_array_iterator__operator-_eq"></a> checked_array_iterator::operator-=  
 Verringert einen angegebenen Offset von `checked_array_iterator`.  
  
```
checked_array_iterator<_Iterator>& operator-=(difference_type _Off);
```  
  
### <a name="parameters"></a>Parameter  
 `_Off`  
 Der Offset, um den der Iterator inkrementiert werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf das von `checked_array_iterator` adressierte Element.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [Überprüfte Iteratoren](../standard-library/checked-iterators.md).  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// checked_array_iterators_op_minus_eq.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main() {  
   using namespace stdext;  
   using namespace std;  
   int a[] = {6, 3, 77, 199, 222};  
   int b[5];  
   copy(a, a + 5, checked_array_iterator<int*>(b,5));  
  
   checked_array_iterator<int*> checked_output_iterator(b,5);  
  
   checked_output_iterator += 3;  
   cout << *checked_output_iterator << endl;  
   checked_output_iterator -= 2;  
   cout << *checked_output_iterator << endl;  
}  
\* Output:   
199  
3  
*\  
```  
  
##  <a name="checked_array_iterator__operator-"></a> checked_array_iterator::operator-  
 Verringert einen Offset von einem Iterator und gibt den neuen `checked_array_iterator` zurück, der auf das eingefügte Element an der neuen Offsetposition zeigt.  
  
```
checked_array_iterator<_Iterator> operator-(difference_type _Off) const;

difference_type operator-(const checked_array_iterator& right) const;
```  
  
### <a name="parameters"></a>Parameter  
 `_Off`  
 Der von `checked_array_iterator` zu dekrementierende Offset.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `checked_array_iterator`, der das Offsetelement adressiert.  
  
### <a name="remarks"></a>Hinweise  
 Siehe [checked_array_iterator::operator-](#operator-) für ein Codebeispiel.  
  
 Weitere Informationen finden Sie unter [Überprüfte Iteratoren](../standard-library/checked-iterators.md).  
  
##  <a name="op_at"></a> checked_array_iterator::operator[]  
 Gibt einen Verweis auf ein Elementoffset aus dem Element zurück, das von `checked_array_iterator` mithilfe der angegebenen Anzahl von Positionen adressiert wird.  
  
```
reference operator[](difference_type _Off) const;
```  
  
### <a name="parameters"></a>Parameter  
 `_Off`  
 Der Offset von der `checked_array_iterator`-Adresse.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Verweis auf den Elementoffset.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [Überprüfte Iteratoren](../standard-library/checked-iterators.md).  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// checked_array_iterators_op_diff.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main() {  
   using namespace std;     
   int V1[10];  
  
   for (int i = 0; i < 10 ; i++)  
      V1[i] = i;  
  
   // Declare a difference type for a parameter  
   stdext::checked_array_iterator<int*>::difference_type diff = 2;  
  
   stdext::checked_array_iterator<int*> VChkIter(V1, 10);  
  
   stdext::checked_array_iterator<int*>::reference refrpos = VChkIter [diff];  
  
   cout << refrpos + 1 << endl;  
}  
\* Output:   
3  
*\  
```  
  
##  <a name="pointer"></a> checked_array_iterator::pointer  
 Ein Typ, mit dem ein Zeiger auf ein Element bereitgestellt wird, die von `checked_array_iterator` adressiert werden.  
  
```
typedef typename iterator_traits<_Iterator>::pointer pointer;
```  
  
### <a name="remarks"></a>Hinweise  
 Siehe [checked_array_iterator::operator*](#op_star) für ein Codebeispiel.  
  
 Weitere Informationen finden Sie unter [Überprüfte Iteratoren](../standard-library/checked-iterators.md).  
  
##  <a name="reference"></a> checked_array_iterator::reference  
 Ein Typ, mit dem ein Verweis auf ein Element bereitgestellt wird, die von `checked_array_iterator` adressiert werden.  
  
```
typedef typename iterator_traits<_Iterator>::reference reference;
```  
  
### <a name="remarks"></a>Hinweise  
 Siehe [checked_array_iterator::operator[]](#op_at) für ein Codebeispiel.  
  
 Weitere Informationen finden Sie unter [Überprüfte Iteratoren](../standard-library/checked-iterators.md).  
  
## <a name="see-also"></a>Siehe auch  
 [\<iterator>](../standard-library/iterator.md)   
 [C++ Standard Library Reference (C++-Standardbibliotheksreferenz)](../standard-library/cpp-standard-library-reference.md)




