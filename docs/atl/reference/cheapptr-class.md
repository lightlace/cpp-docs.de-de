---
title: Klasse CHeapPtr | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
caps.latest.revision: 20
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 41334cd7497c9e21d1cf047d7ab304864f663758
ms.lasthandoff: 02/24/2017

---
# <a name="cheapptr-class"></a>CHeapPtr-Klasse
Ein intelligenter Zeiger-Klasse für die Verwaltung von Heap Zeiger.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template<typename T, class Allocator=CCRTAllocator>  
class CHeapPtr : public CHeapPtrBase<T, Allocator>
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Objekttyp, auf dem Heap gespeichert werden.  
  
 `Allocator`  
 Die Speicher-Allocation-Klasse verwenden.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CHeapPtr::CHeapPtr](#cheapptr)|Der Konstruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CHeapPtr::Allocate](#allocate)|Rufen Sie diese Methode zum Belegen des Arbeitsspeichers auf dem Heap, Objekte zu speichern.|  
|[CHeapPtr::Reallocate](#reallocate)|Rufen Sie diese Methode, um den Arbeitsspeicher auf dem Heap neu zuordnen.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CHeapPtr::operator =](#operator_eq)|Der Zuweisungsoperator.|  
  
## <a name="remarks"></a>Hinweise  
 `CHeapPtr`stammt von [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md) und verwendet Sie standardmäßig die CRT-Routinen (in [CCRTAllocator](../../atl/reference/ccrtallocator-class.md)) zum Zuordnen und Freigeben von Arbeitsspeicher. Die Klasse [CHeapPtrList](../../atl/reference/cheapptrlist-class.md) kann verwendet werden, um eine Liste von zu erstellen. Siehe auch [CComHeapPtr](../../atl/reference/ccomheapptr-class.md), die COM-Arbeitsspeicher Reservierungsroutinen verwendet.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)  
  
 `CHeapPtr`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcore.h  
  
##  <a name="allocate"></a>CHeapPtr::Allocate  
 Rufen Sie diese Methode zum Belegen des Arbeitsspeichers auf dem Heap, Objekte zu speichern.  
  
```
bool Allocate(size_t nElements = 1) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nElements`  
 Die Anzahl der Elemente verwendet, um die Menge des zu belegenden Speichers zu berechnen. Der Standardwert ist 1.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt True zurück, wenn der Arbeitsspeicher wurde erfolgreich zugewiesen, bei einem Fehler False.  
  
### <a name="remarks"></a>Hinweise  
 Die Zuweisung Routinen werden verwendet, um genügend Arbeitsspeicher auf dem Heap speichern reservieren *nElement* Objekte eines Typs, der im Konstruktor definiert.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&#77;](../../atl/codesnippet/cpp/cheapptr-class_1.cpp)]  
  
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
 Der Heapzeiger kann optional mit einem vorhandenen Zeiger, erstellt werden oder ein `CHeapPtr` Objekt. Wenn dies der Fall ist, die neue `CHeapPtr` Objekt übernimmt die Verantwortung für die Verwaltung der neue Zeiger und Ressourcen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&#78;](../../atl/codesnippet/cpp/cheapptr-class_2.cpp)]  
  
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
 [!code-cpp[NVC_ATL_Utilities&#80;](../../atl/codesnippet/cpp/cheapptr-class_3.cpp)]  
  
##  <a name="reallocate"></a>CHeapPtr::Reallocate  
 Rufen Sie diese Methode, um den Arbeitsspeicher auf dem Heap neu zuordnen.  
  
```
bool Reallocate(size_t nElements) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nElements`  
 Die neue Anzahl der Elemente, die die Menge des zu belegenden Speichers berechnet.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt True zurück, wenn der Arbeitsspeicher wurde erfolgreich zugewiesen, bei einem Fehler False.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities&#79;](../../atl/codesnippet/cpp/cheapptr-class_4.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [CHeapPtrBase-Klasse](../../atl/reference/cheapptrbase-class.md)   
 [CCRTAllocator-Klasse](../../atl/reference/ccrtallocator-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

