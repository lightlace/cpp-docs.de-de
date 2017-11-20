---
title: CDefaultHashTraits Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDefaultHashTraits
- ATLCOLL/ATL::CDefaultHashTraits
- ATLCOLL/ATL::CDefaultHashTraits::Hash
dev_langs: C++
helpviewer_keywords: CDefaultHashTraits class
ms.assetid: d8ec4b37-6d58-447b-a0c1-8580c5b1ab85
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 383cdc49f9ac78447186a677bc712287b71b3994
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="cdefaulthashtraits-class"></a>CDefaultHashTraits-Klasse
Diese Klasse stellt eine statische Funktion zum Berechnen von Hashwerten bereit.  
  
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
|[CDefaultHashTraits::Hash](#hash)|(Statisch) Mit dieser Funktion können einen Hashwert für ein angegebenes Element zu berechnen.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse enthält eine einzelne statische Funktion, die einen Hashwert für ein angegebenes Element zurückgibt. Diese Klasse wird verwendet, durch die [CDefaultElementTraits Klasse](../../atl/reference/cdefaultelementtraits-class.md).  
  
 Weitere Informationen finden Sie unter [ATL-Auflistungsklassen](../../atl/atl-collection-classes.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcoll.h  
  
##  <a name="hash"></a>CDefaultHashTraits::Hash  
 Mit dieser Funktion können einen Hashwert für ein angegebenes Element zu berechnen.  
  
```
static ULONG Hash(const T& element) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `element`  
 Das Element.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Hashwert zurück.  
  
### <a name="remarks"></a>Hinweise  
 Der Standardhashalgorithmus ist sehr einfach: der Rückgabewert ist die Anzahl der Element. Überschreiben Sie diese Funktion, wenn ein etwas komplizierter Algorithmus erforderlich ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../../atl/atl-class-overview.md)
