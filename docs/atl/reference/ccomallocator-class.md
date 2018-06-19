---
title: CComAllocator Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComAllocator
- ATLBASE/ATL::CComAllocator
- ATLBASE/ATL::CComAllocator::Allocate
- ATLBASE/ATL::CComAllocator::Free
- ATLBASE/ATL::CComAllocator::Reallocate
dev_langs:
- C++
helpviewer_keywords:
- CComAllocator class
ms.assetid: 0cd706fd-0c7b-42d3-9054-febe2966fc8e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3606df325bfd41dabf99bb790ff154b383ab987f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32358276"
---
# <a name="ccomallocator-class"></a>CComAllocator-Klasse
Diese Klasse stellt Methoden zum Verwalten von Speicher mithilfe des COM-Arbeitsspeicher Routinen bereit.  
  
## <a name="syntax"></a>Syntax  
  
```
class CComAllocator
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComAllocator::Allocate](#allocate)|Rufen Sie diese statische Methode, um Arbeitsspeicher zuzuordnen.|  
|[CComAllocator::Free](#free)|Rufen Sie diese statische Methode, um den belegten Arbeitsspeicher freizugeben.|  
|[CComAllocator::Reallocate](#reallocate)|Rufen Sie diese statische Methode, um Arbeitsspeicher neu zuzuordnen.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse wird verwendet, indem [CComHeapPtr](../../atl/reference/ccomheapptr-class.md) der COM-Arbeitsspeicher Reservierungsroutinen bereitstellen kann. Die Klasse Gegenstück [CCRTAllocator](../../atl/reference/ccrtallocator-class.md), bietet die gleichen Methoden, die mit der CRT-Routinen.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
  
##  <a name="allocate"></a>  CComAllocator::Allocate  
 Rufen Sie diese statische Funktion auf, um Arbeitsspeicher zu belegen.  
  
```
static void* Allocate(size_t nBytes) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nBytes`  
 Die Anzahl der zu belegenden Bytes.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen void-Zeiger auf den belegten Speicherplatz oder NULL zurück, wenn nicht genügend Speicher verfügbar ist.  
  
### <a name="remarks"></a>Hinweise  
 Belegt Arbeitsspeicher. Finden Sie unter [CoTaskMemAlloc](http://msdn.microsoft.com/library/windows/desktop/ms692727) Weitere Details.  
  
##  <a name="free"></a>  CComAllocator::Free  
 Rufen Sie diese statischen Funktion um belegten Arbeitsspeicher freizugeben.  
  
```
static void Free(void* p) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `p`  
 Zeiger auf zugewiesenen Speicher.  
  
### <a name="remarks"></a>Hinweise  
 Gibt den belegten Arbeitsspeicher frei. Finden Sie unter [CoTaskMemFree](http://msdn.microsoft.com/library/windows/desktop/ms680722) Weitere Details.  
  
##  <a name="reallocate"></a>  CComAllocator::Reallocate  
 Rufen Sie diese statischen Funktion auf, um Arbeitsspeicher neu zuzuordnen.  
  
```
static void* Reallocate(void* p, size_t nBytes) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `p`  
 Zeiger auf zugewiesenen Speicher.  
  
 `nBytes`  
 Die Anzahl der zuzuordnenden Bytes.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen void-Zeiger auf den zugeordneten Speicherplatz oder NULL zurück, wenn nicht genügend Arbeitsspeicher  
  
### <a name="remarks"></a>Hinweise  
 Ändert die Größe des belegten Speichers. Finden Sie unter [CoTaskMemRealloc](http://msdn.microsoft.com/library/windows/desktop/ms687280) Weitere Details.  
  
## <a name="see-also"></a>Siehe auch  
 [CComHeapPtr-Klasse](../../atl/reference/ccomheapptr-class.md)   
 [CCRTAllocator-Klasse](../../atl/reference/ccrtallocator-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
