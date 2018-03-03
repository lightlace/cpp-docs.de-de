---
title: CHeapPtr Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CHeapPtr
- ATLCORE/ATL::CHeapPtr
- ATLCORE/ATL::CHeapPtr::CHeapPtr
- ATLCORE/ATL::CHeapPtr::Allocate
- ATLCORE/ATL::CHeapPtr::Reallocate
dev_langs:
- C++
helpviewer_keywords:
- CHeapPtr class
ms.assetid: e5c5bfd4-9bf1-4164-8a83-8155fe253454
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 47fe8c0d7475c67228fd7335b1aa167ced237202
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cheapptr-class"></a>CHeapPtr-Klasse
Ein intelligenter Zeiger-Klasse zum Verwalten von Heaps Zeiger.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template<typename T, class Allocator=CCRTAllocator>  
class CHeapPtr : public CHeapPtrBase<T, Allocator>
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Objekttyp, auf dem Heap gespeichert werden.  
  
 `Allocator`  
 Die Arbeitsspeicher-Allocation-Klasse, verwendet.  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CHeapPtr::CHeapPtr](#cheapptr)|Der Konstruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CHeapPtr::Allocate](#allocate)|Rufen Sie diese Methode, um auf dem Heap zum Speichern von Objekten belegt werden.|  
|[CHeapPtr::Reallocate](#reallocate)|Rufen Sie diese Methode, um den Arbeitsspeicher auf dem Heap neu zuzuordnen.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CHeapPtr::operator =](#operator_eq)|Der Zuweisungsoperator.|  
  
## <a name="remarks"></a>Hinweise  
 `CHeapPtr`stammt aus [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md) und verwendet Sie standardmäßig die CRT-Routinen (in [CCRTAllocator](../../atl/reference/ccrtallocator-class.md)) zu reservieren und Freigeben von Arbeitsspeicher. Die Klasse [CHeapPtrList](../../atl/reference/cheapptrlist-class.md) kann verwendet werden, um eine Liste von Zeigern Heap erstellen. Siehe auch [CComHeapPtr](../../atl/reference/ccomheapptr-class.md), die Arbeitsspeicher-Reservierungsroutinen COM verwendet.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)  
  
 `CHeapPtr`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcore.h  
  
##  <a name="allocate"></a>CHeapPtr::Allocate  
 Rufen Sie diese Methode, um auf dem Heap zum Speichern von Objekten belegt werden.  
  
```
bool Allocate(size_t nElements = 1) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nElements`  
 Die Anzahl von Elementen verwendet, um die Menge an Arbeitsspeicher zum Zuordnen zu berechnen. Der Standardwert ist 1.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" zurück, wenn der Speicher wurde erfolgreich zugeordnet und "false" bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Die Allocator-Routinen dienen zum Reservieren ausreichend Arbeitsspeicher auf dem Heap zum Speichern von *nElement* Objekte eines Typs, die im Konstruktor definiert.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#77](../../atl/codesnippet/cpp/cheapptr-class_1.cpp)]  
  
##  <a name="cheapptr"></a>CHeapPtr::CHeapPtr  
 Der Konstruktor.  
  
```
CHeapPtr() throw();
explicit CHeapPtr(T* p) throw();
CHeapPtr(CHeapPtr<T, Allocator>& p) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `p`  
 Einem vorhandenen Heapzeiger oder `CHeapPtr`.  
  
### <a name="remarks"></a>Hinweise  
 Der Heapzeiger kann optional mit einem vorhandenen Zeiger erstellt werden oder ein `CHeapPtr` Objekt. Wenn dies der Fall ist, die neue `CHeapPtr` Objekt übernimmt die Verantwortung für die Verwaltung der neue Zeiger und der Ressourcen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#78](../../atl/codesnippet/cpp/cheapptr-class_2.cpp)]  
  
##  <a name="operator_eq"></a>CHeapPtr::operator =  
 Zuweisungsoperator.  
  
```
CHeapPtr<T, Allocator>& operator=(
    CHeapPtr<T, Allocator>& p) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `p`  
 Ein vorhandenes `CHeapPtr`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Verweis auf die aktualisierte `CHeapPtr`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#80](../../atl/codesnippet/cpp/cheapptr-class_3.cpp)]  
  
##  <a name="reallocate"></a>CHeapPtr::Reallocate  
 Rufen Sie diese Methode, um den Arbeitsspeicher auf dem Heap neu zuzuordnen.  
  
```
bool Reallocate(size_t nElements) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nElements`  
 Die neue Anzahl von Elementen verwendet, um die Menge an Arbeitsspeicher zum Zuordnen zu berechnen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" zurück, wenn der Speicher wurde erfolgreich zugeordnet und "false" bei einem Fehler.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#79](../../atl/codesnippet/cpp/cheapptr-class_4.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [CHeapPtrBase-Klasse](../../atl/reference/cheapptrbase-class.md)   
 [CCRTAllocator-Klasse](../../atl/reference/ccrtallocator-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
