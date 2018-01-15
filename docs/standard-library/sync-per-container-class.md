---
title: sync_per_container-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocators/stdext::sync_per_container
- allocators/stdext::sync_per_container::equals
dev_langs: C++
helpviewer_keywords: sync_per_container class
ms.assetid: 0b4b2904-b668-4d94-a422-d4f919cbffab
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7864b6367d716ff7504982c4a8cbbed55f7784c0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="syncpercontainer-class"></a>sync_per_container-Klasse
Beschreibt einen [Synchronisierungsfilter](../standard-library/allocators-header.md), der für jedes Zuweisungsobjekt ein getrenntes Cache-Objekt bereitstellt.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class Cache>  
class sync_per_container
 : public Cache
```  
  
#### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`Cache`|Der Cachetyp, der diesem Synchronisierungsfilter zugeordnet werden soll. Dieser kann [cache_chunklist](../standard-library/cache-chunklist-class.md), [cache_freelist](../standard-library/cache-freelist-class.md) oder [cache_suballoc](../standard-library/cache-suballoc-class.md) sein.|  
  
### <a name="member-functions"></a>Memberfunktionen  
  
|||  
|-|-|  
|[equals](#equals)|Vergleicht zwei Caches auf Gleichheit.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<allocators>  
  
 **Namespace:** stdext  
  
##  <a name="equals"></a> sync_per_container::equals  
 Vergleicht zwei Caches auf Gleichheit.  
  
```
bool equals(const sync_per_container<Cache>& Other) const;
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`Cache`|Das Cache-Objekt des Synchronisierungsfilters.|  
|`Other`|Das Cache-Objekt, das auf Gleichheit verglichen werden soll.|  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Memberfunktion gibt immer `false` zurück.  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [\<allocators>](../standard-library/allocators-header.md)



