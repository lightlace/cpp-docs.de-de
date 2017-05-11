---
title: allocator_chunklist-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- stdext::allocators::allocator_chunklist
- allocators::allocator_chunklist
- allocators/stdext::allocator_chunklist
- allocators/stdext::allocators::allocator_chunklist
- allocator_chunklist
dev_langs:
- C++
helpviewer_keywords:
- allocator_chunklist class
ms.assetid: ea72ed0a-dfdb-4c8b-8096-e4baf567b80f
caps.latest.revision: 20
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4ecf60434799708acab4726a95380a2d3b9dbb3a
ms.openlocfilehash: 9acdadca2530f8ed54ec4bde7a6a1fe218f00f8a
ms.contentlocale: de-de
ms.lasthandoff: 04/19/2017

---
# <a name="allocatorchunklist-class"></a>allocator_chunklist-Klasse
Beschreibt ein Objekt, das die Speicherbelegung und -freigabe für Objekte, die einen Zwischenspeicher des Typs [cache_chunklist](../standard-library/cache-chunklist-class.md) verwenden.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class Type>  
class allocator_chunklist;
```  
  
#### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`Type`|Der Elementtyp, die durch die Zuweisung zugeordnet wird.|  
  
## <a name="remarks"></a>Hinweise  
 Das Makro [ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl) übergibt diese Klasse als Parameter `name` in der folgenden Anweisung: `ALLOCATOR_DECL(CACHE_CHUNKLIST, SYNC_DEFAULT, allocator_chunklist``);`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<allocators>  
  
 **Namespace:** stdext  
  
## <a name="see-also"></a>Siehe auch  
 [\<allocators>](../standard-library/allocators-header.md)




