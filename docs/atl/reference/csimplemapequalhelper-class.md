---
title: Klasse CSimpleMapEqualHelper | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: ddb793889748446b9613c91ce6fcefe28da32eb3
ms.lasthandoff: 02/24/2017

---
# <a name="csimplemapequalhelper-class"></a>CSimpleMapEqualHelper-Klasse
Diese Klasse ist eine Hilfsklasse für die [CSimpleMap](../../atl/reference/csimplemap-class.md) Klasse.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class TKey, class TVal>  
class CSimpleMapEqualHelper
```  
  
#### <a name="parameters"></a>Parameter  
 `TKey`  
 Das wichtigste Element.  
  
 `TVal`  
 Das Value-Element.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSimpleMapEqualHelper::IsEqualKey](#isequalkey)|(Statisch) Testet zwei Schlüssel auf Gleichheit.|  
|[CSimpleMapEqualHelper::IsEqualValue](#isequalvalue)|(Statisch) Testet die Gleichheit zweier Werte zu.|  
  
## <a name="remarks"></a>Hinweise  
 Diese "traits"-Klasse ist eine Ergänzung zu den `CSimpleMap` Klasse. Es bietet Methoden zum Vergleichen von zwei `CSimpleMap` Objektelemente (insbesondere die Schlüssel-Wert-Komponenten) auf Gleichheit. In der Standardeinstellung die Schlüssel und Werte werden verglichen mit `operator==()`, aber wenn die Zuordnung komplexe Datentypen, die keine eigene Gleichheitsoperator enthält, kann diese Klasse überschrieben werden, um die zusätzliche erforderliche Funktionalität bereitzustellen.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlsimpcoll.h  
  
##  <a name="isequalkey"></a>CSimpleMapEqualHelper::IsEqualKey  
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
  
##  <a name="isequalvalue"></a>CSimpleMapEqualHelper::IsEqualValue  
 Testet die Gleichheit zweier Werte zu.  
  
```
static bool IsEqualValue(const TVal& v1, const TVal& v2);
```  
  
### <a name="parameters"></a>Parameter  
 *V1*  
 Der erste Wert.  
  
 *v2*  
 Der zweite Wert.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt true zurück, wenn die Werte gleich sind, und false sind.  
  
## <a name="see-also"></a>Siehe auch  
 [CSimpleMapEqualHelperFalse-Klasse](../../atl/reference/csimplemapequalhelperfalse-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

