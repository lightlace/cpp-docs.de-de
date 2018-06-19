---
title: CSimpleMapEqualHelperFalse Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CSimpleMapEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse::IsEqualKey
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse::IsEqualValue
dev_langs:
- C++
helpviewer_keywords:
- CSimpleMapEqualHelperFalse class
ms.assetid: a873eea3-e130-45cc-a476-61ee79511c3b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bebd9c6628924b5927fb48518925bdd665b0ee14
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32360017"
---
# <a name="csimplemapequalhelperfalse-class"></a>CSimpleMapEqualHelperFalse-Klasse
Diese Klasse ist ein Hilfsprogramm für die [CSimpleMap](../../atl/reference/csimplemap-class.md) Klasse.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class TKey, class TVal>  
class CSimpleMapEqualHelperFalse
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSimpleMapEqualHelperFalse::IsEqualKey](#isequalkey)|(Statisch) Testet zwei Schlüsseln auf Gleichheit.|  
|[CSimpleMapEqualHelperFalse::IsEqualValue](#isequalvalue)|(Statisch) Gibt "false".|  
  
## <a name="remarks"></a>Hinweise  
 Diese Merkmalklasse ist eine Ergänzung zur der `CSimpleMap` Klasse. Es bietet eine Methode zum Vergleichen von zwei Elemente in der `CSimpleMap` Objekts, insbesondere zwei Wertelemente oder zwei wichtige Elemente.  
  
 Der Wertevergleich immer "false" zurückgeben, und darüber hinaus ruft `ATLASSERT` mit dem Argument "false", wenn es jemals verwiesen wird. In Situationen, in dem der Gleichheitstest auf ist nicht ausreichend definiert, diese Klasse ermöglicht es eine Karte mit Schlüssel-Wert-Paaren für die meisten Methoden ordnungsgemäß ausgeführt werden, jedoch in einer klar definierten Weise für Methoden, die für Vergleiche, wie z. B. abhängen fehl [CSimpleMap:: FindVal](../../atl/reference/csimplemap-class.md#findval).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlsimpcoll.h  
  
##  <a name="isequalkey"></a>  CSimpleMapEqualHelperFalse::IsEqualKey  
 Testet zwei Schlüsseln auf Gleichheit.  
  
```
static bool IsEqualKey(const TKey& k1, const TKey& k2);
```  
  
### <a name="parameters"></a>Parameter  
 `k1`  
 Der erste Schlüssel.  
  
 `k2`  
 Der zweite Schlüssel.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" zurück, wenn die Schlüssel gleich "false", andernfalls sind.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft [CSimpleArrayEqualHelper](../../atl/reference/csimplearrayequalhelper-class.md).  
  
##  <a name="isequalvalue"></a>  CSimpleMapEqualHelperFalse::IsEqualValue  
 Gibt false zurück.  
  
```
static bool IsEqualValue(const TVal&, const TVal&);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt false zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode immer "false" zurückgegeben, und rufen `ATLASSERT` mit dem Argument "false", wenn es jemals verwiesen wird. Der Zweck der `CSimpleMapEqualHelperFalse::IsEqualValue` wird gezwungen Methoden mit, dass Vergleiche in einer klar definierten Weise fehl, wenn Gleichheitstests nicht adäquat definiert wurden.  
  
## <a name="see-also"></a>Siehe auch  
 [CSimpleMapEqualHelper-Klasse](../../atl/reference/csimplemapequalhelper-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
