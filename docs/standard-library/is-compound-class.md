---
title: is_compound-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::is_compound
dev_langs: C++
helpviewer_keywords:
- is_compound class
- is_compound
ms.assetid: bdad1167-cf3f-4f37-8321-62a5df159ead
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 97751cae1d0909465e0bf91d8b4453d5f4f0265c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="iscompound-class"></a>is_compound-Klasse
Testet, ob der angegebene Typ nicht grundlegend ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class Ty>  
struct is_compound;  
```  
  
#### <a name="parameters"></a>Parameter  
 `Ty`  
 Der abzufragende Typ.  
  
## <a name="remarks"></a>Hinweise  
 Eine Instanz des Typprädikats enthält `false`, wenn der Typ von `Ty` ein grundlegender Typ ist (d.h., wenn [is_fundamental](../standard-library/is-fundamental-class.md)`<Ty>` `true` enthält); andernfalls ist `true` enthalten. Daher enthält das Prädikat `true`, wenn `Ty` ein Arraytyp, ein Funktionstyp, ein Zeiger auf `void` oder auf ein Objekt oder eine Funktion, ein Verweis, eine Klasse, eine Vereinigung, eine Enumeration oder ein Zeiger auf ein nicht-statisches Klassenmember oder eine *cv-qualified*-Form eines dieser Elemente ist.  
  
## <a name="example"></a>Beispiel  
  
```cpp  
// std__type_traits__is_compound.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_compound<trivial> == " << std::boolalpha   
        << std::is_compound<trivial>::value << std::endl;   
    std::cout << "is_compound<int[]> == " << std::boolalpha   
        << std::is_compound<int[]>::value << std::endl;   
    std::cout << "is_compound<int()> == " << std::boolalpha   
        << std::is_compound<int()>::value << std::endl;   
    std::cout << "is_compound<int&> == " << std::boolalpha   
        << std::is_compound<int&>::value << std::endl;   
    std::cout << "is_compound<void *> == " << std::boolalpha   
        << std::is_compound<void *>::value << std::endl;   
    std::cout << "is_compound<int> == " << std::boolalpha   
        << std::is_compound<int>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
is_compound<trivial> == true  
is_compound<int[]> == true  
is_compound<int()> == true  
is_compound<int&> == true  
is_compound<void *> == true  
is_compound<int> == false  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<type_traits>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [<type_traits>](../standard-library/type-traits.md)   
 [is_class-Klasse](../standard-library/is-class-class.md)
