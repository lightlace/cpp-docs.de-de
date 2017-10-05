---
title: allocator_variable_size-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocators/stdext::allocator_variable_size
- allocators/stdext::allocators::allocator_variable_size
- stdext::allocators::allocator_variable_size
dev_langs:
- C++
helpviewer_keywords:
- stdext::allocator_variable_size
- stdext::allocators [C++], allocator_variable_size
ms.assetid: c3aa4105-ae45-4385-bbbe-9f23060478cb
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 713a1c651c67e8b55b45819797d7fb55080a8251
ms.contentlocale: de-de
ms.lasthandoff: 10/03/2017

---
# <a name="allocatorvariablesize-class"></a>allocator_variable_size-Klasse
Beschreibt ein Objekt, das die Speicherbelegung und -freigabe für Objekte des Typs `Type` verwaltet, die einen Cache des Typs [cache_freelist](../standard-library/cache-freelist-class.md) mit einer von [max_variable_size](../standard-library/max-variable-size-class.md) verwalteten Länge verwenden.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class Type>  
class allocator_variable_size;
```  
  
#### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`Type`|Der Elementtyp, die durch die Zuweisung zugeordnet wird.|  
  
## <a name="remarks"></a>Hinweise  
 Das Makro [ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl) übergibt diese Klasse als Parameter `name` in der folgenden Anweisung: `ALLOCATOR_DECL(CACHE_FREELIST(stdext::allocators::max_variable_size), SYNC_DEFAULT, allocator_variable_size);`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<allocators>  
  
 **Namespace:** stdext  
  
## <a name="see-also"></a>Siehe auch  
 [\<allocators>](../standard-library/allocators-header.md)




