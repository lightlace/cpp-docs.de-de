---
title: sync_none-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sync_none
- allocators/stdext::sync_none
- stdext::sync_none
- allocators/stdext::sync_none::allocate
- allocators/stdext::sync_none::deallocate
- allocators/stdext::sync_none::equals
dev_langs:
- C++
helpviewer_keywords:
- sync_none class
ms.assetid: f7473cee-14f3-4fe1-88bc-68cd085e59e1
caps.latest.revision: 21
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
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: f56f09f3c3591d0c969ea3b3e242cf39812356fb
ms.contentlocale: de-de
ms.lasthandoff: 04/29/2017

---
# <a name="syncnone-class"></a>sync_none-Klasse
Beschreibt einen [Synchronisierungsfilter](../standard-library/allocators-header.md), der keine Synchronisierung bietet.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class Cache>  
class sync_none
```  
  
#### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`Cache`|Der Cachetyp, der diesem Synchronisierungsfilter zugeordnet werden soll. Dieser kann [cache_chunklist](../standard-library/cache-chunklist-class.md), [cache_freelist](../standard-library/cache-freelist-class.md) oder [cache_suballoc](../standard-library/cache-suballoc-class.md) sein.|  
  
### <a name="member-functions"></a>Memberfunktionen  
  
|||  
|-|-|  
|[allocate](#allocate)|Belegt einen Speicherblock.|  
|[deallocate](#deallocate)|Gibt eine angegebene Anzahl von Objekten im Speicher frei, beginnend an einer angegebenen Position.|  
|[equals](#equals)|Vergleicht zwei Caches auf Gleichheit.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<allocators>  
  
 **Namespace:** stdext  
  
##  <a name="allocate"></a> sync_none::allocate  
 Belegt einen Speicherblock.  
  
```
void *allocate(std::size_t count);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`count`|Die Anzahl der zuzuordnenden Elemente des Arrays.|  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt `cache.allocate(count)` zurück, wobei `cache` das Cache-Objekt ist.  
  
##  <a name="deallocate"></a> sync_none::deallocate  
 Gibt eine angegebene Anzahl von Objekten im Speicher frei, beginnend an einer angegebenen Position.  
  
```
void deallocate(void* ptr, std::size_t count);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`ptr`|Ein Zeiger auf das erste Objekt, dessen Zuweisung zum Speicher aufgehoben werden soll.|  
|`count`|Die Anzahl von Objekten, deren Zuweisung zum Speicherplatz aufgehoben werden soll.|  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion ruft `cache.deallocate(ptr, count)` auf, wobei `cache` das Cache-Objekt darstellt.  
  
##  <a name="equals"></a> sync_none::equals  
 Vergleicht zwei Caches auf Gleichheit.  
  
```
bool equals(const sync<Cache>& Other) const;
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`Cache`|Das Cache-Objekt des Synchronisierungsfilters.|  
|`Other`|Das Cache-Objekt, das auf Gleichheit verglichen werden soll.|  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Memberfunktion gibt immer `true` zurück.  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [\<allocators>](../standard-library/allocators-header.md)




