---
title: is_destructible-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- type_traits/std::is_destructible
dev_langs:
- C++
helpviewer_keywords:
- is_destructible
ms.assetid: 3bb9b718-1ad5-49ae-93cc-92b93b546b4d
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- es-es
- pl-pl
- pt-br
- tr-tr
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 438af85bce45bb0fe7d1386fdc46f1fab0217999
ms.contentlocale: de-de
ms.lasthandoff: 10/03/2017

---
# <a name="isdestructible-class"></a>is_destructible-Klasse
Testet, ob der Typ „destructible“ ist.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class T>  
struct is_destructible;
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der abzufragende Typ.  
  
## <a name="remarks"></a>Hinweise  
 Eine Instanz des Typprädikats ist „true“, wenn der Typ `T` vom Typ „destructible“ ist; andernfalls „false“. „destructible“-Typen sind Referenztypen, Objekttypen und Typen, bei denen für einige Typen `U` gleich `remove_all_extents_t<T>` der nicht ausgewertete Operand `std::declval<U&>.~U()` wohlgeformt ist. Andere Typen, z. B. unvollständige Typen, `void`und Funktionstypen, sind keine „destructible“-Typen.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<type_traits>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [<type_traits>](../standard-library/type-traits.md)




