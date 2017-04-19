---
title: add_pointer-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- add_pointer
- type_traits/std::add_pointer
dev_langs:
- C++
helpviewer_keywords:
- add_pointer class
- add_pointer
ms.assetid: d8095cb0-6578-4143-b78f-87f82485298c
caps.latest.revision: 22
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
translationtype: Machine Translation
ms.sourcegitcommit: 51fbd09793071631985720550007dddbe16f598f
ms.openlocfilehash: 008f19421575b8a930498a615642fdfdad99b7b6
ms.lasthandoff: 02/24/2017

---
# <a name="addpointer-class"></a>add_pointer-Klasse
Wandelt einen angegebenen Typ in einen Zeiger auf den Typ um.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class T>  
struct add_pointer;  
 
template <class T>
using add_pointer_t = typename add_pointer<T>::type;  
```  
  
#### <a name="parameters"></a>Parameter  
*T*  
Der zu ändernde Typ.  
  
## <a name="remarks"></a>Hinweise  
Der typedef-Member `type` benennt den gleichen Typ mit `remove_reference<T>::type*`. Das Alias `add_pointer_t` ist eine Verknüpfung für den Zugriff auf den typedef-Member `type`.  
  
Da es unzulässig ist, einen Zeiger aus einem Verweis zu erstellen, wird der Verweis durch `add_pointer` ggf. vom angegebenen Typ entfernt, bevor der Zeiger auf den Typ erstellt wird. Daher können Sie einen Typ mit `add_pointer` verwenden, ohne sich überlegen zu müssen, ob der Typ ein Verweis ist.  
  
## <a name="example"></a>Beispiel  
Das folgende Beispiel zeigt, dass `add_pointer` eines Typs mit einem Zeiger auf diesen Typ identisch ist.  
  
```cpp  
#include <type_traits>   
#include <iostream>   
  
int main()   
{   
    std::add_pointer_t<int> *p = (int **)0;   
  
    p = p;  // to quiet "unused" warning   
    std::cout << "add_pointer_t<int> == "   
        << typeid(*p).name() << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
add_pointer_t<int> == int *  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<type_traits>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [<type_traits>](../standard-library/type-traits.md)   
 [remove_pointer-Klasse](../standard-library/remove-pointer-class.md)

