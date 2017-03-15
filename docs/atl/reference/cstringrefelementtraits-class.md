---
title: Klasse CStringRefElementTraits | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CStringRefElementTraits
- ATL.CStringRefElementTraits
- ATL::CStringRefElementTraits
dev_langs:
- C++
helpviewer_keywords:
- CStringRefElementTraits class
ms.assetid: cc15062d-5627-46cc-ac2b-1744afdc2dbd
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
ms.openlocfilehash: 3709a5d4aac02651e5b6fafd441499fea1f8eabc
ms.lasthandoff: 02/24/2017

---
# <a name="cstringrefelementtraits-class"></a>CStringRefElementTraits-Klasse
Diese Klasse stellt statische Funktionen im Zusammenhang mit Zeichenfolgen, die in der Auflistung Klassenobjekte gespeichert. Die String-Objekte werden als Verweise behandelt.  
  
## <a name="syntax"></a>Syntax  
  
```
template <typename T>  
class CStringRefElementTraits : public CElementTraitsBase<T>
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Der Typ der Daten in der Auflistung gespeichert werden.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CStringRefElementTraits::CompareElements](#compareelements)|Rufen Sie diese statischen Funktion um zwei Zeichenfolgenelemente auf Gleichheit verglichen werden soll.|  
|[CStringRefElementTraits::CompareElementsOrdered](#compareelementsordered)|Rufen Sie die statische Funktion zum Vergleichen von zwei String-Elementen.|  
|[CStringRefElementTraits::Hash](#hash)|Rufen Sie diese statischen Funktion um einen Hashwert für das Element der angegebenen Zeichenfolge zu berechnen.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse stellt statische Funktionen zum Vergleichen von Zeichenfolgen und zum Erstellen eines Hashwerts. Diese Funktionen sind hilfreich, wenn Sie eine Auflistungsklasse zeichenfolgenbasierte Datenspeicher mit. Im Gegensatz zu [CStringElementTraits](../../atl/reference/cstringelementtraits-class.md) und [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md), `CStringRefElementTraits` bewirkt, dass die `CString` als zu übergebenden Argumente **const CString &** verweisen.  
  
 Weitere Informationen finden Sie unter [ATL-Auflistungsklassen](../../atl/atl-collection-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 `CStringRefElementTraits`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcoll.h  
  
##  <a name="a-namecompareelementsa--cstringrefelementtraitscompareelements"></a><a name="compareelements"></a>CStringRefElementTraits::CompareElements  
 Rufen Sie diese statischen Funktion um zwei Zeichenfolgenelemente auf Gleichheit verglichen werden soll.  
  
```
static bool CompareElements(INARGTYPE element1, INARGTYPE element2) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `element1`  
 Die erste Zeichenfolge Element.  
  
 `element2`  
 Die zweite Zeichenfolge Element.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt True zurück, wenn die Elemente gleich sind.  
  
##  <a name="a-namecompareelementsordereda--cstringrefelementtraitscompareelementsordered"></a><a name="compareelementsordered"></a>CStringRefElementTraits::CompareElementsOrdered  
 Rufen Sie die statische Funktion zum Vergleichen von zwei String-Elementen.  
  
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
  
##  <a name="a-namehasha--cstringrefelementtraitshash"></a><a name="hash"></a>CStringRefElementTraits::Hash  
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
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

