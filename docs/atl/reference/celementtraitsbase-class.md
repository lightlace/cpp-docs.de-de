---
title: CElementTraitsBase Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CElementTraitsBase
- ATLCOLL/ATL::CElementTraitsBase
- ATLCOLL/ATL::CElementTraitsBase::INARGTYPE
- ATLCOLL/ATL::CElementTraitsBase::OUTARGTYPE
- ATLCOLL/ATL::CElementTraitsBase::CopyElements
- ATLCOLL/ATL::CElementTraitsBase::RelocateElements
dev_langs: C++
helpviewer_keywords: CElementTraitsBase class
ms.assetid: 75284caf-347e-4355-a7d8-efc708dd514a
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c9bbea69d2265563a0da4fda8b45cc09234a7789
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="celementtraitsbase-class"></a>CElementTraitsBase-Klasse
Diese Klasse bietet standardmäßig kopieren und Verschieben von Methoden für eine Auflistungsklasse.  
  
## <a name="syntax"></a>Syntax  
  
```
template<typename T>  
class CElementTraitsBase
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Typ der Daten in der Auflistung gespeichert werden.  
  
## <a name="members"></a>Member  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CElementTraitsBase::INARGTYPE](#inargtype)|Der Datentyp zum Hinzufügen von Elementen auf das Klassenobjekt Auflistung verwendet werden soll.|  
|[CElementTraitsBase::OUTARGTYPE](#outargtype)|Der Datentyp zum Abrufen von Elementen aus der Auflistung-Klassenobjekt verwendet werden soll.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CElementTraitsBase::CopyElements](#copyelements)|Rufen Sie diese Methode, um ein Klassenobjekt Auflistung gespeicherten Elemente kopieren.|  
|[CElementTraitsBase::RelocateElements](#relocateelements)|Rufen Sie diese Methode, um ein Klassenobjekt Auflistung gespeicherten Elemente zu verschieben.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Basisklasse definiert Methoden zum Kopieren und Verschieben von Elementen in einer Auflistungsklasse. Es wird verwendet, durch die Klassen [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md), [CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md), und [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md).  
  
 Weitere Informationen finden Sie unter [ATL-Auflistungsklassen](../../atl/atl-collection-classes.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcoll.h  
  
##  <a name="copyelements"></a>CElementTraitsBase::CopyElements  
 Rufen Sie diese Methode, um ein Klassenobjekt Auflistung gespeicherten Elemente kopieren.  
  
```
static void CopyElements(
    T* pDest,
    const T* pSrc,
    size_t nElements);
```  
  
### <a name="parameters"></a>Parameter  
 `pDest`  
 Zeiger auf das erste Element, das die kopierten Daten erhält.  
  
 `pSrc`  
 Zeiger auf das erste Element zu kopieren.  
  
 `nElements`  
 Die Anzahl der zu kopierenden Elemente.  
  
### <a name="remarks"></a>Hinweise  
 Die Quell- und Zielschemas Elemente sollten sich nicht überschneiden.  
  
##  <a name="inargtype"></a>CElementTraitsBase::INARGTYPE  
 Der Datentyp für Elemente der Auflistung hinzugefügt werden soll.  
  
```
typedef const T& INARGTYPE;
```  
  
##  <a name="outargtype"></a>CElementTraitsBase::OUTARGTYPE  
 Der Datentyp zum Abrufen von Elementen aus der Auflistung verwendet werden soll.  
  
```
typedef T& OUTARGTYPE;
```  
  
##  <a name="relocateelements"></a>CElementTraitsBase::RelocateElements  
 Rufen Sie diese Methode, um ein Klassenobjekt Auflistung gespeicherten Elemente zu verschieben.  
  
```
static void RelocateElements(
    T* pDest,
    T* pSrc,
    size_t nElements);
```  
  
### <a name="parameters"></a>Parameter  
 `pDest`  
 Zeiger auf das erste Element, das die verschobenen Daten erhält.  
  
 `pSrc`  
 Zeiger auf das erste Element zu verschieben.  
  
 `nElements`  
 Die Anzahl der Elemente zu verschieben.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft [Memmove](../../c-runtime-library/reference/memmove-wmemmove.md), dies ist ausreichend für die meisten Datentypen. Wenn die Objekte, die verschobene Zeiger auf ihre eigenen Member enthalten, müssen diese Methode außer Kraft gesetzt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../../atl/atl-class-overview.md)
