---
title: make_unsigned-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- type_traits/std::make_unsigned
dev_langs:
- C++
helpviewer_keywords:
- make_unsigned class
- make_unsigned
ms.assetid: 7a6a3c4f-1a4c-47e8-9ee2-ac1f7b669353
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: fdd04e8b2b235e9711036fbb66f9ac0ed8a99e75
ms.contentlocale: de-de
ms.lasthandoff: 10/03/2017

---
# <a name="makeunsigned-class"></a>make_unsigned-Klasse
Macht den Typ oder den kleinsten Typ ohne Vorzeichen größer oder gleich dem Typ.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class T>
struct make_unsigned;

template <class T>
using make_unsigned_t = typename make_unsigned<T>::type;
```  
  
#### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`T`|Der zu ändernde Typ.|  
  
## <a name="remarks"></a>Hinweise  
 Eine Instanz des Typmodifizierers enthält einen GeänderteTyp an, wenn der `T` als `is_unsigned<T>` true ist. Andernfalls ist dies der kleinste Datentyp mit Vorzeichen `ST`, für den `sizeof (T) <= sizeof (ST)`.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<type_traits>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [<type_traits>](../standard-library/type-traits.md)




