---
title: CStringRefElementTraits-Klasse
ms.date: 11/04/2016
f1_keywords:
- CStringRefElementTraits
- ATLCOLL/ATL::CStringRefElementTraits
- ATLCOLL/ATL::CStringRefElementTraits::CompareElements
- ATLCOLL/ATL::CStringRefElementTraits::CompareElementsOrdered
- ATLCOLL/ATL::CStringRefElementTraits::Hash
helpviewer_keywords:
- CStringRefElementTraits class
ms.assetid: cc15062d-5627-46cc-ac2b-1744afdc2dbd
ms.openlocfilehash: c57fda64689a80dfa548977e56b0416641bb4360
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57301622"
---
# <a name="cstringrefelementtraits-class"></a>CStringRefElementTraits-Klasse

Diese Klasse stellt statische Funktionen, die im Zusammenhang mit Zeichenfolgen, die in der Auflistung von Klassenobjekten gespeichert. Der String-Objekte werden als Verweise behandelt.

## <a name="syntax"></a>Syntax

```
template <typename T>
class CStringRefElementTraits : public CElementTraitsBase<T>
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Der Typ der Daten in der Auflistung gespeichert werden.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CStringRefElementTraits::CompareElements](#compareelements)|Rufen Sie diese statischen Funktion um zwei Zeichenfolgenelementen auf Gleichheit verglichen werden soll.|
|[CStringRefElementTraits::CompareElementsOrdered](#compareelementsordered)|Rufen Sie diese statische Funktion zum Vergleichen von zwei Zeichenfolgenelementen.|
|[CStringRefElementTraits::Hash](#hash)|Rufen Sie diese statischen Funktion um einen Hashwert für das Element der angegebenen Zeichenfolge zu berechnen.|

## <a name="remarks"></a>Hinweise

Diese Klasse stellt statische Funktionen zum Vergleichen von Zeichenfolgen und zum Erstellen eines Hashwerts. Diese Funktionen sind hilfreich, wenn eine Auflistungsklasse verwenden, um zeichenfolgenbasierter Daten zu speichern. Im Gegensatz zu [CStringElementTraits](../../atl/reference/cstringelementtraits-class.md) und [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md), `CStringRefElementTraits` bewirkt, dass die `CString` als zu übergebenden Argumente **const** `CString&` verweist auf.

Weitere Informationen finden Sie unter [ATL-Auflistungsklassen](../../atl/atl-collection-classes.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

`CStringRefElementTraits`

## <a name="requirements"></a>Anforderungen

**Header:** atlcoll.h

##  <a name="compareelements"></a>  CStringRefElementTraits::CompareElements

Rufen Sie diese statischen Funktion um zwei Zeichenfolgenelementen auf Gleichheit verglichen werden soll.

```
static bool CompareElements(INARGTYPE element1, INARGTYPE element2) throw();
```

### <a name="parameters"></a>Parameter

*element1*<br/>
Die erste Zeichenfolge Element.

*element2*<br/>
Die zweite Zeichenfolge Element.

### <a name="return-value"></a>Rückgabewert

Gibt "true" zurück, wenn die Elemente gleich "false", andernfalls sind.

##  <a name="compareelementsordered"></a>  CStringRefElementTraits::CompareElementsOrdered

Rufen Sie diese statische Funktion zum Vergleichen von zwei Zeichenfolgenelementen.

```
static int CompareElementsOrdered(INARGTYPE str1, INARGTYPE str2) throw();
```

### <a name="parameters"></a>Parameter

*str1*<br/>
Die erste Zeichenfolge Element.

*str2*<br/>
Die zweite Zeichenfolge Element.

### <a name="return-value"></a>Rückgabewert

0 (null), wenn die Zeichenfolgen identisch sind, < 0 Wenn *str1* ist kleiner als *str2*, oder > 0, wenn *str1* ist größer als *str2*. Die [CStringT::Compare](../../atl-mfc-shared/reference/cstringt-class.md#compare) Methode wird verwendet, um die Vergleiche durchzuführen.

##  <a name="hash"></a>  CStringRefElementTraits::Hash

Rufen Sie diese statischen Funktion um einen Hashwert für das Element der angegebenen Zeichenfolge zu berechnen.

```
static ULONG Hash(INARGTYPE str) throw();
```

### <a name="parameters"></a>Parameter

*str*<br/>
Das String-Element.

### <a name="return-value"></a>Rückgabewert

Gibt einen Hashwert berechnet mithilfe des Inhalts der Zeichenfolge zurück.

## <a name="see-also"></a>Siehe auch

[CElementTraitsBase-Klasse](../../atl/reference/celementtraitsbase-class.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
