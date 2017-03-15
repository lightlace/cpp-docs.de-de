---
title: Klasse CStringElementTraitsI | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CStringElementTraitsI
- CStringElementTraitsI
- ATL.CStringElementTraitsI
dev_langs:
- C++
helpviewer_keywords:
- CStringElementTraitsI class
ms.assetid: c23f92b1-91e5-400f-96ed-258b02622b7a
caps.latest.revision: 18
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
ms.openlocfilehash: 995c4798f92db3b3f065bf2176ab52ff53d282b0
ms.lasthandoff: 02/24/2017

---
# <a name="cstringelementtraitsi-class"></a>CStringElementTraitsI-Klasse
Diese Klasse stellt statische Funktionen im Zusammenhang mit Zeichenfolgen, die in der Auflistung Klassenobjekte gespeichert. Es ähnelt dem [CStringElementTraits](../../atl/reference/cstringelementtraits-class.md), jedoch führt bei vergleichen.  
  
## <a name="syntax"></a>Syntax  
  
```
template <typename T, class CharTraits = CDefaultCharTraits<T ::XCHAR>>  
class CStringElementTraitsI : public CElementTraitsBase<T>
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Typ der Daten in der Auflistung gespeichert werden.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-typedefs"></a>Öffentliche Typedefs  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CStringElementTraitsI::INARGTYPE](#inargtype)|Der Datentyp für das Klassenobjekt Auflistung Elemente hinzugefügt.|  
|[CStringElementTraitsI::OUTARGTYPE](#outargtype)|Der Datentyp für das Abrufen von Elementen aus der-Auflistung-Klasse.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CStringElementTraitsI::CompareElements](#compareelements)|Rufen Sie die statische Funktion zum Vergleichen von zwei Zeichenfolgenelemente Gleichheit Unterschiede im Fall ignoriert.|  
|[CStringElementTraitsI::CompareElementsOrdered](#compareelementsordered)|Rufen Sie die statische Funktion zum Vergleichen von zwei String-Elemente, die Unterschiede im Fall ignoriert.|  
|[CStringElementTraitsI::Hash](#hash)|Rufen Sie diese statischen Funktion um einen Hashwert für das Element der angegebenen Zeichenfolge zu berechnen.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse stellt statische Funktionen zum Vergleichen von Zeichenfolgen und zum Erstellen eines Hashwerts. Diese Funktionen sind hilfreich, wenn Sie eine Auflistungsklasse zeichenfolgenbasierte Datenspeicher mit. Verwendung [CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md) die Zeichenfolgeobjekte wurden mit als Verweise überwunden werden müssen.  
  
 Weitere Informationen finden Sie unter [ATL-Auflistungsklassen](../../atl/atl-collection-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 `CStringElementTraitsI`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcoll.h  
  
##  <a name="a-namecompareelementsa--cstringelementtraitsicompareelements"></a><a name="compareelements"></a>CStringElementTraitsI::CompareElements  
 Rufen Sie die statische Funktion zum Vergleichen von zwei Zeichenfolgenelemente Gleichheit Unterschiede im Fall ignoriert.  
  
```
static bool CompareElements(INARGTYPE str1, INARGTYPE str2) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `str1`  
 Die erste Zeichenfolge Element.  
  
 `str2`  
 Die zweite Zeichenfolge Element.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt True zurück, wenn die Elemente gleich sind.  
  
### <a name="remarks"></a>Hinweise  
 Vergleiche werden Groß-und Kleinschreibung beachtet.  
  
##  <a name="a-namecompareelementsordereda--cstringelementtraitsicompareelementsordered"></a><a name="compareelementsordered"></a>CStringElementTraitsI::CompareElementsOrdered  
 Rufen Sie die statische Funktion zum Vergleichen von zwei String-Elemente, die Unterschiede im Fall ignoriert.  
  
```
static int CompareElementsOrdered(INARGTYPE str1, INARGTYPE str2) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `str1`  
 Die erste Zeichenfolge Element.  
  
 `str2`  
 Die zweite Zeichenfolge Element.  
  
### <a name="return-value"></a>Rückgabewert  
 NULL, wenn die Zeichenfolgen identisch sind, < 0="" if=""> `str1` ist kleiner als `str2`, > 0 oder wenn `str1` ist größer als `str2`. Die [CStringT::Compare](../../atl-mfc-shared/reference/cstringt-class.md#compare) -Methode verwendet, um die Vergleiche durchführen.  

  
### <a name="remarks"></a>Hinweise  
 Vergleiche werden Groß-und Kleinschreibung beachtet.  
  
##  <a name="a-namehasha--cstringelementtraitsihash"></a><a name="hash"></a>CStringElementTraitsI::Hash  
 Rufen Sie diese statischen Funktion um einen Hashwert für das Element der angegebenen Zeichenfolge zu berechnen.  
  
```
static ULONG Hash(INARGTYPE str) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `str`  
 Das String-Element.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Hashwert berechnet wird, verwenden den Inhalt der Zeichenfolge zurück.  
  
##  <a name="a-nameinargtypea--cstringelementtraitsiinargtype"></a><a name="inargtype"></a>CStringElementTraitsI::INARGTYPE  
 Der Datentyp für das Klassenobjekt Auflistung Elemente hinzugefügt.  
  
```
typedef T::PCXSTR INARGTYPE;
```  
  
##  <a name="a-nameoutargtypea--cstringelementtraitsioutargtype"></a><a name="outargtype"></a>CStringElementTraitsI::OUTARGTYPE  
 Der Datentyp für das Abrufen von Elementen aus der-Auflistung-Klasse.  
  
```
typedef T& OUTARGTYPE;
```  
  
## <a name="see-also"></a>Siehe auch  
 [CElementTraitsBase-Klasse](../../atl/reference/celementtraitsbase-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)   
 [CStringElementTraits-Klasse](../../atl/reference/cstringelementtraits-class.md)

