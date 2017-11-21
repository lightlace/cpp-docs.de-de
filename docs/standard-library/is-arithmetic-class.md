---
title: is_arithmetic-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::is_arithmetic
dev_langs: C++
helpviewer_keywords:
- is_arithmetic class
- is_arithmetic
ms.assetid: ea427b7e-0141-4a04-848f-561054c53001
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 55c62444cbe9fec8e099520cddba7992fad6f208
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="isarithmetic-class"></a>is_arithmetic-Klasse
Prüft, ob der Typ arithmetisch ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class Ty>  
struct is_arithmetic;  
```  
  
#### <a name="parameters"></a>Parameter  
 `Ty`  
 Der abzufragende Typ.  
  
## <a name="remarks"></a>Hinweise  
 Eine Instanz des Typs Prädikat enthält true, wenn der Typ `Ty` ein arithmetischer Typ ist, d. h., ein ganzzahliger Typ, ein Gleitkommawert, oder ein `cv-qualified`-Formular, andernfalls enthält er false.  
  
## <a name="example"></a>Beispiel  
  
```cpp  
// std__type_traits__is_arithmetic.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_arithmetic<trivial> == " << std::boolalpha   
        << std::is_arithmetic<trivial>::value << std::endl;   
    std::cout << "is_arithmetic<int> == " << std::boolalpha   
        << std::is_arithmetic<int>::value << std::endl;   
    std::cout << "is_arithmetic<float> == " << std::boolalpha   
        << std::is_arithmetic<float>::value << std::endl;   
  
    return (0);   
    }  
```  
  
```Output  
is_arithmetic<trivial> == false  
is_arithmetic<int> == true  
is_arithmetic<float> == true  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<type_traits>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [<type_traits>](../standard-library/type-traits.md)   
 [is_floating_point-Klasse](../standard-library/is-floating-point-class.md)   
 [is_integral-Klasse](../standard-library/is-integral-class.md)
