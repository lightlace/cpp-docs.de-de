---
title: remove_pointer-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::remove_pointer
dev_langs: C++
helpviewer_keywords:
- remove_pointer class
- remove_pointer
ms.assetid: 2cd4e417-32fb-4f53-bd16-4e8a98240832
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ba07a13c8955a45c49797619ba69f7f89f71d5bc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="removepointer-class"></a>remove_pointer-Klasse
Wandelt einen Zeiger auf den Typ in einen Typ um.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class T>  
struct remove_pointer;  
 
template <class T>  
using remove_pointer_t = typename remove_pointer<T>::type;  
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der zu ändernde Typ.  
  
## <a name="remarks"></a>Hinweise  
 Eine Instanz von `remove_pointer<T>` enthält einen geänderten Typ, der `T1` ist, wenn `T` das Format `T1*`, `T1* const`, `T1* volatile` oder `T1* const volatile` hat; andernfalls `T`.  
  
## <a name="example"></a>Beispiel  
  
```cpp  
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    int *p = (std::remove_pointer_t<int *> *)0;   
  
    p = p;  // to quiet "unused" warning   
    std::cout << "remove_pointer_t<int *> == "   
        << typeid(*p).name() << std::endl;   
  
    return (0);   
    }  
```  
  
```Output  
remove_pointer_t<int *> == int  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<type_traits>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [<type_traits>](../standard-library/type-traits.md)   
 [add_pointer-Klasse](../standard-library/add-pointer-class.md)