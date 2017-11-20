---
title: CComAllocator Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComAllocator
- ATLBASE/ATL::CComAllocator
- ATLBASE/ATL::CComAllocator::Allocate
- ATLBASE/ATL::CComAllocator::Free
- ATLBASE/ATL::CComAllocator::Reallocate
dev_langs: C++
helpviewer_keywords: CComAllocator class
ms.assetid: 0cd706fd-0c7b-42d3-9054-febe2966fc8e
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b1ba2b12110e4c312b84b2a24831687e782cc339
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="ccomallocator-class"></a>CComAllocator-Klasse
Diese Klasse stellt Methoden zum Verwalten von Speicher mithilfe des COM-Arbeitsspeicher Routinen bereit.  
  
## <a name="syntax"></a>Syntax  
  
```
class CComAllocator
```  
  
## <a name="members"></a>Mitglieder  
  
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
  
##  <a name="allocate"></a>CComAllocator::Allocate  
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
  
##  <a name="free"></a>CComAllocator::Free  
 Rufen Sie diese statischen Funktion um belegten Arbeitsspeicher freizugeben.  
  
```
static void Free(void* p) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `p`  
 Zeiger auf zugewiesenen Speicher.  
  
### <a name="remarks"></a>Hinweise  
 Gibt den belegten Arbeitsspeicher frei. Finden Sie unter [CoTaskMemFree](http://msdn.microsoft.com/library/windows/desktop/ms680722) Weitere Details.  
  
##  <a name="reallocate"></a>CComAllocator::Reallocate  
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
