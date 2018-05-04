---
title: CCRTAllocator-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CCRTAllocator
- ATLCORE/ATL::CCRTAllocator
- ATLCORE/ATL::CCRTAllocator::Allocate
- ATLCORE/ATL::CCRTAllocator::Free
- ATLCORE/ATL::CCRTAllocator::Reallocate
dev_langs:
- C++
helpviewer_keywords:
- CCRTAllocator class
ms.assetid: 3e1b8cb0-859a-41ab-8e93-6f0b5ceca49d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2f92ae3f4041b143a8cc4d58b1060c7d5b9a7bb4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ccrtallocator-class"></a>CCRTAllocator-Klasse
Diese Klasse stellt Methoden zum Verwalten des Arbeitsspeichers, die mit der CRT-Speicher-Routinen bereit.  
  
## <a name="syntax"></a>Syntax  
  
```
class ATL::CCRTAllocator
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Ccrtallocator:: Allocate](#allocate)|(Statisch) Rufen Sie diese Methode, um Arbeitsspeicher belegt werden.|  
|[Ccrtallocator:: Free](#free)|(Statisch) Rufen Sie diese Methode, um Arbeitsspeicher freizugeben.|  
|[Ccrtallocator:: Allocate](#reallocate)|(Statisch) Rufen Sie diese Methode, um Arbeitsspeicher neu zuzuordnen.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse wird verwendet, indem [CHeapPtr](../../atl/reference/cheapptr-class.md) der CRT-Arbeitsspeicher Reservierungsroutinen bereitstellen kann. Die Klasse Gegenstück [CComAllocator](../../atl/reference/ccomallocator-class.md), bietet die gleichen Methoden, die mit COM-Routinen.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcore.h  
  
##  <a name="allocate"></a>  Ccrtallocator:: Allocate  
 Rufen Sie diese statische Funktion auf, um Arbeitsspeicher zu belegen.  
  
```
static __declspec(allocator) void* Allocate(size_t nBytes) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nBytes`  
 Die Anzahl der zu belegenden Bytes.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen void-Zeiger auf den belegten Speicherplatz oder NULL zurück, wenn nicht genügend Speicher verfügbar ist.  
  
### <a name="remarks"></a>Hinweise  
 Belegt Arbeitsspeicher. Finden Sie unter ["malloc"](../../c-runtime-library/reference/malloc.md) Weitere Details.  
  
##  <a name="free"></a>  Ccrtallocator:: Free  
 Rufen Sie diese statischen Funktion um Arbeitsspeicher freizugeben.  
  
```
static void Free(void* p) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `p`  
 Zeiger auf zugewiesenen Speicher.  
  
### <a name="remarks"></a>Hinweise  
 Gibt den belegten Arbeitsspeicher frei. Finden Sie unter [freien](../../c-runtime-library/reference/free.md) Weitere Details.  
  
##  <a name="reallocate"></a>  Ccrtallocator:: Allocate  
 Rufen Sie diese statischen Funktion auf, um Arbeitsspeicher neu zuzuordnen.  
  
```
static __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `p`  
 Zeiger auf zugewiesenen Speicher.  
  
 `nBytes`  
 Die Anzahl der zuzuordnenden Bytes.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen void-Zeiger auf den zugeordneten Speicherplatz oder NULL zurück, wenn nicht genügend Speicher verfügbar ist.  
  
### <a name="remarks"></a>Hinweise  
 Ändert die Größe des belegten Speichers. Finden Sie unter [Realloc](../../c-runtime-library/reference/realloc.md) Weitere Details.  
  
## <a name="see-also"></a>Siehe auch  
 [CHeapPtr-Klasse](../../atl/reference/cheapptr-class.md)   
 [CComAllocator-Klasse](../../atl/reference/ccomallocator-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
