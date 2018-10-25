---
title: CStringElementTraits-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 51e612e889c06b8736e13e3c0fe04baf07b11a9b
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50078283"
---
# <a name="cstringelementtraits-class"></a>CStringElementTraits-Klasse

Diese Klasse stellt statische Funktionen, die durch das Speichern von Auflistungsklassen verwendet `CString` Objekte.

## <a name="syntax"></a>Syntax

```
template <typename T>
class CStringElementTraits
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Der Typ der Daten in der Auflistung gespeichert werden.

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|Beschreibung|
|----------|-----------------|
|[CStringElementTraits::INARGTYPE](#inargtype)|Der Datentyp, zum Hinzufügen von Elementen für das Objekt der Sammlung-Klasse verwendet werden soll.|
|[CStringElementTraits::OUTARGTYPE](#outargtype)|Der Datentyp für das Abrufen von Elementen aus dem Auflistungsobjekt-Klasse.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CStringElementTraits::CompareElements](#compareelements)|(Statisch) Mit dieser Funktion können Sie zwei Zeichenfolgenelementen auf Gleichheit verglichen werden soll.|
|[CStringElementTraits::CompareElementsOrdered](#compareelementsordered)|(Statisch) Rufen Sie diese Funktion zum Vergleichen von zwei Zeichenfolgenelementen.|
|[CStringElementTraits::CopyElements](#copyelements)|(Statisch) Rufen Sie diese Funktion kopiert `CString` in ein Klassenobjekt Auflistung gespeicherten Elemente.|
|[CStringElementTraits::Hash](#hash)|(Statisch) Rufen Sie diese Funktion, um einen Hashwert für das Element der angegebenen Zeichenfolge zu berechnen.|
|[CStringElementTraits::RelocateElements](#relocateelements)|(Statisch) Mit dieser Funktion wird zum Verschieben `CString` in ein Klassenobjekt Auflistung gespeicherten Elemente.|

## <a name="remarks"></a>Hinweise

Diese Klasse stellt statische Funktionen zum Kopieren, verschieben und Vergleichen von Zeichenfolgen und zum Erstellen eines Hashwerts. Diese Funktionen sind hilfreich, wenn eine Auflistungsklasse verwenden, um zeichenfolgenbasierter Daten zu speichern. Verwendung [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md) wenn Groß-/Kleinschreibung Vergleiche erforderlich sind. Verwendung [CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md) bei der String-Objekte werden als Verweise überwunden werden müssen.

Weitere Informationen finden Sie unter [ATL-Auflistungsklassen](../../atl/atl-collection-classes.md).

## <a name="requirements"></a>Anforderungen

**Header:** cstringt.h

##  <a name="compareelements"></a>  CStringElementTraits::CompareElements

Rufen Sie diese statischen Funktion um zwei Zeichenfolgenelementen auf Gleichheit verglichen werden soll.

```
static bool CompareElements(INARGTYPE str1, INARGTYPE str2);
```

### <a name="parameters"></a>Parameter

*str1*<br/>
Die erste Zeichenfolge Element.

*str2*<br/>
Die zweite Zeichenfolge Element.

### <a name="return-value"></a>Rückgabewert

Gibt "true" zurück, wenn die Elemente gleich "false", andernfalls sind.

##  <a name="compareelementsordered"></a>  CStringElementTraits::CompareElementsOrdered

Rufen Sie diese statische Funktion zum Vergleichen von zwei Zeichenfolgenelementen.

```
static int CompareElementsOrdered(INARGTYPE str1, INARGTYPE str2);
```

### <a name="parameters"></a>Parameter

*str1*<br/>
Die erste Zeichenfolge Element.

*str2*<br/>
Die zweite Zeichenfolge Element.

### <a name="return-value"></a>Rückgabewert

0 (null), wenn die Zeichenfolgen identisch sind, < 0 Wenn *str1* ist kleiner als *str2*, oder > 0, wenn *str1* ist größer als *str2*. Die [CStringT::Compare](../../atl-mfc-shared/reference/cstringt-class.md#compare) Methode wird verwendet, um die Vergleiche durchzuführen.

##  <a name="copyelements"></a>  CStringElementTraits::CopyElements

Rufen Sie diese statische Funktion zum Kopieren `CString` in ein Klassenobjekt Auflistung gespeicherten Elemente.

```
static void CopyElements(
    T* pDest,
    const T* pSrc,
    size_t nElements);
```

### <a name="parameters"></a>Parameter

*pDest*<br/>
Zeiger auf das erste Element, das die kopierten Daten erhält.

*pSrc*<br/>
Zeiger auf das erste Element zu kopieren.

*nElements*<br/>
Die Anzahl der zu kopierenden Elemente.

### <a name="remarks"></a>Hinweise

Die Quelle und Ziel-Elemente sollten sich nicht überschneiden.

##  <a name="hash"></a>  CStringElementTraits::Hash

Rufen Sie diese statischen Funktion um einen Hashwert für das Element der angegebenen Zeichenfolge zu berechnen.

```
static ULONG Hash(INARGTYPE str);
```

### <a name="parameters"></a>Parameter

*str*<br/>
Das String-Element.

### <a name="return-value"></a>Rückgabewert

Gibt einen Hashwert berechnet mithilfe des Inhalts der Zeichenfolge zurück.

##  <a name="inargtype"></a>  CStringElementTraits::INARGTYPE

Der Datentyp, zum Hinzufügen von Elementen für das Objekt der Sammlung-Klasse verwendet werden soll.

```
typedef T::PCXSTR INARGTYPE;
```

##  <a name="outargtype"></a>  CStringElementTraits::OUTARGTYPE

Der Datentyp für das Abrufen von Elementen aus dem Auflistungsobjekt-Klasse.

```
typedef T& OUTARGTYPE;
```

##  <a name="relocateelements"></a>  CStringElementTraits::RelocateElements

Rufen Sie diese statische Funktion verschieben `CString` in ein Klassenobjekt Auflistung gespeicherten Elemente.

```
static void RelocateElements(
    T* pDest,
    T* pSrc,
    size_t nElements);
```

### <a name="parameters"></a>Parameter

*pDest*<br/>
Zeiger auf das erste Element, das die verschobenen Daten erhält.

*pSrc*<br/>
Zeiger auf das erste Element, zu verschieben.

*nElements*<br/>
Die Anzahl der Elemente zu verschieben.

### <a name="remarks"></a>Hinweise

Diese statischen Funktion ruft [Memmove](../../c-runtime-library/reference/memmove-wmemmove.md), dies ist ausreichend für die meisten Datentypen. Wenn die Objekte, die verschoben werden Zeiger auf ihre eigenen Member enthalten, müssen diese statischen Funktion außer Kraft gesetzt werden.

## <a name="see-also"></a>Siehe auch

[CElementTraitsBase-Klasse](../../atl/reference/celementtraitsbase-class.md)<br/>
[CStringElementTraitsI-Klasse](../../atl/reference/cstringelementtraitsi-class.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
