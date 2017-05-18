---
title: Klasse CDefaultCompareTraits | Microsoft-Dokumentation
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 1d1253b7a7d69024465627cc9fb37fcd2afba693
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cdefaultcomparetraits-class"></a>CDefaultCompareTraits-Klasse
Diese Klasse stellt Element Vergleichsfunktionen.  
  
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
|[CDefaultCompareTraits::CompareElements](#compareelements)|(Statisch) Rufen Sie diese Funktion, um zwei Elemente auf Gleichheit verglichen werden soll.|  
|[CDefaultCompareTraits::CompareElementsOrdered](#compareelementsordered)|(Statisch) Rufen Sie diese Funktion, um das Element größer und kleiner zu bestimmen.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse enthält zwei statische Funktionen zum Vergleichen von Elementen in einem Auflistungsobjekt-Klasse gespeichert. Diese Klasse wird verwendet, indem die [CDefaultElementTraits Klasse](../../atl/reference/cdefaultelementtraits-class.md).  
  
 Weitere Informationen finden Sie unter [ATL-Auflistungsklassen](../../atl/atl-collection-classes.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcoll.h  
  
##  <a name="compareelements"></a>CDefaultCompareTraits::CompareElements  
 Rufen Sie diese Funktion, um zwei Elemente auf Gleichheit verglichen werden soll.  
  
```
static bool CompareElements(const T& element1, const T& element2);
```  
  
### <a name="parameters"></a>Parameter  
 `element1`  
 Das erste Element.  
  
 `element2`  
 Das zweite Element.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt True zurück, wenn die Elemente gleich sind.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung dieser Funktion wird die Gleichheit ( `==`) Operator. Für Objekte als einfache Datentypen kann diese Funktion außer Kraft gesetzt werden müssen.  
  
##  <a name="compareelementsordered"></a>CDefaultCompareTraits::CompareElementsOrdered  
 Rufen Sie diese Funktion, um das Element größer und kleiner zu bestimmen.  
  
```
static int CompareElementsOrdered(const T& element1, const T& element2);
```  
  
### <a name="parameters"></a>Parameter  
 `element1`  
 Das erste Element.  
  
 `element2`  
 Das zweite Element.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt eine ganze Zahl, die anhand der folgenden Tabelle zurück:  
  
|Bedingung|Rückgabewert|  
|---------------|------------------|  
|`element1` < `element2`|<0|  
|`element1` == `element2`|0|  
|`element1` > `element2`|>0|  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung dieser Funktion verwendet die `==`, ** \< **, und ** > ** Operatoren. Für Objekte als einfache Datentypen kann diese Funktion außer Kraft gesetzt werden müssen.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

