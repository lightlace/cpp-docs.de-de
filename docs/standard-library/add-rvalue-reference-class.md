---
title: add_rvalue_reference-Klasse| Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- type_traits/std::add_rvalue_reference
- add_rvalue_reference
dev_langs:
- C++
helpviewer_keywords:
- add_rvalue_reference Class
ms.assetid: 76b0cb7c-1031-45d0-b409-f03ab0297580
caps.latest.revision: 11
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
ms.sourcegitcommit: 4ecf60434799708acab4726a95380a2d3b9dbb3a
ms.openlocfilehash: faa8014788d12841df6a0822ec7fe379198f06d1
ms.contentlocale: de-de
ms.lasthandoff: 04/19/2017

---
# <a name="addrvaluereference-class"></a>add_rvalue_reference-Klasse
Erstellt einen rvalue-Verweistyp des Vorlagenparameters, wenn es sich dabei um einen Objekt- oder Funktionstyp handelt. Ansonsten ist der Typ aufgrund der Semantik der Verweisreduzierung der Gleiche wie der Vorlagenparameter.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
template <class T>
struct add_rvalue_reference;

template <class T>
using add_rvalue_reference_t = typename add_rvalue_reference<T>::type;
```  
  
#### <a name="parameters"></a>Parameter  
 T  
 Der zu ändernde Typ.  
  
## <a name="remarks"></a>Hinweise  
 Die `add_rvalue_reference`-Klasse hat einen Member mit dem Namen `type`, der ein Alias für einen rvalue-Referenztyp des Vorlagenparameter `T` ist. Die Semantik der Verweisreduzierung impliziert, dass `T&&` für Nicht-Objekt- und Nicht-Funktion-`T`-Typen `T` ist. Wenn `T` z.B. ein lvalue-Verweistyp ist, ist `add_rvalue_reference<T>::type` der lvalue-und nicht der rvalue-Verweistyp.  
  
 Der Einfachheit halber definiert <type_traits> eine Hilfsprogrammvorlage `add_rvalue_reference_t`, die ein Alias für den `type`-Member von `add_rvalue_reference` darstellt.  
  
## <a name="example"></a>Beispiel  
 Dieses Codebeispiel verwendet static_assert, um anzuzeigen, wie rvalue-Verweistypen mithilfe von `add_rvalue_reference` und `add_rvalue_reference_t` erstellt werden, und wie das Ergebnis von `add_rvalue_reference` eines rvalue-Verweistyps kein rvalue-Verweis ist, sondern auf einen lvalue-Typ reduziert wird.  
  
```cpp  
// ex_add_rvalue_reference.cpp  
// Build by using: cl /EHsc /W4 ex_add_rvalue_reference.cpp  
#include <type_traits>   
#include <iostream>   
#include <string>  
  
using namespace std;  
int main()  
{  
    static_assert(is_same<add_rvalue_reference<string>::type, string&&>::value,   
        "Expected add_rvalue_reference_t<string> to be string&&");  
    static_assert(is_same<add_rvalue_reference_t<string*>, string*&&>::value,   
        "Expected add_rvalue_reference_t<string*> to be string*&&");  
    static_assert(is_same<add_rvalue_reference<string&>::type, string&>::value,   
        "Expected add_rvalue_reference_t<string&> to be string&");  
    static_assert(is_same<add_rvalue_reference_t<string&&>, string&&>::value,   
        "Expected add_rvalue_reference_t<string&&> to be string&&");  
    cout << "All static_assert tests of add_rvalue_reference passed." << endl;  
    return 0;  
}  
  
/*Output:  
All static_assert tests of add_rvalue_reference passed.  
*/  
```  
  
## <a name="requirements"></a>Anforderungen  
 Header: <type_traits> Namespace: std  
  
## <a name="see-also"></a>Siehe auch  
 [<type_traits>](../standard-library/type-traits.md)   
 [add_lvalue_reference-Klasse](../standard-library/add-lvalue-reference-class.md)   
 [is_rvalue_reference-Klasse](../standard-library/is-rvalue-reference-class.md)

