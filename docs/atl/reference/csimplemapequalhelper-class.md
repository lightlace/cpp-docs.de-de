---
title: CSimpleMapEqualHelper-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CSimpleMapEqualHelper
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper::IsEqualKey
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper::IsEqualValue
dev_langs:
- C++
helpviewer_keywords:
- CSimpleMapEqualHelper class
ms.assetid: 9bb2968a-d609-405c-8272-ff3b42df6164
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7d629806582d7ad9902ef5ca0d9425d6f1ecd7d7
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "37879693"
---
# <a name="csimplemapequalhelper-class"></a>CSimpleMapEqualHelper-Klasse
Diese Klasse ist eine Hilfsklasse für die [CSimpleMap](../../atl/reference/csimplemap-class.md) Klasse.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class TKey, class TVal>  
class CSimpleMapEqualHelper
```  
  
#### <a name="parameters"></a>Parameter  
 *TKey*  
 Das wichtigste Element.  
  
 *TVal*  
 Das Value-Element.  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSimpleMapEqualHelper::IsEqualKey](#isequalkey)|(Statisch) Testet zwei Schlüsseln auf Gleichheit.|  
|[CSimpleMapEqualHelper::IsEqualValue](#isequalvalue)|(Statisch) Testet zwei Werte hinsichtlich ihrer Gleichheit.|  
  
## <a name="remarks"></a>Hinweise  
 Diese "traits"-Klasse dient zur Ergänzung der `CSimpleMap` Klasse. Es bietet Methoden zum Vergleichen von zwei `CSimpleMap` Objektelemente (insbesondere die Schlüssel-Wert-Komponenten) hinsichtlich ihrer Gleichheit. In der Standardeinstellung die Schlüssel und Werte sind im Vergleich mit **operator==()**, aber wenn die Zuordnung von komplexen Datentypen, die ihre eigenen Equality-Operator hat enthält, kann diese Klasse überschrieben werden, um die zusätzliche erforderliche Funktionalität bereitzustellen.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlsimpcoll.h  
  
##  <a name="isequalkey"></a>  CSimpleMapEqualHelper::IsEqualKey  
 Testet zwei Schlüsseln auf Gleichheit.  
  
```
static bool IsEqualKey(const TKey& k1, const TKey& k2);
```  
  
### <a name="parameters"></a>Parameter  
 *k1*  
 Der erste Schlüssel.  
  
 *k2*  
 Der zweite Schlüssel.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" zurück, wenn die Schlüssel gleich "false", andernfalls sind.  
  
##  <a name="isequalvalue"></a>  CSimpleMapEqualHelper::IsEqualValue  
 Testet zwei Werte hinsichtlich ihrer Gleichheit.  
  
```
static bool IsEqualValue(const TVal& v1, const TVal& v2);
```  
  
### <a name="parameters"></a>Parameter  
 *V1*  
 Der erste Wert.  
  
 *v2*  
 Der zweite Wert.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" zurück, wenn die Werte gleich "false", andernfalls sind.  
  
## <a name="see-also"></a>Siehe auch  
 [CSimpleMapEqualHelperFalse-Klasse](../../atl/reference/csimplemapequalhelperfalse-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)
