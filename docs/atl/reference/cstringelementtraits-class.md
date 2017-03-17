---
title: Klasse CStringElementTraits | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
ms.openlocfilehash: f46ff072bcd0f772dac1bba52b114d82ee433112
ms.lasthandoff: 02/24/2017

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
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CStringElementTraits::INARGTYPE](#inargtype)|Der Datentyp für das Klassenobjekt Auflistung Elemente hinzugefügt.|  
|[CStringElementTraits::OUTARGTYPE](#outargtype)|Der Datentyp für das Abrufen von Elementen aus der-Auflistung-Klasse.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CStringElementTraits::CompareElements](#compareelements)|(Statisch) Rufen Sie diese Funktion, um zwei String Elemente auf Gleichheit verglichen werden soll.|  
|[CStringElementTraits::CompareElementsOrdered](#compareelementsordered)|(Statisch) Rufen Sie diese Funktion zum Vergleichen von zwei String-Elementen.|  
|[CStringElementTraits::CopyElements](#copyelements)|(Statisch) Rufen Sie diese Funktion zum Kopieren `CString` in ein Objekt der Klasse Auflistung gespeicherten Elemente.|  
|[CStringElementTraits::Hash](#hash)|(Statisch) Rufen Sie diese Funktion, um einen Hashwert für das Element der angegebenen Zeichenfolge zu berechnen.|  
|[CStringElementTraits::RelocateElements](#relocateelements)|(Statisch) Rufen Sie diese Funktion zum Verschieben `CString` in ein Objekt der Klasse Auflistung gespeicherten Elemente.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse stellt statische Funktionen zum Kopieren, verschieben und Vergleichen von Zeichenfolgen und zum Erstellen des Hashwerts. Diese Funktionen sind hilfreich, wenn Sie eine Auflistungsklasse zeichenfolgenbasierte Datenspeicher mit. Verwendung [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md) Wenn bei Vergleichen erforderlich sind. Verwendung [CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md) Wenn sind String-Objekte als Verweise überwunden werden müssen.  
  
 Weitere Informationen finden Sie unter [ATL-Auflistungsklassen](../../atl/atl-collection-classes.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** cstringt.h  
  
##  <a name="compareelements"></a>CStringElementTraits::CompareElements  
 Rufen Sie diese statischen Funktion um zwei Zeichenfolgenelemente auf Gleichheit verglichen werden soll.  
  
```
static bool CompareElements(INARGTYPE str1, INARGTYPE str2);
```  
  
### <a name="parameters"></a>Parameter  
 `str1`  
 Die erste Zeichenfolge Element.  
  
 `str2`  
 Die zweite Zeichenfolge Element.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt True zurück, wenn die Elemente gleich sind.  
  
##  <a name="compareelementsordered"></a>CStringElementTraits::CompareElementsOrdered  
 Rufen Sie die statische Funktion zum Vergleichen von zwei String-Elementen.  
  
```
static int CompareElementsOrdered(INARGTYPE str1, INARGTYPE str2);
```  
  
### <a name="parameters"></a>Parameter  
 `str1`  
 Die erste Zeichenfolge Element.  
  
 `str2`  
 Die zweite Zeichenfolge Element.  
  
### <a name="return-value"></a>Rückgabewert  
 NULL, wenn die Zeichenfolgen identisch sind, < 0="" if=""> `str1` ist kleiner als `str2`, > 0 oder wenn `str1` ist größer als `str2`. Die [CStringT::Compare](../../atl-mfc-shared/reference/cstringt-class.md#compare) -Methode verwendet, um die Vergleiche durchführen.  

  
##  <a name="copyelements"></a>CStringElementTraits::CopyElements  
 Rufen Sie die statische Funktion zum Kopieren `CString` in ein Objekt der Klasse Auflistung gespeicherten Elemente.  
  
```
static void CopyElements(
    T* pDest,
    const T* pSrc,
    size_t nElements);
```  
  
### <a name="parameters"></a>Parameter  
 `pDest`  
 Ein Zeiger auf das erste Element, das die kopierten Daten empfängt.  
  
 `pSrc`  
 Ein Zeiger auf das erste Element zu kopieren.  
  
 `nElements`  
 Die Anzahl der zu kopierenden Elemente.  
  
### <a name="remarks"></a>Hinweise  
 Die Quelle und Ziel-Elemente sollten sich nicht überschneiden.  
  
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
 Der Datentyp für das Klassenobjekt Auflistung Elemente hinzugefügt.  
  
```
typedef T::PCXSTR INARGTYPE;
```  
  
##  <a name="outargtype"></a>CStringElementTraits::OUTARGTYPE  
 Der Datentyp für das Abrufen von Elementen aus der-Auflistung-Klasse.  
  
```
typedef T& OUTARGTYPE;
```  
  
##  <a name="relocateelements"></a>CStringElementTraits::RelocateElements  
 Rufen Sie die statische Funktion zum Verschieben `CString` in ein Objekt der Klasse Auflistung gespeicherten Elemente.  
  
```
static void RelocateElements(
    T* pDest,
    T* pSrc,
    size_t nElements);
```  
  
### <a name="parameters"></a>Parameter  
 `pDest`  
 Ein Zeiger auf das erste Element, das die verschobenen Daten empfängt.  
  
 `pSrc`  
 Ein Zeiger auf das erste Element zu verschieben.  
  
 `nElements`  
 Die Anzahl der Elemente, die zu verschieben.  
  
### <a name="remarks"></a>Hinweise  
 Ruft die statische Funktion [Memmove](../../c-runtime-library/reference/memmove-wmemmove.md), dies ist ausreichend für die meisten Datentypen. Die verschobene Objekte, Zeiger auf ihre eigenen Member enthalten, müssen die statische Funktion außer Kraft gesetzt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [CElementTraitsBase-Klasse](../../atl/reference/celementtraitsbase-class.md)   
 [CStringElementTraitsI-Klasse](../../atl/reference/cstringelementtraitsi-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

