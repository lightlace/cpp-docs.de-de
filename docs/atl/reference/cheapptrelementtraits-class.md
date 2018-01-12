---
title: CHeapPtrElementTraits Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CHeapPtrElementTraits
- ATLCOLL/ATL::CHeapPtrElementTraits
- ATLCOLL/ATL::CHeapPtrElementTraits::INARGTYPE
- ATLCOLL/ATL::CHeapPtrElementTraits::OUTARGTYPE
dev_langs: C++
helpviewer_keywords: CHeapPtrElementTraits class
ms.assetid: 910e0e06-3c8b-4242-bf00-b57eb74fbc77
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0fb646e6f6d2358018c38439e5bea4c651e9d994
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cheapptrelementtraits-class"></a>CHeapPtrElementTraits-Klasse
Diese Klasse enthält Methoden, statische Funktionen und Typdefinitionen hilfreich beim Erstellen von Sammlungen von Heap Zeigern.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template<typename T, class Allocator = ATL::CCRTAllocator>  
class CHeapPtrElementTraits : 
   public CDefaultElementTraits<ATL::CHeapPtr<T, Allocator>>
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Objekttyp in die Auflistungsklasse gespeichert werden.  
  
 `Allocator`  
 Die Arbeitsspeicher-Allocation-Klasse, verwendet. Die Standardeinstellung ist [CCRTAllocator](../../atl/reference/ccrtallocator-class.md).  
  
## <a name="members"></a>Member  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CHeapPtrElementTraits::INARGTYPE](#inargtype)|Der Datentyp zum Hinzufügen von Elementen auf das Klassenobjekt Auflistung verwendet werden soll.|  
|[CHeapPtrElementTraits::OUTARGTYPE](#outargtype)|Der Datentyp zum Abrufen von Elementen aus der Auflistung-Klassenobjekt verwendet werden soll.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse enthält Methoden, statische Funktionen und Typdefinitionen für die Erstellung von Auflistungsobjekten-Klasse mit Zeigern Heap Beihilfe. Die Klasse `CHeapPtrList` leitet sich von `CHeapPtrElementTraits`.  
  
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
 Der Datentyp zum Hinzufügen von Elementen auf das Klassenobjekt Auflistung verwendet werden soll.  
  
```
typedef CHeapPtr<T, Allocator>& INARGTYPE;
```  
  
##  <a name="outargtype"></a>CHeapPtrElementTraits::OUTARGTYPE  
 Der Datentyp zum Abrufen von Elementen aus der Auflistung-Klassenobjekt verwendet werden soll.  
  
```
typedef T *& OUTARGTYPE;
```  
  
## <a name="see-also"></a>Siehe auch  
 [CDefaultElementTraits-Klasse](../../atl/reference/cdefaultelementtraits-class.md)   
 [CComHeapPtr-Klasse](../../atl/reference/ccomheapptr-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
