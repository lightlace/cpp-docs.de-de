---
title: is_nothrow_assignable-Klasse | Microsoft-Dokumentation
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
- type_traits/std::is_nothrow_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_nothrow_assignable
ms.assetid: aa3aca92-308b-4b1d-b3f3-c54216c48fe7
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: f4e0b1cc873c5b83f7a307e98965ac4891153f60
ms.contentlocale: de-de
ms.lasthandoff: 10/03/2017

---
# <a name="isnothrowassignable-class"></a>Is_nothrow_assignable-Klasse
Testet, ob der Wert des `From`-Typ dem `To`-Typ zugewiesen werden kann und die Zuweisung nicht ausgelöst wird.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class To, class From>  
struct is_nothrow_assignable;
```  
  
#### <a name="parameters"></a>Parameter  
 Aktion  
 Der Typ des Objekts, das die Zuweisung empfängt.  
  
 Von  
 Der Typ des Objekts, das den Wert bereitstellt.  
  
## <a name="remarks"></a>Hinweise  
 Der Ausdruck `declval<To>() = declval<From>()` muss wohlgeformt sein und der Compiler muss wissen, dass er nicht auslöst. Sowohl `From` als auch `To` müssen vollständige Typen `void` sein, oder Arrays mit unbekannter Grenze.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<type_traits>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [<type_traits>](../standard-library/type-traits.md)




