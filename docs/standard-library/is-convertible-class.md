---
title: is_convertible-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::is_convertible
dev_langs: C++
helpviewer_keywords:
- is_convertible class
- is_convertible
ms.assetid: 75614008-1894-42ea-bd57-974399628536
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7fbcaee978d6fdf0041510a9c06cf9f901426e81
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="isconvertible-class"></a>is_convertible-Klasse
Testet, ob ein Typ in einen anderen konvertiert werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class From, class To>  
struct is_convertible;  
```  
  
#### <a name="parameters"></a>Parameter  
 `From`  
 Der Typ, aus dem konvertiert wird.  
  
 `Ty`  
 Der Typ, in den konvertiert werden soll.  
  
## <a name="remarks"></a>Hinweise  
 Eine Instanz des Typprädikats ist TRUE, wenn der Ausdruck `To to = from;`, wobei `from` ein Objekt vom Typ `From` ist, wohlgeformt ist.  
  
## <a name="example"></a>Beispiel  
  
```cpp  
// std__type_traits__is_convertible.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_convertible<trivial, int> == " << std::boolalpha   
        << std::is_convertible<trivial, int>::value << std::endl;   
    std::cout << "is_convertible<trivial, trivial> == " << std::boolalpha   
        << std::is_convertible<trivial, trivial>::value << std::endl;   
    std::cout << "is_convertible<char, int> == " << std::boolalpha   
        << std::is_convertible<char, int>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
is_convertible<trivial, int> == false  
is_convertible<trivial, trivial> == true  
is_convertible<char, int> == true  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<type_traits>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [<type_traits>](../standard-library/type-traits.md)   
 [is_base_of-Klasse](../standard-library/is-base-of-class.md)
