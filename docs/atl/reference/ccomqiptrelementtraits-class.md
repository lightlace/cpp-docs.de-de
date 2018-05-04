---
title: CComQIPtrElementTraits Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComQIPtrElementTraits
- ATLCOLL/ATL::CComQIPtrElementTraits
- ATLCOLL/ATL::CComQIPtrElementTraits::INARGTYPE
dev_langs:
- C++
helpviewer_keywords:
- CComQIPtrElementTraits class
ms.assetid: 9df9250a-5413-4362-b133-332932a597c4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9122431d0d71d33406250a624048dbede46fd387
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ccomqiptrelementtraits-class"></a>CComQIPtrElementTraits-Klasse
Diese Klasse enthält Methoden, statische Funktionen und Typdefinitionen hilfreich beim Erstellen von Sammlungen von COM-Schnittstellenzeiger auf.  
  
## <a name="syntax"></a>Syntax  
  
```
template<typename I, const IID* piid=& __uuidof(I)>  
class CComQIPtrElementTraits : 
   public CDefaultElementTraits<ATL::CComQIPtr<I, piid>>
```  
  
#### <a name="parameters"></a>Parameter  
 `I`  
 Eine COM-Schnittstelle, die Angabe des Typs der Zeiger gespeichert werden soll.  
  
 `piid`  
 Ein Zeiger auf die IID der `I`.  
  
## <a name="members"></a>Member  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComQIPtrElementTraits::INARGTYPE](#inargtype)|Der Datentyp zum Hinzufügen von Elementen auf das Klassenobjekt Auflistung verwendet werden soll.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse Methoden abgeleitet und stellt eine Typedef, die hilfreich beim Erstellen einer Auflistungsklasse der [CComQIPtr](../../atl/reference/ccomqiptr-class.md) com-Zeiger Benutzeroberflächenobjekte. Diese Klasse wird verwendet, sowohl die [CInterfaceArray](../../atl/reference/cinterfacearray-class.md) und [CInterfaceList](../../atl/reference/cinterfacelist-class.md) Klassen.  
  
 Weitere Informationen finden Sie unter [ATL-Auflistungsklassen](../../atl/atl-collection-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)  
  
 [CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)  
  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)  
  
 `CComQIPtrElementTraits`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcoll.h  
  
##  <a name="inargtype"></a>  CComQIPtrElementTraits::INARGTYPE  
 Der Datentyp zum Hinzufügen von Elementen auf das Klassenobjekt Auflistung verwendet werden soll.  
  
```
typedef I* INARGTYPE;
```  
  
## <a name="see-also"></a>Siehe auch  
 [CDefaultElementTraits-Klasse](../../atl/reference/cdefaultelementtraits-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
