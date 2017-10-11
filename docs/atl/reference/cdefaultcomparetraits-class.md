---
title: CDefaultCompareTraits Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: c55726a1728185f699afbac4ba68a6dc0f70c2bf
ms.openlocfilehash: 410d34d59da33b6d929abbe2af0798a6cf46238b
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

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
  
## <a name="members"></a>Mitglieder  
  
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
  
##  <a name="compareelements"></a>CDefaultCompareTraits::CompareElements  
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
  
##  <a name="compareelementsordered"></a>CDefaultCompareTraits::CompareElementsOrdered  
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
 Die Standardimplementierung dieser Funktion verwendet die `==`,  **\<** , und  **>**  Operatoren. Diese Funktion müssen möglicherweise für andere Objekte als einfache Datentypen außer Kraft gesetzt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../../atl/atl-class-overview.md)

