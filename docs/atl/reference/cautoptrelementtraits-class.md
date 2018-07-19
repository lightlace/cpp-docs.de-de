---
title: CAutoPtrElementTraits Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c845243e3b99be10af70042688e672fa867fb888
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32357444"
---
# <a name="cautoptrelementtraits-class"></a>CAutoPtrElementTraits-Klasse
Diese Klasse enthält Methoden, statische Funktionen und Typdefinitionen hilfreich beim Erstellen von Auflistungen von intelligenten Zeigern.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
template<typename T>  
class CAutoPtrElementTraits 
    : public CDefaultElementTraits<ATL::CAutoPtr<T>>
```    
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Zeigertyp.  
  
## <a name="members"></a>Member  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CAutoPtrElementTraits::INARGTYPE](#inargtype)|Der Datentyp zum Hinzufügen von Elementen auf das Klassenobjekt Auflistung verwendet werden soll.|  
|[CAutoPtrElementTraits::OUTARGTYPE](#outargtype)|Der Datentyp zum Abrufen von Elementen aus der Auflistung-Klassenobjekt verwendet werden soll.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse enthält Methoden, statische Funktionen und Typdefinitionen für die Erstellung von Auflistungsobjekten-Klasse mit intelligenten Zeigern Beihilfe. Die Klassen [CAutoPtrArray](../../atl/reference/cautoptrarray-class.md) und [CAutoPtrList](../../atl/reference/cautoptrlist-class.md) abgeleitet `CAutoPtrElementTraits`. Wenn beim Erstellen einer Auflistung von intelligenten Zeigern, der neue Vektor und Delete-Operatoren erfordert, verwenden [CAutoVectorPtrElementTraits](../../atl/reference/cautovectorptrelementtraits-class.md) stattdessen.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)  
  
 [CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)  
  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)  
  
 `CAutoPtrElementTraits`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcoll.h  
  
##  <a name="inargtype"></a>  CAutoPtrElementTraits::INARGTYPE  
 Der Datentyp zum Hinzufügen von Elementen auf das Klassenobjekt Auflistung verwendet werden soll.  
  
```
typedef CAutoPtr<T>& INARGTYPE;
```  
  
##  <a name="outargtype"></a>  CAutoPtrElementTraits::OUTARGTYPE  
 Der Datentyp zum Abrufen von Elementen aus der Auflistung-Klassenobjekt verwendet werden soll.  
  
```
typedef T *& OUTARGTYPE;
```  
  
## <a name="see-also"></a>Siehe auch  
 [CDefaultElementTraits-Klasse](../../atl/reference/cdefaultelementtraits-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
