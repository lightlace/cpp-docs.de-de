---
title: CCRTAllocator Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
ms.openlocfilehash: 5154a095409705e96dee6f52c67d7c23b0e6691f
ms.lasthandoff: 02/24/2017

---
# <a name="ccrtallocator-class"></a>CCRTAllocator-Klasse
Diese Klasse stellt Methoden zum Verwalten von Speicher mithilfe von CRT-Arbeitsspeicher Routinen.  
  
## <a name="syntax"></a>Syntax  
  
```
class ATL::CCRTAllocator
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Ccrtallocator:: Allocate](#allocate)|(Statisch) Rufen Sie diese Methode, um Speicher zu belegen.|  
|[Ccrtallocator:: Free](#free)|(Statisch) Rufen Sie diese Methode, um Arbeitsspeicher freizugeben.|  
|[CCRTAllocator::Reallocate](#reallocate)|(Statisch) Rufen Sie diese Methode, um Arbeitsspeicher neu zuzuordnen.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse wird verwendet, indem [CHeapPtr](../../atl/reference/cheapptr-class.md) der CRT-Arbeitsspeicher Reservierungsroutinen bereitstellen. Die Klasse Gegenstück [CComAllocator](../../atl/reference/ccomallocator-class.md), bietet die gleichen Methoden, die mit COM-Routinen.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcore.h  
  
##  <a name="allocate"></a>Ccrtallocator:: Allocate  
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
 Belegt Arbeitsspeicher. Finden Sie unter [Malloc](../../c-runtime-library/reference/malloc.md) für weitere Details.  
  
##  <a name="free"></a>Ccrtallocator:: Free  
 Rufen Sie diese statischen Funktion um Arbeitsspeicher freizugeben.  
  
```
static void Free(void* p) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `p`  
 Zeiger auf zugewiesenen Speicher.  
  
### <a name="remarks"></a>Hinweise  
 Gibt den Arbeitsspeicher frei. Finden Sie unter [kostenlose](../../c-runtime-library/reference/free.md) für weitere Details.  
  
##  <a name="reallocate"></a>CCRTAllocator::Reallocate  
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
 Ändert die Größe des belegten Speichers. Finden Sie unter [Realloc](../../c-runtime-library/reference/realloc.md) für weitere Details.  
  
## <a name="see-also"></a>Siehe auch  
 [CHeapPtr-Klasse](../../atl/reference/cheapptr-class.md)   
 [CComAllocator-Klasse](../../atl/reference/ccomallocator-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

