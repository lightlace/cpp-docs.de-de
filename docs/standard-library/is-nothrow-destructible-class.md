---
title: is_nothrow_destructible-Klasse | Microsoft-Dokumentation
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
- type_traits/std::is_nothrow_destructible
dev_langs:
- C++
helpviewer_keywords:
- is_nothrow_destructible
ms.assetid: 0bbd8a28-e312-4d72-bd28-aac027f974d3
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 857d37d89ff61dd7e6f0768796024565b03c920f
ms.contentlocale: de-de
ms.lasthandoff: 10/03/2017

---
# <a name="isnothrowdestructible-class"></a>is_nothrow_destructible-Klasse
Testet, ob der Typ zerstörbar ist, und ob der Compiler weiß, dass der Destruktor nicht ausgelöst wird.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class T>  
struct is_nothrow_destructible;
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der abzufragende Typ.  
  
## <a name="remarks"></a>Hinweise  
 Eine Instanz des Typprädikats ist TRUE, wenn der Typ `T` ein zerstörbarer Typ ist, und wenn der Compiler weiß, dass der Destruktor nicht ausgelöst wird. Andernfalls ist sie FALSE.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<type_traits>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [<type_traits>](../standard-library/type-traits.md)



