---
title: Klasse CElementTraitsBase | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CElementTraitsBase
- ATLCOLL/ATL::CElementTraitsBase
- ATLCOLL/ATL::CElementTraitsBase::INARGTYPE
- ATLCOLL/ATL::CElementTraitsBase::OUTARGTYPE
- ATLCOLL/ATL::CElementTraitsBase::CopyElements
- ATLCOLL/ATL::CElementTraitsBase::RelocateElements
dev_langs:
- C++
helpviewer_keywords:
- CElementTraitsBase class
ms.assetid: 75284caf-347e-4355-a7d8-efc708dd514a
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: a06af7698afb24c1c2391b762673c7e3633018d4
ms.lasthandoff: 02/24/2017

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
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CElementTraitsBase::INARGTYPE](#inargtype)|Der Datentyp für das Klassenobjekt Auflistung Elemente hinzugefügt.|  
|[CElementTraitsBase::OUTARGTYPE](#outargtype)|Der Datentyp für das Abrufen von Elementen aus der-Auflistung-Klasse.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CElementTraitsBase::CopyElements](#copyelements)|Rufen Sie diese Methode, um in ein Objekt der Klasse Auflistung gespeicherten Elemente kopieren.|  
|[CElementTraitsBase::RelocateElements](#relocateelements)|Rufen Sie diese Methode, um in ein Objekt der Klasse Auflistung gespeicherten Elemente zu verschieben.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Basisklasse definiert Methoden zum Kopieren und Verschieben von Elementen in einer Auflistungsklasse. Es wird von den Klassen verwendet [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md), [CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md), und [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md).  
  
 Weitere Informationen finden Sie unter [ATL-Auflistungsklassen](../../atl/atl-collection-classes.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcoll.h  
  
##  <a name="copyelements"></a>CElementTraitsBase::CopyElements  
 Rufen Sie diese Methode, um in ein Objekt der Klasse Auflistung gespeicherten Elemente kopieren.  
  
```
static void CopyElements(
    T* pDest,
    const T* pSrc,
    size_t nElements);
```  
  
### <a name="parameters"></a>Parameter  
 `pDest`  
 Ein Zeiger auf das erste Element, das die kopierten Daten empfängt.  
  
 `pSrc`  
 Ein Zeiger auf das erste Element zu kopieren.  
  
 `nElements`  
 Die Anzahl der zu kopierenden Elemente.  
  
### <a name="remarks"></a>Hinweise  
 Die Quelle und Ziel-Elemente sollten sich nicht überschneiden.  
  
##  <a name="inargtype"></a>CElementTraitsBase::INARGTYPE  
 Der Datentyp für Elemente der Auflistung hinzugefügt werden soll.  
  
```
typedef const T& INARGTYPE;
```  
  
##  <a name="outargtype"></a>CElementTraitsBase::OUTARGTYPE  
 Der Datentyp für das Abrufen von Elementen aus der Auflistung.  
  
```
typedef T& OUTARGTYPE;
```  
  
##  <a name="relocateelements"></a>CElementTraitsBase::RelocateElements  
 Rufen Sie diese Methode, um in ein Objekt der Klasse Auflistung gespeicherten Elemente zu verschieben.  
  
```
static void RelocateElements(
    T* pDest,
    T* pSrc,
    size_t nElements);
```  
  
### <a name="parameters"></a>Parameter  
 `pDest`  
 Ein Zeiger auf das erste Element, das die verschobenen Daten empfängt.  
  
 `pSrc`  
 Ein Zeiger auf das erste Element zu verschieben.  
  
 `nElements`  
 Die Anzahl der Elemente, die zu verschieben.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft [Memmove](../../c-runtime-library/reference/memmove-wmemmove.md), dies ist ausreichend für die meisten Datentypen. Die verschobene Objekte, Zeiger auf ihre eigenen Member enthalten, müssen diese Methode außer Kraft gesetzt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

