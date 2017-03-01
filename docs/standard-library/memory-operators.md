---
title: '&lt;memory&gt;-Operatoren | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- memory/std::operator!=
- memory/std::operator>
- memory/std::operator>=
- memory/std::operator<
- memory/std::operator<=
- memory/std::operator<<
- memory/std::operator==
ms.assetid: 257e3ba9-c4c2-4ae8-9b11-b156ba9c28de
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 28baed4badda4f2c1d7e5b20235fe8d40c2a7195
ms.openlocfilehash: 50cfd9e09a7534ea7c615ebf6b0c781806013965
ms.lasthandoff: 02/24/2017

---
# <a name="ltmemorygt-operators"></a>&lt;memory&gt;-Operatoren
||||  
|-|-|-|  
|[operator!=](#operator_neq)|[operator&gt;](#operator_gt_)|[operator&gt;=](#operator_gt__eq)|  
|[operator&lt;](#operator_lt_)|[operator&lt;&lt;](#operator_lt__lt_)|[operator&lt;=](#operator_lt__eq)|  
|[operator==](#operator_eq_eq)|  
  
##  <a name="a-nameoperatorneqa--operator"></a><a name="operator_neq"></a> operator!=  
 Prüft auf Ungleichheit zwischen Objekten.  
  
```  
template <class Type, class Other>  
bool operator!=(
    const allocator<Type>& left,  
    const allocator<Other>& right) throw();

template <class T, class Del1, class U, class Del2>  
bool operator!=(
    const unique_ptr<T, Del1>& left,  
    const unique_ptr<U&, Del2>& right);

template <class Ty1, class Ty2>  
bool operator!=(
    const shared_ptr<Ty1>& left,  
    const shared_ptr<Ty2>& right);
```  
  
### <a name="parameters"></a>Parameter  
 ` left`  
 Eines der Objekte, die auf Ungleichheit geprüft werden sollen.  
  
 ` right`  
 Eines der Objekte, die auf Ungleichheit geprüft werden sollen.  
  
 `Ty1`  
 Der vom linken gemeinsamen Zeiger gesteuerte Typ.  
  
 `Ty2`  
 Der vom rechten gemeinsamen Zeiger gesteuerte Typ.  
  
### <a name="return-value"></a>Rückgabewert  
 **TRUE**, wenn die Objekte nicht gleich sind; **FALSE**, wenn die Objekte gleich sind.  
  
### <a name="remarks"></a>Hinweise  
 Der erste Vorlagenoperator gibt "false" zurück. (Alle standardmäßigen allocator-Objekte sind gleich.)  
  
 Die zweite und der dritte Vorlagenoperator geben `!(`` left` `==` ` right``)` zurück.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// memory_op_me.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
int main( )   
{  
   allocator<double> Alloc;  
   vector <char>:: allocator_type v1Alloc;  
  
   if ( Alloc != v1Alloc )  
      cout << "The allocator objects Alloc & v1Alloc not are equal."  
           << endl;  
   else  
      cout << "The allocator objects Alloc & v1Alloc are equal."  
           << endl;  
}  
```  
  
```Output  
The allocator objects Alloc & v1Alloc are equal.  
```  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__memory__operator_ne.cpp   
// compile with: /EHsc   
#include <memory>   
#include <iostream>   
  
int main()   
    {   
    std::shared_ptr<int> sp0(new int(0));   
    std::shared_ptr<int> sp1(new int(0));   
  
    std::cout << "sp0 != sp0 == " << std::boolalpha   
        << (sp0 != sp0) << std::endl;   
    std::cout << "sp0 != sp1 == " << std::boolalpha   
        << (sp0 != sp1) << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
sp0 != sp0 == false  
sp0 != sp1 == true  
```  
  
##  <a name="a-nameoperatoreqeqa--operator"></a><a name="operator_eq_eq"></a> operator==  
 Prüft auf Gleichheit zwischen Objekten.  
  
```  
template <class Type, class Other>  
bool operator==(
    const allocator<Type>& left,  
    const allocator<Other>& right) throw();

template <class Ty1, class Del1, class Ty2, class Del2>  
bool operator==(
    const unique_ptr<Ty1, Del1>& left,  
    const unique_ptr<Ty2, Del2>& right);

template <class Ty1, class Ty2>  
bool operator==(
    const shared_ptr<Ty1>& left;,  
    const shared_ptr<Ty2>& right);
```  
  
### <a name="parameters"></a>Parameter  
 ` left`  
 Eines der Objekte, die auf Gleichheit geprüft werden sollen.  
  
 ` right`  
 Eines der Objekte, die auf Gleichheit geprüft werden sollen.  
  
 `Ty1`  
 Der vom linken gemeinsamen Zeiger gesteuerte Typ.  
  
 `Ty2`  
 Der vom rechten gemeinsamen Zeiger gesteuerte Typ.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn die Objekte gleich sind, `false`, wenn die Objekte nicht gleich sind.  
  
### <a name="remarks"></a>Hinweise  
 Der erste Vorlagenoperator gibt "true" zurück. (Alle standardmäßigen allocator-Objekte sind gleich.)  
  
 Der zweite und der dritte Vorlagenoperator geben ` left.get() ==  right.get()` zurück.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// memory_op_eq.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
int main( )   
{  
   allocator<char> Alloc;  
   vector <int>:: allocator_type v1Alloc;  
  
   allocator<char> cAlloc(Alloc);   
   allocator<int> cv1Alloc(v1Alloc);  
  
   if ( cv1Alloc == v1Alloc )  
      cout << "The allocator objects cv1Alloc & v1Alloc are equal."  
           << endl;  
   else  
      cout << "The allocator objects cv1Alloc & v1Alloc are not equal."  
           << endl;  
  
   if ( cAlloc == Alloc )  
      cout << "The allocator objects cAlloc & Alloc are equal."  
           << endl;  
   else  
      cout << "The allocator objects cAlloc & Alloc are not equal."  
           << endl;  
}  
```  
  
```Output  
The allocator objects cv1Alloc & v1Alloc are equal.  
The allocator objects cAlloc & Alloc are equal.  
```  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__memory__operator_eq.cpp   
// compile with: /EHsc   
#include <memory>   
#include <iostream>   
  
int main()   
    {   
    std::shared_ptr<int> sp0(new int(0));   
    std::shared_ptr<int> sp1(new int(0));   
  
    std::cout << "sp0 == sp0 == " << std::boolalpha   
        << (sp0 == sp0) << std::endl;   
    std::cout << "sp0 == sp1 == " << std::boolalpha   
        << (sp0 == sp1) << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
sp0 == sp0 == true  
sp0 == sp1 == false  
```  
  
##  <a name="a-nameoperatorgteqa--operatorgt"></a><a name="operator_gt__eq"></a> operator&gt;=  
 Testet, ob ein Objekt größer gleich einem zweiten Objekt ist.  
  
```  
template <class T, class Del1, class U, class Del2>  
bool operator>=(
    const unique_ptr<T, Del1>& left,  
    const unique_ptr<U, Del2>& right);

template <class Ty1, class Ty2>  
bool operator>=(
    const shared_ptr<Ty1>& left,  
    const shared_ptr<Ty2>& right);
```  
  
### <a name="parameters"></a>Parameter  
 ` left`  
 Eines der zu vergleichenden Objekte.  
  
 ` right`  
 Eines der zu vergleichenden Objekte.  
  
 `Ty1`  
 Der vom linken gemeinsamen Zeiger gesteuerte Typ.  
  
 `Ty2`  
 Der vom rechten gemeinsamen Zeiger gesteuerte Typ.  
  
### <a name="remarks"></a>Hinweise  
 Die Vorlagenoperatoren geben ` left``.get() >=` ` right``.get()` zurück.  
  
##  <a name="a-nameoperatorlta--operatorlt"></a><a name="operator_lt_"></a> operator&lt;  
 Testet, ob ein Objekt kleiner als ein zweites Objekt ist.  
  
```  
template <class T, class Del1, class U, class Del2>  
bool operator<(
    const unique_ptr<T, Del1>& left,  
    const unique_ptr<U&, Del2>& right);

template <class Ty1, class Ty2>  
bool operator<(
    const shared_ptr<Ty1>& left,  
    const shared_ptr<Ty2>& right);
```  
  
### <a name="parameters"></a>Parameter  
 ` left`  
 Eines der zu vergleichenden Objekte.  
  
 ` right`  
 Eines der zu vergleichenden Objekte.  
  
 `Ty1`  
 Der vom linken Zeiger gesteuerte Typ.  
  
 `Ty2`  
 Der vom rechten Zeiger gesteuerte Typ.  
  
##  <a name="a-nameoperatorlteqa--operatorlt"></a><a name="operator_lt__eq"></a> operator&lt;=  
 Testet, ob ein Objekt kleiner gleich einem zweiten Objekt ist.  
  
```  
template <class T, class Del1, class U, class Del2>  
bool operator<=(
    const unique_ptr<T, Del1>& left,  
    const unique_ptr<U&, Del2>& right);

template <class Ty1, class Ty2>  
bool operator<=(
    const shared_ptr<Ty1>& left,  
    const shared_ptr<Ty2>& right);
```  
  
### <a name="parameters"></a>Parameter  
 ` left`  
 Eines der zu vergleichenden Objekte.  
  
 ` right`  
 Eines der zu vergleichenden Objekte.  
  
 `Ty1`  
 Der vom linken gemeinsamen Zeiger gesteuerte Typ.  
  
 `Ty2`  
 Der vom rechten gemeinsamen Zeiger gesteuerte Typ.  
  
### <a name="remarks"></a>Hinweise  
 Die Vorlagenoperatoren geben ` left``.get() <=` ` right``.get()` zurück  
  
##  <a name="a-nameoperatorgta--operatorgt"></a><a name="operator_gt_"></a> operator&gt;  
 Testet, ob ein Objekt größer als ein zweites Objekt ist.  
  
```  
template <class Ty1, class Del1, class Ty2, class Del2>  
bool operator>(
    const unique_ptr<Ty1, Del1>& left,  
    const unique_ptr<Ty2&, Del2gt;& right);

template <class Ty1, class Ty2>  
bool operator>(
    const shared_ptr<Ty1>& left,  
    const shared_ptr<Ty2>& right);
```  
  
### <a name="parameters"></a>Parameter  
 ` left`  
 Eines der zu vergleichenden Objekte.  
  
 ` right`  
 Eines der zu vergleichenden Objekte.  
  
 `Ty1`  
 Der vom linken gemeinsamen Zeiger gesteuerte Typ.  
  
 `Ty2`  
 Der vom rechten gemeinsamen Zeiger gesteuerte Typ.  
  
##  <a name="a-nameoperatorltlta--operatorltlt"></a><a name="operator_lt__lt_"></a> operator&lt;&lt;  
Schreibt den freigegebenen Zeiger auf den Stream.  
  
```  
template <class Elem, class Tr, class Ty>  
std::basic_ostream<Elem, Tr>& operator<<(std::basic_ostream<Elem, Tr>& out,  
    shared_ptr<Ty>& sp);
```  
  
### <a name="parameters"></a>Parameter  
 `Elem`  
 Der Typ des Streamelements.  
  
 `Tr`  
 Der Typ des Streamelements.  
  
 `Ty`  
 Der vom freigegebenen Zeiger gesteuerte Typ.  
  
 `out`  
 Der Ausgabestream.  
  
 `sp`  
 Der freigegebene Zeiger.  
  
### <a name="remarks"></a>Hinweise  
 Die Vorlagenfunktion gibt `out << sp.get()` zurück.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// std__memory__operator_sl.cpp   
// compile with: /EHsc   
#include <memory>   
#include <iostream>   
  
int main()   
    {   
    std::shared_ptr<int> sp0(new int(5));   
  
    std::cout << "sp0 == " << sp0 << " (varies)" << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
sp0 == 3f3040 (varies)  
```  
  
## <a name="see-also"></a>Siehe auch  
 [\<memory>](../standard-library/memory.md)


