---
title: CDefaultCompareTraits Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CDefaultCompareTraits
- ATLCOLL/ATL::CDefaultCompareTraits
- ATLCOLL/ATL::CDefaultCompareTraits::CompareElements
- ATLCOLL/ATL::CDefaultCompareTraits::CompareElementsOrdered
dev_langs:
- C++
helpviewer_keywords:
- CDefaultCompareTraits class
ms.assetid: a17e2740-e7b4-48f2-aeb7-c80ce84b63f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c5b06bf475c60c0190fc6ab78f4357e1b247f1d8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="cdefaultcomparetraits-class"></a>CDefaultCompareTraits-Klasse
Diese Klasse stellt Vergleichsfunktionen Element.  
  
## <a name="syntax"></a>Syntax  
  
```
template<typename T>  
class CDefaultCompareTraits
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Typ der Daten in der Auflistung gespeichert werden.  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDefaultCompareTraits::CompareElements](#compareelements)|(Statisch) Mit dieser Funktion wird zum Vergleichen von zwei Elementen auf Gleichheit.|  
|[CDefaultCompareTraits::CompareElementsOrdered](#compareelementsordered)|(Statisch) Rufen Sie diese Funktion, um das Element größere und kleinere zu bestimmen.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse enthält zwei statische Funktionen zum Vergleichen von Elementen in einem Auflistungsobjekt-Klasse gespeichert. Diese Klasse wird verwendet, durch die [CDefaultElementTraits Klasse](../../atl/reference/cdefaultelementtraits-class.md).  
  
 Weitere Informationen finden Sie unter [ATL-Auflistungsklassen](../../atl/atl-collection-classes.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcoll.h  
  
##  <a name="compareelements"></a>  CDefaultCompareTraits::CompareElements  
 Mit dieser Funktion wird zum Vergleichen von zwei Elementen auf Gleichheit.  
  
```
static bool CompareElements(const T& element1, const T& element2);
```  
  
### <a name="parameters"></a>Parameter  
 `element1`  
 Das erste Element.  
  
 `element2`  
 Das zweite Element.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" zurück, wenn die Elemente gleich "false", andernfalls sind.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung dieser Funktion wird auf Gleichheit ( `==`) Operator. Diese Funktion müssen möglicherweise für andere Objekte als einfache Datentypen außer Kraft gesetzt werden.  
  
##  <a name="compareelementsordered"></a>  CDefaultCompareTraits::CompareElementsOrdered  
 Rufen Sie diese Funktion, um das Element größere und kleinere zu bestimmen.  
  
```
static int CompareElementsOrdered(const T& element1, const T& element2);
```  
  
### <a name="parameters"></a>Parameter  
 `element1`  
 Das erste Element.  
  
 `element2`  
 Das zweite Element.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt eine ganze Zahl, die auf Grundlage der folgenden Tabelle:  
  
|Bedingung|Rückgabewert|  
|---------------|------------------|  
|`element1` < `element2`|<0|  
|`element1` == `element2`|0|  
|`element1` > `element2`|>0|  
  
### <a name="remarks"></a>Hinweise  
 Die Standardimplementierung dieser Funktion verwendet die `==`, **\<**, und **>** Operatoren. Diese Funktion müssen möglicherweise für andere Objekte als einfache Datentypen außer Kraft gesetzt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../../atl/atl-class-overview.md)
