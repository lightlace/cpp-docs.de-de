---
title: CPrimitiveElementTraits-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CPrimitiveElementTraits
- ATLCOLL/ATL::CPrimitiveElementTraits
- ATLCOLL/ATL::CPrimitiveElementTraits::INARGTYPE
- ATLCOLL/ATL::CPrimitiveElementTraits::OUTARGTYPE
dev_langs:
- C++
helpviewer_keywords:
- CPrimitiveElementTraits class
ms.assetid: 21c1cea8-2c5a-486c-b65c-85490f3ed4e6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2219be699e879afb6ec19ad84acc50f18d93a9a9
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "37885808"
---
# <a name="cprimitiveelementtraits-class"></a>CPrimitiveElementTraits-Klasse
Diese Klasse stellt die Standardmethoden und -Funktionen für eine Auflistungsklasse bestehend aus primitiven Datentypen.  
  
## <a name="syntax"></a>Syntax  
  
```
template <typename T>  
class CPrimitiveElementTraits : public CDefaultElementTraits<T>
```  
  
#### <a name="parameters"></a>Parameter  
 *T*  
 Der Typ der Daten in das Klassenobjekt Auflistung gespeichert werden.  
  
## <a name="members"></a>Member  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPrimitiveElementTraits::INARGTYPE](#inargtype)|Der Datentyp, zum Hinzufügen von Elementen für das Objekt der Sammlung-Klasse verwendet werden soll.|  
|[CPrimitiveElementTraits::OUTARGTYPE](#outargtype)|Der Datentyp für das Abrufen von Elementen aus dem Auflistungsobjekt-Klasse.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse bietet standardmäßig statische Funktionen und Methoden zum Verschieben, kopieren, vergleichen und hashing primitiven Typ Datenelemente in einem Auflistungsobjekt-Klasse gespeichert.  
  
 Weitere Informationen finden Sie unter [ATL-Auflistungsklassen](../../atl/atl-collection-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)  
  
 [CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)  
  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)  
  
 `CPrimitiveElementTraits`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcoll.h  
  
##  <a name="inargtype"></a>  CPrimitiveElementTraits::INARGTYPE  
 Der Datentyp, zum Hinzufügen von Elementen für das Objekt der Sammlung-Klasse verwendet werden soll.  
  
```
typedef T INARGTYPE;
```  
  
##  <a name="outargtype"></a>  CPrimitiveElementTraits::OUTARGTYPE  
 Der Datentyp für das Abrufen von Elementen aus dem Auflistungsobjekt-Klasse.  
  
```
typedef T& OUTARGTYPE;
```  
  
## <a name="see-also"></a>Siehe auch  
 [CDefaultElementTraits-Klasse](../../atl/reference/cdefaultelementtraits-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)
