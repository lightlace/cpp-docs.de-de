---
title: cache_suballoc-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocators/stdext::cache_suballoc
- allocators/stdext::cache_suballoc::allocate
- allocators/stdext::cache_suballoc::deallocate
dev_langs:
- C++
helpviewer_keywords:
- stdext::cache_suballoc
- stdext::cache_suballoc [C++], allocate
- stdext::cache_suballoc [C++], deallocate
ms.assetid: 9ea9c5e9-1dcc-45d0-b3a7-a56a93d88898
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: ab861704bfb44546a3dcb5a4a3b2f4210dbe8774
ms.contentlocale: de-de
ms.lasthandoff: 10/03/2017

---
# <a name="cachesuballoc-class"></a>cache_suballoc-Klasse
Definiert eine [Blockzuweisung](../standard-library/allocators-header.md), die Speicherblöcke einheitlicher Größe zuweist und freigibt.  
  
## <a name="syntax"></a>Syntax  
  
```
template <std::size_t Sz, size_t Nelts = 20>  
class cache_suballoc
```  
  
#### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`Sz`|Die Anzahl der zuzuordnenden Elemente des Arrays.|  
  
## <a name="remarks"></a>Hinweise  
 Die Vorlagenklasse cache_suballoc speichert freigegebene Speicherblöcke in einer Freiliste mit unbegrenzter Länge unter Verwendung von `freelist<sizeof(Type), max_unbounded>` und führt eine Unterzuweisung von Speicherblöcken aus einem größeren Block durch, die mit `operator new` zugeordnet werden, wenn die Freiliste leer ist.  
  
 Jeder Block enthält `Sz * Nelts` Bytes Speicherkapazität und die Daten, die `operator new` und `operator delete` benötigen. Zugeordnete Blöcke werden niemals freigegeben.  
  
### <a name="constructors"></a>Konstruktoren  
  
|||  
|-|-|  
|[cache_suballoc](#cache_suballoc)|Konstruiert ein Objekt vom Typ `cache_suballoc`.|  
  
### <a name="member-functions"></a>Memberfunktionen  
  
|||  
|-|-|  
|[allocate](#allocate)|Belegt einen Speicherblock.|  
|[deallocate](#deallocate)|Gibt eine angegebene Anzahl von Objekten im Speicher frei, beginnend an einer angegebenen Position.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<allocators>  
  
 **Namespace:** stdext  
  
##  <a name="allocate"></a> cache_suballoc::allocate  
 Belegt einen Speicherblock.  
  
```
void *allocate(std::size_t count);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`count`|Die Anzahl der zuzuordnenden Elemente des Arrays.|  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf das zugewiesene Objekt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="cache_suballoc"></a> cache_suballoc::cache_suballoc  
 Konstruiert ein Objekt vom Typ `cache_suballoc`.  
  
```
cache_suballoc();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="deallocate"></a> cache_suballoc::deallocate  
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
  
## <a name="see-also"></a>Siehe auch  
 [\<allocators>](../standard-library/allocators-header.md)



