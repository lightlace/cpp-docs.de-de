---
title: Klasse CAutoPtrElementTraits | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAutoPtrElementTraits
- ATLCOLL/ATL::CAutoPtrElementTraits
- ATLCOLL/ATL::CAutoPtrElementTraits::INARGTYPE
- ATLCOLL/ATL::CAutoPtrElementTraits::OUTARGTYPE
dev_langs:
- C++
helpviewer_keywords:
- CAutoPtrElementTraits class
ms.assetid: 777c1b14-6ab7-491f-b9a5-be149e71d4a2
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
ms.openlocfilehash: 1c543eaa678d86e083207915bcb4f43766ee23c5
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cautoptrelementtraits-class"></a>CAutoPtrElementTraits-Klasse
Diese Klasse enthält Methoden, statische Funktionen und Typdefinitionen hilfreich beim Erstellen von Auflistungen von intelligenten Zeigern.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template<typename T>  
class CAutoPtrElementTraits 
    : public CDefaultElementTraits<ATL::CAutoPtr<T>>
```    
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Zeigertyp.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAutoPtrElementTraits::INARGTYPE](#inargtype)|Der Datentyp für das Klassenobjekt Auflistung Elemente hinzugefügt.|  
|[CAutoPtrElementTraits::OUTARGTYPE](#outargtype)|Der Datentyp für das Abrufen von Elementen aus der-Auflistung-Klasse.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse enthält Methoden, statische Funktionen und Typdefinitionen für die Erstellung von Auflistungsobjekten-Klasse, die intelligente Zeiger Netzwerkstack. Die Klassen [CAutoPtrArray](../../atl/reference/cautoptrarray-class.md) und [CAutoPtrList](../../atl/reference/cautoptrlist-class.md) ableiten `CAutoPtrElementTraits`. Wenn beim Erstellen einer Auflistung von intelligenten Zeigern, die neue Vektor und Delete-Operatoren erfordert, verwenden [CAutoVectorPtrElementTraits](../../atl/reference/cautovectorptrelementtraits-class.md) stattdessen.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)  
  
 [CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)  
  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)  
  
 `CAutoPtrElementTraits`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcoll.h  
  
##  <a name="inargtype"></a>CAutoPtrElementTraits::INARGTYPE  
 Der Datentyp für das Klassenobjekt Auflistung Elemente hinzugefügt.  
  
```
typedef CAutoPtr<T>& INARGTYPE;
```  
  
##  <a name="outargtype"></a>CAutoPtrElementTraits::OUTARGTYPE  
 Der Datentyp für das Abrufen von Elementen aus der-Auflistung-Klasse.  
  
```
typedef T *& OUTARGTYPE;
```  
  
## <a name="see-also"></a>Siehe auch  
 [CDefaultElementTraits-Klasse](../../atl/reference/cdefaultelementtraits-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

