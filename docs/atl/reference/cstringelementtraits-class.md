---
title: CStringElementTraits Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CStringElementTraits
- CSTRINGT/ATL::CStringElementTraits
- CSTRINGT/ATL::CStringElementTraits::INARGTYPE
- CSTRINGT/ATL::CStringElementTraits::OUTARGTYPE
- CSTRINGT/ATL::CStringElementTraits::CompareElements
- CSTRINGT/ATL::CStringElementTraits::CompareElementsOrdered
- CSTRINGT/ATL::CStringElementTraits::CopyElements
- CSTRINGT/ATL::CStringElementTraits::Hash
- CSTRINGT/ATL::CStringElementTraits::RelocateElements
dev_langs:
- C++
helpviewer_keywords:
- CStringElementTraits class
ms.assetid: 74d7134b-099d-4455-bf91-3e68ccbf95bc
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 025c9aa66a8647fd5d8ca9803aedb50b27ed3be1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cstringelementtraits-class"></a>CStringElementTraits-Klasse
Diese Klasse enthält statische Funktionen, die durch das Speichern von Auflistungsklassen verwendet `CString` Objekte.  
  
## <a name="syntax"></a>Syntax  
  
```
template <typename T>  
class CStringElementTraits
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Typ der Daten in der Auflistung gespeichert werden.  
  
## <a name="members"></a>Member  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CStringElementTraits::INARGTYPE](#inargtype)|Der Datentyp zum Hinzufügen von Elementen auf das Klassenobjekt Auflistung verwendet werden soll.|  
|[CStringElementTraits::OUTARGTYPE](#outargtype)|Der Datentyp zum Abrufen von Elementen aus der Auflistung-Klassenobjekt verwendet werden soll.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CStringElementTraits::CompareElements](#compareelements)|(Statisch) Mit dieser Funktion können Sie zwei Zeichenfolgenelementen auf Gleichheit verglichen werden soll.|  
|[CStringElementTraits::CompareElementsOrdered](#compareelementsordered)|(Statisch) Mit dieser Funktion wird zum Vergleichen von zwei Zeichenfolgenelementen.|  
|[CStringElementTraits::CopyElements](#copyelements)|(Statisch) Mit dieser Funktion wird auf Kopieren `CString` ein Klassenobjekt Auflistung gespeicherten Elemente.|  
|[CStringElementTraits::Hash](#hash)|(Statisch) Mit dieser Funktion wird zum Berechnen der eines Hashwert für das Element der angegebenen Zeichenfolge.|  
|[CStringElementTraits::RelocateElements](#relocateelements)|(Statisch) Mit dieser Funktion werden zum Verschieben `CString` ein Klassenobjekt Auflistung gespeicherten Elemente.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse enthält statische Funktionen zum Kopieren, verschieben und Vergleichen von Zeichenfolgen und zum Erstellen eines Hashwerts. Diese Funktionen sind hilfreich, wenn Sie eine Auflistungsklasse verwenden zum Speichern von Daten zeichenfolgenbasierten. Verwendung [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md) wenn Groß-/Kleinschreibung Vergleiche erforderlich sind. Verwendung [CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md) Wenn die Zeichenfolgeobjekte sind als Verweise mit behandelt werden.  
  
 Weitere Informationen finden Sie unter [ATL-Auflistungsklassen](../../atl/atl-collection-classes.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** cstringt.h  
  
##  <a name="compareelements"></a>CStringElementTraits::CompareElements  
 Rufen Sie diese statischen Funktion um zwei Zeichenfolgenelementen auf Gleichheit verglichen werden soll.  
  
```
static bool CompareElements(INARGTYPE str1, INARGTYPE str2);
```  
  
### <a name="parameters"></a>Parameter  
 `str1`  
 Das erste string-Element.  
  
 `str2`  
 Das zweite string-Element.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" zurück, wenn die Elemente gleich "false", andernfalls sind.  
  
##  <a name="compareelementsordered"></a>CStringElementTraits::CompareElementsOrdered  
 Rufen Sie diese statische Funktion zum Vergleichen von zwei Zeichenfolgenelementen.  
  
```
static int CompareElementsOrdered(INARGTYPE str1, INARGTYPE str2);
```  
  
### <a name="parameters"></a>Parameter  
 `str1`  
 Das erste string-Element.  
  
 `str2`  
 Das zweite string-Element.  
  
### <a name="return-value"></a>Rückgabewert  
 0 (null), wenn die Zeichenfolgen identisch sind, < 0 Wenn `str1` ist kleiner als `str2`, oder 0 > Wenn `str1` ist größer als `str2`. Die [CStringT::Compare](../../atl-mfc-shared/reference/cstringt-class.md#compare) Methode wird verwendet, um die Qualität der Vergleiche ausführen.  

  
##  <a name="copyelements"></a>CStringElementTraits::CopyElements  
 Rufen Sie diese statische Funktion zum Kopieren `CString` ein Klassenobjekt Auflistung gespeicherten Elemente.  
  
```
static void CopyElements(
    T* pDest,
    const T* pSrc,
    size_t nElements);
```  
  
### <a name="parameters"></a>Parameter  
 `pDest`  
 Zeiger auf das erste Element, das die kopierten Daten erhält.  
  
 `pSrc`  
 Zeiger auf das erste Element zu kopieren.  
  
 `nElements`  
 Die Anzahl der zu kopierenden Elemente.  
  
### <a name="remarks"></a>Hinweise  
 Die Quell- und Zielschemas Elemente sollten sich nicht überschneiden.  
  
##  <a name="hash"></a>CStringElementTraits::Hash  
 Rufen Sie diese statischen Funktion um einen Hashwert für das Element der angegebenen Zeichenfolge zu berechnen.  
  
```
static ULONG Hash(INARGTYPE str);
```  
  
### <a name="parameters"></a>Parameter  
 `str`  
 Das String-Element.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Hashwert berechnet wird, verwenden den Inhalt der Zeichenfolge zurück.  
  
##  <a name="inargtype"></a>CStringElementTraits::INARGTYPE  
 Der Datentyp zum Hinzufügen von Elementen auf das Klassenobjekt Auflistung verwendet werden soll.  
  
```
typedef T::PCXSTR INARGTYPE;
```  
  
##  <a name="outargtype"></a>CStringElementTraits::OUTARGTYPE  
 Der Datentyp zum Abrufen von Elementen aus der Auflistung-Klassenobjekt verwendet werden soll.  
  
```
typedef T& OUTARGTYPE;
```  
  
##  <a name="relocateelements"></a>CStringElementTraits::RelocateElements  
 Rufen Sie diese statische Funktion verschieben `CString` ein Klassenobjekt Auflistung gespeicherten Elemente.  
  
```
static void RelocateElements(
    T* pDest,
    T* pSrc,
    size_t nElements);
```  
  
### <a name="parameters"></a>Parameter  
 `pDest`  
 Zeiger auf das erste Element, das die verschobenen Daten erhält.  
  
 `pSrc`  
 Zeiger auf das erste Element zu verschieben.  
  
 `nElements`  
 Die Anzahl der Elemente zu verschieben.  
  
### <a name="remarks"></a>Hinweise  
 Diese statische Funktion ruft [Memmove](../../c-runtime-library/reference/memmove-wmemmove.md), dies ist ausreichend für die meisten Datentypen. Wenn die Objekte, die verschobene Zeiger auf ihre eigenen Member enthalten, müssen diese statischen Funktion außer Kraft gesetzt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [CElementTraitsBase-Klasse](../../atl/reference/celementtraitsbase-class.md)   
 [CStringElementTraitsI-Klasse](../../atl/reference/cstringelementtraitsi-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
