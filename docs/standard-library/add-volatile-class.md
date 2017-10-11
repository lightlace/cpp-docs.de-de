---
title: add_volatile-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- type_traits/std::add_volatile
dev_langs:
- C++
helpviewer_keywords:
- add_volatile class
- add_volatile
ms.assetid: cde57277-d764-402d-841e-97611ebaab14
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 7e652a784276d01c572ffad0379a20359a7b39f2
ms.contentlocale: de-de
ms.lasthandoff: 10/03/2017

---
# <a name="addvolatile-class"></a>add_volatile-Klasse
Wandelt einen angegebenen Typ in einen volatile-Typ um.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class Ty>  
struct add_volatile;  
 
template <class T>
using add_volatile_t = typename add_volatile<T>::type;  
```  
  
### <a name="parameters"></a>Parameter  
*T*  
Der zu ändernde Typ.  
  
## <a name="remarks"></a>Hinweise  
Eine Instanz des `add_volatile<T>` enthält einen geänderten typedef-Member`type`, der *T* ist, wenn *T* ein Verweis, eine Funktion oder ein volatile-qualified-Typ ist; andernfalls `volatile` *T*. Das Alias `add_volatile_t` ist eine Verknüpfung für den Zugriff auf den typedef-Member`type`. 
  
## <a name="example"></a>Beispiel  
  
```cpp  
#include <type_traits>   
#include <iostream>   
  
int main()   
{   
    std::add_volatile_t<int> *p = (volatile int *)0;   
  
    p = p;  // to quiet "unused" warning   
    std::cout << "add_volatile<int> == "   
        << typeid(*p).name() << std::endl;   
  
    return (0);   
} 
```  
  
```Output  
add_volatile<int> == int  
```  
  
## <a name="requirements"></a>Anforderungen  

**Header:** \<type_traits>  
  
**Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
[<type_traits>](../standard-library/type-traits.md)   
[remove_volatile-Klasse](../standard-library/remove-volatile-class.md)

