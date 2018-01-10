---
title: cache_freelist-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocators/stdext::cache_freelist
- allocators/stdext::cache_freelist::allocate
- allocators/stdext::cache_freelist::deallocate
dev_langs: C++
helpviewer_keywords:
- stdext::cache_freelist
- stdext::cache_freelist [C++], allocate
- stdext::cache_freelist [C++], deallocate
ms.assetid: 840694de-36ba-470f-8dae-2b723d5a8cd9
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c971a4aebcd0f0a7c0baa59a445059f681f7e8af
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cachefreelist-class"></a>cache_freelist-Klasse
Definiert eine [Blockzuweisung](../standard-library/allocators-header.md), die Speicherblöcke einheitlicher Größe zuweist und freigibt.  
  
## <a name="syntax"></a>Syntax  
  
```
template <std::size_t Sz, class Max>  
class cache_freelist
```  
  
#### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`Sz`|Die Anzahl der zuzuordnenden Elemente des Arrays.|  
|`Max`|Die max-Klasse, die die maximale Größe der Freiliste angibt. Dies kann [max_fixed_size](../standard-library/max-fixed-size-class.md), [max_none](../standard-library/max-none-class.md), [max_unbounded](../standard-library/max-unbounded-class.md) oder [max_variable_size](../standard-library/max-variable-size-class.md) sein.|  
  
## <a name="remarks"></a>Hinweise  
 Die Vorlagenklasse cache_freelist verwaltet eine Freiliste von Speicherblöcken der Größe `Sz`. Wenn die Freiliste voll ist, verwendet sie `operator delete`, um Speicherblöcke freizugeben. Wenn die Freiliste leer ist, verwendet sie `operator new`, um neue Speicherblöcke zuzuordnen. Die maximale Größe der Freiliste richtet sich nach der max-Klasse der Klasse, die im `Max`-Parameter übergeben wird.  
  
 Jeder Speicherblock enthält `Sz` Bytes Speicherkapazität und die Daten, die `operator new` und `operator delete` benötigen.  
  
### <a name="constructors"></a>Konstruktoren  
  
|||  
|-|-|  
|[cache_freelist](#cache_freelist)|Konstruiert ein Objekt vom Typ `cache_freelist`.|  
  
### <a name="member-functions"></a>Memberfunktionen  
  
|||  
|-|-|  
|[allocate](#allocate)|Belegt einen Speicherblock.|  
|[deallocate](#deallocate)|Gibt eine angegebene Anzahl von Objekten im Speicher frei, beginnend an einer angegebenen Position.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<allocators>  
  
 **Namespace:** stdext  
  
##  <a name="allocate"></a> cache_freelist::allocate  
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
  
##  <a name="cache_freelist"></a> cache_freelist::cache_freelist  
 Konstruiert ein Objekt vom Typ `cache_freelist`.  
  
```
cache_freelist();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="deallocate"></a> cache_freelist::deallocate  
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



