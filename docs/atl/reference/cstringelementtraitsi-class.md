---
title: CStringElementTraitsI-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CStringElementTraitsI
- ATLCOLL/ATL::CStringElementTraitsI
- ATLCOLL/ATL::CStringElementTraitsI::INARGTYPE
- ATLCOLL/ATL::CStringElementTraitsI::OUTARGTYPE
- ATLCOLL/ATL::CStringElementTraitsI::CompareElements
- ATLCOLL/ATL::CStringElementTraitsI::CompareElementsOrdered
- ATLCOLL/ATL::CStringElementTraitsI::Hash
dev_langs:
- C++
helpviewer_keywords:
- CStringElementTraitsI class
ms.assetid: c23f92b1-91e5-400f-96ed-258b02622b7a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 12b75398db6e078f28fab4525da55aaae8193663
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43765293"
---
# <a name="cstringelementtraitsi-class"></a>CStringElementTraitsI-Klasse

Diese Klasse stellt statische Funktionen, die im Zusammenhang mit Zeichenfolgen, die in der Auflistung von Klassenobjekten gespeichert. Sie ähnelt damit [CStringElementTraits](../../atl/reference/cstringelementtraits-class.md), aber die Groß-/Kleinschreibung Vergleiche ausgeführt.

## <a name="syntax"></a>Syntax

```
template <typename T, class CharTraits = CDefaultCharTraits<T ::XCHAR>>  
class CStringElementTraitsI : public CElementTraitsBase<T>
```

#### <a name="parameters"></a>Parameter

*T*  
Der Typ der Daten in der Auflistung gespeichert werden.

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|Beschreibung|
|----------|-----------------|
|[CStringElementTraitsI::INARGTYPE](#inargtype)|Der Datentyp, zum Hinzufügen von Elementen für das Objekt der Sammlung-Klasse verwendet werden soll.|
|[CStringElementTraitsI::OUTARGTYPE](#outargtype)|Der Datentyp für das Abrufen von Elementen aus dem Auflistungsobjekt-Klasse.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CStringElementTraitsI::CompareElements](#compareelements)|Rufen Sie diese statische Funktion zum Vergleichen von zwei Zeichenfolgenelementen Gleichheit, ignorieren die Unterschiede bei.|
|[CStringElementTraitsI::CompareElementsOrdered](#compareelementsordered)|Rufen Sie diese statische Funktion zum Vergleichen von zwei Zeichenfolgenelementen, ignorieren die Unterschiede bei.|
|[CStringElementTraitsI::Hash](#hash)|Rufen Sie diese statischen Funktion um einen Hashwert für das Element der angegebenen Zeichenfolge zu berechnen.|

## <a name="remarks"></a>Hinweise

Diese Klasse stellt statische Funktionen zum Vergleichen von Zeichenfolgen und zum Erstellen eines Hashwerts. Diese Funktionen sind hilfreich, wenn eine Auflistungsklasse verwenden, um zeichenfolgenbasierter Daten zu speichern. Verwendung [CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md) Wenn die Zeichenfolgeobjekte sind mit als Verweise überwunden werden müssen.

Weitere Informationen finden Sie unter [ATL-Auflistungsklassen](../../atl/atl-collection-classes.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

`CStringElementTraitsI`

## <a name="requirements"></a>Anforderungen

**Header:** atlcoll.h

##  <a name="compareelements"></a>  CStringElementTraitsI::CompareElements

Rufen Sie diese statische Funktion zum Vergleichen von zwei Zeichenfolgenelementen Gleichheit, ignorieren die Unterschiede bei.

```
static bool CompareElements(INARGTYPE str1, INARGTYPE str2) throw();
```

### <a name="parameters"></a>Parameter

*str1*  
Die erste Zeichenfolge Element.

*str2*  
Die zweite Zeichenfolge Element.

### <a name="return-value"></a>Rückgabewert

Gibt "true" zurück, wenn die Elemente gleich "false", andernfalls sind.

### <a name="remarks"></a>Hinweise

Beim Vergleichen wird die Groß-/Kleinschreibung.

##  <a name="compareelementsordered"></a>  CStringElementTraitsI::CompareElementsOrdered

Rufen Sie diese statische Funktion zum Vergleichen von zwei Zeichenfolgenelementen, ignorieren die Unterschiede bei.

```
static int CompareElementsOrdered(INARGTYPE str1, INARGTYPE str2) throw();
```

### <a name="parameters"></a>Parameter

*str1*  
Die erste Zeichenfolge Element.

*str2*  
Die zweite Zeichenfolge Element.

### <a name="return-value"></a>Rückgabewert

0 (null), wenn die Zeichenfolgen identisch sind, < 0 Wenn *str1* ist kleiner als *str2*, oder > 0, wenn *str1* ist größer als *str2*. Die [CStringT::Compare](../../atl-mfc-shared/reference/cstringt-class.md#compare) Methode wird verwendet, um die Vergleiche durchzuführen.  

### <a name="remarks"></a>Hinweise

Beim Vergleichen wird die Groß-/Kleinschreibung.

##  <a name="hash"></a>  CStringElementTraitsI::Hash

Rufen Sie diese statischen Funktion um einen Hashwert für das Element der angegebenen Zeichenfolge zu berechnen.

```
static ULONG Hash(INARGTYPE str) throw();
```

### <a name="parameters"></a>Parameter

*str*  
Das String-Element.

### <a name="return-value"></a>Rückgabewert

Gibt einen Hashwert berechnet mithilfe des Inhalts der Zeichenfolge zurück.

##  <a name="inargtype"></a>  CStringElementTraitsI::INARGTYPE

Der Datentyp, zum Hinzufügen von Elementen für das Objekt der Sammlung-Klasse verwendet werden soll.

```
typedef T::PCXSTR INARGTYPE;
```

##  <a name="outargtype"></a>  CStringElementTraitsI::OUTARGTYPE

Der Datentyp für das Abrufen von Elementen aus dem Auflistungsobjekt-Klasse.

```
typedef T& OUTARGTYPE;
```

## <a name="see-also"></a>Siehe auch

[CElementTraitsBase-Klasse](../../atl/reference/celementtraitsbase-class.md)   
[Übersicht über die Klasse](../../atl/atl-class-overview.md)   
[CStringElementTraits-Klasse](../../atl/reference/cstringelementtraits-class.md)
