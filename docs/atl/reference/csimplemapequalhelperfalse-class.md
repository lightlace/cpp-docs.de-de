---
title: Klasse CSimpleMapEqualHelperFalse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CSimpleMapEqualHelperFalse
- CSimpleMapEqualHelperFalse
- ATL.CSimpleMapEqualHelperFalse
dev_langs:
- C++
helpviewer_keywords:
- CSimpleMapEqualHelperFalse class
ms.assetid: a873eea3-e130-45cc-a476-61ee79511c3b
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 68a08ffc0ba126c523a779e3d1a72217dead6235
ms.lasthandoff: 02/24/2017

---
# <a name="csimplemapequalhelperfalse-class"></a>CSimpleMapEqualHelperFalse-Klasse
Diese Klasse ist eine Hilfsklasse für die [CSimpleMap](../../atl/reference/csimplemap-class.md) Klasse.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class TKey, class TVal>  
class CSimpleMapEqualHelperFalse
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSimpleMapEqualHelperFalse::IsEqualKey](#isequalkey)|(Statisch) Testet zwei Schlüssel auf Gleichheit.|  
|[CSimpleMapEqualHelperFalse::IsEqualValue](#isequalvalue)|(Statisch) Gibt False zurück.|  
  
## <a name="remarks"></a>Hinweise  
 Diese "traits"-Klasse ist eine Ergänzung zu den `CSimpleMap` Klasse. Eine Methode zum Vergleichen von zwei Elemente in der `CSimpleMap` -Objekt, insbesondere zwei Elemente mit dem Wert oder zwei Hauptelemente.  
  
 Der Wertevergleich gibt immer false zurück und darüber hinaus ruft `ATLASSERT` mit dem Argument False, wenn es jemals verwiesen wird. In Situationen, in denen der Gleichheitstest auf ist nicht ausreichend definiert, mit dieser Klasse können Sie eine Karte mit Schlüssel-Wert-Paare, um eine klar definierte Weise für Methoden, die für Vergleiche, wie z. B. abhängen tritt jedoch ordnungsgemäß für die meisten Methoden [CSimpleMap::FindVal](../../atl/reference/csimplemap-class.md#findval).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlsimpcoll.h  
  
##  <a name="a-nameisequalkeya--csimplemapequalhelperfalseisequalkey"></a><a name="isequalkey"></a>CSimpleMapEqualHelperFalse::IsEqualKey  
 Testet zwei Schlüssel auf Gleichheit.  
  
```
static bool IsEqualKey(const TKey& k1, const TKey& k2);
```  
  
### <a name="parameters"></a>Parameter  
 `k1`  
 Der erste Schlüssel.  
  
 `k2`  
 Der zweite Schlüssel.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt True zurück, wenn die Schlüssel gleich sind.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft [CSimpleArrayEqualHelper](../../atl/reference/csimplearrayequalhelper-class.md).  
  
##  <a name="a-nameisequalvaluea--csimplemapequalhelperfalseisequalvalue"></a><a name="isequalvalue"></a>CSimpleMapEqualHelperFalse::IsEqualValue  
 Gibt false zurück.  
  
```
static bool IsEqualValue(const TVal&, const TVal&);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt false zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode immer "false" zurückgibt und ruft `ATLASSERT` mit dem Argument False, wenn es jemals verwiesen wird. Der Zweck der `CSimpleMapEqualHelperFalse::IsEqualValue` besteht darin, erzwingen Methoden mit Vergleiche in einer klar definierten Weise fehlschlägt, wenn Tests auf Gleichheit nicht angemessen definiert wurden.  
  
## <a name="see-also"></a>Siehe auch  
 [CSimpleMapEqualHelper-Klasse](../../atl/reference/csimplemapequalhelper-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

