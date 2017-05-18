---
title: Klasse CComQIPtrElementTraits | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: d6405cc3ec04988d0e0d7dd9a98f22c271b3608d
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="ccomqiptrelementtraits-class"></a>CComQIPtrElementTraits-Klasse
Diese Klasse enthält Methoden, statische Funktionen und Typdefinitionen hilfreich zum Erstellen von Sammlungen von COM-Schnittstellenzeigern.  
  
## <a name="syntax"></a>Syntax  
  
```
template<typename I, const IID* piid=& __uuidof(I)>  
class CComQIPtrElementTraits : 
   public CDefaultElementTraits<ATL::CComQIPtr<I, piid>>
```  
  
#### <a name="parameters"></a>Parameter  
 `I`  
 Eine COM-Schnittstelle, die den Typ des Zeigers gespeichert werden.  
  
 `piid`  
 Ein Zeiger auf die ID der `I`.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComQIPtrElementTraits::INARGTYPE](#inargtype)|Der Datentyp für das Klassenobjekt Auflistung Elemente hinzugefügt.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse Methoden abgeleitet und bietet eine Typedef, die hilfreich beim Erstellen einer Auflistungsklasse von [CComQIPtr](../../atl/reference/ccomqiptr-class.md) COM-Schnittstelle Zeiger Objekte. Diese Klasse wird verwendet, sowohl die [CInterfaceArray](../../atl/reference/cinterfacearray-class.md) und [CInterfaceList](../../atl/reference/cinterfacelist-class.md) Klassen.  
  
 Weitere Informationen finden Sie unter [ATL-Auflistungsklassen](../../atl/atl-collection-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)  
  
 [CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)  
  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)  
  
 `CComQIPtrElementTraits`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcoll.h  
  
##  <a name="inargtype"></a>CComQIPtrElementTraits::INARGTYPE  
 Der Datentyp für das Klassenobjekt Auflistung Elemente hinzugefügt.  
  
```
typedef I* INARGTYPE;
```  
  
## <a name="see-also"></a>Siehe auch  
 [CDefaultElementTraits-Klasse](../../atl/reference/cdefaultelementtraits-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

