---
title: Klasse CDefaultHashTraits | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDefaultHashTraits
- ATLCOLL/ATL::CDefaultHashTraits
- ATLCOLL/ATL::CDefaultHashTraits::Hash
dev_langs:
- C++
helpviewer_keywords:
- CDefaultHashTraits class
ms.assetid: d8ec4b37-6d58-447b-a0c1-8580c5b1ab85
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
ms.openlocfilehash: 5191327e5e60935829750c7d1e04ba89fcddc771
ms.lasthandoff: 02/24/2017

---
# <a name="cdefaulthashtraits-class"></a>CDefaultHashTraits-Klasse
Diese Klasse stellt eine statische Funktion zur Berechnung der Hashwerte.  
  
## <a name="syntax"></a>Syntax  
  
```
template<typename T>  
class CDefaultHashTraits
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Typ der Daten in der Auflistung gespeichert werden.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDefaultHashTraits::Hash](#hash)|(Statisch) Rufen Sie diese Funktion, um einen Hashwert für ein bestimmtes Element zu berechnen.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse enthält eine einzelne statische Funktion, die einen Hashwert für ein bestimmtes Element zurückgibt. Diese Klasse wird verwendet, indem die [CDefaultElementTraits Klasse](../../atl/reference/cdefaultelementtraits-class.md).  
  
 Weitere Informationen finden Sie unter [ATL-Auflistungsklassen](../../atl/atl-collection-classes.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcoll.h  
  
##  <a name="hash"></a>CDefaultHashTraits::Hash  
 Rufen Sie diese Funktion, um einen Hashwert für ein bestimmtes Element zu berechnen.  
  
```
static ULONG Hash(const T& element) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `element`  
 Das Element.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Hashwert zurück.  
  
### <a name="remarks"></a>Hinweise  
 Der Standardhashalgorithmus ist sehr einfach: der Rückgabewert ist die Anzahl der Element. Überschreiben Sie diese Funktion, wenn ein komplizierter Algorithmus erforderlich ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

