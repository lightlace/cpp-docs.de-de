---
title: Klasse CComAllocator | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CComAllocator
- ATL::CComAllocator
- CComAllocator
dev_langs:
- C++
helpviewer_keywords:
- CComAllocator class
ms.assetid: 0cd706fd-0c7b-42d3-9054-febe2966fc8e
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
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
translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: d395d347e81b24462a41de5ae3b9d8791d7f82fd
ms.lasthandoff: 02/24/2017

---
# <a name="ccomallocator-class"></a>CComAllocator-Klasse
Diese Klasse stellt Methoden zum Verwalten von Speicher mithilfe von COM-Arbeitsspeicher Routinen.  
  
## <a name="syntax"></a>Syntax  
  
```
class CComAllocator
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComAllocator::Allocate](#allocate)|Rufen Sie diese statische Methode, um Speicher zu belegen.|  
|[CComAllocator::Free](#free)|Rufen Sie diese statische Methode, um den belegten Speicher freizugeben.|  
|[CComAllocator::Reallocate](#reallocate)|Rufen Sie diese statische Methode, um Arbeitsspeicher neu zuzuordnen.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse wird verwendet, indem [CComHeapPtr](../../atl/reference/ccomheapptr-class.md) der COM-Arbeitsspeicher Reservierungsroutinen bereitstellen. Die Klasse Gegenstück [CCRTAllocator](../../atl/reference/ccrtallocator-class.md), bietet die gleichen Methoden mithilfe der CRT-Routinen.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  
  
##  <a name="a-nameallocatea--ccomallocatorallocate"></a><a name="allocate"></a>CComAllocator::Allocate  
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
 Belegt Arbeitsspeicher. Finden Sie unter [CoTaskMemAlloc](http://msdn.microsoft.com/library/windows/desktop/ms692727) für weitere Details.  
  
##  <a name="a-namefreea--ccomallocatorfree"></a><a name="free"></a>CComAllocator::Free  
 Rufen Sie diese statischen Funktion um belegten Speicher freizugeben.  
  
```
static void Free(void* p) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `p`  
 Zeiger auf zugewiesenen Speicher.  
  
### <a name="remarks"></a>Hinweise  
 Gibt den Arbeitsspeicher frei. Finden Sie unter [CoTaskMemFree](http://msdn.microsoft.com/library/windows/desktop/ms680722) für weitere Details.  
  
##  <a name="a-namereallocatea--ccomallocatorreallocate"></a><a name="reallocate"></a>CComAllocator::Reallocate  
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
 Ändert die Größe des belegten Speichers. Finden Sie unter [CoTaskMemRealloc](http://msdn.microsoft.com/library/windows/desktop/ms687280) für weitere Details.  
  
## <a name="see-also"></a>Siehe auch  
 [CComHeapPtr-Klasse](../../atl/reference/ccomheapptr-class.md)   
 [CCRTAllocator-Klasse](../../atl/reference/ccrtallocator-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

