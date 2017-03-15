---
title: is_default_constructible-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- is_default_constructible
- std.is_default_constructible
- std::is_default_constructible
- type_traits/std::is_default_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_default_constructible
ms.assetid: dd8f1c44-dae5-4258-891f-c5e048d94092
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: e3542b828eb6c9f67ee21660875ee401f043888e
ms.lasthandoff: 02/24/2017

---
# <a name="isdefaultconstructible-class"></a>is_default_constructible-Klasse
Testet, ob ein Typ einen Standardkonstruktor besitzt.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class Ty>  
struct is_default_constructible;  
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der abzufragende Typ.  
  
## <a name="remarks"></a>Hinweise  
 Eine Instanz des Typprädikats ist „true“, wenn der Typ `T` ein Klassentyp ist, der einen trivialen Konstruktor aufweist; andernfalls „false“. Dies entspricht dem Prädikat `is_constructible<T>`. Typ `T` muss ein vollständiger Typ, `void`oder ein Array mit unbekannter Grenze sein.  
  
## <a name="example"></a>Beispiel  
  
```cpp  
#include <type_traits>   
#include <iostream>   
  
struct Simple  
{  
    Simple() : val(0) {}  
    int val;  
};  
  
struct Simple2  
{  
    Simple2(int v) : val(v) {}  
    int val;  
};  
  
int main()  
{  
    std::cout << "is_default_constructible<Simple> == " << std::boolalpha  
        << std::is_default_constructible<Simple>::value << std::endl;  
    std::cout << "is_default_constructible<Simple2> == " << std::boolalpha  
        << std::is_default_constructible<Simple2>::value << std::endl;  
  
    return (0);  
}  
  
```  
  
```Output  
is_default_constructible<Simple> == true  
is_default_constructible<Simple2> == false  
```  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<type_traits>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [<type_traits>](../standard-library/type-traits.md)


