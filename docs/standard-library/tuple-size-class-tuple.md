---
title: tuple_size-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- tuple_size
- std::tuple_size
- utility/std::tuple_size
dev_langs:
- C++
helpviewer_keywords:
- tuple_size Class
ms.assetid: 73852fc5-eb68-41f1-8379-465cedc2314a
caps.latest.revision: 23
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.sourcegitcommit: 41b445ceeeb1f37ee9873cb55f62d30d480d8718
ms.openlocfilehash: f0ae102852f1db46b68d86438e20ce9645535d19
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="tuplesize-class"></a>tuple_size-Klasse;
Ruft die Anzahl der Elemente in einem `tuple` ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
// TEMPLATE STRUCT tuple_size  
template <class Tuple>  
   struct tuple_size;  
  
// number of elements in array  
template <class Elem, size_t Size>  
   struct tuple_size<array<Elem, Size>>  
      : integral_constant<size_t, Size>; 
  
// size of pair
template <class T1, class T2>
   struct tuple_size<pair<T1, T2>> 
      : integral_constant<size_t, 2>

// size of tuple  
template <class... Types>  
   struct tuple_size<tuple<Types...>>  
      : integral_constant<size_t, sizeof...(Types)>;  
  
// size of const tuple  
template <class Tuple>  
   struct tuple_size<const Tuple>;  
  
// size of volatile tuple  
template <class Tuple>  
   struct tuple_size<volatile Tuple>;  
  
// size of const volatile tuple  
template <class Tuple>  
   struct tuple_size<const volatile Tuple>;   
```  
  
#### <a name="parameters"></a>Parameter  
*Tuple*  
Der Typ des Tupels. 
  
*Elem*  
Der Typ der Arrayelemente. 
  
*Size*  
Die Größe des Arrays. 
  
*T1*  
Der Typ des ersten Members des Paares. 
  
*T2*  
Der Typ des zweiten Members des Paares. 
  
*Typen*  
Die Typen der Elemente des Tupels. 
  
  
## <a name="remarks"></a>Hinweise  
Die Vorlagenklasse verfügt über einen Member `value` , der einem ganzzahligen konstanten Ausdruck entspricht, dessen Wert dem Wertebereich des Tupeltyps `Tuple`entspricht.  
  
Die Vorlagenspezialisierung für Arrays verfügt über einen Member `value`, der ein ganzzahliger konstanter Ausdruck ist, dessen Wert `Size` und damit die Größe des Arrays ist.  
  
Die Vorlagenspezialisierung für Paare verfügt über einen Member `value`, der ein ganzzahliger konstanter Ausdruck ist, dessen Wert 2 ist.  
  
## <a name="example"></a>Beispiel  
  
```cpp  
#include <tuple>   
#include <iostream>  
  
using namespace std;  
  
typedef tuple<int, double, int, double> MyTuple;  
int main()  
{  
    MyTuple c0(0, 1.5, 2, 3.7);  
  
    // display contents " 0 1 2 3"   
    cout << " " << get<0>(c0);  
    cout << " " << get<1>(c0);  
    cout << " " << get<2>(c0);  
    cout << " " << get<3>(c0) << endl;  
  
    // display size " 4"   
    cout << " " << tuple_size<MyTuple>::value << endl;  
}  
```  
  
```Output  
 0 1.5 2 3.7  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<tuple>  
 **Header:** \<array> (für Arrayspezialisierung)  
 **Header:** \<utility> (für Paarspezialisierung)  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [\<tuple>](../standard-library/tuple.md)   
 [tuple](../standard-library/tuple-class.md)  
 [tuple_element-Klasse](../standard-library/tuple-element-class-tuple.md)

