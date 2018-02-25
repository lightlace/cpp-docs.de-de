---
title: is_pointer-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- type_traits/std::is_pointer
dev_langs:
- C++
helpviewer_keywords:
- is_pointer class
- is_pointer
ms.assetid: 44e0a403-7241-4e0a-8922-32877bcb9a4c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3f0c4048ebaa98a6533e210335ecedceb931c644
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="ispointer-class"></a>is_pointer-Klasse
Testet, ob der Typ ein Zeiger ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class Ty>  
struct is_pointer;  
```  
  
#### <a name="parameters"></a>Parameter  
 `Ty`  
 Der abzufragende Typ.  
  
## <a name="remarks"></a>Hinweise  
 Eine Instanz des Typprädikats ist „true“, wenn der Typ `Ty` ein Zeiger auf `void`, ein Zeiger auf ein Objekt oder ein Zeiger auf eine Funktion oder ein `cv-qualified`-Formular von einem davon ist, andernfalls „false“. Beachten Sie, dass `is_pointer` „false“ ist, wenn `Ty` ein Zeiger auf ein Member oder ein Zeiger auf eine Memberfunktion ist.  
  
## <a name="example"></a>Beispiel  
  
```cpp  
// std__type_traits__is_pointer.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_pointer<trivial> == " << std::boolalpha   
        << std::is_pointer<trivial>::value << std::endl;   
    std::cout << "is_pointer<int trivial::*> == " << std::boolalpha   
        << std::is_pointer<int trivial::*>::value << std::endl;   
    std::cout << "is_pointer<trivial *> == " << std::boolalpha   
        << std::is_pointer<trivial *>::value << std::endl;   
    std::cout << "is_pointer<int> == " << std::boolalpha   
        << std::is_pointer<int>::value << std::endl;   
    std::cout << "is_pointer<int *> == " << std::boolalpha   
        << std::is_pointer<int *>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
is_pointer<trivial> == false  
is_pointer<int trivial::*> == false  
is_pointer<trivial *> == true  
is_pointer<int> == false  
is_pointer<int *> == true  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<type_traits>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [<type_traits>](../standard-library/type-traits.md)   
 [is_member_pointer-Klasse](../standard-library/is-member-pointer-class.md)   
 [is_reference-Klasse](../standard-library/is-reference-class.md)
