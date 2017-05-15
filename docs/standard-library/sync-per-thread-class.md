---
title: sync_per_thread-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- stdext::sync_per_thread
- sync_per_thread
- allocators/stdext::sync_per_thread
- allocators/stdext::sync_per_thread::allocate
- allocators/stdext::sync_per_thread::deallocate
- allocators/stdext::sync_per_thread::equals
dev_langs:
- C++
helpviewer_keywords:
- sync_per_thread class
ms.assetid: 47bf75f8-5b02-4760-b1d3-3099d08fe14c
caps.latest.revision: 19
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
ms.openlocfilehash: 71d2dd481c2c14303c71ec461ddcb5c041859531
ms.contentlocale: de-de
ms.lasthandoff: 04/29/2017

---
# <a name="syncperthread-class"></a>sync_per_thread-Klasse
Beschreibt einen [Synchronisierungsfilter](../standard-library/allocators-header.md), der für jeden Thread ein getrenntes Cache-Objekt bereitstellt.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class Cache>  
class sync_per_thread
```  
  
#### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`Cache`|Der Cachetyp, der diesem Synchronisierungsfilter zugeordnet werden soll. Dieser kann [cache_chunklist](../standard-library/cache-chunklist-class.md), [cache_freelist](../standard-library/cache-freelist-class.md) oder [cache_suballoc](../standard-library/cache-suballoc-class.md) sein.|  
  
## <a name="remarks"></a>Hinweise  
 Zuweisungen, die `sync_per_thread` verwenden, können identisch sein, auch wenn die Zuweisung von in einem Thread zugewiesenen Blöcken nicht von einem anderen Thread aufgehoben werden kann. Wenn mit einer der Zuweisungen verwendet wird, sollten in einem Thread zugewiesene Speicherblöcke nicht für andere Threads sichtbar gemacht werden. In der Praxis bedeutet dies, dass nur ein einzelner Thread auf einen Container zugreifen kann, der eine der folgenden Zuweisungen verwendet.  
  
### <a name="member-functions"></a>Memberfunktionen  
  
|||  
|-|-|  
|[allocate](#allocate)|Belegt einen Speicherblock.|  
|[deallocate](#deallocate)|Gibt eine angegebene Anzahl von Objekten im Speicher frei, beginnend an einer angegebenen Position.|  
|[equals](#equals)|Vergleicht zwei Caches auf Gleichheit.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<allocators>  
  
 **Namespace:** stdext  
  
##  <a name="allocate"></a> sync_per_thread::allocate  
 Belegt einen Speicherblock.  
  
```
void *allocate(std::size_t count);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`count`|Die Anzahl der zuzuordnenden Elemente des Arrays.|  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt das Ergebnis eines Aufrufs von `cache::allocate(count)` auf dem Cache-Objekt zurück, das zu dem aktuellen Thread gehört. Wenn kein Cache-Objekt für den aktuellen Thread zugewiesen wurde, wird zuerst eines zugewiesen.  
  
##  <a name="deallocate"></a> sync_per_thread::deallocate  
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
 Die Memberfunktion ruft `deallocate` auf dem Cache-Objekt auf, das zu dem aktuellen Thread gehört. Wenn kein Cache-Objekt für den aktuellen Thread zugewiesen wurde, wird zuerst eines zugewiesen.  
  
##  <a name="equals"></a> sync_per_thread::equals  
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
 `false`, wenn für dieses Objekt kein Cache-Objekt zugewiesen wurde, oder für `Other` im aktuellen Thread. Andernfalls wird das Ergebnis der Anwendung von `operator==` auf die beiden Cache-Objekte zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [\<allocators>](../standard-library/allocators-header.md)




