---
title: Klasse CHeapPtrElementTraits | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CHeapPtrElementTraits
- ATLCOLL/ATL::CHeapPtrElementTraits
- ATLCOLL/ATL::CHeapPtrElementTraits::INARGTYPE
- ATLCOLL/ATL::CHeapPtrElementTraits::OUTARGTYPE
dev_langs:
- C++
helpviewer_keywords:
- CHeapPtrElementTraits class
ms.assetid: 910e0e06-3c8b-4242-bf00-b57eb74fbc77
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: cf442a47a8f7f56a9563b73d03224165248232d5
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cheapptrelementtraits-class"></a>CHeapPtrElementTraits-Klasse
Diese Klasse enthält Methoden, statische Funktionen und Typdefinitionen hilfreich zum Erstellen von Sammlungen des Heap-Zeiger.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template<typename T, class Allocator = ATL::CCRTAllocator>  
class CHeapPtrElementTraits : 
   public CDefaultElementTraits<ATL::CHeapPtr<T, Allocator>>
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Objekttyp in der Auflistungsklasse gespeichert werden.  
  
 `Allocator`  
 Die Speicher-Allocation-Klasse verwenden. Der Standardwert ist [CCRTAllocator](../../atl/reference/ccrtallocator-class.md).  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CHeapPtrElementTraits::INARGTYPE](#inargtype)|Der Datentyp für das Klassenobjekt Auflistung Elemente hinzugefügt.|  
|[CHeapPtrElementTraits::OUTARGTYPE](#outargtype)|Der Datentyp für das Abrufen von Elementen aus der-Auflistung-Klasse.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse enthält Methoden, statische Funktionen und Typdefinitionen für dadurch, dass die Erstellung von Auflistungsobjekten-Klasse, die Heap-Zeiger. Die Klasse `CHeapPtrList` leitet sich von `CHeapPtrElementTraits`.  
  
 Weitere Informationen finden Sie unter [ATL-Auflistungsklassen](../../atl/atl-collection-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)  
  
 [CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)  
  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)  
  
 `CHeapPtrElementTraits`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcoll.h  
  
##  <a name="inargtype"></a>CHeapPtrElementTraits::INARGTYPE  
 Der Datentyp für das Klassenobjekt Auflistung Elemente hinzugefügt.  
  
```
typedef CHeapPtr<T, Allocator>& INARGTYPE;
```  
  
##  <a name="outargtype"></a>CHeapPtrElementTraits::OUTARGTYPE  
 Der Datentyp für das Abrufen von Elementen aus der-Auflistung-Klasse.  
  
```
typedef T *& OUTARGTYPE;
```  
  
## <a name="see-also"></a>Siehe auch  
 [CDefaultElementTraits-Klasse](../../atl/reference/cdefaultelementtraits-class.md)   
 [CComHeapPtr-Klasse](../../atl/reference/ccomheapptr-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

