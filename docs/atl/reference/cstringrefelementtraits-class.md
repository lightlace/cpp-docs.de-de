---
title: CStringRefElementTraits Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CStringRefElementTraits
- ATLCOLL/ATL::CStringRefElementTraits
- ATLCOLL/ATL::CStringRefElementTraits::CompareElements
- ATLCOLL/ATL::CStringRefElementTraits::CompareElementsOrdered
- ATLCOLL/ATL::CStringRefElementTraits::Hash
dev_langs: C++
helpviewer_keywords: CStringRefElementTraits class
ms.assetid: cc15062d-5627-46cc-ac2b-1744afdc2dbd
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c89a1e0d87550614fb8991ac3efe6bf369d147e7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cstringrefelementtraits-class"></a>CStringRefElementTraits-Klasse
Diese Klasse enthält statische Funktionen, die im Zusammenhang mit Zeichenfolgen, die in der Auflistung von Klassenobjekten gespeichert. Die Zeichenfolgeobjekte werden als Verweise behandelt.  
  
## <a name="syntax"></a>Syntax  
  
```
template <typename T>  
class CStringRefElementTraits : public CElementTraitsBase<T>
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Typ der Daten in der Auflistung gespeichert werden.  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CStringRefElementTraits::CompareElements](#compareelements)|Rufen Sie diese statischen Funktion um zwei Zeichenfolgenelementen auf Gleichheit verglichen werden soll.|  
|[CStringRefElementTraits::CompareElementsOrdered](#compareelementsordered)|Rufen Sie diese statische Funktion zum Vergleichen von zwei Zeichenfolgenelementen.|  
|[CStringRefElementTraits::Hash](#hash)|Rufen Sie diese statischen Funktion um einen Hashwert für das Element der angegebenen Zeichenfolge zu berechnen.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse enthält statische Funktionen zum Vergleichen von Zeichenfolgen und zum Erstellen eines Hashwerts. Diese Funktionen sind hilfreich, wenn Sie eine Auflistungsklasse verwenden zum Speichern von Daten zeichenfolgenbasierten. Im Gegensatz zu [CStringElementTraits](../../atl/reference/cstringelementtraits-class.md) und [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md), `CStringRefElementTraits` bewirkt, dass die `CString` als zu übergebenden Argumente **const CString &** verweist auf.  
  
 Weitere Informationen finden Sie unter [ATL-Auflistungsklassen](../../atl/atl-collection-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 `CStringRefElementTraits`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcoll.h  
  
##  <a name="compareelements"></a>CStringRefElementTraits::CompareElements  
 Rufen Sie diese statischen Funktion um zwei Zeichenfolgenelementen auf Gleichheit verglichen werden soll.  
  
```
static bool CompareElements(INARGTYPE element1, INARGTYPE element2) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `element1`  
 Das erste string-Element.  
  
 `element2`  
 Das zweite string-Element.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" zurück, wenn die Elemente gleich "false", andernfalls sind.  
  
##  <a name="compareelementsordered"></a>CStringRefElementTraits::CompareElementsOrdered  
 Rufen Sie diese statische Funktion zum Vergleichen von zwei Zeichenfolgenelementen.  
  
```
static int CompareElementsOrdered(INARGTYPE str1, INARGTYPE str2) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `str1`  
 Das erste string-Element.  
  
 `str2`  
 Das zweite string-Element.  
  
### <a name="return-value"></a>Rückgabewert  
 0 (null), wenn die Zeichenfolgen identisch sind, < 0 Wenn `str1` ist kleiner als `str2`, oder 0 > Wenn `str1` ist größer als `str2`. Die [CStringT::Compare](../../atl-mfc-shared/reference/cstringt-class.md#compare) Methode wird verwendet, um die Qualität der Vergleiche ausführen.  
  
##  <a name="hash"></a>CStringRefElementTraits::Hash  
 Rufen Sie diese statischen Funktion um einen Hashwert für das Element der angegebenen Zeichenfolge zu berechnen.  
  
```
static ULONG Hash(INARGTYPE str) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `str`  
 Das String-Element.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Hashwert berechnet wird, verwenden den Inhalt der Zeichenfolge zurück.  
  
## <a name="see-also"></a>Siehe auch  
 [CElementTraitsBase-Klasse](../../atl/reference/celementtraitsbase-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
